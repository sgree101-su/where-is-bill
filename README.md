## Where Is Bill?

Bills don't turn laws in one day!

###### [Check out Jarrod demo!](https://vimeo.com/246520840)


###### Project Overview: 
Bills do not turn laws in one day! Where is Bill? is a python program designed to track and find more information about the current status of a bill. The complex lawmaking process often makes it complicated for constituents to remain informed on latest proposed legislation. Has the bill been voted by Congress? Is it sitting in a Senate Committee? Did the President of the United States veto it? Using a simple keywords search, Where is Bill? will return the most recent bill information such as its identification number, where it currently stands on the hill and offer constituents some suggestions to voice their opinion. 

###### Program Interaction:
The user will start at a menu and have to press a key to continue. It will prompt him to enter one or more keywords to start the legislation search. The program will return a list of the most recent 20 matching bills. Then, the user will have the opportunity to enter the bill identification number to track its current location. Finally, a prompt will ask the user to provide his address to find contact information about his federal elected representatives. Our goal is to give them a voice in the legislation process. 

###### Algorithm:
To code this program we will need to import some libraries (json, requests, pandas, numpy, pprint and warnings) and code 6 functions.

Bill, the logo is storred in the function window for clarity purposes. 

The class color is defined to allow bold text. 

The first function we have to define is getrecentbill(query). It will connect to [ProPublica Congress API](https://projects.propublica.org/api-docs/congress-api/) and return matched bills in a data frame using pandas, Python Data Analysis Library. We will use lists, dictionaries and iteration to index and sort the json data to fit our needs. 

The function getbillstatus(bill_id) will connect back to the [ProPublica Congress API](https://projects.propublica.org/api-docs/congress-api/) to find more about the bill latest major action and deduce its current location. 

The third function will be useraddress(). It will create a dict to store the user address. 

Then, getstateanddistrict(address) will use [SmartyStreets API](https://smartystreets.com/products/apis/us-street-api) to return data about the user district. This API was originally designed to perform address validation for mail and carrier servicesbut we realized it also returned the congressional district. Despite being limited to 250 queries, it's a great and cheap way to match address with their respective districts. 

Lastly, gethrrep(user_data) and getsenaterep(address) will match user state and congressional district to legislators-current.csv and both return their respective elected representative. This csv file was found online on the [@unitedstates/congress-legislator](https://github.com/unitedstates/congress-legislators) Github repository and contains a lot of information about the current members of Congress. We just decided to include their Last Name, First Name, State, District (if applicable), Party and Phone. 



