# Predicting Customer Personality to Boost Marketing Campaign
Project by Rakamin Academy

**Overview**

A company can grow rapidly by understanding customer personalities, which allows it to provide better services and benefits to potential loyal customers. By analyzing historical marketing campaign data to improve performance and target the right customers for transactions on the company's platform, the focus is on creating a predictive clustering model to facilitate decision-making.

**Objective:**

To identify ideal customers for maximizing marketing reach.

**Goal:**

To build a clustering model and develop business strategies to optimize the company's marketing campaigns.

## Data Understanding
- The dataset comprises 2,240 records with 30 columns/features.
- Data types include float64, int64, and object.
- There are 24 null values in the Income feature.
- No duplicate data entries.
- The data tends to have outliers.

Data cleaning and feature engineering will be performed to create new features such as conversion rate and to extract insights from features like age, income, and spending patterns. The aim is to identify customer behavior patterns that provide valuable insights into conversion rates.

## TASK 1: Conversion Rate Analysis Based on Income, Spending, and Age

![image](https://github.com/user-attachments/assets/76be7fcd-2c2a-4727-924c-0fc632445488)

![image](https://github.com/user-attachments/assets/4b1a0f5b-ddb7-403c-881e-3abdc5810c48)

- Total Spending vs Conversion Rate: There is no clear relationship between the amount spent and the frequency of purchases. Therefore, spending decisions do not always lead to higher conversions.
- Conversion Rate vs Income: Ironically, the conversion rate tends to decrease with higher income. Thus, money does not always buy customer loyalty.
- Conversion Rate vs Age: There is no linear relationship between customer age and conversion rate. However, the data distribution shows fairly uniform variation across age ranges, indicating that other factors have a greater influence on conversion rates.
- Total Spending vs Income: Higher income corresponds to higher total spending. This means that more money allows for more spending.

![image](https://github.com/user-attachments/assets/e1d03ddf-90e4-4fb4-8f49-a3facc272aa6)

In the Income, Total Spending, and Conversion Rate features, there are no clear patterns or age groups. Age distribution is fairly uniform and does not significantly cluster. This suggests that, in this context, age is not a dominant factor influencing the relationship between income, spending, and conversion rates. Factors such as income and spending patterns have a greater impact on determining customer conversion rates. Nonetheless, age should still be considered in marketing strategies and further analysis. 

## TASK 2: Data Cleaning & Preprocessing

**Missing Values:** Fill missing values with the median. This approach is robust to outliers and ensures that the imputed values are representative of the central tendency of the feature.

**Anomalies:** Handle anomalies using the Interquartile Range (IQR) method. This involves identifying outliers by calculating the IQR and removing or adjusting data points that fall outside of the acceptable range.

**Categorical Features:** Categorical features will be encoded to make them suitable for machine learning algorithms. This typically involves techniques such as one-hot encoding or label encoding, depending on the nature of the categorical data.

**Feature Standardization:** Standardize features to avoid bias in the model. Standardization involves scaling features to have a mean of 0 and a standard deviation of 1. This ensures that all features contribute equally to the model, preventing any single feature from disproportionately influencing the results due to differing scales.

## TASK 3: Data Modeling

![image](https://github.com/user-attachments/assets/b6722fb4-ffd5-4eb3-aa8e-713508a39734)

From the Distortion Score and Elbow Method, the optimal number of clusters is determined to be 4.

![image](https://github.com/user-attachments/assets/6d49b367-5f2e-4e41-b18e-ffb570affa9a)

**Clustering:**

Algorithm: K-Means.

The results from modeling and clustering the data using the K-Means algorithm show that the clusters formed clearly and effectively separate the data into distinct groups. This plot demonstrates how the data can be well-differentiated into unique segments, reflecting the diversity of patterns and characteristics present.


## Evaluation

![image](https://github.com/user-attachments/assets/dd7d7407-6216-4b39-89a6-cfb7ddd027b0)

Based on the silhouette score, the optimal number of clusters appears to be 2 clusters (0.542) or 3 clusters (0.484), as these configurations provide the highest silhouette scores.

## TASK 4: Customer Personality Analysis for Marketing Retargeting

![image](https://github.com/user-attachments/assets/347d3ffc-dd5d-459e-ada3-4b42d86f368b)

1. Cluster 0: Loyal Customers with Medium Transactions (Loyal Spenders)
    - Customers in this cluster tend to have a relatively high transaction frequency, indicating they are loyal customers who frequently make purchases. However, their spending is at a moderate level. With a decent income, they could be potential targets for increased sales through more attractive promotions. Their relatively older age suggests a preference and loyalty to brands they have trusted over time.

2. Cluster 1: Younger Customers with Low Transactions (Emerging Users)
    - Customers in this cluster exhibit low transaction frequency and spending, indicating they may be new or less frequent buyers. With lower incomes, they are likely more price-sensitive. The very low conversion rates suggest the need for more personalized marketing strategies and offers that fit their budget. Their younger age shows potential for long-term engagement if their loyalty can be successfully cultivated.

3. Cluster 2: Premium Customers with High Spending (High Rollers)
    - This cluster contains customers with very high transaction frequency and spending, as well as the highest income among all clusters. High conversion rates indicate they are highly responsive to marketing campaigns. These customers are prime targets for premium promotions and exclusive services. Their middle-aged demographic reflects a balance between experience and strong purchasing power.

4. Cluster 3: Most Active Customers with Maximum Transactions (Top Engagers)
    - Customers in this cluster have the highest transaction frequency and spending, almost equivalent to Cluster 2. Their income is quite high, but their conversion rate is slightly lower compared to Cluster 2. This suggests that, despite their frequent transactions, there may be opportunities to enhance the effectiveness of marketing campaigns. Their older age may mean they value the experience and reliability offered by the brand.
