# E-Commerce Analyst Big Data Engineering Project

## Overview
This project aimed to build a robust **ETL pipeline** for analyzing the Brazilian E-commerce dataset provided by Olist (available on Kaggle). It involved **data ingestion, transformation, storage, and orchestration** using **Azure Synapse Analytics, Databricks, and Data Lake Storage Gen2**. The final goal was to enable efficient querying and data analysis through a well-structured **data pipeline architecture**.

## Data Sources
The project ingested data from multiple sources:
- **Olist E-commerce Dataset (Kaggle)** (CSV files):
  - `olist_customers_dataset.csv`
  - `olist_geolocation_dataset.csv`
  - `olist_order_items_dataset.csv`
  - `olist_order_payments_dataset.csv`
  - `olist_order_reviews_dataset.csv`
  - `olist_orders_dataset.csv`
  - `olist_products_dataset.csv`
  - `olist_sellers_dataset.csv`
  - `product_category_name_translation.csv`
- **SQL Database (Files.io):** Hosted `olist_order_payments_dataset.csv`.
- **HTTP (GitHub):** Hosted seven CSV files.
- **MongoDB (Files.io):** Hosted `product_category_name_translation.csv`.

## ETL Pipeline - Data Processing Steps
### **1. Data Ingestion (Azure Data Factory)**
- **SQL Data:** Extracted from a pre-processed SQL database and loaded into ADLS Gen2 (Bronze Layer) using **ADF pipelines**.
- **HTTP Data (GitHub):** Ingested using a **parameterized ADF pipeline** that dynamically generated URLs.
- **MongoDB Data:** Extracted using **Spark connectors** in Databricks.
- All data landed in the **Bronze Layer** of **Azure Data Lake Storage Gen2** following the **Medallion Architecture**.

### **2. Data Transformation & Cleaning (Azure Databricks)**
- Connected Databricks to **ADLS Gen2 and MongoDB**.
- Performed data cleaning operations:
  - Removed **duplicates** and **null values**.
  - **Integrated datasets** using primary key relationships.
- Conducted **exploratory data analysis (EDA)** using **Databricks visualizations**.
- Stored the cleaned and transformed data in the **Silver Layer** (Parquet format) for optimized querying.

### **3. Data Serving (Azure Synapse Analytics)**
- **External tables** were created in **Azure Synapse Analytics** to access **Silver Layer** data.
- Defined a **Gold schema** in Synapse for optimized querying.
- Created **views and external tables** over Parquet files in the **Gold Layer**.
- Enabled **SQL-based analytics** for data analysts and scientists.

## **Technologies Used**
- **Azure Data Factory (ADF)** – ETL Orchestration
- **Azure Data Lake Storage Gen2 (ADLS Gen2)** – Data Warehousing
- **Azure Databricks (Apache Spark)** – Data Processing & Transformation
- **Azure Synapse Analytics** – Query & Analytics Engine
- **Google Colab & Pandas** – Data Pre-processing
- **MongoDB (Files.io)** – NoSQL Data Source
- **GitHub & Files.io** – Data Hosting & Storage

## **Data Pipeline Architecture**
The project followed a **Medallion Architecture** with structured data flow:
- **Bronze Layer:** Raw Data Storage (Landing Zone)
- **Silver Layer:** Cleaned & Transformed Data
- **Gold Layer:** Optimized Data for Analysis

## **Key Enhancements & Features**
✅ **Automated & Parameterized ETL Pipelines** for **scalable ingestion**.
✅ **Separation of Data Layers (Bronze, Silver, Gold)** for better governance.
✅ **Spark-based transformation** to handle large datasets efficiently.
✅ **External tables & views in Synapse** for fast querying.
✅ **Integration of SQL, HTTP & NoSQL sources** into a unified data model.

## **Conclusion**
This project successfully implemented an end-to-end **Big Data Analytics Pipeline** using Azure services. The structured **ETL workflow** and **optimized data storage** enable seamless data analysis, making it a valuable asset for **E-commerce analytics and business intelligence**.

---
**🔗 [GitHub Repository](#)** (Add your repo link here)

This README provides a structured and detailed overview of the project, making it suitable for GitHub documentation. Let me know if you need any modifications! 🚀

