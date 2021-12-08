# motreminder
MOT reminder program using Python and the MOT API from the DVSA.

We need to create an excel or csv file with vehicle registrations and their corresponding email IDs and/or mobile numbers. The registrations data will be used to extract their corresponding MOT data from the MOT database. The email ID and mobile number will be used to send an email and/or text reminder to the owner if their MOT is expiring soon.

The MOT data is extracted from the MOT database using the API provided by the DVSA. The API can be requested by going on the following link: https://dvsa.github.io/mot-history-api-documentation/ and completing the application form on that page.

The program uses the API to extract the data and filters it for the given vehicle registrations in the excel file. The file is stored as a pandas dataframe in the program and a new column is added which shows how many days are left for each vehicle before their MOT expires.

The program then checks if the days left are less than 30 and if true, it sends an email and text reminder. The email is sent using the smtplib library. The text message can be sent using Twilio or the boto3 library from AWS.

The script is set to loop every 24 hours so that it can account for any new vehicles that fall under the < 30 days left filter.
