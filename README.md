# Global Health Analysis

This project combines global health indicators from the **Google COVID-19 Open Data** project with macroeconomic data from the **World Bank API** to explore how health outcomes relate to economic conditions across countries. The results are communicated through an interactive Quarto website hosted on GitHub Pages.

## 1. Data Sources

- **Health data**
  - Source: Google / Harvard Global Health Institute – COVID-19 Open Data
  - File: `health.csv` (downloaded from  
    `https://storage.googleapis.com/covid19-open-data/v3/health.csv`)
- **Economic data**
  - Source: World Bank API
  - Indicator used: `NY.GDP.PCAP.CD` (GDP per capita, current US$)
  - Retrieved programmatically via the World Bank REST API

The processed datasets are stored in the `data/` folder:
- `data/df_clean.csv` – merged health + economic data (country-level)
- `data/df_enriched.csv` – cleaned version with derived variables
- `data/economic_data.csv` – GDP per capita from the World Bank API

## 2. Cloing the Repository

```test
To Clone the Repository, Run the Following: 
git clone https://github.com/rjlee01/GlobalHealth.git
cd GlobalHealth
```

## 3. Install Required Python Packages

Create a virtual environment and install packages
```test
python3 -m venv .venv
source .venv/bin/activate
```

Then:
```text
pip install -r requirements.txt
```

## 4. Repository Structure

```text
GlobalHealth/
├─ data/
│  ├─ df_clean.csv
│  ├─ df_enriched.csv
│  └─ economic_data.csv
├─ retrieval.ipynb      # Download health.csv + fetch World Bank data
├─ enrichment.ipynb     # Cleaning, merging, feature engineering
├─ analysis.ipynb       # Statistical analysis + static plots
├─ regression.ipynb     # Interactive regression explorer
├─ all.ipynb            # Jupyter notebook with all steps combined
├─ index.qmd            # Quarto homepage (interactive visuals)
├─ _quarto.yml          # Quarto website configuration
├─ requirements.txt
├─ README.md
└─ (other project files)
```

## 5. Reproducing the Project
Once dependencies are installed, you can:

Re-run data retrieval
    Open retrieval.ipynb to download health.csv and fetch World Bank API data.
Regenerate enriched datasets
    Run enrichment.ipynb to create df_clean.csv and df_enriched.csv.
Recreate analysis & visuals
    Open analysis.ipynb or view them on the Quarto site.
Render the website locally (optional)

```bash
quarto render
```
Publish to GitHub Pages
```bash
quarto publish gh-pages
```