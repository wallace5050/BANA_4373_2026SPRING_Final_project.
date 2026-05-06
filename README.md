# BANA_4373_2026SPRING_Final_project.
A final project for SHSU Business analytics class BANA 4373 2026 spring semester. Exploring the after effects of Hurricane Katrina on the population of  New Orleans, Louisiana compared to surrounding areas.
# Group 2 Final Project: Hurricane Katrina and the Population of New Orleans

## Project Summary
This project asks: **How did Hurricane Katrina impact the population of New Orleans?** To answer that question, we use annual county-level resident population data from the Federal Reserve Economic Data (FRED) database for **Orleans Parish, Louisiana** and **Jefferson County, Alabama** (used as the Birmingham comparison group). Using a Difference-in-Differences (DiD) design over the **1995-2015** period, we compare population changes in Orleans Parish before and after Katrina to changes in the control group over the same years. Our key finding is that Hurricane Katrina had a **large and persistent negative effect** on New Orleans population: Orleans Parish experienced an estimated post-Katrina population loss of about **134.5 thousand residents** relative to the control group, and by 2015 the parish had recovered to only about **85.76%** of its 2005 population level.

## Repository Layout
The project should follow this structure:

```text
your-team-repo/
README.md
data_raw/
data_clean/
notebooks/
exports/
requirements.txt
```

For this project, the main analysis notebook is:

- `notebooks/group_2_final_project_DiD_04_MAY.ipynb`



## How to Reproduce the Project
Assume a fresh Python environment.

1. Clone the repository and open it as your working directory.
2. Create and activate a virtual environment.

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

3. Install the required packages.

```powershell
pip install -r requirements.txt
```

4. Launch Jupyter.

```powershell
jupyter notebook
```

5. Open the notebook in the `notebooks/` folder:
   - `group_2_final_project_DiD_04_MAY.ipynb`

6. Run the notebook **from top to bottom** using `Run All`.
7. The notebook will:
   - pull the FRED population series,
   - create the `data_raw/` and `data_clean/` files,
   - generate the DiD table and regression results,
   - export figures and tables to the `exports/` folder.

## Notebook Run Order
This project uses a single final notebook for the full pipeline, so the run order is:

1. `notebooks/group_2_final_project_DiD_04_MAY.ipynb`



## Expected Outputs
After running the notebook, the following files should appear in `exports/`:

- `did_table_birmingham.csv`
- `event_study_birmingham.csv`
- `event_study_birmingham.png`
- `kat_parallel_trends.png`
- `population_indexed_birmingham.png`
- `population_levels_birmingham.png`
- `regression_results_birmingham.csv`
- `summary_stats_birmingham.csv`

The cleaned panel should appear in:

- `data_clean/population_panel_birmingham.csv`

## Data Sources
All project data come from public FRED population series:

- Orleans Parish, Louisiana population:
  [https://fred.stlouisfed.org/series/LAORLE0POP](https://fred.stlouisfed.org/series/LAORLE0POP)
- Jefferson County, Alabama population:
  [https://fred.stlouisfed.org/series/ALJEFF5POP](https://fred.stlouisfed.org/series/ALJEFF5POP)
- FRED CSV download pattern used in the notebook:
  `https://fred.stlouisfed.org/graph/fredgraph.csv?id=<SERIES_ID>`

Example:

- `https://fred.stlouisfed.org/graph/fredgraph.csv?id=LAORLE0POP`
- `https://fred.stlouisfed.org/graph/fredgraph.csv?id=ALJEFF5POP`

## Team Members
- Servando Balderas — GitHub:@ValleyBal
- Ashtyn Aldrete — GitHub: @ashtynaldrete
- Connor McMullen — GitHub:@Wallace5050 



## API Key Note
This notebook currently pulls the FRED data from the **public CSV endpoint**, so a real API key is **not required** to reproduce the analysis as written.
