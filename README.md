`src` -> Inside the src folder all the actual source code regarding the project will reside, this will not include any kind of tests. (You might want to make separate tests folder).

Lets take a look inside the `src` folder


-`config` -> In this folder anything and eveything regarding any configurations or setup of a library or module will be done. For example : setting up `dotenv` so that we can use the environment variable anywhere in a cleaner fashion, this is done in the `server-config.js`. One more example can be to setup you logging library should also be done here.

-`routes` -> In the routes folder, we register a router and the corresponding middleware and controllers to it.

-`middlewares` -> They are just going to intercept the incoming requests where we can write our validators, authenticators etc.

-`controllers` -> They are kind of the last middlewares as post the myou call your business layer to execute the budiness logic. In controllers we just receive the incoming requests and data and then pass it to the business layer, and once business layer returns an output, we structure the API response in controllers and send the output.

-`repositories` -> This folder contains all the logic using which we interact the DB by writing queries, all the raw queries or ORM queries will go here.

-`services` -> Contains the business logic and interacts with repositories for data from the database.

-`utils` -> contains helper methods, error classes etc.

### Setup the project
 -Go inside the folder and perform
```
npm install
```

- In root directory create a `.env` file and add the following env variables
```
    PORT = <port number of your choice>
```
- go inside the `src` folder and execute the following command : 
```
    npx sequelize init
```
- By executing the above command you will get migrations and seeders folder along with a config.json inside the config folder
- If you're setting up your development environment, then write the username of your db, password of your db, and in dialect mention whatever db you are using for ex : mysql,mariadb etc
- If you're setting up test or prod environment, make sure you also replace the host with the hosted db url

- To run the server execute 
```
npm run dev
```

