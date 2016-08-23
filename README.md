# keenio-sample

This is a very simple application that illustrates the use of the [Keen.io connector](https://github.com/scriptrdotio/keenio).
The implemented scenario is as follows: From an HTML page, end users can select a location and rate the quality of its services by pressing one of the "good", "average" or "bad" icons on the page. These values, along with the corresponding location, are sent in real-time to Keen.io. Reporting is also obtained via different scripts that determine:
- The percentage of good, average and bad results per location, 
- The location that has the best rating 
- The llocation that has the worse evaluations
- Ratings for all locations

# Application's components

- analytics: the main script that contains function to send rating events to, respectively run queries on, Keen.io using the connector
- api/addRating: API script that uses "analytics" to send a rating event to Keen.io
- api/getRatings: API script that uses "analytics" to return the ratings at a given location
- api/getBestVenue: API script that uses "analytics" to return the venue that has the highest ratings
- api/getWorseVenue: API script that uses "analytics" to return the venue that has the lowest ratings
- api/report: API script that uses "analytics" to return the ratings of all venues
- view/survey.html: very simple HTML used as a User Interface (entry point)
- view/charts: scriptr.io chart script used by the former HTML page to display the ratings

# Dependencies

- This sample application uses the [Keen.io connector](https://github.com/scriptrdotio/keenio) that needs to be deployed on your account (from your scriptr.io workspace)
- You will also need to sign-up to an account at Keeni.io and create a project

# How to use

- Deploy the Keen.i connector to your scriptr.io account
- In the "keenio/analytics" script, replace "YOUR_KEENIO_PROJECTKEY" with the actual key of hyour Keen.io project in 
``
var keenio = new keenioclient.Keenio("YOUR_KEENIO_PROJECTKEY"); 
``
- From a browser, open the HTML page: http://iotdemos.scriptrapps.io/keeniosample/view/survey.html
