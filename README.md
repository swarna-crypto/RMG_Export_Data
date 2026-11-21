# RMG_Export_Data
# Bangladesh RMG monthly export data (July 2010 to October 2026)

## What is here

| Folder / file | What it holds |
|---|---|
| `data/raw_epb/` | 174 monthly export reports exactly as downloaded from EPB (file names kept as saved) |
| `data/raw_epb/MANIFEST.csv` | One row per raw file: report month, fiscal year, format, report type |
| `data/processed/RMG_monthly_Jul2010-Jun2026_modelling.csv` | 192 months used for modelling |
| `data/processed/RMG_monthly_Jul-Oct2026_holdout.csv` | 4 months held back (never used in modelling) |
| `data/processed/RMG_monthly_master_Jul2010-Oct2026.xlsx` | Full series with Data, Checks and Notes sheets |

## Source

Export Promotion Bureau (EPB), Bangladesh, https://epb.gov.bd, Export Data section.
All files were downloaded on 14 November 2026.

## Columns in the processed files

- `month`: year-month
- `knitwear_musd`: knitwear exports, HS chapter 61, USD million
- `woven_musd`: woven exports, HS chapter 62, USD million
- `rmg_musd`: knitwear + woven, USD million (the series forecast)
- `revised_basis`: 0 for EPB's original figures (to June 2022), 1 for EPB's revised figures (from July 2022)

## How monthly values were made

EPB reports are fiscal-year-to-date (July to June). Each monthly value is this month's
year-to-date total minus last month's. FY2010-11 and FY2013-14 have no separate monthly files
here; those months come from the "same period last year" columns of the next year's reports.
That is why the raw folder has 174 files for 196 months.

## Things to know

- EPB removed double counting in 2024 for FY2022-23 and FY2023-24 only. Figures from
  July 2022 are on the revised basis and are not directly comparable with earlier years.
- The most recent months are provisional and may be revised by EPB.
- Bangladesh Bank publishes export figures that differ from EPB's.
- File `March 220.doc` is March 2020 (typo in the saved name).

## AI use

The dataset was compiled with help from Claude (Anthropic). This is disclosed in the report.
