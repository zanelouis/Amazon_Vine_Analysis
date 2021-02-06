# Amazon_Vine_Analysis

## Overview
An Amazon RDS used as our server for a Postgres Database that is used to create data analyzations. Google Colab and pySpark are used to extract and transform datasets from Amazon Review Sources and load into pgAdmin tables to calculate different metrics.

## Resources
Data Source: [Amazon Review datasets](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt), [Music Review dataset](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Music_v1_00.tsv.gz)

Software: Google Colab Notebook, PostgreSQL 11.9, pgAdmin 4, AWS

## Results
In our Amazon_Reviews_ETL notebook, multiple tables were created to reflect: review, customers, products, review id and vine DataFrames. We cleaned up the product table to drop any duplicates, change the format of review date in review id table and created and renamed a customer count column in our customer table.

In our Vine_Review_Analysis notebook, multiple tables were created to filter the vine DataFrame in the Amazon_Reviews_ETL notebook to calculate the percentage of 5-star ratings reviews with total votes greater than or equal to 20 and helpful votes divided by total votes are greater than or equal to 50%, grouped by being paid ("vine" == "Y) and unpaid reviews.

- 7 total paid reviews
- 105,979 total unpaid reviews
- 0 total 5-star paid reviews
- 67,580 total 5-star unpaid reviews
- 0% of paid 5-star reviews
- 64% of unpaid 5-star reviews

## Summary
To summarize, there is a higher chance of 5-star reviews from unpaid reviewers in the music industry based on the music Vine dataset Amazon provides and about zero chance for paid reviews.

![Screenshot 2021-02-05 182942](https://user-images.githubusercontent.com/71358697/107106588-3afe9f00-67e1-11eb-9654-dd7e361bf413.png)
