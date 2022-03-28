# Cryptocurrencies

## Overview

We have been asked to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for a new investment. Since the data does not have any known outcome, we needed to preprocess it to fit an unsupervised Machine Learning model that will enable us to run a clustering algorithm that will allow us to group the cryptocurrencies.

## Results

## Deliverable 1: Preprocessing the Data for PCA

![Screen Shot 2022-03-27 at 9 13 42 PM](https://user-images.githubusercontent.com/93485455/160315260-b214201d-b607-4833-8f20-7a213585c18f.png)

All cryptocurrencies that are not being traded are removed
![Screen Shot 2022-03-27 at 9 13 56 PM](https://user-images.githubusercontent.com/93485455/160315302-9fc4bf8e-481c-4cd6-859d-ff8d857ff33d.png)

The IsTrading column is dropped
![Screen Shot 2022-03-27 at 9 14 27 PM](https://user-images.githubusercontent.com/93485455/160315334-edff399a-3f50-4a03-8b33-97a65636d158.png)

All the rows that have at least one null value are removed
![Screen Shot 2022-03-27 at 9 14 39 PM](https://user-images.githubusercontent.com/93485455/160315347-43a1cf6b-8e0c-4e6d-a904-ac8a62be04ac.png)

All the rows that do not have coins being mined are removed
![Screen Shot 2022-03-27 at 9 14 51 PM](https://user-images.githubusercontent.com/93485455/160315359-23ac3020-fe1e-4da6-a6d8-b7cb93fa3f46.png)

A new DataFrame is created that stores all cryptocurrency names from the CoinName column and retains the index from the crypto_df DataFrame
![Screen Shot 2022-03-27 at 9 15 25 PM](https://user-images.githubusercontent.com/93485455/160315378-897a0e7e-0aa8-4c10-9a6b-83703d5f73dd.png)

The CoinName column is dropped 
![Screen Shot 2022-03-27 at 9 15 39 PM](https://user-images.githubusercontent.com/93485455/160315394-77784c1f-34ea-46b1-a41d-c5bac6be0068.png)

The get_dummies() method is used to create variables for the text features, which are then stored in a new DataFrame, X
![Screen Shot 2022-03-27 at 9 15 52 PM](https://user-images.githubusercontent.com/93485455/160315406-9d48b3d6-2ab4-47a2-ae74-8c350c97e2c0.png)

The features from the X DataFrame have been standardized using the StandardScaler fit_transform() function
![Screen Shot 2022-03-27 at 9 16 10 PM](https://user-images.githubusercontent.com/93485455/160315417-495d2098-e215-414e-a614-e7a8a5b5864c.png)


## Deliverable 2: Reducing Data Dimensions Using PCA

Apply PCA to reduce the dimensions to three principal components. Create a new DataFrame named pcs_df that includes the following columns, PC 1, PC 2, and PC 3, and uses the index of the crypto_df DataFrame as the index.
![Screen Shot 2022-03-27 at 9 20 11 PM](https://user-images.githubusercontent.com/93485455/160315594-fae24639-2d71-4e25-a007-1a8d1248ad44.png)

## Deliverable 3: Clustering Cryptocurrencies Using K-means

An elbow curve is created using hvPlot to find the best value for K
![Screen Shot 2022-03-27 at 9 24 43 PM](https://user-images.githubusercontent.com/93485455/160317993-32d03de4-bbfc-47e0-ab2f-fb725043b131.png)

A new DataFrame is created with the same index as the crypto_df DataFrame and has the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class
![Screen Shot 2022-03-27 at 9 22 12 PM](https://user-images.githubusercontent.com/93485455/160315784-1b0ee97f-cd7e-4b3e-b2c8-801a5013f82c.png)

## Deliverable 4: Visualizing Cryptocurrencies Results

The clusters are plotted using a 3D scatter plot, and each data point shows the CoinName and Algorithm on hover
![Screen Shot 2022-03-27 at 9 23 43 PM](https://user-images.githubusercontent.com/93485455/160318275-0a29187c-5740-4808-94bb-f9c20a0e1846.png)


![Screen Shot 2022-03-27 at 9 25 16 PM](https://user-images.githubusercontent.com/93485455/160318312-f1983b94-a887-4b11-b615-693ff4370807.png)

![Screen Shot 2022-03-27 at 9 25 49 PM](https://user-images.githubusercontent.com/93485455/160318337-e1b77cc5-38b4-45ad-b3c2-d074cb3bd212.png)

![Screen Shot 2022-03-27 at 9 26 02 PM](https://user-images.githubusercontent.com/93485455/160318352-6bf99cae-26fb-4d46-94a7-e1c1e0c894b1.png)


