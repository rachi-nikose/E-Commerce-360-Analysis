# E-Commerce 360 Analysis
![Screenshot 2023-10-04 203357](https://github.com/Fardin-Data/E-Commerce-360-Analysis/assets/137788371/f53aa2ea-0dd9-4c3d-8f7b-f5ae18e279d4)


## Project Overview
The goal is to provide a 360-degree view of operations, uncovering critical information that can drive strategic decisions. By the end of this journey, the aim is not only to understand the business better but also to provide recommendations that can drive growth and success.

## Problem Statement
A two-year-old e-commerce company has experienced notable growth and is now seeking a data-driven approach to understand its current business landscape. The company aims to chart a strategic path forward, leveraging data insights to sustain and enhance its growth trajectory. Recommendations are sought to guide future actions, ensuring continued expansion and sustained success in the e-commerce industry.

## Process
`Database Creation`

- Using the provided script, a database was established with a defined structure, incorporating tables and their respective columns, each with associated values.
<pre><code>
  CREATE TABLE Customers(
    CustomerID bigint,
    FirstName varchar(30),
    LastName varchar(30),
    Date_of_Birth datetime,
    City varchar(30),
    State varchar(30),
    Country varchar(30),
    PostalCode bigint,
    Phone bigint,
    Email varchar(30),
    DateEntered datetime
  );
</code></pre>

`Exploration`

- After the database setup, the data within it was explored to become familiar with the tables and columns. This step helped understand the data and its structure.

`Analysis`

With an understanding of the database, the data was analyzed. This analysis involved defining the project's end goals and objectives, determining the insights or information to extract from the data, and planning how to achieve those objectives.
<pre><code>
  #Total inactive customers:
  SELECT COUNT(customerid) as Inactive_Customers 
  FROM (
      SELECT customerid, MAX(orderdate) as Last_order 
      FROM orders 
      GROUP BY customerid
      HAVING MAX(orderdate) < DATE_SUB((SELECT MAX(orderdate) FROM orders), INTERVAL 6 MONTH)
  ) as subquery;
</code></pre>

`Export to CSV`

The results of SQL queries (Data Query Language or DQL) were exported into CSV files. This step allowed working with the data in Power BI.

`Power Query Editor` 

Upon importing the CSV files into Power BI, the Power Query Editor was used to perform some data transformations. Specifically, the first row was specified as the header to ensure Power Query recognized the correct data types.

`DAX Measures`

Minor measures were created using Data Analysis Expressions (DAX). DAX is a formula language used in Power BI to create custom calculations, aggregations, and metrics.

`Report Creation`

Using the transformed data from Power Query Editor, a multifaceted Power BI report was created. This report is designed to provide a 360-degree view of the business based on the data from the database

## Report Previews
### Structure:
The Power BI report comprises five key sheets, each providing unique insights into our business operations:
1. **Introduction Page:** This page serves as a navigation hub with bookmark links to other sheets within the report.
2. **Sales View:** Insights and analysis related to our sales data, including performance trends and key metrics.
3. **Customer View:** A detailed examination of customer behavior and engagement, offering insights into customer preferences and demographics.
4. **Payments View:** Analysis of payment methods used by customers, with a focus on optimizing transaction processes.
5. **Suppliers View:** Evaluation of supplier relationships, including performance, reliability, and opportunities for improvement.
6. **Shipping View:** Insights into our shipping processes, ensuring efficient delivery and customer satisfaction.

Feel free to explore each sheet for a deeper understanding of business analytics.

<div style="display: flex; flex-wrap: nowrap; overflow-x: auto; gap: 10px;">
  <img src="https://github.com/Fardin-Data/E-Commerce-360-Analysis/assets/137788371/1ee38292-04e0-4c74-a422-b35ffe97aa0a" alt="Screenshot 1" style="width: 400px;">
  <img src="https://github.com/Fardin-Data/E-Commerce-360-Analysis/assets/137788371/356b7dcc-d27f-421f-acd8-3bc01f24129b" alt="Screenshot 2" style="width: 400px;">
  <img src="https://github.com/Fardin-Data/E-Commerce-360-Analysis/assets/137788371/f5cc6df4-8203-4384-bf7d-fee3416f7b85" alt="Screenshot 3" style="width: 400px;">
  <img src="https://github.com/Fardin-Data/E-Commerce-360-Analysis/assets/137788371/204fc0b5-c1ba-4bc2-a21c-3fd6953908e0" alt="Screenshot 4" style="width: 400px;">
  <img src="https://github.com/Fardin-Data/E-Commerce-360-Analysis/assets/137788371/2abf8927-8306-4618-b94a-790d2327ea1a" alt="Screenshot 5" style="width: 400px;">
  <img src="https://github.com/Fardin-Data/E-Commerce-360-Analysis/assets/137788371/64babf18-42b9-4002-b747-dfbf7551fd07" alt="Screenshot 6" style="width: 400px;">
</div>


## Insights
- Our most successful category is "Beauty & Hygiene," closely followed by "Kitchen, Garden & Pets." These findings reveal a clear customer preference, and focusing on these categories will drive our business growth.
- The majority of our customers hail from the United States and India. Notably, the United States and India lead in terms of sales, underscoring their significant market potential.
- Our customer base primarily comprises adults and older individuals. This demographic alignment correlates with our top categories, which revolve around home and personal care.
- Upon analyzing the data, I identified a consistent trend: New customer additions peak at the beginning of the year but gradually decline as the year progresses.
- A substantial portion of our customers prefers online payments, with roughly 50% opting for credit card transactions.


## Recommendations
- Invest in improving product offerings within the top-selling categories of "Beauty and Hygiene" and "Kitchen, Garden & Pets" to cater to customer preferences effectively.
- Continuously gather customer feedback and reviews to understand their evolving needs and preferences. Tailor promotions and product offerings accordingly to maintain interest.
- While continuing to serve our strong customer base in the United States and India, explore strategies to expand our presence in other regions to ensure business diversification.
- Launch targeted marketing campaigns to attract and engage younger customers, introducing them to our product range and services.
- Develop and launch targeted promotional strategies during periods of declining customer additions. Offer special promotions, discounts, and bundled deals to entice both new and existing customers. Timely and compelling offers can rekindle interest in our products.
- To align with customer preferences and boost orders, I recommend activating “Pay Later.” This flexible payment option allows customers to place orders without immediate payment, enhancing their shopping experience and encouraging more orders.


## Limitation and Challenges
`Limited Data`

 The challenge of working with a relatively new business with a limited dataset made it difficult to identify trends accurately.


`Effective Presentation` 

Presenting the findings in the most suitable and effective manner required careful consideration.


`Strategic Recommendations`

Despite a strong understanding of the business, crafting actionable suggestions for business growth demanded thoughtful analysis.


## Learnings
`Data Organization`

Despite the limited dataset, the data's organization and informativeness became evident during this analysis.


`Data Visualization`

Overcoming the challenge of presenting outcomes was achieved through applying knowledge of data visualization techniques and learning new methods.


`Strategic Insights`

Leveraging my profound business understanding and investing time in strategic thinking led to valuable insights, connecting important dots within the data.


## Files Information
`Data`

- **E-Commerce Database Script:** Within this file, you will find all the queries used to create and populate the database.

`SQL`

- **Analysis Queries:** This file contains all the SQL queries written for data analysis purposes.

`Results`

- **Overview Report:** The Power BI report includes five key sheets, each offering distinct insights into our business operations.
  

## Tech Stack
- `MySQL` Utilized for data analysis and querying.
- `Power BI` Leveraged to create comprehensive reports and visualizations.
- `DAX (Data Analysis Expressions)` Applied for creating additional necessary measures and calculations.
- `Power Query` Employed for minor data adjustments and transformations.


Enjoy exploring the project!
