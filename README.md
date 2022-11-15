# Python-SQL-connection
Connecting local SQL server with python with the help of pyodbc and pandas libraries

Requirements:-
* Python and its libraries (pandas, pyodbc)
* SQL

We can connect our python IDE directly to the SQL server, so that we can do some certain task by directly writing query in the python IDE. We can also export the output data by storing into pandas library and then export with the help of to_csv files or to_excel.

At first we have to extablish the connection from python to our local SQL server;
##  Python code;
    import pyodbc
    conn = pyodbc.connect('Driver={SQL Server};' 
                 'Server=PREDATOR\SQLSERVER;'  #Name of the SQL server, eg. PREDATOR\SQLSERVER (my local SQL server name)
                 'Database=Project1;' #name of the database which you want to access within the mention SQL server, eg. Project1 
                 'Trusted_Connection=no;')
                     
## To read SQL query in python;
    import pandas as pd
    df = pd.read_sql("select * from table_name", conn)
    df.head()

    df.to_csv("local path where you want to export your data, eg. C:/Users/batman/Desktop/file_name.csv") #to export data into CSV files
