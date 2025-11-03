
# **Retail Analytics Dashboard — Power BI**

## 📘 **Project Overview**

This repository contains the **Retail Analytics Dashboard** built in **Power BI**.  
The project focuses on analyzing retail sales performance using key metrics such as total sales, category performance, and regional sales trends.  
It was created to demonstrate data cleaning, data modeling, and interactive visualization skills using a realistic retail dataset.

---

## 🗂️ **Dataset**

* **Source:** Custom SQL dataset (Products, Customers, Sales)
* **Format:** SQL / Excel
* **Description:**  
  Contains detailed retail transactions including product information, customer demographics, and regional sales.

**Tables Included:**
- **products:** product details like category and price  
- **customers:** customer demographics such as gender, age, and city  
- **sales:** transactional data including quantity sold, sales amount, date, and region  

---

---

## 🎯 **Dashboard Features**

* **KPIs:**
  - Total Sales Amount  
  - Total Quantity Sold  
  - Average Sales per Customer  
  - Number of Orders  

* **Visuals:**
  - Sales by **Category**, **Region**, and **Date**
  - **Top Products** and **Top Customers**
  - **Monthly Sales Trend**
  - **Category-Wise Revenue Distribution**

* **Slicers:**
  - Region  
  - Category  
  - Year/Month  

---

## 🧹 **Data Cleaning (Power Query Steps)**

1. Removed null or duplicate records  
2. Verified and corrected data types:  
   * Date → Date  
   * Quantity, Price, Sales Amount → Decimal  
3. Removed negative or invalid values (e.g., age < 0)  
4. Merged `sales`, `products`, and `customers` tables using keys  
5. Created calculated columns:
   * `Total_Sales_Amount = [Quantity_Sold] * [Price]`  
   * `Order_Year = YEAR([Sale_Date])`  
   * `Month_Name = FORMAT([Sale_Date], "MMM")`

---

## ⚙️ **DAX Measures Used**

```dax
Total Sales = SUM('Sales'[Sale_Amount])
Total Quantity = SUM('Sales'[Quantity_Sold])
Average Order Value = DIVIDE([Total Sales], [Total Quantity])
Orders Count = COUNTROWS('Sales')
Sales LY = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Sales'[Sale_Date]))

ashboard preview

(![Sales Dashboard](https://github.com/sanjanagawh9443/PowerBI-Sales-Dashboard-Superstore/blob/main/Sales%20Overview%20Dashboard.png)

---

## 👩‍💻 **Contributor**

**Sanjana Gawhande**
