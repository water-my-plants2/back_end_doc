

#  Build Week - unit 4 - Water My Plants

## Base URL
https://watermyplants02.herokuapp.com

![Screen Shot 2021-07-26 at 9 27 35 PM](https://user-images.githubusercontent.com/55516943/127095511-2ae5a9b9-fbce-4c08-9f71-efc6d9ee797f.png)

## API endpoints

### login/register

| Auth | Endpoint           | Required                  | Restrictions | Notes                                             |
| -----| ------------------ | --------------------------| -------------| ------------------------------------------------- |
| POST | /api/auth/register | username, password, phone | Username: unique,min 3 & max 25 chars, password:min 8 & max 25 chars & phone: unique, ###-###-#### format| Creates a new user with auto Id.|
| POST | /api/auth/login    | username, password        | None         | Returns a welcome message and the JSON Web Token. |


### Users

| Auth | Endpoint              | Required            | Restrictions      -| Notes                                    |
| -----| --------------------- | --------------------| -------------------|------------------------------------------|
| GET  | /api/users/           | None                | authenticated user | Returns the specified user object.       |
| GET  | /api/users/:id        | None                | authenticated user | Returns the specified user object.       |
| GET  | /api/users/:id/plants | None                | authenticated user | Returns array of users plants.           |


### Plants

| Auth   | Endpoint        | Required            | Restrictions          | Notes                                       |
| -------| --------------- | --------------------| ----------------------| ------------------------------------------- |
| GET    | /api/plants/    | None                | authenticated user    |  Returns array of All plants.               |
| POST   | /api/plants/    | nickname, species, h2oFrequency, userId | authenticated user        | Returns new plant object. |
| PUT    | /api/plants/:id | userId, nickname, species, h2oFrequency | authenticated user        | Returns updated plant object.  |
| DELETE | /api/plants/:id | plant_id            | authenticated user | Returns deleted record if successfully deleted. |


### Detailed_endpoints

[POST] REGISTER (/api/auth/register). 
---------------------

*receives*    

{  
  username,  
  password,                                                                                                                                                       
  phone,                                                                                                                                                        
  email (optional)                                                                                                                                                 
}   

*returns*    
{   
  user_id,  
  username,  
  password   
}

[POST] LOGIN (/api/auth/login). 
---------------------

*receives*  
{  
  username,  
  password  
}

*returns*      
{  
  message,    
  token  
} 

[GET] All users *restricted* (/api/users). 
---------------------

*returns*    

[
    
    {  
        
        user_id,
        username,
        password,
        user_email,
        user_phone,
        created_at
    },  
    {  
        user_id,
        username,
        password,
        user_email,
        user_phone,
        created_at
    },  
    ...    
]   

[GET] user by ID *restricted* (api/users/:userId)   
---------------------

*returns*    

{  

    user_id,
    username,
    password,
    user_email,
    user_phone,
    created_at  
 }
 
 [GET] plants by userId *restricted* (/api/users/:userId/plants)
---------------------

*returns*  

[
    
    {
        user_id,
        username,
        plant_id,
        plant_nickname,
        plant_species,
        h2ofrequency
    },
    {
        user_id,
        username,
        plant_id,
        plant_nickname,
        plant_species,
        h2ofrequency
    }
]
    
   
Login_credential: these credentials can be used to test the login and end points, if you did not register yet                                                      
username: lambda                                                                                                                                                  
password: lambda123

