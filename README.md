# Personal Expense Tracker

A command-line application written in **pure Python** (standard library only) that lets users record, review and analyse their daily spending.

## Problem Statement
Students often lose track of where their money goes. This project provides a simple, offline tool to log expenses, group them by category, and view clear summaries so that spending habits become visible.

## Objectives
- Record expenses quickly with proper validation
- Keep data saved between sessions
- Give useful summaries (totals, category share, monthly spending)
- Allow data to be exported for use in Excel

## Features
| # | Feature | Description |
|---|---|---|
| 1 | Add expense | Amount, category, date (defaults to today) and optional note |
| 2 | View all expenses | Formatted table sorted by date, with total |
| 3 | Search by category | Shows only the chosen category |
| 4 | Delete expense | Remove an entry using its ID |
| 5 | Summary report | Total, average, spending by category (with %) and by month |
| 6 | Export to CSV | Creates `expenses_export.csv` |
| 7 | Exit | Data is already saved after every change |

## Technologies Used
- Python 3.8 or above
- Standard library modules only: `json`, `csv`, `os`, `datetime`

## Python Concepts Demonstrated
- Functions and modular code
- Lists, dictionaries and dictionary-based menu dispatch
- Loops and conditional statements
- File handling with JSON and CSV
- Exception handling (`try/except`) for invalid input and unreadable files
- Input validation for amount, date and menu choices
- Sorting with `sorted()` and `lambda`
- Generator expressions and f-string formatting

## How to Run
1. Install Python 3.8 or above.
2. Download `personal_expense_tracker.py` into a folder.
3. Open a terminal in that folder and run:
   ```
   python personal_expense_tracker.py
   ```
4. Follow the on-screen menu (enter a number from 1 to 7).

No extra packages need to be installed.

## Sample Output
```
========================================
   PERSONAL EXPENSE TRACKER
========================================

1. Add expense
2. View all expenses
3. Search by category
4. Delete expense
5. Summary report
6. Export to CSV
7. Exit
Enter your choice (1-7): 2

--- All Expenses ---

ID   Date        Category        Amount  Note
-------------------------------------------------------
1    2026-09-10  Food            250.50  Lunch
2    2026-09-29  Bills          1200.00  Train ticket
-------------------------------------------------------
Total: Rs. 1450.50
```

## Project Structure
```
Personal-Expense-Tracker/
├── personal_expense_tracker.py   # complete program
├── README.md                     # documentation
├── expenses.json                 # auto-created when data is saved
└── expenses_export.csv           # auto-created on CSV export
```

## How It Works
1. On start, `load_expenses()` reads `expenses.json` (or starts with an empty list).
2. Each expense is stored as a dictionary: `id`, `amount`, `category`, `date`, `note`.
3. Every add or delete calls `save_expenses()`, so nothing is lost if the program closes.
4. The menu in `main()` uses a dictionary to call the correct function for each choice.

## Testing Performed
| Test | Input | Expected result |
|---|---|---|
| Invalid amount | `abc` or `-50` | Error message, asks again |
| Invalid date | `2026-13-45` | Error message, asks again |
| Empty date | Press Enter | Today's date is used |
| Invalid menu choice | `9` | Error message, menu shown again |
| Delete unknown ID | `999` | "No expense found with that ID." |
| Empty data | Open summary with no expenses | "No data to summarise yet." |
| Restart program | Close and reopen | Previous expenses are still present |

## Limitations
- Command-line only (no graphical interface)
- No option to edit an existing expense
- Single user, data stored locally

## Future Enhancements
- Edit expense option
- Monthly budget limit with warnings
- Charts using `matplotlib`
- GUI using `tkinter`

## Author
**Name:** Ritik Kumar
**Registration No.:**26BAI10331
**University:** VIT
