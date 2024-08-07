<a href= "https://colab.research.google.com/github/shahkarKhan24/Sentiment-Analysis-With-LSTMs/blob/main/Notebook.ipynb">   <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></h2>
<h3>Introduction:</h3>
The task that I am working on is like a sentiment analysis given a certain sentence. I must design a model to predict the sentiment of that sentence i.e. neutral or hateful.

<h3>Dataset Description:</h3>
The dataset that I am working on I called fallback dataset, which consist of one training set and two test sets. Each sample has a sentence in Italian with choices ["neutrale", "odio"] followed by its correct label i.e. 0 or 1.

<h3>Non-Baseline:</h3>
I implemented two models, one for base line and other extra for improving accuracy. The first one consist of simple LSTM model which consist of embedding layers, couple of LSTM layer and linear layer in the end. The second model is LSTM-CNN Hybrid model, CNNs are excellent at capturing local patterns and features in data, while LSTMs are proficient in understanding temporal dependencies. Combining them allows for hierarchical feature extraction, where CNNs can extract low-level features, and LSTMs can learn higher-level temporal patterns from these features. CNNs are also prone to overfitting when trained on limited data, especially for tasks with small datasets. This model consist of embedding layer followed by three 1D convolutional layers, simple LSTM layers and then in the end linear layer for prediction.
<div>
<img src="https://github.com/shahkarKhan24/Sentiment-Analysis-With-LSTMs/blob/main/Images/Extra-Baseline.png" width="400" alt="Dataset"/>
</div>

<h3>Design Choices:</h3>
I chose Adam optimizer which works best in most of the LSTM model with learning rate of 0.0001 which was found suitable after grid search. Also, by trail and run I chose a dropout of 0.4 in my model. For a batch size of 128, I ran my model for like 30 epoch which was way more given a small training dataset.
<h3>Baseline Model:</h3>
In baseline model which consist of a simple LSTM layer followed by linear layer. First trained my model without any validation set the accuracy was about 48 -53 % on both test set, I also use early stopping just in case if the model overfit the training stop after 20 epoch because there was no improvement in loss of validation set. but it seems like the dataset is too small to acquire a decent accuracy.

<div>
<img src="https://github.com/shahkarKhan24/Sentiment-Analysis-With-LSTMs/blob/main/Images/baseline.png" width="400" alt="Dataset"/>
</div>

<h3>Results:</h3>
To compare result which can also be seen on figure mentioned inn appendix, non-baseline model which is CNN-LSTM hybrid model works slight better than baseline model with accuracy ranging upto 58.4% for test set 1 and 51.9 % for test set 2. Which can be considered a good model given such a small amount of data.



