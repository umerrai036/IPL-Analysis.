# 🏏 IPL Matches Dataset (2008 - 2022)

This repository contains a comprehensive dataset of Indian Premier League (IPL) matches. It includes match-by-match details spanning from the inaugural season in 2008 through the 2022 season.

This dataset is perfect for data analysis, visualization, and machine learning projects aimed at predicting match outcomes or analyzing team strategies.

## 📂 File Description

- **Filename:** `ipl-matches.csv`
- **Format:** Comma Separated Values (CSV)
- **Data Range:** 2008 – 2022

## 📝 Data Dictionary

The dataset contains the following columns:

| Column | Description |
| :--- | :--- |
| `ID` | Unique identifier for the match |
| `City` | The city where the match was played |
| `Date` | Date of the match (YYYY-MM-DD) |
| `Season` | The IPL season (Year) |
| `MatchNumber` | Match number in the schedule or stage (e.g., Final, Qualifier) |
| `Team1` | The name of the first team |
| `Team2` | The name of the second team |
| `Venue` | The stadium where the match took place |
| `TossWinner` | The team that won the coin toss |
| `TossDecision` | The decision made by the toss winner (Bat or Field) |
| `SuperOver` | Indicates if the match went to a Super Over (Y/N) |
| `WinningTeam` | The team that won the match |
| `WonBy` | Indicates if the win was by 'Runs' or 'Wickets' |
| `Margin` | The margin of victory (number of runs or wickets) |
| `method` | If the Duckworth-Lewis (D/L) method was used (NA if normal) |
| `Player_of_Match` | The player awarded Man of the Match |
| `Team1Players` | List of players playing for Team 1 |
| `Team2Players` | List of players playing for Team 2 |
| `Umpire1` | Name of the first on-field umpire |
| `Umpire2` | Name of the second on-field umpire |

## 🚀 Getting Started

### Prerequisites
To analyze this data, you will likely need Python with the following libraries:
* Pandas
* Matplotlib / Seaborn (for visualization)
* NumPy

### Quick Load (Python)

```python
import pandas as pd
import ast

# Load the dataset
df = pd.read_csv('ipl-matches.csv')

# Note: The player columns are string representations of lists. 
# You can convert them to actual Python lists using ast.literal_eval
df['Team1Players'] = df['Team1Players'].apply(ast.literal_eval)
df['Team2Players'] = df['Team2Players'].apply(ast.literal_eval)

# Display first 5 rows
print(df.head())
