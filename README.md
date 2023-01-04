# Amazon_Vine_Analysis

# Overview of Project


The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

In this project, We are reviewing the Electronics category to analyze datasets and use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. PySpark was used to determine if there is any bias toward favorable reviews from Vine members in the dataset.  

## Deliverables 

| Deliverables      | Description |
| ----------- | ----------- |
| Deliverable 1      | Perform ETL on Amazon Product Reviews       |
| Deliverable 2       | Determine Bias of Vine Reviews       | 
| Deliverable 3       | A Written Report on the Analysis       | 


| Resource  |
| ----------- |   
| `https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Electronics_v1_00.tsv.gz` |


| Software / Environment   |
| ---------------------- |
| PySpark  |
| pgAdmin    | 
| Google Colab |
| AWS RDS |


## Results 

![image](https://user-images.githubusercontent.com/22928255/210461087-a48bd9f3-97f2-4af4-97a0-4d8def3f9554.png)

For the Electronics product category, we have 3M data which we filter out based on the creteria below :
* Votes Greater than 20 

![image](https://user-images.githubusercontent.com/22928255/210461436-7e958f76-cd2a-4cb4-8c02-917a8a69c89d.png)

<img width="960" alt="image" src="https://user-images.githubusercontent.com/22928255/210461257-6432c792-b6ff-4872-8779-cc83217b2a87.png">

* Percetage of helpful votes to total votes should be greater than or equal to  50%.

<img width="960" alt="image" src="https://user-images.githubusercontent.com/22928255/210461598-2d692504-e44f-447f-a42a-67e3a4d60558.png">

![image](https://user-images.githubusercontent.com/22928255/210462346-94c24a1c-4717-4855-913a-be56b551aec6.png)

After the ETL process we have `50,753` reviews for `VINE` or `NON VINE` members. 


### 1. Vine and non Vine reviews

From the total reviews `50,753` , we have `1,080` `VINE` reviews which is approx 2% and 98% are `NON VINE` reviews.

<img width="212" alt="image" src="https://user-images.githubusercontent.com/22928255/210462806-caea18ac-2b2b-48fd-8398-c25a426a0b1e.png">

![image](https://user-images.githubusercontent.com/22928255/210463201-df0920fc-8325-4ab6-9d02-290c061068cd.png)

<img width="960" alt="image" src="https://user-images.githubusercontent.com/22928255/210463048-3a02f259-2098-4891-9905-3cf79ff11957.png">

<img width="960" alt="image" src="https://user-images.githubusercontent.com/22928255/210463078-6cacdd74-93b8-447e-bfe7-6e1afed90437.png">


### 2. 5 Start reviews 

<img width="358" alt="image" src="https://user-images.githubusercontent.com/22928255/210463511-2f78a20c-a741-46f7-9d9b-9355c4aaefaa.png">
* Vine members gave `454` out of `1,080` reviews a 5 star rating.
* Non-Vine members gave `23,034` out of `49,659` reviews a 5 star rating.

### 3. Percentage of 5 Start reviews 

<img width="576" alt="image" src="https://user-images.githubusercontent.com/22928255/210463532-1467a04c-6f0f-4c8f-af1b-8484b323debd.png">

* 42% Vine members gave 5 star. 
* 46.4% non vine members gave 5 star.

## Summary 

After analysising the result , we observed that the VINE members are not biased while reviewing the products for their 5 star rating. The VINE members provide the true rating and more critic on the product reviewing. NON Vine members are little higher percentage for their reviwing of 5 star electronic product.  In this product list we only consider the 50% , we can get the correct pattern by including more data and predict the VINE members star rating. 

To get the actual behavior on these VINE users we should consider the more product category and plot the pattern to understand the VINE members rating system. 


