# VandyHacks Capital One Income Visualization

**Summary**
We used the [Capital One API](http://api.reimaginebanking.com) and the [Google Chrome's WebGL Globe](https://www.chromeexperiments.com/globe) in order to visualize the Capital One's data. We used the [Google Maps API](https://developers.google.com/maps/) in order to convert a customer's location from Capital One's API into latitudes and longitudes and used the income of the customer from Capital One's API as the height on the WebGL Globe. 

**Inspiration**
Our inspiration for this idea came from the scope of mock Customer data present in Capital One's API. With 50,000 people spread to the ends of the globe, our first thought was "How would this data look if it was plotted globally?". Naturally, we did not want to plot the latitude, longitude, and magnitude (income) of each customer individually, so we created an application that does it for us.

**What it does**
Income Visualization utilizes the mock Customer data present within Capital One's API and WebGL to create a 3D globe with customer location and income represented visually, with a persons given balance in their account as the data's magnitude. You could apply this method of data visualization to a variety of data sets and represent the data in a variety of different formats.

**How we built it**
We first obtained our data from Capital One's Customer API, which returned a customer ID and address information. We then used the ID to map the address to that customer's balance, which was found by the Accounts API. From there, we plugged the address into Google's Geocoding API which returned longitude and latitude data. Once we obtained that, we were able to loop through all accounts to obtain a JSON containing user location and balance data, and fed that into the WebGL 3D globe visualization.

**Challenges we ran into**
For the data gathering side of the project, the main challenge was obtaining any significant amount of data from Google's Geocoding API, as there was a requests per second limit, normally around ten. For some reason, our project had an unusually low limit, so even when exceeding two requests per second we got denied further requests, and as a result were not able to obtain all ~57000 addresses. We ended up getting only around 700 people in the Northeast in the end. When it came to plotting the data with WebGL, we came across many problems including the readme not working initially, lack of online support for the project, scaling problems with the magnitude of the data, and the data on the globe not being changed even when replaced with a different JSON. Overall, it took around twelve hours to get everything in order with the globe visualization.

**Accomplishments that we're proud of**
We're proud of linking several different API's together to obtain a solid output, as well as being able to utilize WebGL to give a stylish representation of our data.

**What we learned**
How to fully utilize a given API, how WebGL's library can be used for visualization, and how to properly use Google Developer Console. Working around API request limits was also very informative.

**What's next for Income Visualization**
We are currently working on integrating Income Visualization with Microsoft Face API. The result would be an application that can identify a customer and retrieve their data using only the customer's face.

