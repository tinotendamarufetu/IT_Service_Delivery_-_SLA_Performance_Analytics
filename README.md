🏦 Banking IT Operations Analytics Suite
Executive Summary
This project is an end-to-end Business Intelligence solution designed to optimize IT service delivery for a mid-sized banking institution.

Using Python for realistic data simulation and Tableau for advanced visualization, I built a 3-dashboard suite that analyzes 10,000+ support tickets to uncover hidden financial risks, operational bottlenecks, and workforce efficiency gaps.

🔗 View the Interactive Dashboards on Tableau Public: https://public.tableau.com/app/profile/tinotenda.muchenje/viz/IT-Service-Delivery-Dashboard/ExecutiveDashboard?publish=yes

💼 The Business Problem
The IT Operations department was facing rising support costs and declining customer satisfaction. The management team lacked visibility into:
1. Financial Risk: Which system failures were costing the bank the most money?
2. Root Cause: Why were critical SLA breaches happening?
3. Workforce Efficiency: Which engineers were over-performing vs. struggling?

📊 The Solution: 3-Part BI Suite
1. Executive Service Overview
A high-level view for the CTO/CIO to monitor overall health and critical incidents.
- Key Features: KPI cards with conditional formatting, Donut charts for ticket distribution, and volume trends.
- Insight: Identified that while "Internet Banking" had high volume, it was low risk.

2. System Reliability & Financial Impact
A strategic tool for Risk Managers to prioritize technical debt.
Key Features:
- Risk Matrix (Scatter Plot): Classifies systems by 'Frequency of Failure' vs. 'Financial Loss'.
- Stability Heatmap: Visualizes downtime patterns to identify "Bad Months" (Nov/Dec).
- Insight: The Mobile Banking App was identified as the highest risk, driving $100M+ in potential financial exposure despite not having the highest ticket count.

3. Operational Efficiency & Scorecards
A tactical view for Team Leads to manage performance.
- Key Features:
  - Engineer Scorecard: A heatmap matrix using LOD expressions to rank engineers by Volume, Resolution Speed, and Fix Quality.
  -Dual Axis Chart: Tracking resolution velocity against ticket volume.
- Insight: Uncovered a 40% productivity gap; top performers were handling 400+ tickets while the team average was ~100.

🛠️ Technical Implementation
Data Engineering (Python)
I generated a synthetic dataset to mimic real-world banking operations using the Faker and NumPy libraries. The data generation process involved:
- Weighted Probabilities: Simulating realistic ticket distribution (e.g., Password Resets are common, Database Failures are rare).
- Complex Logic: Calculating SLA_Breach flags based on ticket priority and resolution time.
- Trend Simulation: Injecting seasonal spikes (e.g., End-of-Year outages) to test the dashboard's ability to spot anomalies.

Python
# Snippet: Simulating Financial Risk Logic
def calculate_risk(system, downtime_hours):
    hourly_cost = {
        'Core Banking': 50000,
        'Mobile App': 85000,  # High Customer Impact
        'Internal HR': 500
    }
    return hourly_cost.get(system, 1000) * downtime_hours

Tableau Development
--Calculated Fields: Used FIXED LOD expressions to calculate specific benchmarks per engineer.
- Parameter Actions: Dynamic date filtering and metric swapping.
- UI/UX Design: Implemented a clean "Corporate Card" layout with a color-blind friendly palette (Navy/Teal/Red).

🚀 Key Insights & Recommendations
Based on the analysis, the following actions were recommended:
1. Prioritize Mobile App Stability: Shift 2 Senior Engineers to focus solely on the Mobile App codebase, as it accounts for 80% of financial risk.
2. Invest in Training: The scorecard revealed that 30% of the team struggles with "Permanent Fixes," relying heavily on "Workarounds." A training program on Root Cause Analysis is required.
3. Automate Password Resets: "Service Requests" make up 25% of volume but 0% of risk. Implementing a self-service bot would free up 600+ engineering hours per year.
