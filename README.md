# 🔍 Crime Data Analysis — Python Final Project

A data analysis project built with Python and Plotly to explore and uncover trends in a real-world crime dataset containing **247,988 records** across **12 features**.

---

## 📁 Dataset

| Feature | Description |
|---|---|
| `DR_NO` | Report number |
| `Date Rptd` | Date the crime was reported |
| `DATE OCC` | Date the crime occurred |
| `TIME OCC` | Time the crime occurred (HHMM format) |
| `AREA NAME` | Geographic area name |
| `Crm Cd Desc` | Crime type description |
| `Vict Age` | Victim's age |
| `Vict Sex` | Victim's sex (M/F) |
| `Vict Descent` | Victim's ethnic descent |
| `Weapon Desc` | Weapon used (if any) |
| `Status Desc` | Case resolution status |
| `LOCATION` | Street address of crime |

---

## 🧹 Data Cleaning

- **`Weapon Desc`** — 167,901 nulls filled with `"No Weapon"` (crimes committed without a weapon)
- **`Vict Sex`** — 32,248 nulls filled with `"Unknown"`
- **`Vict Descent`** — 32,249 nulls filled with `"Unknown"`
- **Duplicate rows** — 0 duplicates found
- **Outlier ages** — Values `0` and `99` excluded from age analysis (used as placeholders for unknown age)

---

## 📊 Core Analysis Tasks

### 1. 🕛 Peak Crime Hour
Extracted the hour from `TIME OCC` using integer division (`// 100`) and identified the hour with the highest number of reported crimes.

> **Result:** Peak crime hour is **12:00 PM (noon)**

**Visualization:** Line chart — *Crimes by Hour of Day*

---

### 2. 🌙 Night Crime Geography
Filtered crimes occurring between **10:00 PM and 3:59 AM** and identified the top 10 areas with the highest night crime counts.

> **Result:** The area with the most night crimes is **Central**

**Visualization:** Horizontal bar chart — *Top 10 Areas - Night Crimes*

---

### 3. 👥 Victim Demographics
Grouped victim ages into brackets using `pd.cut()` after removing placeholder values (0 and 99).

Age brackets used:

| Group | Range |
|---|---|
| 0-17 | Minors |
| 18-25 | Young Adults |
| 26-34 | Adults |
| 35-44 | Mid Adults |
| 45-54 | Middle Age |
| 55-64 | Older Adults |
| 65+ | Seniors |

**Visualization:** Bar chart — *Victim Age Distribution*

---

### 4. 🔎 Anomaly Detection
Used the **IQR (Interquartile Range)** method to statistically detect outliers in the `Vict Age` column.

- Lower bound: `-67.5`
- Upper bound: `112.5`
- Number of statistical outliers: **0** (after cleaning placeholder values)

**Visualization:** Box plot + Histogram — *Outliers in Victim Age*

---

## ⭐ Bonus Analysis

### 📅 Crime Trend by Day of Week
Analyzed which days of the week have the highest crime counts.

> **Result:** **Friday** has the highest crime count (38,553), while **Tuesday** has the lowest (32,646)

**Visualization:** Line chart with data labels — *Crime Trend Across Days of the Week*

---

### 📆 Crimes by Month
Extracted the month from `DATE OCC` to identify seasonal crime patterns.

> **Result:** Crime peaks dramatically in **June** (~35k), with the lowest counts in **February**

**Visualization:** Line chart — *Crimes by Month*

---

### 🏙️ Top 5 Most Dangerous Areas Overall
Identified the 5 areas with the highest overall crime counts across the entire dataset.

> **Top areas:** Central, 77th Street, Southwest, Pacific, Olympic

**Visualization:** Bar chart — *Top 5 Most Dangerous Areas Overall*

---

### 🔫 Top 10 Most Common Crimes
Ranked crime types by frequency across the full dataset.

> **Most common:** Vehicle Stolen, Theft of Identity, Battery - Simple Assault

**Visualization:** Horizontal bar chart — *Top 10 Most Common Crimes*

---

### ⚤ Crimes by Victim Sex
Analyzed the gender distribution of crime victims (excluding Unknown values).

> **Result:** Males account for ~52.7% of victims, Females ~47.3%

**Visualization:** Donut pie chart — *Percentage of Crimes by Victim Sex*

---

## 🛠️ Technologies Used

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, and manipulation |
| `plotly.express` | Interactive visualizations |
| `numpy` | Statistical calculations (IQR) |

---

## 🚀 How to Run

1. Clone this repository:
```bash
git clone https://github.com/ziad-fawzy/Crime-Data-Analysis.git
```

2. Open `Crimes.ipynb` in [![Google Colab](https://colab.research.google.com/)](https://colab.research.google.com/drive/1r_0iHVN_R4Bq8H4J0a8t8ZCR5R-WcOR2?usp=sharing) or Jupyter Notebook

3. Upload the dataset file `crimes.csv` to `/content/`

4. Run all cells in order ▶️

---

## 📌 Key Findings

- 🕛 Crime peaks at **noon (12 PM)** and stays elevated through the evening
- 🌙 **Central** is the most dangerous area at night
- 👤 The **26–34** age group is the most victimized
- 📅 **Friday** is the most dangerous day; **Sunday** the safest
- 🚗 **Vehicle theft** is the single most common crime type
- ⚤ Males are slightly more likely to be crime victims than females

---

## 👤 Author

**Ziad Fawzy**  
Python Data Analysis — Final Project
