# riya_tih38wBB69SBEp49

# Background:

To understand if customers are satisfied with the company's performance, they recently surveyed a select customer cohort. 
The problem presents a subset of this data.

## Data Description:

Y = target attribute (Y) with values indicating 0 (unhappy) and 1 (happy) customers <br>
X1 = My order was delivered on time <br>
X2 = contents of my order was as I expected <br>
X3 = I ordered everything I wanted to order <br>
X4 = I paid a good price for my order <br>
X5 = I am satisfied with my courier <br>
X6 = The app makes ordering easy for me <br>

Attributes X1 to X6 indicate the responses for each question and have values from 1 to 5 where the smaller number indicates less and the higher number indicates more towards the answer. 

## Goal(s):

Predict if a customer is happy or not based on the answers they give to questions asked.

## Success Metrics:
Reach 73% accuracy score or above, or convince us why your solution is superior.

## Bonus(es):
We are very interested in finding which questions/features are more important when predicting a customer’s happiness. Using a feature selection approach help us 
understand what is the minimal set of attributes/features that would preserve the most information about the problem while increasing predictability of the data we have.
Is there any question that we can remove in our next survey?

# Solution:

This is a binary classification problem. 

The repository contains a solution in the `python notebook`, where multiple ML classifiers are trained on a training dataset and the desired accuracy of 73% is achieved. 
Two chosen models with the best performance are submitted as solutions. 

## Training and Evaluation: 
Tree-based models were performing better according to `LazyClassifier` library. I found that ensemble models with the base model of `Decision Tree Classifier`, such as the `Bagging Classifier` and the  `XGBoost Classifier` 
performed the best. Model performance was measured by `accuracy`, `precision`, `recall`, and `f1-score`. To evaluate the best model, hyperparameter optimization was performed using `Grid Search` and `Random Search` algorithms.
To boost model robustness, and avoid overfitting, `k-fold cross validation` and regularization methods such as `L1 regularization` were employed. `Recursive Feature Elimination` was employed to determine feature selection.

# Conclusion:

For the given dataset, I found the best performance model to be a `Voting Classifier` which used the base models of `Logistic Regression`, `Decision Tree Classifier` and `XGBoost Classifier`. It gives an accuracy of 81%. 
The exclusion of the least-important feature 'X4' led to a decrease in model performance, hence all features were used to evaluate the final model.
