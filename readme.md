# This package will ease your task with mysql

## It manage all the data processing issue. Build on top of mysql. So you will get all the basic function

### Not Ready, Developing Actully :D

### Doc v-1

# Basic Init

##### Import mysqlr

```
const mysqlr = require('mysqlr');
```

##### At the startup u have to init the mysqlr

```
mysqlr.init({
    host: "localhost",
    user: "root",
    password: "mysql",
    database: "mysqlrTesting"
})
```

This is for my local database. You can use your own details

Simple right !!!

# Oparations

#### Supporse you have a mysql database and table like below

#### Database Name mysqlrTesting

#### Table name: table_1

|COL1|COL2|COL3|COL4|
|----|----|----|----|
|dt11|dt12|dt13|dt14|
|dt21|dt22|dt23|dt24|
|dt31|dt32|dt33|dt34|
|dt41|dt42|dt43|dt44|
|dt51|dt52|dt53|dt54|


##Then the query be like

### Select Query 

with promise 

```
mysqlr.query('SELECT * FROM test1').then(response => {
    consle.log(response)
}):
```

or with async/await

```
let qry = await mysqlr.query('SELECT * FROM test1');
```

### Insert Query

```
let qry = await mysqlr.query("INSERT INTO test1(t1,t2) VALUES ('dt61','dt64')");
```

Using mysqlr you can just insert a json object like as

```
   const data = {
                    test1:
                    {
                        t1: 'Hello',
                        t4: 'Hello'
                    },
                }
    mysqlr.jsonInsert(data).then(response => console.log(response))
```
or

```
    let qry = await mysqlr.jsonInsert(data));
```

and... that's it. 
The Data will be inserted into the database. 
No Need to take any extra measure. 
It works like sequelize but at the behide works as normal mysql lib.

## Clean table data

Clean all data from a table

```
let basic_1 = await mysqlr.del('test1')
```

Remove Specific data/item from table

Here peramitter are

mysqlr.cleanByItem(table_name, colume name, item name)

```
let basic_1 = await mysqlr.delByItem('test1', 't1', "Hello")
```

## Sample Code 1

mysqlr init will use memory to remember the config. so no needed to init every time. Just init it at the start of the code.

```
const mysqlr = require('mysqlr');

mysqlr.init({
    host: "localhost",
    user: "root",
    password: "mysql",
    database: "mysqlrTesting"
})

mysqlr.query('SELECT * FROM test1').then(response => {
    consle.log(response)
})
```

## Sample Code 2

filename: start.js .  
```
const mysqlr = require('mysqlr');

mysqlr.init({
    host: "localhost",
    user: "root",
    password: "mysql",
    database: "mysqlrTesting"
})

..... other codes
```

filename: searchQuery.js .   
```
const mysqlr = require('mysqlr');

mysqlr.query('SELECT * FROM test1').then(response => {
    consle.log(response)
})
```

Simple :D

<br/><br/><br/>

# More are coming. Hope this will be AWESOME at the END 
