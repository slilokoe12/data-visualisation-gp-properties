### How to view the 

1. Install all the required Python packages (libraries) with pip
`pip install -r requirements.txt`
2. Run jupyter note bookbook.
3. Run the 'Part_I_exploration_template.ipynb notebook' and restart the kennel to rerun the code for the cleaning process and and data exploration from a 
single-variable (1d) to multiple-variable (2d) explorations.
4. To see the slideshow of the findings, open the slide_deck_template.slides.html file.

# Gauteng residential properties: Effects of the property's features on price
## by (Nkhesani Lilokoe)


## Dataset

The following investigation will look at the characteristics that could be used to predict the prices of residential property that were advertised for sale (property under offer and those still waiting for interested parties) by the second week of October 2021.The variable of interest is the price and the following features will be used to form part of the investigation of what determines the price of a residential property in Gauteng: Price/m^2, type of property, number of bedrooms and of bathrooms. The study will also investigate which property type is value for more based on price/m^2 of residential property sold in surburbs with more than 200 properties in the market to see which location and property type gives value for money. The data set that we'll use contains prices and attributes of around 97000 properties that were scraped from the biggest property South African online real estate portal. Some of the key features were missing on some rows so after cleaning we are working with ~26000 properties.

Questions I will try answer: 
1.Does property type affect price?
2.Does the number of rooms (Bed and bath) affect price?
3.Does size matter? (I will use price/m^200) 
3.Does location matter?
4. Which locations gives value for money?

## Summary of Findings

-Looking at the residential property market assortment, we can see that there are more free standing houses being sold(and or bought), followed by Apartments then townhouses (houses in a complex). The data proportions are consistent in the before and after cleaning process.

-The property price distribution has a long-tailed distribution, with a lot of the properties on the low price end of around 700K-1 mil, and some dripping towards the hundred millions. To cleaned some of the outliers, I logged the prices to smooth out the skewness and I got a bell-like shape centering around the hundred thousands below 1 mil with the highest steep between 600-700 thousand. I also looked at the price per meter squared to check the disribution of propery size value. Using a bigger bin, the graph is right skewed with a bulge was around 10K per square meter with a long tail to the higher prices per m^2. I was interested in the spike that was around 4K and made a smaller bin to see if there was any significant information to note. Even with a smaller bin, properties the were around 4 thousand per m^2 had the highest peak. 

-I used bar graphs for the univariable analysis part for all of the features because after removing unrealistic rooms/spaces values, like values with point something (expect for point 5's in bathrooms and bedrooms), most were whole numbers. 0.5 bathrooms mean that there's only a toilet and not shower and or bath. And point 0.5 edrooms are studies or are used for bachelor flats. 

### Bedrooms
An average residential property in Gauteng surburbs has 3 bedrrooms, followed closely by 2 bedrooms. The least number of rooms in a property was 4.5
### Bathrooms
2 bathrooms was the average number of bathrooms in a property people call home, closely followed by 1 bathroom. 12 bathroom properties were the least.   
### Garages/ carpots area
The highest count of parking spaces in properties is 2. 
Interesting to note that the highest averages were the same pre and post cleaning. The methodology used allowed the number to go up to 12 but 11 was the least average number of bathrooms in the properties after cleaning.

### Price reduction
Whilst people who want to sell fast put their prices at ready to go pricing, some people realise after a bit of not getting interested buyers that they can benefit from a "sale' and reduce their asking offers. But that is a very small proportion as we can se below. Interested to see what proportion of "Reduced" properties go into "under offer" which was explored in the bivariant section and I found that none of the reduced houses were on under offer. Are they over priced or something is wrong with them that repels potential buyers? These are questions of interest but this study does not answer them.

Under offer properties are fewer than the ones still looking for buyers. I assumed this is normal since they remove sold houses within a week of finalization. 

### Location
Location gave interesting changes in the pre clean and post output. Bryanston had an incredible lead before I filtered most missing data and outliers. However the top 20 is still the top 20, just in a different order. As mentioned in the cleaning section, most data was entered incorrectly and more surburbs with townhouses suffered from many outliers because they account for the facilities within the complex and not what a buyer is solely entitled to, leading to very large floor size and tiny rands/m^2. After filtering, Soshanguve VV had the most properties in the market. These are the top 10 selling suburbs:'Bryanston', 'Hatfield', 'Soshanguve VV', 'Morningside','Greenstone Hill', 'North Riding', 'Soshanguve UU', 'Fourways','Sunnyside', 'Bedfordview'. 

On the day the data was extracted these were the 10 most selling (had interested buyers- under offer) surburbs:
'Bryanston', 'Blairgowrie', 'Greenstone Hill', 'North Riding','Equestria', 'Midstream Estate', 'Faerie Glen', 'Parkhurst', 'Wilgeheuwel', 'Lenasia South'],

Great multicollinearity between bedrooms and Bathroom with a Variance inflation factor of over 10 on both features. It is more likely like properties with more rooms have more bathrooms.


## Key Insights for Presentation

Free standing houses are on average more expensive than other residential properties, followed by townhouses then the least expensive being apartments. We can however notice an inverse relationship when it comes to price per square meter. Houses are the cheapest per square meter as they have bigger Erf size than the other 2 types. On the opposite end, apartments are the most expensive per square meter as they have smaller floor sizes. with townhouses in the middle but towards the higher end of the apartment prices. Free standing houses have on average 3 bedrooms and 2 bathrooms. They are the ones that influence the high frequecy of 3 bedroom and 2 bathroom residential properties which is similar to townshouses. There is also a noticeale bulge in 4 bedrooms for houese and 1 bathroom.  Apartments have a great bulge in 2 bedrooms and 1 bathroom. They do however have noticeable bulges in in 1 and 3 bedrooms and 2 bathrooms. We can say that 3 bedroom and 2 bathroom houses are cheaper in price/m^2 but are more expensive in absolute value. 

Bryanston', 'Greenstone Hill', 'North Riding' and 'Fourways' are some of the most expensive surburbs by price/m^2 but the same surburbs have the top 10 selling and bought properties. 
