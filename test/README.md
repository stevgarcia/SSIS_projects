This package creates two tables:

testdata where the data is loaded
tbl_logs where we can track which file was loaded and the amount of rows.
Inside a foreach logic:

checks with an SQL task and an expression the count over tbl_logs
the sucess arrow has defined and expression and constraint to allow to update only new files [User::IsFileAlreadyLoaded]==0
the dataflow task takes the files, makes a row count and delivers the data into a SQL
Lastly, the sql task populates testdata and tbl_logs
