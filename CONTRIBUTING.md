# Contributing

I built this as a personal portfolio project, but I am happy to receive
contributions that improve the queries, data cleaning logic, or schema.

## How I would like contributions to work

1. **Open an issue first.**  If you find a bug, a data quality edge case that
   the ETL does not handle, or a schema change you think would improve the
   design, please open an issue and describe what is wrong or what you would
   improve.  I find it easier to review a pull request when I already
   understand the problem it is solving.

2. **Fork the repository and submit a pull request.**  Keep each pull request
   focused on one change.  A pull request that adds a new SQL query, for
   example, should not also refactor the ETL script; I prefer to review those
   as separate changes.

3. **Match the existing code style.**  I wrote the ETL script in plain Python
   with pandas and the queries in plain SQL.  I would prefer not to add
   frameworks or external dependencies unless they solve a real problem that
   cannot be addressed with what is already here.

4. **Test end to end before submitting.**  Run `python etl.py` followed by
   `python run_queries.py` and confirm everything completes without errors.
   I test against a freshly generated `warehouse.db` so I know the full
   pipeline works from scratch.

## What fits this project

- New SQL queries that answer a realistic healthcare imaging question
- Additional data quality checks or cleaning steps in `etl.py`
- Schema changes that are backwards-compatible, with a note explaining why
- Corrections or improvements to documentation

## What does not fit

- Switching from SQLite to a server-based database (the whole point of this
  project is that it runs anywhere with just Python)
- Adding an ORM, workflow orchestration, or any framework that obscures the
  SQL and ETL logic I am trying to demonstrate
- Anything that requires real patient data; I use only synthetic data here
