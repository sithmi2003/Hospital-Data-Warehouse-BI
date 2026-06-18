# Hospital-Data-Warehouse-BI
# 🏥 DWBI Assignments – Hospital Data Warehouse & Business Intelligence

**Student:** Jayawan K P S M
**Course:** Data Warehousing & Business Intelligence (DWBI)
**Year:** 3 | **Semester:** 1 | **Year:** 2026
**Institution:** Sri Lanka Institute of Information Technology (SLIIT)

---

## 📁 Repository Structure

```
DWBI-Assignments/
├── README.md
├── Data_Warehousing.pdf
└── Business_Intelligence
```

---

## 📌 Project Overview

This project involves designing and implementing a **Data Warehouse and Business Intelligence solution** for a hospital management system using a dataset of **50,000 hospital admission records** collected from multiple major hospitals in Sri Lanka over a two-year period (January 2021 – December 2022).

---

## 📄 Assignment 01 – Data Warehouse Design & ETL Development

### ✅ Tasks Covered

| Task | Description |
|------|-------------|
| Task 01 | Dataset Selection |
| Task 02 | Preparation of Data Sources |
| Task 03 | Solution Architecture |
| Task 04 | Data Warehouse Design & Development |
| Task 05 | ETL Development (SSIS) |
| Task 06 | Accumulating Fact Tables |

### 🗄️ Dataset
- **Source:** [Kaggle – Hospital Records](https://www.kaggle.com/datasets/mrnize/hospital-records)
- **Records:** 50,000 hospital admission records
- **Period:** January 2021 – December 2022
- **Hospitals:** 5 major hospitals across Sri Lanka

### 🏗️ Data Sources (ETL)
- `Hospital_Admissions.csv` – Patient and admission data
- `Treatment_Billing.txt` – Clinical and financial data
- `Doctor_Table` (SQL Server DB) – Doctor and department data

### 🌟 Star Schema Design

**Fact Table:**
- `Fact_Admissions` – One record per hospital admission

**Dimension Tables:**

| Dimension | Description |
|-----------|-------------|
| `Dim_Date` | Time-based analysis (Year → Quarter → Month → Date) |
| `Dim_Hospital` | Hospital location (Province, District, Hospital Name) |
| `Dim_Department` | Hospital departments |
| `Dim_Doctor` | Doctor details (SCD Type 2) |
| `Dim_Patient` | Patient demographics (Gender, Age) |
| `Dim_Diagnosis` | Diagnosis information |
| `Dim_Payment` | Payment method and insurance details |

**Measures:**
- `Total_Bill_LKR`
- `Medication_Cost_LKR`
- `Room_Charges_LKR`
- `Lab_Charges_LKR`
- `Doctor_Fee_LKR`
- `Length_of_Stay_Days`
- `Lab_Tests_Count`

### ⚙️ ETL Process (SSIS)
- Data extracted from 3 heterogeneous sources
- Staging area used for data cleaning and validation
- Data profiling performed to detect null values and inconsistencies
- Slowly Changing Dimension (Type 2) implemented for `Dim_Doctor`
- Accumulating fact table pattern implemented with `accm_txn_create_time`, `accm_txn_complete_time`, and `txn_process_time_hours`

---

## 📄 Assignment 02 – SSAS Cube, OLAP & Power BI Reports

### ✅ Tasks Covered

| Step | Description |
|------|-------------|
| Step 1 | Data Source Overview |
| Step 2 | SSAS Cube Implementation |
| Step 3 | OLAP Operations Demonstration |
| Step 4 | Power BI Reports |

### 🧊 SSAS Cube Implementation
- Created using **SQL Server Analysis Services (SSAS)**
- Data Source View (DSV) built with all fact and dimension tables
- Hierarchy defined: `Year → Quarter → Month → Date`
- Cube deployed to `localhost\MSSQLSERVER2`

### 🔄 OLAP Operations Demonstrated

| Operation | Description |
|-----------|-------------|
| **Roll-Up** | Summarized Total Bill LKR at Year level |
| **Drill-Down** | Navigated from Year → Quarter → Month → Date |
| **Slice** | Filtered by a single hospital (e.g., Karapitiya General Hospital) |
| **Dice** | Applied multiple filters (Hospital Name + Year) |
| **Pivot** | Rearranged axes – Date Hierarchy as columns, Hospital Name as rows |

### 📊 Power BI Reports

| Report | Description |
|--------|-------------|
| **Report 1** | Matrix visual – Hospital revenue by year |
| **Report 2** | Multiple slicers (Province, Hospital) with bar, pie, and line charts |
| **Report 3** | Drill-down column chart using Date hierarchy |
| **Report 4** | Drill-through to hospital-specific department billing details |

- **Published to Power BI Service** ✅
- All relationships defined as many-to-one (`*:1`) star schema

---

## 🛠️ Technologies Used

![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=flat&logo=microsoftsqlserver&logoColor=white)
![SSIS](https://img.shields.io/badge/SSIS-0078D4?style=flat&logo=microsoft&logoColor=white)
![SSAS](https://img.shields.io/badge/SSAS-0078D4?style=flat&logo=microsoft&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-217346?style=flat&logo=microsoftexcel&logoColor=white)

| Tool | Purpose |
|------|---------|
| SQL Server 2022 | Data warehouse hosting |
| SSIS (Visual Studio) | ETL pipeline development |
| SSAS (Visual Studio) | OLAP cube creation |
| Power BI Desktop | Interactive report creation |
| Microsoft Excel | OLAP pivot table analysis |

---

## 📬 Contact

**Jayawan K P S M**
📧 maheemasithmi@gmail.com
🏫 Sri Lanka Institute of Information Technology
