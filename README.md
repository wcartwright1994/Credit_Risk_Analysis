# Credit_Risk_Analysis

## Overview of the Analysis

The purpose of this analysis is to evaluate the performance of 6 different machine learning algorithms to determine if they should be used to predict credit risk.

The algorithms included are broken down into the following categories:
  * Oversampling (RandomOverSampler and SMOTE)
  * Undersampling (ClusterCentroids)
  * Combination of Oversampling and Undersampling (SMOTEENN)
  * Bias Reduction (BalancedRandomForestClassifier and EasyEnsembleClassifier)

## Results

**Oversampling - Random**
 * Accuracy: 67%
 * Precision: 1%
 * Recall: 70%

![RandomOversampling](https://user-images.githubusercontent.com/82549092/129476630-06222f8c-5c3f-4515-8917-31ef1b8c80b8.PNG)

**Oversampling - SMOTE**
 * Accuracy: 66%
 * Precision: 1%
 * Recall: 63%

![SMOTE](https://user-images.githubusercontent.com/82549092/129476634-21c00bb8-079e-4551-8161-2b21c3fa9a9a.PNG)

**Undersampling**
 * Accuracy: 54%
 * Precision: 1%
 * Recall: 69%

![Undersampling](https://user-images.githubusercontent.com/82549092/129476635-2c69e6a3-761e-4687-8dc6-c2544d42e2fc.PNG)

**Combination of Oversampling and Undersampling - SMOTEENN**
 * Accuracy: 67%
 * Precision: 1%
 * Recall: 77%

![SMOTEENN](https://user-images.githubusercontent.com/82549092/129476637-d976ba73-8aff-4224-ba38-bb6ddd9f4f4e.PNG)

**Bias Reduction - BalancedRandomForestClassifier**
 * Accuracy: 79%
 * Precision: 3%
 * Recall: 70%

![BalancedRandomForestClassifier](https://user-images.githubusercontent.com/82549092/129476640-ece44169-a8d9-4e88-896c-d99a4700e5f0.PNG)


**Bias Reduction - EasyEnsembleClassifier**
 * Accuracy: 93%
 * Precision: 9%
 * Recall: 93%

![EasyEnsembleClassifier](https://user-images.githubusercontent.com/82549092/129476643-e4c84b5e-9fe2-49cd-ad59-d4d412cea05a.PNG)


## Summary

When predicting credit risk, recall is more important for a bank than precision. If a customer defaults on an loan, the bank is at risk of losing its principal, whereas if they assign a higher-risk rating to a customer and he does not default, the bank will earn more in interest than if they assigned a lower-risk rating. However, if the model is not precise and assigns high-risk ratings to customers when they are low-risk, the bank would risk losing the customer if another bank charged a lower interest rate or required less collateral.

Based on the data provided, I would not suggest using any of these models for the following reasons:
 * All of the models tested have f1 scores below .2.
 * The average accuracy score of the models was 71%, with 4 of the models being less than 70% accurate.
 * Although the most accurate model, EasyEnsembleClassifier, had an accuracy of 93%, it only had a precision of 9%, meaning it was extremely conservative and classified too many customers as high-risk.

The main cause of the model weakness is due to the use of binary classifications for risk. Credit risk is better represented as either a continuous variable or a discrete variable with many different buckets. In addition, concentration risk is also a large factor, as a customer may be considered "low-risk", but may cause a bank to become overexposed to a specific sector or loan type. 
