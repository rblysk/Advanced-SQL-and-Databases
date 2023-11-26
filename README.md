# Advanced-SQL-and-Databases

**INTRODUCTION TO DATA ANALYTICS, SQL GRADED TASK**


**In this graded task you will be asked to create queries to solve specific business questions.**

You will have to explore Adventureworks 2005 database, identify the needed data and the correct way to get it/merge it together with other tables within this database.

The database can be accessed here using the BigQuery account provided to you by Turing College via email.

-----

**TIPS:**

Use schema for guidance when exploring tables and pay attention to the primary & foreign key when writing joins.
If the query is running slower during reruns, limit the scope of output while writing & experimenting. After the query is done then increase the scope to the intended one.
Use Google to find functions and solutions you may need to solve these tasks, experimentation & curiosity is key in succeeding as a junior data analyst.
**There is no one right way to get the correct result.**

-----

**To complete this task you need to create a results Google spreadsheet.**

For each section of task you are required to copy your query result in one sheet and the written query in another sheet.
For example, when you solve 1.1, add sheet “1.1 result” and “1.1 query” and so forth.
If you are not able to get the right result, copy in your effort/ideas, we take into account effort.
During the correction, have the BigQuery GCP open, as you may be asked to run your queries and/or show data validation using BigQuery.

-----

**TASKS:**

**1.1** You’ve been tasked to create a detailed overview of all individual customers

(these are defined by customerType = ‘I’ and/or stored in an individual table).

**Write a query that provides:**

**Identity information:** CustomerId, Firstname, Last Name, FullName (First Name & Last Name).

**An Extra column called addressing_title** i.e. (Mr. Achong), if the title is missing - Dear Achong.

**Contact information:** Email, phone, account number, CustomerType.

**Location information:** City, State & Country, address.

**Sales:** number of orders, total amount (with Tax), date of the last order.

Copy only the top 200 rows from your written select ordered by total amount (with tax).

-----

**1.2** Business finds the original query valuable to analyze customers and now want to get the data from the first query for the top 200 customers with the highest total amount (with tax) who have not ordered for the last 365 days. 

**How would you identify this segment?**

**Hints:**

You can use temp table, cte and/or subquery of the 1.1 select.

Note that the database is old and the current date should be defined by finding the latest order date in the orders table.

-----

**1.3** Enrich your original 1.1 SELECT by creating a new column in the view that marks active & inactive customers based on whether they have ordered anything during the last 365 days.

Copy only the top 500 rows from your written select ordered by CustomerId desc.

-----

**1.4** Business would like to extract data on all active customers from North America. 

Only customers that have either ordered 2500 in total amount (with Tax) or ordered 5 + times should be presented.

In the output for these customers divide their address line into two columns, i.e.:

**AddressLine1	--  address_no  --	Address_st**

**'8603 Elmhurst Lane' --	8603 --	Elmhurst Lane**

**Order the output** by country, state and date_last_order.

-----

**2. Reporting Sales’ numbers**

**Main tables to start from: salesorderheader.**

-----


**2.1** Create a query of monthly sales numbers in each Country & region. 

Include in the query a number of orders, customers and sales persons in each month with a total amount with tax earned. 

Sales numbers from all types of customers are required.

-----

**2.2** Enrich 2.1 query with the cumulative_sum of the total amount with tax earned per country & region.

**Hint:** use CTE or subquery.

-----

**2.3** Enrich 2.2 query by adding ‘sales_rank’ column that ranks rows from best to worst for each country based on total amount with tax earned each month. 

**I.e.** the month where the (US, Southwest) region made the highest total amount with tax earned will be ranked 1 for that region and vice versa.

-----

**2.4** Enrich 2.3 query by adding taxes on a country level:

As taxes can vary in country based on province, the needed column is ‘mean_tax_rate’ -> average tax rate in a country.

Also, as not all regions have data on taxes, you also want to be transparent and show the ‘perc_provinces_w_tax’ **->** a column representing the percentage of provinces with available tax rates for each country

(**i.e.** If US has 53 provinces, and 10 of them have tax rates, then for US it should show 0,19)

-----

**THE PROJECT:** 

https://docs.google.com/spreadsheets/d/1VO5ZhDyntGFneWDdL7pXQg8aapZrOylfSCJDUtflKQg/edit#gid=1543186499
