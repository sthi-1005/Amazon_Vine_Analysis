# Amazon_Vine_Analysis

## Project Overview
The project will provide two deliverables for Amazon Product Review Datasets:
- **Deliverable 1**: ETL on Product Review Datasets provided by Amazon.
  - Amazon S3, Amazon RDS and pgAdmin will be used.
  - The data in pgAdmin will be seperated into the client's requested table sets
- **Deliverable 2**: Analyze the reviews to determine if there is any prositivity bias in reviews participating in Amazon's Vine Review Program
  - Technologies used: Google COLAB, PySpark

### Additional Information:
- Amazon Vine Program: is a paid review program by Amazon to ensure quality reviews for products on their platform. It is an exclusive program only offered to users who meet Amazon's criterion, and the reviewers are also paid by Amazon. More information can be found here: https://www.amazon.com/gp/vine/help
- Dataset Source: https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt

## Deliverable 1: ETL Script

[Amazon_Reviews_ETL.ipynb](https://github.com/sthi-1005/Amazon_Vine_Analysis/blob/5c5c3a32d69a29adf51669897f6eff3f5f457d16/Amazon_Reviews_ETL.ipynb)</br>
The original data and columns were transformed and loaded into the following table (and columns)

|Original Table|Customer Table|Product Table|Review_ID Table|Vine Table|
|---|---|---|---|---|
|marketplace|customer_id|product_id|review_id|review_id|
|customer_id|customer_count|product_title|customer_id|star_rating|
|review_id|||product_id|helpful_votes|
product_id|||product_parent|total_votes|
|product_parent|||review_date|vine|
|product_title|||verified_purchase|
|product_category|
|star_rating|
|helpful_votes|
|total_votes|
|vine|
|verified_purchase|
|review_headline|    
|review_body|
|review_date|

## Deliverable 2
- Dataset Used: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Watches_v1_00.tsv.gz
- Link to script: [Vine_Review_Analysis.ipynb](https://github.com/sthi-1005/Amazon_Vine_Analysis/blob/ba52b53ef5852e7278572db22bfaffb436d2d7c7/Vine_Review_Analysis.ipynb)
### Key Results
![image](https://user-images.githubusercontent.com/79720695/128638473-f9d69e05-5c0f-4858-baf5-8c076b1abe45.png)
<br>Observations:
- The sample size of Vine (Paid) reviews is much smaller than non-Vine (Unpaid) reviews
- The ratio of 5 Star Reviews to Total Reviews per item is: 31.2% (Paid) and 51.8 (Unpaid)
Interpretation:
- Definitive conclusions should not be made using this dataset as the sample size of 47 Paid Reviews is not sufficiently large
- However, from the above dataset, there is no positivity bias observed. In fact, bias looks to skew the other way.
- One possible explanation is that the Vine program eliminates bot/fake 5 star reviews undetected from Amazon's standard approach

### Additional Recommendations
The client is recommended to invest additional resources to allow the analytics team to perform the same analysis on atleast a handful of more datasets with the main objective to capture more Vine (Paid) reviews.
