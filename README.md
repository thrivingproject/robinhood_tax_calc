# Stock and Options Tax Calculator

This project is a set of scripts that will help you calculate taxes owed from stock and options trading reports generated by Robinhood.

## Project Structure

The project has the following structure:

```bash
.
├── data
│   └── transactions.csv  # Put your own file here
├── modules
│   ├── csv_to_db.py
│   ├── database.py
│   └── tax_calc.py
├── tests
├── __init__.py
├── .gitignore
├── main.py
├── README.md
└── transactions.sqlite  # Generated after executing CSV to DB script
```

## Description of Modules

- `database.py`: Contains functions for connecting to the SQLite database.
- `csv_to_db.py`: Converts a CSV file of transactions into a SQLite database. It will create the database, clean the data, and insert it into the database. This same moedule can be ran to insert addional data.
- `tax_calculator.py`: Contains functions for calculating taxes owed from stock and options trading activities. This includes dividends and interest as well as capital gains and losses.
- `main.py`: The main script that ties everything together.

## How to Run

1. Download report from Robinhood and move to `data` directory.
2. Run the CSV to DB script to convert your CSV file of transactions into a SQLite database: `python -m modules.csv_to_db`
3. Run the main script to calculate taxes owed: `python main.py`

## Note

Positions that span multiplie years must have the opening trade included in the report, e.g. if a stock was sold in 2023 and purchased in 2022, the report must include the buy transaction from 2022.

## Future Enhancements

- Integrate trades with other financial statments such as balance sheet, statement of earnings, and statement of cash flow.
- Add logic for long-term capital gains and losses
