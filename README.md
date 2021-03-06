# The Allen AI Science Kaggle Challenge

### Competition Data:  
 - 8th grade, multiple choice science questions
 - *Examples:*
   - When athletes begin to exercise, their heart rates and respiration rates increase.  At what level of organization does the human body coordinate these functions?
     1. at the tissue level
     2. at the organ level  
     3. **at the system level** (CORRECT)
     4. at the cellular level
   - Which example describes a learned behavior in a dog?
     1. smelling the air for odors
     2. barking when disturbed
     3. **sitting on command** (CORRECT)
     4. digging in soil

### Outside Data:  
*Note: no live internet connection / API calls were allowed in the model*
 - [Wikipedia](https://en.wikipedia.org)  
 - [Simple Wikipedia](https://simple.wikipedia.org)  
 - [Quizlet](https://quizlet.com/21753155/8th-grade-physical-science-vocabulary-flash-cards/alphabetical)  
 - [k12.sd.us](https://sb058.k12.sd.us/vocabulary/8th_grade_science_vocabulary_ans.htm)  
 - [Vocabulary.com](http://www.vocabulary.com/lists/24280#view=notes)  
 - [HRW](http://go.hrw.com/resources/go_sc/glossary/termsa.htm)  
 - [Wednet.edu](http://haller.asd.wednet.edu/UserFiles/Servers/Server_3164673/File/migration/8thgradeglossary.doc)

### Technologies:  
 - Python  
   - BeautifulSoup    
   - Pandas  
   - gensim (Word2Vec)
   - NLTK
 - UNIX  
 - Github  
 - Excel  
 - Powerpoint  

### Methodolgy:  
 1. Register for the Kaggle competition and download provided training and validation questions  
 2. Perform exploratory data analysis to develop simple / rule-based model (most common answer and all / none of the above)
 3. Combine each question in the training set with its correct answer  
 4. Scrape and clean all Simple Wikipedia articles and their respective full english (normal) Wikipedia articles; merge with the above
 5. Scrape the individual 8th grade vocabulary / glossary sites, clean this data, and merge with the above to complete the corpus  
 6. Clean the corpus and split into words  
 7. Feed cleaned corpus words into gensim to create Word2Vec model  
 8. To make an answer prediction:
  1. Clean the question and and all its answers and split into words
  2. Get the Word2Vec model (cosine) similarity of the question with each answer separately
  3. Pick the answer with the highest similarity
