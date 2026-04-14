# 🧠 SQL Students Mental Health Project

A beginner-level SQL data analysis project exploring the mental health of international students using aggregate functions, filtering, grouping, and ordering techniques.

---

## 📁 Project Files

| File | Description |
|------|-------------|
| `students.csv` | Dataset containing student records including mental health diagnostic scores |
| `Questions.txt` | Problem statement and analysis questions |
| `Solution.txt` | SQL query solutions |
| `notebook.ipynb` | Jupyter Notebook with full analysis walkthrough |
| `mentalhealth.jpg` | Visual reference / project banner |
| `How To Approach.txt` | Step-by-step guide for solving the project |

---

## 🎯 Project Objective

Analyze the mental health of **international students** by:
- Counting international students in the dataset
- Computing summary statistics (min, max, average) for each diagnostic test score
- Filtering and grouping data specific to international students
- Ordering results by length of stay

---

## 🛠️ Key SQL Concepts Used

- **Aggregate Functions** — `COUNT()`, `AVG()`, `MIN()`, `MAX()`
- **Rounding** — `ROUND()` to two decimal places
- **Aliases** — `AS` keyword (e.g., `min_phq`, `max_phq`, `avg_phq`)
- **Filtering** — `WHERE` clause with equality operator (`=`)
- **Grouping** — `GROUP BY` clause on the `inter_dom` column
- **Ordering** — `ORDER BY ... DESC` on the `stay` field

---

## 📋 Approach

### Step 1 — Perform Calculations
Count the number of international students and calculate summary statistics for each diagnostic test score using aggregate functions. Round average values to two decimal places and alias the columns as `min_phq`, `max_phq`, and `avg_phq`.

### Step 2 — Filter and Group the Data
Apply a `WHERE` clause to filter for international students only (check the `inter_dom` column for the correct value — note case sensitivity). Use `GROUP BY` on the `inter_dom` column to ensure aggregations are applied per group. The grouped column must also appear in the `SELECT` statement.

### Step 3 — Order the Results
Use `ORDER BY stay DESC` to sort the final output in descending order by the students' length of stay.

---

## 📊 Sample Query Structure

```sql
SELECT
    inter_dom,
    COUNT(*) AS count_int,
    ROUND(MIN(todep), 2)  AS min_phq,
    ROUND(MAX(todep), 2)  AS max_phq,
    ROUND(AVG(todep), 2)  AS avg_phq
FROM students
WHERE inter_dom = 'Inter'
GROUP BY inter_dom
ORDER BY stay DESC;
```

> ⚠️ Column names may vary slightly — refer to `students.csv` for exact field names.

---

## 🧰 Tools & Technologies

- **SQL** (PostgreSQL / standard SQL syntax)
- **Python / Jupyter Notebook** (for extended analysis)
- **CSV** (raw dataset)

---

## 🚀 How to Run

1. Import `students.csv` into your preferred SQL environment (e.g., PostgreSQL, MySQL, SQLite, or DataLab).
2. Run the queries from `Solution.txt` or follow along in `notebook.ipynb`.
3. Refer to `Questions.txt` for the original problem statements.

---

## 📌 Skill Level

**Beginner** — suitable for those learning foundational SQL concepts including aggregation, filtering, and grouping.

---

## 🙌 Acknowledgements

This project is part of a structured SQL learning path focusing on real-world datasets. The mental health dataset was used purely for educational purposes.
