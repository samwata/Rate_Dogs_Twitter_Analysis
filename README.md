# We Rate Dog Twitter Analysis

The dataset that you will be wrangling (analyzing and visualizing) is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs. WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. Some of the ratings almost always have a denominator of 10 and we are going to find out why :)

I will we were provided the following three datasets.

1. Enhanced Twitter Archive

The WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets. One column the archive does contain though: each tweet's text, which was used to extract rating, dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo) to make this Twitter archive "enhanced."


2. Additional Data via the Twitter API

This additional data can be gathered by anyone from Twitter's API. Well, "anyone" who has access to data for the 3000 most recent tweets, at least. But I, because I have the WeRateDogs Twitter archive and specifically the tweet IDs within it, can gather this data for all 5000+.

3. Image Predictions File

One more cool thing: every image in the WeRateDogs Twitter archive have been ran through a neural network that can classify breeds of dogs*. The results: a table full of image predictions (the top three only) alongside each tweet ID, image URL, and the image number that corresponded to the most confident prediction (numbered 1 to 4 since tweets can have up to four images).


#### Data Gathering
Imported Enhanced Twitter Archive using Pandas
Used Request to import Image Prediction File through its URL
Twitter API was used to query WeRateDogs handle using Tweepy to gathher the Additional Data via the Twitter API
Data Assesing
This was done virtually and programmatically to assess what has to be cleaned in the data.

#### Data Cleaning
The following are issues encountered and cleaned for proper analysis and visualization:

**Data Quality Issues**
1. Twitter Archive Data
- Retweets columns are present.
- `tweet_id` is an integer.
- Dog stages columns `doggo`, `floofer`, `pupper`, and `puppo` contains `None`, instead of `NaNs`.
- Dog name also containes `None` instead of `NaNs`.
- `timestamp` is object datatype.
- Extract the text from source column

2. Image Predictions Data
- `p1`, `p2` and `p3` contains some entries that are lower cased and some contains underscore.

3. Twitter API Data
- `tweet_id` is an integer instead of string.

**Tidiness Issues**
- 4 different dog stages (doggo, floofer, pupper, puppo) that can just be in a column.
- The 3 dataframes sould be merged into one.

### Data Analysis
The insights gotten are

1. The most used kind of device for tweeting
2. Which dog stage is tweeted the most
3. The most liked dog stage
4. Dog stages that are retweeted the most
5. Correlation between favorite count and retweet count
