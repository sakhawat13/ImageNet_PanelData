> ## First we import the packages


```python
import pandas as pd
import nltk
nltk.download('words')

words = set(nltk.corpus.words.words())
```

    [nltk_data] Downloading package words to
    [nltk_data]     C:\Users\u\AppData\Roaming\nltk_data...
    [nltk_data]   Package words is already up-to-date!
    

> ## Then we make a function to clean up text


```python
def Cleanup_text (texts, keep_number):

    extract = str(())
    word_list = list(())
    for k in nltk.wordpunct_tokenize(texts):
        if keep_number:
            if k.lower() in words or not  k.isalpha() :
                word_list.append(k)
        else:
            if k.lower() in words :
                word_list.append(k)
            
        
        
        
    extract = " ".join(word_list)        

    return extract
```

>## We test the function


```python
Text = "This is asdfoasdf random asdf gibberish 123k-# text"
print("Original text -> " + Text)
```

    Original text -> This is asdfoasdf random asdf gibberish 123k-# text
    


```python
clean_text = Cleanup_text(Text,False)
print ("After Cleanup ->  " + clean_text)
```

    After Cleanup ->  This is random gibberish text
    
