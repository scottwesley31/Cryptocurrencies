# Cryptocurrencies
Module 18

## Overview of Project
The purpose of this project was to employ unsupervised machine learning strategies to a cryptocurrency dataset. The senior manager for the Advisory Services Team at Accountability Accounting (an investment bank), is interested in providing customers with an investment portfolio which includes cryptocurrencies. Due to the abundance and diversity of cryptocurrency options, a grouping/classification system is needed to make these investment portfolios possible. Since it is not known how these cryptocurrencies should be grouped together, the use of unsupervised machine learning clustering algorithms is an appropriate tool. This project involves data preprocessing, dimension reduction using PCA, cryptocurrency clustering using K-means, and data visualizations.

## Results
This section gives a brief overview of the four main deliverables completed within this project.

### Preprocessing the Data for PCA
In this intial stage of the project, the `crypto_data.csv` dataset was loaded, filtered for cryptocurrencies actively being traded (and with a coin supply greater than zero), checked for null values, converted to numerical values, and scaled in preparation for principal component analysis (PCA).

Here's a screenshot of the final dataframe (`crypto_df`) just prior to scaling:

![crypto_df](https://user-images.githubusercontent.com/107309793/196316697-89ca841d-9645-4b92-9c80-433445cc79db.png)

### Reducing Data Dimensions Using PCA
Once the scaled dataset was obtained, the total number of dimensions was reduced down to 3 principal components (which contains most of the information in the original large dataset).

Here is the resulting new dataframe (`pcs_df`):

![pcs_df](https://user-images.githubusercontent.com/107309793/196317613-4b628f20-157c-4cf8-8cbe-2ca754ac1433.png)

### Clustering Cryptocurrencies Using K-means
Following dimensionality reduction, the transformed dataset can then be used to find centroids. This is completed by graphing an elbow curve (inertia, a measure of variance, vs. cluster number, or values of K).

Using the `pcs_df` an elbow curve was plotted:

![elbow_curve](https://user-images.githubusercontent.com/107309793/196318314-070266e8-245f-4d90-8470-197b89ff4e58.png)

This elbow curve suggests that the dataset should involve a K value of 4 (should be clustered into 4 groups). This cluster number was then used with a K-means algorithm which groups all of the datapoints into 4 clusters based off of having some similarity/distance measure to a centroid.

The final dataframe (`clustered_df`) obtained after employing the K-means algorithm is depicted below. The last column `Class` indicates which of the 4 clusters the cryptocurrency was assigned to:

![clustered_df](https://user-images.githubusercontent.com/107309793/196318973-9b35039f-573e-485f-ad2a-36527ae19319.png)

### Visualizing Cryptocurrencies Results
The final step in this project was to visualize the data and clustering. A 3D plot incorporating the principal component values of the `clustered_df` on the x-, y-, and z-axes was generated which colored each datapoint by their assigned `Class`. This allows for a visual representation of the clusters. Each datapoint within this plot provides information when hovered over (like the name of the algorithm and cryptocurrency; this feature is not depicted below):

![3D_plot](https://user-images.githubusercontent.com/107309793/196319963-2d0c26d2-12c9-464e-b040-028697a03258.png)

Another plot was generated on a 2D plane which graphs the total coin supply against the total number of coins mined. Each datapoint is similarly colored based on class and contains hover info about the cryptocurrency coin name.

![2D_plot](https://user-images.githubusercontent.com/107309793/196320258-aad1be9f-1b3f-4684-9136-3a3e93c5e96a.png)

## Summary
The combination of 
