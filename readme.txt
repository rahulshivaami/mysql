/***********MySQL Commands****************/

/***
To export MySQL DATABASE into directory
****/

mysqldump -u [[username]] -p[[password]] [[database_name]] > [[file_name]].sql


/***
To import Data into MySQL
*****/

mysql -u [[username]] -p[[pasword]] [[database_name]] < [[file_name]].sql


/****
To create user in MySQL
*****/

CREATE USER [[username]]@'localhost' IDENTIFIED BY '[[password]]';

To grant access from another host, change the hostname part (localhost) with the remote machine IP. 
For example, to grant access from a machine with IP 10.8.0.5 you would run:

CREATE USER [[username]]@'10.8.0.5' IDENTIFIED BY '[[password]]';

To create a user that can connect from any host, use the '%' wildcard as a host part:

CREATE USER [[username]]@'%' IDENTIFIED BY '[[password]]';

/*****
To grant privileges
******/

The most commonly used privileges are:

ALL PRIVILEGES – Grants all privileges to a user account.
CREATE – The user account is allowed to create databases and tables.
DROP - The user account is allowed to drop databases and tables.
DELETE - The user account is allowed to delete rows from a specific table.
INSERT - The user account is allowed to insert rows into a specific table.
SELECT – The user account is allowed to read a database.
UPDATE - The user account is allowed to update table rows.
To grant specific privileges to a user account, you can use the following syntax:

GRANT [[permission1]], [[permission2]] ON [[database_name]].[[table_name]] TO '[[database_user]]'@'localhost';

Here are some examples:

Grand all privileges to a user account over a specific database:

GRANT ALL PRIVILEGES ON database_name.* TO 'database_user'@'localhost';

Grand all privileges to a user account on all databases:

GRANT ALL PRIVILEGES ON *.* TO 'database_user'@'localhost';

Grand all privileges to a user account over a specific table from a database:

GRANT ALL PRIVILEGES ON database_name.table_name TO 'database_user'@'localhost';
Grant multiple privileges to a user account over a specific database:

GRANT SELECT, INSERT, DELETE ON database_name.* TO database_user@'localhost';

