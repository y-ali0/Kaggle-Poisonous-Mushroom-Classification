# Kaggle-Poisonous-Mushroom-Classification
Please refer to `poisonous-mushroom-classification` notebook for my submission to Kaggle's 'Binary Prediction of Poisonous Mushrooms' Competition

## Problem Definition (information taken from the Kaggle website)
* The goal of this competition is to predict whether a mushroom is edible or poisonous (i.e. determine if a mushroom belonged to class `e` or `p`)  based on its physical characteristics
* 21 features (not including id), with 3116945 instances
* The dataset provided is already split into training and test data, where the targets of the test data are not provided
* The dataset is a modified version of UCI's Mushroom Dataset, but with lots of extraneous categories and missing data present
* The submission is graded using the Matthews Correlation Coefficient: MCC = (TP * TN - FP * FN) / sqrt((TP + FP) * (TP + FN) * (TN + FP) * (TN + FN))
* The MCC provides a more representative performance metric of the binary classifier we will need to train in this task

## The process of completing the task
* Exploratory Data Analysis: The distribution of features, the number of unique categories present for each categorical feature, and other information is examined to get an understanding of how the data needs to be processed
* Data Cleaning: Extraneous categories are removed and replaced with null values to prepare for imputation steps in pre-processing
* Data Pre-Processing: A pre-processing pipeline is set up to carry out data imputation, encode categorical data, and scale and transform numerical data
* Model Selection: Two models were examined a Stochastic Gradient Descent (SGD) classifier (with a log loss function) and a Decision Tree model
* Model Evaluation: 5-fold cross-validation was performed on both the SGD and Decision Tree classifier with the Decision Tree performing significantly better at the expense of training time. The decision tree model yielded an F1 score of 0.98 and an MCC score of 0.96 at this stage.
* Model Testing: The Decision Tree model was then used to generate the predicted class of the mushroom. The model obtained a public MCC score of 0.96160. 

