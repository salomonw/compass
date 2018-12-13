## Compass

Compass is a [web-based](http://lastmile.mit.edu/compass/front/index.php?r=site/login) technology for visualizing and analyzing GPS traces of freight vehicles. Its main objective is to process and analyze GPS data in order to find out statistical information as well as display the information in a friendly way. In this service , the user is be able to have a detailed view of the behavior of the trips, trucks and fleets.

Compass is part of a bigger project, [Last Mile](http://lastmile.mit.edu/), an initiative created by the [MIT Megacity Logistics Lab](http://megacitylab.mit.edu/) that focuses on the visualization of key indicators that relate to logistics operations in megacities all over the world. 

The origin of Compass is a set of scripts written in Matlab with the objective of processing and ana-lyzing data in a more detailed way. The package contains three main scripts which are: _MAIN_PROJECT, GPS_SIGNALS_TOOL and PARAMETERS_TOOL_.

Compass uses built-in processes to clean outliers and to determine the truck's state at all times. To clean outliers Compass uses two filters: 
- When velocity exceeds 150 km/hr
- When trip duration is less than 30 min.

In regards of the state of a truck, Compass identifies three possible states:
- **Idle** defined as the state when a vehicle has passed a certain amount of time within a region. The parameters, time and distance, are set by the user. This state is the key indicator that separates one trip from another. This means that when an idle state ends a new trip begins.

- **Stop** is when a vehicle spend a certain amount of time in a delimited area. The parameters also are set by the user.
- **Traveling** is when a vehicle is not on “Idle” or “stop” state, which means that it’s moving from one place to another.

Once the cleaning and the state procedures have been made, Compass calculates several relevant statistics at three different levels: _Trip, Truck and Fleet level_.

### Technical information
Compass was developed using the _Yii_ framework programmed in _PHP_, as well as _Highcharts_, a javascript library for graphs, _PostgreSQL_ as database management system and Google maps for displaying maps.

### User interface
Compass is a system composed by two interfaces: one that manages and processes the information available on the server, called the Administration Interface, and another that displays this information through graphics, statistics and visual data, called the Main Interface. The access to the whole system, both Administration and Main Interfaces, is restricted and requires a username and password.

The main interface is divided into three main sections: _Trips, Trucks and Stats_. In the Trips section, trips are displayed in the map and information about them are shown in the Trip Information Box. On the Trucks section, the user can choose between getting information of a single truck and viewing graphs that compare data between all the trucks. Finally, in the Stats section, general statistics from the entire fleet are shown in a handy way that is useful to the user.
In the administration interface, users can upload files containing the GPS data of the trucks. Compass is built in such a way that handling data is simpler and only asks for the minimum information required, which is: Truck ID, Latitude, Longitude and Timestamp. The uploading process of this data is through a CSV file that can be made in Microsoft Excel. In this interface, users should define the time and distance parameters that best fit their fleet behavior.

If you want to learn more about the design of this project, please see [Gabriel Arrieta website](https://gabrielap.myportfolio.com/compass)
