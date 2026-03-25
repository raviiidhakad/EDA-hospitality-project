# EDA-hospitality-project
# 🏨 AtliQ Hotels — Hospitality Data Analysis Project

A data analysis project on hospitality domain data for **AtliQ Hotels**, covering data import, exploration, cleaning, transformation, and business insight generation using Python and Pandas.

---

## 📁 Project Structure

```
hospitality-analysis/
│
├── datasets/
│   ├── dim_date.csv
│   ├── dim_hotels.csv
│   ├── dim_rooms.csv
│   ├── fact_bookings.csv
│   ├── fact_aggregated_bookings.csv
│   └── new_data_august.csv
│
└── Hospitality_project.ipynb
```

---

## 📊 Dataset Description

| File | Description |
|------|-------------|
| `dim_date.csv` | Date dimension — date, month-year label, week number, day type (weekday/weekend) |
| `dim_hotels.csv` | Hotel dimension — property ID, name, category (Luxury/Business), city |
| `dim_rooms.csv` | Room dimension — room ID (RT1–RT4) mapped to room class (Standard, Elite, Premium, Presidential) |
| `fact_bookings.csv` | Individual booking records — booking ID, property, dates, guests, platform, revenue, ratings |
| `fact_aggregated_bookings.csv` | Aggregated bookings per property per day — successful bookings vs capacity |
| `new_data_august.csv` | New August data appended during analysis |

---

## 🔍 Project Workflow

### 1. Data Import & Exploration
- Loaded all 5 datasets using Pandas
- Explored shape, data types, unique values, and distributions
- Visualized booking platforms and city distributions using bar charts

### 2. Data Cleaning
- Removed invalid records with `no_guests <= 0`
- Removed outliers in `revenue_generated` using mean ± 3×std deviation
- Handled null values in `capacity` column using median imputation
- Filtered rows where `successful_bookings > capacity` (data error)

### 3. Data Transformation
- Created `occ_pct` (occupancy percentage) column: `successful_bookings / capacity * 100`
- Merged dimension tables with fact tables for enriched analysis
- Appended August data to the main dataframe using `pd.concat`

### 4. Insights Generated
- 📌 **Average occupancy rate by room class** (Standard, Elite, Premium, Presidential)
- 📌 **Average occupancy rate per city**
- 📌 **Weekday vs Weekend occupancy comparison**
- 📌 **City-wise occupancy for June 2022**
- 📌 **Revenue realized per city**
- 📌 **Month-by-month revenue trend**
- 📌 **Revenue per hotel property**
- 📌 **Average guest ratings per city**
- 📌 **Revenue breakdown by booking platform** (Pie chart)

---

## 🛠️ Tech Stack

- **Python 3**
- **Pandas** — data manipulation and analysis
- **Matplotlib** — data visualization

---

## 🚀 Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/atliq-hotels-analysis.git
   cd atliq-hotels-analysis
   ```

2. **Install dependencies**
   ```bash
   pip install pandas matplotlib jupyter
   ```

3. **Run the notebook**
   ```bash
   jupyter notebook Hospitality_project.ipynb
   ```

> Make sure the `datasets/` folder is in the same directory as the notebook.

---

## 📈 Sample Insights

- **Presidential suite (RT4)** rooms have no significant revenue outliers unlike other categories
- **Weekend occupancy** is higher than weekday occupancy across properties
- Certain cities like **Mumbai and Delhi** show consistently higher revenue realized
- A significant portion (~58%) of ratings in booking records are **null** — noted but not imputed

---

---

## 📄 License

This project is for educational purposes only.

