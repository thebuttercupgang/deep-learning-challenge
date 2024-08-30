# deep-learning-challenge
Module 21 Challenge due 08/29/2024
- The purpose of this analysis is to utilize machine learning and neural networks in order to determine which applicants have the best amount of success in their venture.

## Data Preprocessing
I preprocessed the data by the dropping superfluous columns EIN and NAME and finding the number of unique values in the remaining columns. For the column APPLICATION_TYPE, I set a cutoff value of 528 since the value counts below that amount don't constitute at least 1 percent of the total applications. For the column CLASSIFICATION, I set a cutoff value of 777for the same reason. The counts for the values under the cutoff were binned into a value called “OTHER”
The categorical data was then converted into numeric data using pd.get_dummies()
The target variable (y) was IS_SUCCESSFUL. The data held 44 features.

## Compiling, Training, and Evaluating the Model
The goal of the model was to produce a predictive accuracy of 75%. None of the official attempts I made were able to reach this threshold. The range of accuracy was from 0.728 to 0.731. Each model ran 100 epochs

## Model Summaries
### ATTEMPT 1
In my first attempt, I used two layer with 5 and 10 neurons respectively. This had the lowest accuracy of my three attempts
- layer1 = 5 neurons : activation function = 'relu'
- layer2 = 10 neurons : activation function = 'relu'
- accuracy: 0.7286 - loss: 0.5529

![ATTEMPT 1](https://github.com/thebuttercupgang/deep-learning-challenge/blob/main/Graphs/attempt_1.png?raw=true)


### ATTEMPT 2
In my second attempt, I tried using a tanh function along with a relu function. The accuracy was only marginally higher than the first attempt.
- layer1 = 5 neurons : activation function = 'relu'
- layer2 = 10 neurons : activation function = 'tanh'
- accuracy: 0.7300 - loss: 0.5523

![ATTEMPT 2](https://github.com/thebuttercupgang/deep-learning-challenge/blob/main/Graphs/attempt_2.png?raw=true)

### ATTEMPT 3
In my third attempt, I used a third layer while keeping all the functions relu. This was the highest accuracy score of the three models meaning 73.1% of the model’s predicted values align with the dataset’s true values.
- layer1 = 5 neurons : activation function = 'relu'
- layer2 = 10 neurons : activation function = 'relu'
- layer3 = 10 neurons : activation function = 'relu'
- accuracy: 0.7312 - loss: 0.5540

![ATTEMPT 3](https://github.com/thebuttercupgang/deep-learning-challenge/blob/main/Graphs/attempt_3.png)

## Summary
-  I was not able to find a model that was able to reach 75% accuracy. Tuning the model by adding neurons or layers does not result in higher accuracy. Perhaps another model would yield higher accuracy.
