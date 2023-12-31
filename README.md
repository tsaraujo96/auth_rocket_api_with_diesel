
# Auth Rocket Api

Testing simple api template using diesel with JWT authentication.
## Install

To start the application, you must be using the nightly version of rust.

Because the application Cors (rocket-cors)  is not yet stable.

```bash
  rustup default nightly
```

After intall nightly version, you need up postgresql database on docker, browser to the deploy folder and run this command:


```bash
  docker-compose up -d
```

Run all migrations with Diesel, go to the infrastructure folder and run this command:

```bash
  diesel migration run
```

Now you can run your application using, remember to go back to the project initial folder. This command will compile your application and run it.

```bash
  cargo run
```
    
## API documentation

#### Returns all registered users - *need authentication*

```curl
  GET /get_users
```

#### Create an user  - *dont need authentication*

```curl
  POST /create_user
```

#### Body request 

| Parameter   | Type       | Describe                                   |
| :---------- | :--------- | :------------------------------------------ |
| `email`      | `string` | **Mandatory**. User email of your choice (does not have a validator)  |
| `password`      | `string` | **Mandatory**. Password of your choice (does not have a validator)  |


#### Login 

```curl
  POST /login
```

#### Form-data request 

| Parameter   | Type       |
| :---------- | :--------- | 
| `email`      | `string` | 
| `password`      | `string` |

Return **Bearer Token using JWT**



