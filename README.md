# 🚌 Analysis on Student Daily Commute
### Exploratory Data Analysis — Mini Project

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge&logo=jupyter&logoColor=white"/>
  <img src="https://img.shields.io/badge/Pandas-EDA-green?style=for-the-badge&logo=pandas&logoColor=white"/>
  <img src="https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge"/>
</p>

---

## 🏫 Project Info

| Field | Details |
|---|---|
| **Subject** | Exploratory Data Analysis |
| **Semester** | Sem 2 – B.Tech |
| **Batch** | EnTC A-3 — Group 1 |
| **Project Type** | Mini Project |
| **Data Collection** | Google Forms (Real Student Survey) |

---

## 👥 Team Members

| Name | PRN |
|---|---|
| Tanmay Agarwal | 25070123158 |
| Tannishtha Gupta | 25070123049 |

---

## 📌 Project Overview

Ever wondered how students across Pune juggle daily travel just to reach their destinations? This project dives into the real commuting patterns of students by analysing **724 survey responses** collected via Google Forms.

From the mode of transport and travel time to bottlenecks and satisfaction scores — we explore it all using Python-based Exploratory Data Analysis techniques taught to us in Semester 2.

---

## 📂 Repository Structure

```
📦 student-commute-eda
 ┣ 📓 Student_Commute_EDA.ipynb       ← Main EDA Notebook
 ┣ 📄 student_commute_data_google_form.csv  ← Dataset (Google Form responses)
 ┣ 📄 EDA_Questions_Student-Daily-Commute-Dataset.pdf  ← Questions on which we have performed the EDA
 ┗ 📄 README.md                        ← You are here!
```

---

## 📊 Dataset Description

The dataset was collected through a Google Form survey shared among students. It contains **724 rows** and **10 columns**.

| Column | Description |
|---|---|
| `Timestamp` | Date and time the response was submitted |
| `Starting_Point` | The area from where the student commutes |
| `Destination` | The area the student travels to |
| `Primary_Mode` | Main mode of transport used |
| `Secondary_Mode` | Secondary mode (if multi-leg journey) |
| `Time_of_Day` | Time slot of the usual commute |
| `Travel_Time_min` | Total one-way travel time (in minutes) |
| `One_Way_Cost_INR` | Total one-way cost (in ₹) |
| `Delay_Points` | Major bottlenecks faced on the route |
| `Satisfaction` | Overall commute satisfaction score (1–5) |

### 📍 Starting Points Covered
`Kothrud` · `Baner` · `Pashan` · `Wakad` · `Shivajinagar` · `SIT Lavale Campus` · `Other`

### 🏁 Destinations Covered
`Hinjewadi` · `Kharadi` · `Pune Station` · `Swargate` · `Viman Nagar` · `Other`

---

## 🔬 EDA Techniques Applied

All techniques taught in class were applied to this real-world dataset:

### 1️⃣ Dataset Loading & Inspection
- Loaded the CSV using `pd.read_csv()`
- Renamed columns for cleaner access
- Inspected with `df.head()`, `df.tail()`, `df.info()`, `df.shape`, `df.dtypes`, `df.columns`

### 2️⃣ Descriptive Statistics
- Used `df.describe()` for an overall numerical summary
- Computed individual stats — `mean()`, `median()`, `std()`, `min()`, `max()` — for **Travel Time** and **One-Way Cost**

### 3️⃣ Missing Value Analysis
- Detected nulls using `df.isnull().sum()` and percentage calculation
- Handled 132 missing values in `Delay_Points` by filling them with `'None'` using `fillna()`

### 4️⃣ Frequency Count
- Applied `value_counts()` on: `Primary_Mode`, `Time_of_Day`, `Starting_Point`, `Destination`, `Delay_Points`, and `Satisfaction`

### 5️⃣ Unique Values
- Used `unique()` to list all distinct categories per column
- Used `nunique()` to count distinct values across the entire dataset

### 6️⃣ Percentage Distribution
- Computed `value_counts(normalize=True) * 100` for all key categorical columns

### 7️⃣ Filtering Data
- Filtered Metro users, Morning Peak commuters, high-cost trips (> ₹300), long commutes (> 90 min), and students starting from Kothrud

### 8️⃣ Cross Tabulation
- `pd.crosstab()` applied on 5 combinations:
  - Primary Mode × Time of Day
  - Starting Point × Primary Mode
  - Destination × Primary Mode
  - Primary Mode × Satisfaction Rating
  - Time of Day × Delay Points

### 9️⃣ Groupby Analysis
- `groupby()` to find mean travel time & cost per mode, mean satisfaction per mode, trip count per starting point, and max cost per mode

### 🔟 Sorting
- Sorted dataset by Travel Time (ascending), One-Way Cost (descending), and Satisfaction (descending)

### 1️⃣1️⃣ Derived Column
- Added a new `Commute_Category` column using `apply()`:
  - `Short` → ≤ 30 min
  - `Medium` → 31–60 min
  - `Long` → > 60 min

### 1️⃣2️⃣ Visualizations
- Bar charts, pie chart, and histograms using `matplotlib` and `seaborn`

---

## 📈 Key Findings

| Metric | Result |
|---|---|
| 🧑‍🤝‍🧑 Total Responses | 724 students |
| 🏆 Most Used Mode | Metro (18.09%) |
| ⚡ Fastest Mode (avg) | Metro (~39 min) |
| 💸 Cheapest Mode (avg) | Metro (~₹23) |
| 💰 Most Expensive Mode | Cab / Ola / Uber (~₹298) |
| ⏱️ Average Travel Time | ~57 minutes |
| 💵 Average One-Way Cost | ~₹127 |
| 🚦 Biggest Bottleneck | Waiting for Bus/Metro (133 cases) |
| 🔴 Missing Values | 132 (in Delay_Points — filled with 'None') |

---

## 🛠️ Tech Stack

```
Python 3.x
├── pandas       — Data loading, manipulation, EDA
├── numpy        — Numerical operations
├── matplotlib   — Visualizations (bar, pie, histogram)
└── seaborn      — Statistical plots
```

---

## 🚀 How to Run

**1. Clone the repository**
```bash
git clone https://github.com/<your-username>/student-commute-eda.git
cd student-commute-eda
```

**2. Open the notebook**

Upload both files to [Google Colab](https://colab.research.google.com/) and run all cells, **or** run locally:

```bash
jupyter notebook Student_Commute_EDA.ipynb
```

**3. Make sure the CSV is in the same directory as the notebook before running.**

---

## 📝 Acknowledgements

- All 724 students who filled our Google Form survey 🙏
- Special Thanks to our EDA ma'am (mrs. Snehal Bhosale) for teaching us these techniques in Sem 2
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Matplotlib Documentation](https://matplotlib.org/)

---

<p align="center">
  Made with ❤️ by <strong>EnTC A-3, Group 1</strong> · B.Tech Sem 2
</p>
