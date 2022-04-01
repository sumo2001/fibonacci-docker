# fibonacci-docker
![image](https://user-images.githubusercontent.com/51809378/161189642-d4869eba-9bcb-4c96-b1df-717e6d1195e6.png)

This is a fibonacci based dockeraized application, where the home page presents you the fibonaaci value based on the index passed, and even the UI shows your previous index search history, so this is application is more focused about docerizing a complex application

 - ![image](https://user-images.githubusercontent.com/51809378/161189178-9bd514e6-9f80-481a-9065-d28570792ade.png)


## The Architecture Explained:
- The application contains of server, client and worker on top of them we have a nginx application running to recieve and process oour requests
- We will have a react server for nice little GUI to take input from the end user
- We will have an Express server to do manage all the api calls to respond and reply back accordingly
- We will have a postgres and redis server in the back ground, to store our input indcies and the values of the indicies given
- The postgres will store all the indcies we passed
- The redis will store all the indicies and value the index
- Once again, I am making this as a complex application, bare with me
- As soon the input is given the react server will pass it to the express server, the server will save a copy of index in postgres server, and another copy will be sent to redis, as a soon redis recieves the copy of a indice, a worker node will kickin, and calculates the value of the index given and updates it the redis
- The Express server pulls up values from postgres and redis and passes them to react server as soon as we refresh
- ![Screenshot from 2022-04-01 08-35-44](https://user-images.githubusercontent.com/51809378/161188966-7cab56de-fd26-45d6-9c44-9d8accdf55c8.png)



## To install
- Assuming you have your docker configured on your machine
- Steps :
   - git clone https://github.com/sumo2001/fibonacci-docker.git
   - cd fibonaaci-docker
   - docker-compose up
   - open your local browser and type in localhost:3050
   - Pass in your index you wanna find out and submit it
   - Refresh the page
   - **Indices I have seen is from postgres db and the calculated values from the redis db**
  
![image](https://user-images.githubusercontent.com/51809378/161122621-ceb0787d-83bb-4b82-93ff-a66f0474bca3.png)
