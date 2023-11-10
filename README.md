# Tweet_Classification_Using_BERT
Predict which Tweets are non-racist or racist by using BERT model.

## Overview
BERT model:
- BERT stands for Bidirectional Encoder Representation from Transformer, meaning a two-way representation model based on Transformer technology.
- Trained on Wikipedia (~2.5 billion words) and Google's BooksCorpus (~800 million words).
- The BERT model used is `bert-base-uncased` with 110 million parameters. The "base" corresponds to 12 transformer encoder layers, and "uncased" is suitable for languages without diacritics, such as English.

### 1. Quick EDA

Training dataset have: 21602 rows and 3 collumns.
Test dataset have : 17197 rows and 2 collumns.
**Meaning of collumns:**
* `id`: the tweet ID
* `tweet`:  the tweet content.
* `label`: only present in the training data, indicating whether the tweet is racist or not. (0) represents non-racist, and (1) represents racist.

### 2. Preprocessing Data

Apply some text preprocessing steps:
* Stemming and lemmatization.
* Convert uppercase letters to lowercase.
* Expand abbreviations to full words.
* Remove non-ASCII characters.
* Remove stopwords.

### 3. BERT Model for Tweet classification

* Using the pretrained bert-base-uncased to tokenize text into vector
* Fine-tune the Pretrained BERT model on `X_train` (80% of train data) and evaluate it on `X_val` (20% of train data) with 10 epochs
* Evaluate the model: The model achieves a relatively high accuracy on this dataset, specifically 98% for non-racist sentences and 72% for racist sentences. This may be due to the significant imbalance in the number of non-racist and racist sentences.
* Classification on test dataset
