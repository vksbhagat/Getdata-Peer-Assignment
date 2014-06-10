By running  "run_analysis.R" script performs the following steps to clean the data:

1. Read training data and test data and then concatenate them.

2. Read the features.txt file and store the data in a variable called features. We only extract the measurements on the mean and standard deviation. This results in a 66 indices list. We get a subset of joinData with the 66 corresponding columns.

3. Clean the column names of the subset. We remove the "()" and "-" symbols in the names, as well as make the first letter of "mean" and "std" a capital letter "M" and "S" respectively.

4. Read the activity_labels.txt file and store the data in a variable called activity.

5. Clean the activity names in the second column of activity. We first make all names to lower cases. If the name has an underscore between letters, we remove the underscore and capitalize the letter immediately after the underscore.

6. Transform the values of joinLabel according to the activity data frame.

7. Combine the joinSubject, joinLabel and joinData by column to get a new cleaned 10299x68 data frame, cleanedData. Properly name the first two columns, "subject" and "activity". The "subject" column contains integers that range from 1 to 30 inclusive; the "activity" column contains 6 kinds of activity names; the last 66 columns contain measurements that range from -1 to 1 exclusive.

8. Write the cleanedData out to "merged_data.txt" file in current working directory.

9. Finally, generate a second independent tidy data set with the average of each measurement for each activity and each subject. We have 30 unique subjects and 6 unique activities, which result in a 180 combinations of the two. Then, for each combination, we calculate the mean of each measurement with the corresponding combination. So, after initializing the result data frame and performing the two for-loops, we get a 180x68 data frame.

10. Write the result out to "data_with_means.txt" file in current working directory.
