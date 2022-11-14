# Customers-Segmentation-Using-RFM
Customers Segmentation Using RFM analysis (Recency, Frequency and Monetary) with Data Orders
Data orders is a company that sells good that can be ordered by customers in large quantities at once

[![forthebadge made-with-python](http://ForTheBadge.com/images/badges/made-with-python.svg)](https://www.python.org/)

[![Made withJupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?style=for-the-badge&logo=Jupyter)](https://jupyter.org/try)

[![Ask Me Anything !](https://img.shields.io/badge/Ask%20me-anything-1abc9c.svg)](https://GitHub.com/Naereen/ama)

# Use Case

* **Use Case Summary**


* **Objective Statement** :

    * Get business insight about how many customers
    * Get business insight about the average, maximum and minimum amount by the customer 
    * Get business insight about how many orders by year
    * Get business insight for each customers based on labeled defined such as Loyal Customer, Big Spanders, Best Customers, Lost Cheap Customers and Almost Lost
    * Build models using RFM to learn customer segmentation  
    
    
* **Challanges** :
    * Large size of data, can not maintain by excel spreadsheet
    * Change the data type of column which doesn't match
    * Display data every year
    * Make a definition of each segment obtained
    * Don't know the location of retail data


* **Methodology / Analytic Technique** :
    * Descriptive analysis
        * Describe the information such as, min/max value of each column, average, and the total count of data contained in grand_total column.
    * Graph analysis
        * View data changes by time (Year)
    * Using Modelling Segementation 
        * RFM Model


* **Business Benefit**:

    * Gain insight to treat and keep customers based on segment
    * Gain insight to improve the quality of company services so that customers remain loyal and gain more profit for the company
    * Build models using RFM to know customer segement


* **Expected Outcome**:

    * Know how many customer?
    * Know how about the average, maximum and minimum amount issued by the customer?
    * Know how many orders by year
    * know how behavior customers based on labeled defined such as Loyal Customer, Big Spanders, Best Customers, Lost Cheap Customers and Almost Lost
    * Know how to build model using RFM

# Business Understanding
* Data orders is a company that sells good that can be ordered by customers in large quantities at once
- This case has some business question using the data:
    * How many customer?
    * How about the average, maximum and minimum amount issued by the customer?
    * How many orders by year?
    * How behavior customers based on labeled defined such as Loyal Customer, Big Spanders, Best Customers, Lost Cheap Customers and Almost Lost?
    * How to build model using RFM modelling?
    
# Data Understanding


* **Source Data**:
    * The dataset used is data from https://www.kaggle.com/datasets/siddinho/sample-orders-dataset-retail
    * Data start from January 4 2011 - Desember 31 2014
    * The raw data contains 5009 rows and 4 columns.


* **Data Dictionary** :
    * order_date : date of ordering items by customer
    * order_id : the transaction id of ordering items by the customer
    * customer: the name of the customer who made the purchase
    * grand_total : total price paid by customer
    
# Data Preparation

* **Code use**:
    * Python 3.9.13
    * Package: Pandas, Numpy, Matplotlib, Seaborn, Scipy, Sklearn, and Warning 
    
# Data Cleansing
   * Change data type from order of object to datetime
   * Retrieve data only month and year only

# Exploratory Data Analysis

* **How many customers?**

![1 how many customers](https://user-images.githubusercontent.com/101789879/201461567-5cceef7b-effb-4b34-906d-5f86d4944896.jpg)

from here it can be seen, **total customers are 793**. The number of Order_id turns out to be not the same as the number of Customers, so there are **some Order_ids that have the same Customers**. This shows that there are customers who **repeat orders** or do not only shop once at the company. **order_date** shows that there are several **transactions on the same day**

* **Average, maximum and minimum amount by the customer?**

![2 average min max and more spend customers](https://user-images.githubusercontent.com/101789879/201461631-82d55ef0-e46b-47ef-9aa6-11c91d4b7ec1.jpg)

Based on the data above, it is known that **on average** customers make product purchases with a total price of **458.626672**, the customer with the lowest purchase is rated **1** and the highest purchase is rated **23661**

**number 1** may get **high discount** for example black friday sale promo, and **23661** the possibility of buying items that are considered quite **expensive**

* **Timebound**

![3 time start end](https://user-images.githubusercontent.com/101789879/201461711-24b5a987-551f-4780-9940-bb26c24cbd45.jpg)

From here that we know date **started from January 4, 2011**. terminated **until December 31, 2014**.

* **Orders by Month**

![4 orders by mounth](https://user-images.githubusercontent.com/101789879/201461765-41be7316-3e76-4971-abcf-8428727f9d55.jpg)

* **Orders in 2011**

![5 orders in 2011](https://user-images.githubusercontent.com/101789879/201461806-1fbaa5ab-34f4-4ca6-93d3-b7a4f12b4eed.jpg)

The number of items purchased tends to **increase every mounth**. In **October** sales **declined sharply** but **increased** in the following month, even exceeding sales in September because normally In most countries in the Northern Hemisphere, **September is the time for students to start new school year at school**. **November's sales are high** because there are usually lots of **Black Friday** promotions. Meanwhile, sales in **December** experienced a **decline again**.

* **Orders in 2012**

![6 orders in 2012](https://user-images.githubusercontent.com/101789879/201461869-f7ccde7d-28f5-41b6-b456-bd2af4cd97e6.jpg)

The number of items purchased tends to **increase** every month, in **February to March** there is a sharp increase of up to **2 times**. In **September** there was **a sharp increase**. However, in the following month, **October, there was a sharp decline** because in that month, **started the new school year**. in **November** there was a high increase even higher than September and again **increased** because of **Black Friday**, and sales in **December** fell again

* **Orders in 2013**

![7 orders in 2013](https://user-images.githubusercontent.com/101789879/201461919-d3ffcb93-8a4c-415d-8600-f034953ceb3e.jpg)

The number of items purchased tends to **increase** every month, in **February to March** there is a fairly sharp increase to **almost 2 times**. In the month of **September** there was **a sharp increase** because many parents bought school supplies for their children. However, in the following month, **October, there was a sharp decline** due to **new school year**. However, in **November** there was a **high** increase in the number of items purchased because **Black Fiday** promos usually occur and again **slightly decreased** sales in **December**.

* **Orders in 2014**

![8 orders in 2014](https://user-images.githubusercontent.com/101789879/201461953-fb78513b-10b0-4932-937c-b73a51dfbe81.jpg)

The number of items purchased tends to **increase** every month, in **February to March** there is a fairly sharp increase to **almost 2 times**. In September there is a sharp increase in the new school year. However, in the following month, **October, there was a sharp decline**. However, in November **November there was a high increase** in the number of items purchased even **higher than September** due to Black Friday and again **slightly decreased** sales in **December**


* **Total orders by Years**

![9 total orders by year](https://user-images.githubusercontent.com/101789879/201462045-cd672d4b-7773-464c-995b-b5d76590f165.jpg)

In the barchart above, you can see how much the order increases each year. In **2011** with a grand total of **484260** with a value of **percentage of 21%**. In **2012** with a grand total of **470539** with a percentage value of 20%. In 2013 with a grand total of 608477 with a percentage value of 26%. and in 2014 with a grand total of 733985 with a percentage value of 32%.

# Modelling with RFM (Recency, Frequency, Monetary Value)

* **RFM Model Definition**

Recency, frequency, monetary value (RFM) is a model used in marketing analysis that segments a company's consumer base by their purchasing patterns or habits. In particular, it evaluates customers' recency (how long ago they made a purchase), frequency (how often they make purchases), and monetary value (how much money they spend).

* **Modeling Result - RFM Quantile**

![1 model RFM result](https://user-images.githubusercontent.com/101789879/201462147-d9653b69-8d5d-45a0-b74a-5e87ff277609.jpg)

**the bigger the number in R_quartile**, then it proves that the customer is **the longer they haven't shopped**. while **the smaller the number in the R_quartile**, it proves that the customer **the more recently shopped**.

From this example, it can be seen, Aaron Bergman last shopped **415 days ago**, because it's been a while, he got an R_quartile 4, while Aaron Hawkins last shopped **12 days ago**, he got an R_quartile 1 .

**the bigger the number in F_quartile**, then it proves that the customer is **the less frequency he shopped**. while **the smaller the number in F_quartile**, it proves that the customer **the more frequency he shopped**.

Likewise for **M_quartile**, **the bigger the number in M_quartile**, then it proves that the customer is **the smaller the amount spent**. while **the smaller the number in M_quartile**, it proves that the customer **the more amount he spends for shopping**.

* **Modeling Result - Customer Segment Lable Result**

![2 customers label result](https://user-images.githubusercontent.com/101789879/201462233-ce09ba0d-b326-42cf-8080-891d0b5a973a.jpg)

There are 7 customer segmentation based on RFM : Loyal Customers, Big Spenders, Lost Cheap Customers, Lost Customers, Best Customers, Almost Lost, and Others

  * A total of **16.27%** of the total customers (with a total of 129 customers) are included in **Loyal Customers** where this segment's customers have the most shopping frequency than other segments.
  * Furthermore, **15.76%** of the total customers (with a total of 125 customers) in the company entered the **Big Spenders** segment. This segment has the highest total purchases than any other segment.
  * **Lost Cheap Customers** segment consists of 67 customers with a percentage of **8.44%** of the total customers. Customers who enter this type of segment tend to churn because they have not bought goods from the company for a long time, have the least frequency of shopping, and have the least total purchases compared to other segments.
  * Then as much as **3.9% of** total customers (with a total of 31 customers) are classified as **Lost Customers** which is almost the same as customers in the Lost Cheap Customers segment, Lost Customers tend to churn.
  * A total of 30 customers with a percentage of **3.78%** of the total customers, entered the **Best Customer** segment. Customers in this segment have recently purchased goods from the company, have the most shopping frequency, and have the most total purchases than other segments.
  * Then **0.25%** of the total customers (with a total of 2 customers) are customers who enter the **Almost Lost** segment. Customers in the Almost Lost segment have recently purchased goods from the company, but have quite a bit of shopping frequency, and the lowest total purchases compared to other segments.
  
# Result 

* The **total of customers is 793**. The number of Order_id turns out to be not the same as the number of Customers, so there are **some Order_ids that have the same Customers**. This shows that there are customers who **repeat orders** or do not only shop once at the company. **order_date** shows that there are several **transactions on the same day**

* **The average** purchasing amount from the customers is **458.626672**, while the **lowest** purchasing amount was rated **1** and the **highest** purchase was rated **23661**.

* We start the analysis in **2011**, the number of items purchased tends to **increase every month**. In **October** sales **declined sharply**, then **increased** in the following month, even exceeding sales in September because normally In most countries in the Northern Hemisphere, **September is the time for students to start the new school year at school**. **November's sales are high** because there are usually lots of **Black Friday** promotions. Meanwhile, sales in **December** experienced a **decline again**.
   
* Next to **2012**, same as 2011 the transaction tends to **increase** every month, from the EDA in **February to March** there is a fairly sharp increase of customer purchases up to **2 times**. After that, in **September** there was **a sharp increase**. However, in the following month, **October, there was a sharp decline** because, in that month, the consumer price index (CPI) was raised. in **November** there was a high increase even higher than in September and again **increased** because of **Black Friday**, and sales in **December** fell again


* Similarly in **2013**, the number of items purchased tends to **increase** every month, for the **February to March** there is a fairly sharp increase to **almost 2 times**. In the month of **September**, there was **a sharp increase** probably because many parents bought school supplies for their children. However, in the following month, **October, there was a sharp decline** due to the raise of the consumer price index (CPI) based on the Bureau of Labor Statistics (BLS). However, in **November** there was a **significant** increase in the number of items purchased because **Black Friday** promos usually occur and again **slightly decreased** sales in **December**.


* Lastly for **2014**, the number of items purchased tends to **increase** every month, in **February to March** there is a sharp increase to **almost 2 times**. In September there is a sharp increase in the new school year. In the following month, based on BLS the CPI was an increase, so that **October, there was a sharp decline**. However, in November **November there was a high increase** in the number of items purchased even **higher than in September** due to Black Friday and again **slightly decreased** sales in **December**


* Based on **results of modeling** customer segmentation **using RFM**, the company's customers are divided into 7 segments, namely **Best Customers, Loyal Customers, Big Spenders, Lost Cheap Customers, and Almost Lost**.

* A total of 30 customers with a percentage of **3.78% of the total customers**, entered the **Best Customer** segment. Customers in this segment have recently purchased goods from the company, have the most shopping frequency, and have the most total purchases than other segments.A total of **16.27% of the total customers** (with a total of 129 of 793  customers) are included in **Loyal Customers** where this segment's customers have the most shopping frequency than other segments. Furthermore, **15.76% of the total customers** (with a total of 125 of 793 customers) in the company entered the **Big Spenders** segment. This segment has the highest total purchases than any other segment.

* Another segment is the **Lost Cheap Customers** segment which consists of 67 of 793 customers with a percentage of **8.44% of the total customers**. This type of customer segment highly tends to churn because they have not bought goods from the company for a long time, have the least frequency of shopping, and have the least total purchases compared to other segments. Then as much as **3.9% of total customers** (with a total of 31 of 793 customers) are classified as **Lost Customers** which is almost the same as customers in the Lost Cheap Customers segment, Lost Customers tend to churn. Then **0.25% of the total customers** (with a total of 2 of 793 customers) are customers which are categorized as the **Almost Lost** segment. Customers in this segment have recently purchased goods from the company, but have quite a bit of shopping frequency, and the lowest total purchases compared to other segments.

* Lastly, other customers are classified into **Others** segment, where this segment is a mixed segment (in this case **undefined segment**).

# Recomendation

• Recommendations for increased orders in a particular month such as September and November: focus on *increasing the amount of supply* of goods to compensate the high demand. Then for a decrease orders in a given month such as October, the marketing team can focus on improving the company promotion strategy. The company could also suppress the goods price as competitive as the company can or even slightly below the market price.

• The following are the Recommendation for each customer segment. For the **"Best Customers"** segment, the company can focus on the reward for this type of customer, such as *posting their picture* in the store as the "Best Customer" and granting the reward for them. The reason is the best customer tends to do repeat orders as usually they did. In addition, we also need to take into account whenever the best customer transaction behavior change in term of a decrease of purchase. The company can raise their profit from implementing cross and up selling technique to the customer.

• Next to **"Loyal Customers"** segment, the company must *optimize services for the loyal customer* in order to maintain their loyalty and increase their value. The company should increase its engagement with the loyal customer, such as remembering their name and asking for feedback through interview sessions and grant a reward for that. 

• For the **"Big Spenders"** segment, the business team should focus on doing *research on which products match the big spender customer interests or products that they are buying most*. From that, the company can offer special membership, so that they will do repeat orders even though not so often. On the other hand, the company can also *offer products with brand new high specifications or top-level products* and also apply cross and up selling technique to them. Lastly, the big spender customers should be given good service, such as giving a special offering for the new and exclusive product from their favorite media platform.

• The next recommendation is for the **"Almost Lost"** segment. Since this customer segment is recently purchased, the company can *offer a high discount or promo* based on their last purchase interest group. This, hopefully, can intrigue them to purchase again from this company. The offering could be *delivered by the cashier employee with some brochures or vouchers*.

• Lastly for the **"Lost Cheap Customers"** and the **"Lost Customer”** segment. The company should *do some research on this customer’s background*. While probably the store distance from their houses is quite far, then the company can implement *delivery services or online shopping services*. Those strategies will not only affect the lost customer but also the other segment of customers. Because we are providing an easier way to purchasing goods.

