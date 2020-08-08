# Prediction for Default Credit Card Customer
## Data Description
This dataset can be accessed from [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients#). The definition of features are defined as below:
- DEFAULT: Whether the user default the next month payment (No = 0, Yes = 1).
- LIMIT_BAL: Amount of the given credit (NT dollar). It includes both the individual consumer credit and his/her family (supplementary) credit.
- SEX: Male of female (1 = male, 2 = female).
- EDUCATION: Consumer's highest education level (1 = graduate school; 2 = university; 3 = high school; 4 = others).
- MARRIAGE: Marital status (1 = married; 2 = single; 3 = divorce; 4 = others).
- AGE: Age in year.
- PAY_0 to PAY_6: History of past payment (-2 = no consumption; -1 = pay duly; 0 = the use of revolving credit; 1 = payment delay for one month; 2 = payment - delay for two months; . . .; 8 = payment delay for eight months; 9 = payment delay for nine months and above).
- BILL_AMT1 to BILL_AMT6: Amount of bill statement (NT dollar).
- PAY_AMT1 to PAY_AMT6: Amount of previous payment (NT dollar).

## Project Procedure
1. Data imputation
2. Explore data with visualizaion

   This step includes checking the correlation between each features.
   
3. Data preprocessing

   Originally we consider applying oversampling to train the model. However, we opt to train the model with the raw data, expecting the algorithm to "learn" all the characteristics of the data. Oversampling is a great tool when your tasks involve descriptive analysis, while in machine learning we tend to avoid using this technique.
   
4. Modeling

   We performed KNN classifier, Logistic Regression, Linear SVC, SVC with kernel, and Decision Tree. Also, providing the visualization for training and validation score in each model.
   
## Conclusion
Support Vector Classifier with rbf kernel (SVC-rbf) outperformed the other models in the end. It reported with 81.20% accuracy rate and 61.90% precision score. Further, precision is the most important measure in our case, since the priority mission is to distinguish those risky customers as many as possible in our prediction. In this case, we were facing several issues from the beginning, and were all solved by the following actions:

1. Ambiguous data - Contact the source data provider for detailed information.
2. Imbalanced data - Implement oversampling technique to get a better result.
3. Computational barrier - Adapt fewer rows to the time consuming model, e.g. support machine model.

Across all the models, we found that SVC with kernel is easily overfitting, leading it overwhelmed other models most of the time. Therefore, the choice of the hyperparameter's range is crucial. We prevent from trying extremely high regularization parameter and gamma, since they will result in an inelastic boundary and a strict similarity measure. Overall, after implementing some preprocessing and data exploratory techniques, we refine the models as better as we can, and provide admissible prediction results.
