# AutoPlanet - Automated Behavior Analysis Application

Type: web application
Team: Zoey Yang, Jilian Lai, and Tasha Kim

## Overview
A fullstack web interface that utilizes machine learning to estimate mice behavior with user-defined time intervals. This application can be used if you need:
- a tool for annotating videos with user-specified animal behaviors
- an interface for initializing, training and testing behavior estimation models
- a practical method for connecting machine learning models and making predictions on new data

## Getting started
To get the Node server running locally:<br/>
1. Clone this repo<br/>
2. Paste your OAuth 2.0 credentials (client ID) at line 5 in<br/>
ui->src->components/navbar->GoogleBtn.js<br/>
3. Navigate to `ui` directory:<br/>
`npm install` to install all required dependencies<br/>
`npm start` to start the local ui server<br/>
3. Navigate to `API` directory:<br/>
`npm install` to install dependencies<br/>
`npm start` to start the backend server <br/>

## Technologies Used
- Backend: Express, Node.js, MongoDB, GraphQL
- Frontend: React.js, HTML/CSS

## Main Features
- User login/logout
- Load videos
- Add, edit, or remove annotations on video
- View summary statistics of annotations
- Save annotations to Database, as 'training' or 'testing' data
- Collect user feedback

## Design Decisions
- Authentication (third-party service, Google) for security
- Mixture of client-side and server-side rendering for efficiency
- User session: keeps track of session variables, and validates user to access parts of the app.
- File validation: checks extension and size of video upon upload. and keeps track of video's unique identifier for loading previous annotations.
- Choice of DB: MongoDB (NoSQL), for its flexibility and adaptability.
- Collections in DB: Annotations, Users, Videos. 
- UI: clean, readable UI. Not too elaborate or fancy, because it is a scientific application.
- Privacy: information collected (access tokens, Google account information, user-defined behavior tags and their corresponding time intervals) is only used in the app and not shared with third parties outside of those used to host the website and database.

## Connection to Client's API
Client will develop a backend Python API that takes inputs from our web application, performs machine learning on training data, then is able to take testing inputs from our web application to make predictions on the behavior of animals on the user-uploaded videos. When prediction outputs of the Python API is sent back to our backend, we retrieve these results and write to a downloadable CSV file that the users can then download on the 'results' page.
