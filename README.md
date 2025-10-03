# 🛍️ End-to-End Retail Data Engineering Project  
**Technologies:** Azure Data Factory • Azure Data Lake • Azure SQL DB • Databricks • Power BI  

---

## 📖 Overview
This project demonstrates an **end-to-end Azure Data Engineering pipeline** for a **Retail domain**.  
It ingests data from multiple sources, transforms it using **Medallion architecture (Bronze → Silver → Gold)**, and visualizes business metrics in **Power BI**.

---

## 🗂️ Architecture
- **Data Ingestion:** Azure Data Factory (ADF) pulls data from:
  - `Transactions`, `Stores`, `Products` → stored in **Azure SQL Database**
  - `Customers` → fetched from a **JSON API**
- **Data Lake:** All raw data lands in **ADLS Gen2** (Bronze layer)
- **Processing:** **Databricks** cleans and joins data:
  - Bronze → Silver → Gold layers
- **Visualization:** **Power BI** dashboards built on the **Gold layer**

---

## 🏗️ Azure Resources
| Resource                | Name (Example)         | Purpose                         |
|-------------------------|------------------------|---------------------------------|
| Azure SQL Server        | `pocserver198`         | Hosts SQL DB                    |
| Azure SQL Database      | `pocdatabase-poc`      | Stores transaction/store/product tables |
| Azure Data Factory      | `poc677657`            | Pipelines to copy/move data     |
| Azure Databricks        | `db-prac`              | Transformations & joins         |
| ADLS Gen2 Storage       | `retailproject12345`   | Bronze / Silver / Gold storage  |

---

## 🗄️ Datasets
- `customers.json` – Customer details (API source)
- `products.json` – Product catalog
- SQL tables – `Transactions`, `Stores`, `Products`
- Cleaned & aggregated data stored as **Parquet/Delta** in ADLS

---

## ⚙️ Pipeline Flow
1. **ADF Pipelines:**  
   - `Copy data` activities for `transaction` → `product` → `store` → `customer`
2. **Databricks:**  
   - Mount ADLS containers  
   - Clean and cast datatypes (Silver layer)  
   - Join tables & create aggregated Gold dataset
3. **Power BI:**  
   - Connects to Gold dataset for reporting

---

## 📊 Power BI Dashboard Highlights
- Total Sales Amount  
- Total Quantity Sold  
- Sales by Store / Product / Category  
- Monthly Sales Trend  
- Average Transaction Value by Location

---

