# Sentiment Analysis

**In this project, I mainly focused on the sentiment analysis.**

## Introduction

I trained 2 models to classify twitters (**is news** or **not news**): [logistic regression model](https://github.com/shuxg2017/NLP-sentiment-analysis-classification/blob/master/bow_logreg.ipynb) and [lstm model](https://github.com/shuxg2017/NLP-sentiment-analysis-classification/blob/master/embedding%20and%20lstm.ipynb)

**The goal is to visualize the concept space, and give you guys intuition that complex models work in the same way as simple models**

## Data Clean

- remove
  - links
  - @...
  - Numbers and single letters
  - Punctuations 
  - Symbols and emojis
- lower case each word

## Logistic Regression Model

- preprocess: bag of words encoding
  - map each twitter to 3001 dimensional vector
- model
  - size: 3002 parameters
  - structure: one dense layer (size = 1)
  - activation: sigmoid
  - metrics: F1 score
- result
  - **in this project, we do not care about the great performance, but more insights we can draw from the model**

## LSTM model

- preprocess: tokenize and encoding
- model
  - size: 6218 parameters
  - structure: one embedding layer (output size = 2), one lstm layer (size = 1), one dense layer (size = 1)
  - activation of dense layer: sigmoid
  - metrics: F1 score
- result
  - not available

## Concept Spaces
### Logistic Regression Model
Each barchart shows the top most significant 21 words out of 3000 words respect to each category (is news or not news).<br>
**These words will appear in the LSTM model's concept space with meaningful patterns!**
![most important words](https://github.com/shuxg2017/NLP-sentiment-analysis-classification/blob/master/results/important_words_logreg.png)

### LSTM Model
The yellow points are the most significant words of isNews in the logistic regresson model.<br>
The red points are the most significant words of notNews in the logistic regression model.<br>
The blue box located at (0, 0) is the least important words which do not contribute for classification.<br>
**This is very intuitive, because both models are consistant about what they have learned.**
![concept space](https://github.com/shuxg2017/NLP-sentiment-analysis-classification/blob/master/results/concept_space.png)

## Conclusion
Simple models are very easy to interpret. Complex models learn the dataset in a similar way which just like simple models, but much harder to interpret. See how I did simple model (logistic regression) to more complex model (very small lstm model). Now, we can move on to much complex models.
