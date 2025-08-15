## Overview
This project is built using **UiPath** and follows the **Robotic Enterprise Framework (REF)**.  
It automates the process of retrieving country capitals by integrating UiPath with the Orchestrator queue and a simple AI prompt.

---

## Features
- Reads a list of countries from a local **Data** file (around 10 countries).
- Uploads each country as a **transaction item** to **UiPath Orchestrator Queue**.
- For each transaction, uses **Copilot** to search for the capital.
- Extracts only the **capital name** without any explanation.
- Stores the results in a **DataTable** for further processing or export.

---

##  Workflow Description
1. **Read Countries Data**  
   - The bot reads a list of countries from the **Data** folder.

2. **Add to Orchestrator Queue**  
   - Each country is pushed to a queue in UiPath Orchestrator.

3. **Process Transactions**  
   - For each transaction, a prompt is generated in the format:  
     ```
     provide me the capital of <CountryName> without explanation
     ```
     Example:  
     ```
     provide me the capital of Germany without explanation
     ```

4. **Retrieve Capital**  
   - Copilot returns only the capital city name (e.g., `Berlin`).

5. **Store in DataTable**  
   - The country-capital pairs are stored in a DataTable for later use.

---
## Orchestrator
![Orch](https://github.com/rewaaalaa7/REF-Country-RPA/blob/main/orch.jpg)
---
## Output 
![output](https://github.com/rewaaalaa7/REF-UiDemo-RPA/blob/main/output.jpg)
---
## Requirements
- **UiPath Studio** (tested on the version you developed with)
- **UiPath Orchestrator** access
- **Copilot** or any AI service capable of returning the capital name given the prompt
---

## How to Run
1. Open the project in UiPath Studio.
2. Ensure the **Orchestrator Queue** is created and linked.
3. Place your countries file in the **Data** folder.
4. Run the project using **REF**'s `Init`, `Get Transaction Data`, and `Process Transaction` stages.
5. Check the output DataTable for country-capital results.
