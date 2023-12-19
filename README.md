# Armenian Dialect Detector

A fun little NLP project where I train different classifiers to determine whether a given text conforms to the Eastern Armenian or Western Armenian dialect. For training/testing data, random articles for both dialects were collected from Wikipedia using the Wikipedia API. Character-level $n$-grams were used for tokenization, with $n \in [3, 4, 5]$. Feature extraction was done by TF-IDF vectorization.

## Installation

```
git clone https://github.com/takavor/Armenian-Dialect-Detector.git
cd Armenian-Dialect-Detector
pip install -r requirements.txt
```

## Results

$n=3$:

| Model               | Accuracy | F1       | Precision | Recall  |
| ------------------- | -------- | -------- | --------- | ------- |
| Logistic Regression | 0.979592 | 0.984615 | 0.969697  | 1.00000 |
| Naive Bayes         | 0.918367 | 0.935484 | 0.939394  | 0.96875 |
| Decision Tree       | 0.938776 | 0.953846 | 0.939394  | 0.96875 |
| SVM                 | 0.979592 | 0.984615 | 0.969697  | 1.00000 |
| MLP                 | 0.979592 | 0.984615 | 0.969697  | 1.00000 |

$n=4$:

| Model               | Accuracy | F1       | Precision | Recall  |
| ------------------- | -------- | -------- | --------- | ------- |
| Logistic Regression | 0.979592 | 0.984615 | 0.969697  | 1.00000 |
| Naive Bayes         | 0.979592 | 0.984615 | 0.969697  | 1.00000 |
| Decision Tree       | 0.938776 | 0.953846 | 0.939394  | 0.96875 |
| SVM                 | 0.979592 | 0.984615 | 0.969697  | 1.00000 |
| MLP                 | 0.979592 | 0.984615 | 0.969697  | 1.00000 |

$n=5$:

| Model               | Accuracy | F1       | Precision | Recall  |
| ------------------- | -------- | -------- | --------- | ------- |
| Logistic Regression | 0.959184 | 0.969697 | 0.941176  | 1.00000 |
| Naive Bayes         | 0.979592 | 0.984615 | 0.969697  | 1.00000 |
| Decision Tree       | 0.959184 | 0.968750 | 0.968750  | 0.96875 |
| SVM                 | 0.959184 | 0.969697 | 0.941176  | 1.00000 |
| MLP                 | 0.979592 | 0.984615 | 0.969697  | 1.00000 |

## Some thoughts

In my opinion, character-level $n$-grams were a good strategy for extracting features from the data. A huge part of the orthographical differences between both dialects stem from different orthographies for words that would otherwise be written the same. This is due to the fact that Eastern Armenian orthography (which is mostly present in Armenia) underwent a reform during the Soviet era, whereas Western Armenian (largely a diasporic language) retained classical orthography. As a result, words in both dialects sometimes differ by 3-5 consecutive letters in their orthography. Of course, this reasoning does not include grammatical differences between both dialects, which are largely prevalent.
