# Intermediate Python: Intro to Pandas

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/wang7337-hub/PythonPDH/blob/main/intro_to_pandas.ipynb)

A hands-on **45-minute PDH exercise** introducing [pandas](https://pandas.pydata.org/),
the standard Python library for working with tabular data (tables, spreadsheets,
CSVs). You'll load a small dataset of campus-store orders and work through
inspecting, filtering, grouping, and plotting it.

**No setup required — click the badge above to run it in Google Colab.**

## What you'll learn

- Load a CSV into a **DataFrame** with `pd.read_csv()`
- **Inspect** data: `.shape`, `.columns`, `.info()`, `.describe()`, `.head()`
- **Filter** rows with boolean masks, and work with dates via `datetime64`
- Create **new columns** from existing ones
- **Sort** with `.sort_values()`
- **Group and aggregate** with `groupby()` (the split–apply–combine pattern)
- **Plot** a quick summary with Matplotlib

## How to run

### Option 1 — Google Colab (recommended)

Click the **Open in Colab** badge above and start with the first cell. Everything
runs in your browser: pandas and matplotlib are already installed, and the
notebook downloads `orders.csv` from this repo automatically when it isn't
found locally — so there is nothing to upload.

### Option 2 — Run locally

You need Python 3.9+ and Jupyter:

```bash
git clone https://github.com/wang7337-hub/PythonPDH.git
cd PythonPDH
pip install -r requirements.txt
jupyter notebook intro_to_pandas.ipynb
```

Run the notebook from this folder so that `pd.read_csv("orders.csv")` finds the
data file.

## The dataset — `orders.csv`

60 simulated campus-store orders (February–March 2025). It's synthetic data
created for this exercise; it doesn't describe any real people or purchases.

| Column | Type | Description |
|---|---|---|
| `order_id` | int | Unique ID for the order (1001–1060) |
| `student` | str | Who placed the order (`Student_1` … `Student_24`) |
| `major` | str | The student's major — one of 8, consistent per student |
| `campus` | str | `Main`, `North`, or `South` |
| `category` | str | `Drink`, `Hoodie`, `Lab Kit`, `Notebook`, `Snack`, `Textbook` |
| `item` | str | Specific product (17 distinct items) |
| `price` | float | Unit price in dollars |
| `quantity` | int | Units purchased (1–4) |
| `total` | float | `price × quantity` |
| `order_date` | str | Order date, `YYYY-MM-DD` (read as text; the notebook converts it to `datetime64`) |

Quick facts: **60 rows × 10 columns**, 23 students, 8 majors, 3 campuses,
6 categories, 17 items, no missing values, $3,026.62 of total revenue.

## Notebook structure

| Section | What you do |
|---|---|
| 1) Setup & Load | Import pandas/matplotlib and read the CSV |
| 2) Inspect & Select | Explore shape, columns, summaries; select columns |
| 3) Filtering & New Columns | Filter by category and date; add `unit_total`; sort |
| 4) GroupBy & Aggregations | Revenue by category; quantity and averages by major |
| Bonus | Plot something interesting |
| Reference Solutions | Instructor answers, collapsed to avoid spoilers |

Cells marked `# Your work here` are for you to fill in. Each section includes
hints, and the notebook ships with outputs cleared so you run it yourself.

## For instructors

Reference solutions live in the final markdown cell, inside a collapsed
`<details>` block so students don't see them by accident. Expand it to reveal
worked answers for every task.
