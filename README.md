# IPL 2026 Auction Analytics Dashboard

## Table of Contents

* Problem Statement
* Datasource
* Data Collection
* Data Cleaning & Transformation
* Data Modelling
* Excel Formulas & Analytical Logic
* Dashboard Preview
* Dataset Files
* Tools Used
* Key Insights
* References

---

# Problem Statement

This project analyzes the **IPL 2026 Auction and Tournament Performance** using Microsoft Excel. The goal was to understand:

* Which teams spent wisely?
* Which players were undervalued or overpriced?
* Which player roles consumed the highest budget?
* Which coach delivered the highest ROI?
* Which captain had the best win percentage?
* Which players were best suited for each role?
* How can we create the strongest Best XI based on data?

This dashboard simulates how IPL franchises use analytics for **auction planning, squad building, and tactical decision-making**.

---

# Datasource

The data was collected from multiple public cricket sources.

### Player Squad Data

https://www.olympics.com/en/news/ipl-2026-teams-squads-list-player-prices

### Batting Statistics

https://www.espncricinfo.com/records/tournament/batting-most-runs-career/indian-premier-league-2026-17740

### Bowling Statistics

https://www.espncricinfo.com/records/tournament/bowling-most-wickets-career/indian-premier-league-2026-17740

### Team Points Table

Official IPL 2026 points table

### Coaches Data

https://sports.yahoo.com/articles/ipl-2026-list-coaches-10-213700148.html

https://www.espncricinfo.com/auction/ipl-2026-auction-1515016

### Captain Data

https://www.espncricinfo.com/records/trophy/individual-most-matches-as-captain/indian-premier-league-117

---


## Home Dashboard

![Home Dashboard](Dashboard_Screenshots/Home_Dashboard_1)

![Home Dashboard](Dashboard_Screenshots/Home_Dashboard_2)

---

## Auction Intelligence

![Auction Intelligence](Dashboard_Screenshots/Auction_Intel_1)

![Auction Intelligence](Dashboard_Screenshots/Auction_Intel_2)

---

## Role-Based Player Analytics

![Role Analytics](Dashboard_Screenshots/Role_Based_Data_1)

![Role Analytics](Dashboard_Screenshots/Role_Based_Data_2)

---

## Coach & Captain Intelligence

![Coach Intelligence](Dashboard_Screenshots/Coach_Captain_intel_1)

![Coach Intelligence](Dashboard_Screenshots/Coach_Captain_intel_2)

---

## Best XI Selector

![Best XI](Dashboard_Screenshots/Best_XI_1)

![Best XI](Dashboard_Screenshots/Best_XI_2)

# Data Collection

Data was collected through:

* Web scraping
* Manual extraction
* Claude AI extraction
* CSV/Excel conversion

Datasets collected:

* Player Master Data
* Batting Data
* Bowling Data
* Team Data
* Coach Data
* Captain Data

---

# Data Cleaning & Transformation

Performed in Excel:

* Removed duplicates
* Removed special symbols (*)
* Removed country tags
* Standardized player names
* Fixed missing values
* Created unique player-team keys

Example:

Ruturaj Gaikwad_CSK

Merged batting + bowling + auction + team datasets into:

Master_Player_Analytics

---

# Data Modelling

Connected all tables using:

### Primary Keys

* Player Name
* Team Name
* Player-Team Key

Relationships:

* Player → Batting
* Player → Bowling
* Team → Coach
* Team → Captain

---

# Excel Formulas & Analytical Logic

## Coach ROI

Wins / Purse Used

---

## Team Spending Efficiency

Team Strength / Team Spend

---

## Opener Score

=(Runs * Strike Rate)/100

Purpose:
Measures top-order aggression and run production.

---

## Middle Order Score

=(Average * 0.4)+(Not Outs * 5)+(Strike Rate * 0.2)+(Runs * 0.1)

Purpose:
Rewards consistency, stability, and clutch batting.

---

## Finisher Score

=((Strike Rate * 0.5)+((6s * 6)+(4s * 4))/(Balls+1)+(Not Outs * 2))

Purpose:
Identifies explosive finishers.

Special filter used:

* Balls < 200
* Strike Rate > 150
* Role = Wicketkeeper or All-Rounder

---

## All-Rounder Score

=((Runs * 0.3)+(Strike Rate * 0.2)+(Wickets * 8)-(Economy * 2)+(Not Outs * 2))

Purpose:
Balances batting + bowling contribution.

---

## Bowler Score

=(Wickets * 10)-Economy

Purpose:
Measures wicket-taking efficiency with economy penalty.

---

## Impact Player Score

=Opener Score + Middle Order Score + Finisher Score + All-Rounder Score + Bowler Score

Purpose:
Finds best non-XI player as impact substitute.

---



# Dataset Files

Raw datasets are available inside:

DataSet/

Contains:

* IPL_2026_All_players.xlsx
* Batting_data.xlsx
* Bowling_data.xlsx
* IPL_2026_Team_Data.xlsx
* IPL_2026_Coaching_Data.xlsx
* Captain_Data_Final.xlsx

---

# Tools Used

* Microsoft Excel
* Pivot Tables
* Pivot Charts
* VLOOKUP
* INDEX MATCH
* SUMIF
* IF
* IFERROR
* Data Cleaning
* Web Scraping
* Claude AI

---

# Key Insights

* GT emerged as the strongest overall team.
* MI showed the highest output per crore spent.
* Finn Allen emerged as the most undervalued player.
* All-rounders consumed the highest auction budgets.
* Mahela Jayawardene delivered the best coach ROI.
* Captain win percentage strongly correlated with playoff qualification.
* Nitish Kumar Reddy was selected as the most balanced finisher.
* Kagiso Rabada emerged as the best bowler based on bowling score.

---

# References

For raw data collection:

Player Squad:
https://www.olympics.com/en/news/ipl-2026-teams-squads-list-player-prices

Batting:
https://www.espncricinfo.com/records/tournament/batting-most-runs-career/indian-premier-league-2026-17740

Bowling:
https://www.espncricinfo.com/records/tournament/bowling-most-wickets-career/indian-premier-league-2026-17740

Coaches:
https://sports.yahoo.com/articles/ipl-2026-list-coaches-10-213700148.html

Auction:
https://www.espncricinfo.com/auction/ipl-2026-auction-1515016

Captains:
https://www.espncricinfo.com/records/trophy/individual-most-matches-as-captain/indian-premier-league-117
