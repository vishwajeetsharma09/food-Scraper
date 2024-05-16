<div align="center" id="top"> 
  <img src="./.github/app.gif" alt="FoodGrab_Scrapping" />

&#xa0;

  <!-- <a href="https://foodgrab_scrapping.netlify.app">Demo</a> -->
</div>

<h1 align="center">FoodGrab_Scrapping</h1>

<br>

where 2-CYKCVZNZJTDFLE is ‍restaurant_id‍

```
0: {id: "SGDD00739", address: {name: "Lucky Saigon - North Canal Road"},…}
address: {name: "Lucky Saigon - North Canal Road"}
businessType: "FOOD"
chainID: "729_Lucky_Saigon"
chainName: "Lucky Saigon"
estimatedDeliveryFee: {currency: {code: "SGD", symbol: "SGD", exponent: 2}, price: 300, priceDisplay: "S$3.00",…}
estimatedDeliveryTime: 30
id: "SGDD00739"
latlng: {latitude: 1.2862877, longitude: 103.84841596}
```

- you can get latitude and longitude from here, make the https://portal.grab.com/foodweb/v2/search request and https://portal.grab.com/foodweb/v2/merchants/{id} with python, but insure all of the http headers must be same with http headers that in the chrome dev tools

but since use of selenium was requested i tried a diffrent way

### Approach - 2

- So since i have to capture a XHR(XMLHttpRequest) request, i have used selenium wire for this for capturing the XHR request, i have used chrome driver for this.
- Solution Desgin

```
1. Load the python libraries needed
2. def load_more - Load the food.grab.com page and automatically activate the "Load More" button until the page contains all the restaurants in the Singapore area
3. def capture_post_response - Use driver to make a POST request for the "grab_internal_post_api" and then decode the data and store it in json format in post_data.
4. def get_restaurant_latlng - remove all the extra and keep name and location only, then store it in a list of dictionaries.
```

- Given a base_url, capture all restaurants (based on user's submitted location, e.g., sg) latitude & longitude
  by intercepting grab-foods internal POST request. self.grab_internal_post_api is found by manually inspecting all XHR made my grab-foods, using chrome dev tools.



## :rocket: Technologies

## :white_check_mark: Requirements

Before starting :checkered_flag:, you need to have [Git](https://git-scm.com) and [python](https://python.org/) installed.

## :checkered_flag: Starting

```bash
# Clone this project
$ git clone https://github.com/{{YOUR_GITHUB_USERNAME}}/foodgrab_scrapping

# Access
$ cd foodgrab_scrapping

# Setup virtual environment
$ python3 -m venv venv

# Install dependencies
$ pip install -r requirements.txt

# Run the project
$ run the project
```
