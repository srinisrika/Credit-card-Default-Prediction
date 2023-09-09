# Credit-card-Default-Prediction

<details>
  <summary>Table of Contents</summary>
  <ol>
    
* [About The Project](#about-the-project)
* [Data Description](#data-description)
* [Feature Engineering](#feature-engineering)
* [Model Implementation](#model-implementation)
* [Conclusion](#conclusion)
    
  </ol>
</details>

## About the Project

The project is aimed at determining customers who default on a payment based on social and
financial factors. A default is the failure to make a payment by the assigned due date. When it
comes to credit cards, defaulting on a payment can result in a poor credit score. It is important
for banks in terms of risk management to know if a potential client is capable of making
payments on time. This factor helps in determining the credit limit, issuance of a credit card, etc.
This dataset helps in evaluating customers as credible or not credible.

The main aim of this project is to predict if the client will default on a payment the next month.
This is done by initially performing Exploratory Data Analysis (EDA) with the features of the
dataset. The relationships of various features with each other are studied followed by feature
engineering and feature selection.

By adopting Supervised Machine Learning models, the basic factors that affect the probability
of a credit card default can be highlighted. In particular, classification models like
**Logistic Regression, Support Vector Machines (SVM), Gaussian Naïve Bayes, Neural
Networks** have been utilized.

## Data Description

This dataset consists of information on customers and their default payments in Taiwan. The analysis
of default payments by customers will help in determining their repayment credibility.  

**2.1 Dataset Attributes**  
This research employed a binary variable, default payment (Yes = 1, No = 0), as the response
variable. This study reviewed the literature and used the following 23 variables as explanatory
variables:

**X1**: Amount of the given credit (New Taiwan (NT) dollar): it includes both the individual
consumer credit and his/her family (supplementary) credit.  
**X2**: Gender (1 = male; 2 = female).  
**X3**: Education (1 = graduate school; 2 = university; 3 = high school; 4 = others).  
**X4**: Marital status (1 = married; 2 = single; 3 = divorced).  
**X5**: Age (year).  
**X6 - X11**: History of past payment. The past monthly payment records (from April to
September, 2005) as follows:  
X6 = the repayment status in September, 2005; X7 = the repayment status in August, 2005; . . .;
**X11** = the repayment status in April, 2005.  
The measurement scale for the repayment status is: -1 = pay duly; 1 = payment delay for one
month; 2 = payment delay for two months; . . .; 8 = payment delay for eight months; 9 =
payment delay for nine months and above.  
**X12-X17**: Amount of bill statement (New Taiwan (NT) dollar).  
X12 = amount of bill statement in September, 2005; X13 = amount of bill statement in August,
2005; . . .; X17 = amount of bill statement in April, 2005.  
**X18-X23**: Amount of previous payment (New Taiwan (NT) dollar).  
X18 = amount paid in September, 2005; X19 = amount paid in August, 2005; . . .; X23 = amount
paid in April, 2005.  

## Feature Engineering

Upon analysis, it was found that,  

* Almost all the features are weakly correlated to the target class except for a few feature  
* Almost all numerical variables are significantly skewed to the right and has lot of outliers  
* The data has a major class imbalance, approx. 3:7 to the class of interest  

To address these problems, the features were transformed in the following way:  

* Captured the total utilization of the available credit limit for those months where data is available  
* Took an average expenditure ranging from 1 month to 6 months. **Avg_exp_1m** captures the average expenditure of a client for the past one month and **Avg_exp_2m** captures the average expenditure of a client for the past 2 months and so on till **Avg_exp_6m** which captures the average expenditure of a client on a particular card for 6 months.

## Model Implementation  

Following are the different Machine Learning Models implemented for Classification:
   * **Logistic Regression**
   * **Gaussian Naive Bayes**
   * **Neural Network**
   * **Support Vector Machine**

**Overview:**  
- Implemented models with balanced as well as unbalanced data.  
- Depicted comparison between Accuracy, F1 Score, Precision, and recall.  
- Implemented over-sampling and under-sampling with balanced data and performed a comparative study at the end.  


## Conclusion

From the evaluation of the ML methods, applied on the dataset - **Logistic Regression**, **Support Vector Machines**, **Gaussian Naive Bayes**, and **Neural Networks**:  

- **SVM**, **GNB**, and **Neural Networks** perform well in a binary classification problem. A point to be noted is the dataset is an unbalanced dataset - so **roc_auc_score** is a better metric to focus on than pure accuracy. In case where balancing techniques are used - the **roc_auc_score** and **recall** are significantly better than where the data is not balanced. 

- Most time was spent on understanding nuances of the features from a statistical standpoint and selecting the best ones based on evidence

- Upscaling was important to elevate our class of interest and **SMOTE** does a good job

- Logistic Regression outperforms other algorithms for our case by having high precision and recall values that are also close to each other

- The best results were obtained when the threshold value for positive classification was over **.81**.





