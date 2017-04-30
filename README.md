# POE LiveSplit Component
Load screen time removal and auto splitting for Path of Exile speedrunning.

## Auto Splitting
Upon entering the first zone in an act for the first time (excluding Twilight Strand on Normal difficulty), the timer will automatically split. This can be used to track progress across acts without the inconvenience of having to manually trigger a split. Note that runs will most likely still have to be ended by the player as races typically do not end on zone entrances but on boss kills or reaching a specific level.

[Demonstration](http://i.imgur.com/at31aiP.gif)

## Load Removal
Load screen time is automatically subtracted from your run. This is done by reading the timestamps on client logs.

### Timer accuracy
The pausing and unpausing of the game timer is an illusion with respect to time calculation. The calculation is done simply by using the LiveSplit real time timer (which was never paused) and subtracting the load times calculated with client log timestamp intervals. As such, any timer inaccuracies can only be from LiveSplit itself or from the timestamps GGG provides. File read latency plays no role in the final time.

The lines in the log file that are used as basis for load screen start and end are "Got Instance Details" and "Entering area..." respectively. From testing, the logs report that I have entered an area slightly before my load screens are finished. Unfortunately, this is the last line the log file reports and may lead to an overestimation of game time. Surprisingly, /played is even more unforgiving and reports my loadscreens as even shorter than they really are.

[Demonstration](http://i.imgur.com/v3BaEQY.gif)

## Setup
1. Go to the official LiveSplit [download page](http://livesplit.org/downloads/) and download the latest development build (the second link)
2. Extract the zip file and run the LiveSplit application executable
3. Right click on the timer and select "Edit Splits"
4. Type "Path of Exile" as the Game Name and click the Activate button below the number of attempts
5. To disable Auto Splitting or Load Removal, click the Settings button

Note that splits are not automatically created for you when Auto Splitting is enabled as LiveSplit components don't have the ability to do this. The Auto Splitter will split on first act zones so if you set up your splits to be A1N, A2N for example, you will move onto your second segment once you enter Southern Forest.

## Additional Setup Instructions for Load Removal
Follow these additional instructions if you want to use load removal.

6. Right click on the timer and select "Edit Layout"
7. Click the Layout Settings button
8. Go to Timer -> Timing Method, select Game Time and then press OK
9. Click the + icon in the layout editor and select Timer -> Timer and then click OK

You now have two timers: the top timer uses Game Time (subtracting load screens) and the bottom uses Real Time.

For issues and suggestions, please use https://github.com/brandondong/POE-LiveSplit-Component/issues.