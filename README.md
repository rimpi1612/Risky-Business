# Risky Business
 
![Credit Risk](Images/credit-risk.jpg)

## Background

Mortgages, student and auto loans, and debt consolidation are just a few examples of credit and loans that people seek online. Peer-to-peer lending services such as Loans Canada and Mogo let investors loan people money without using a bank. However, because investors always want to mitigate risk, a client has asked to help them predict credit risk with machine learning techniques.

We are building and evaluating several machine learning models to predict credit risk using data we woiuld typically see from peer-to-peer lending services. Credit risk is an inherently imbalanced classification problem (the number of good loans is much larger than the number of at-risk loans), so we need to employ different techniques for training and evaluating models with imbalanced classes. We use the imbalanced-learn and Scikit-learn libraries to build and evaluate models using the two following techniques:

1. [Resampling](#Resampling)
2. [Ensemble Learning](#Ensemble-Learning)

- - -

### Files

[Resampling Starter Notebook](Notebook/credit_risk_resampling.ipynb)

[Ensemble Starter Notebook](Notebook/credit_risk_ensemble.ipynb)

[Lending Club Loans Data](Data/LoanStats_2019Q1.csv)

- - -

### Instructions

#### Resampling

Used the [imbalanced learn](https://imbalanced-learn.readthedocs.io) library to resample the LendingClub data and build and evaluate logistic regression classifiers using the resampled data.

To begin:

1. Read the CSV into a DataFrame.

2. Split the data into Training and Testing sets.

3. Scale the training and testing data using the `StandardScaler` from `sklearn.preprocessing`.

4. Use the provided code to run a Simple Logistic Regression:
    * Fit the `logistic regression classifier`.
    * Calculate the `balanced accuracy score`.
    * Display the `confusion matrix`.
    * Print the `imbalanced classification report`.

Next we will:

1. Oversample the data using the `Naive Random Oversampler` and `SMOTE` algorithms.

2. Undersample the data using the `Cluster Centroids` algorithm.

3. Over- and undersample using a combination `SMOTEENN` algorithm.


For each of the above, we will need to:

1. Train a `logistic regression classifier` from `sklearn.linear_model` using the resampled data.

2. Calculate the `balanced accuracy score` from `sklearn.metrics`.

3. Display the `confusion matrix` from `sklearn.metrics`.

4. Print the `imbalanced classification report` from `imblearn.metrics`.


We use the above to answer the following questions:

* Which model had the best balanced accuracy score?

> SMOTEENN and SMOTE resampled logistic regression models have the best balanced accuracy score

* Which model had the best recall score?

> All the models have same avg/total recall score (0.99)

* Which model had the best geometric mean score?

> All the models have the same avg/total geo score (0.99)


#### Ensemble Learning

In this section, we train and compare two different ensemble classifiers to predict loan risk and evaluate each model. We use the [Balanced Random Forest Classifier](https://imbalanced-learn.readthedocs.io/en/stable/generated/imblearn.ensemble.BalancedRandomForestClassifier.html#imblearn-ensemble-balancedrandomforestclassifier) and the [Easy Ensemble Classifier](https://imbalanced-learn.readthedocs.io/en/stable/generated/imblearn.ensemble.EasyEnsembleClassifier.html#imblearn-ensemble-easyensembleclassifier).

To begin:

1. Read the data into a DataFrame using the provided starter code.

2. Split the data into training and testing sets.

3. Scale the training and testing data using the `StandardScaler` from `sklearn.preprocessing`.


Then, complete the following steps for each model:

1. Train the model using the quarterly data from LendingClub provided in the `Resource` folder.

2. Calculate the balanced accuracy score from `sklearn.metrics`.

3. Display the confusion matrix from `sklearn.metrics`.

4. Generate a classification report using the `imbalanced_classification_report` from imbalanced learn.

5. For the balanced random forest classifier only, print the feature importance sorted in descending order (most important feature to least important) along with the feature score.


We use the above to answer the following questions:

* Which model had the best balanced accuracy score?

> EasyEnsembleClassifier has a better balanced accuracy (0.925).

* Which model had the best recall score?

> Both have the same recall score (0.91 to 0.77)

* Which model had the best geometric mean score?

> Both have the same geometric mean score (0.78)

* What are the top three features?

> From the Balanced Random Forest Classifier, the top features are 
    total_rec_prncp, 
    total_rec_int, 
    total_pymnt_inv .
    
- - -

