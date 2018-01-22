# MMM-SwissStationboard

This is a module for the [MagicMirror²](https://github.com/MichMich/MagicMirror/).

It displays the next departures for your favorite (train) station including delays and track change information.

This module is based on the search.ch Fahrplan API <https://fahrplan.search.ch/api/help>

Special thanks to nixnuex <https://github.com/nixnuex/MMM-SwissCommute>

## Example

![Stationboard](https://github.com/vanhoekd/MMM-SwissStationboard/blob/master/Stationboard.PNG)
## Using the module

To use this module, add the following configuration block to the modules array in the `config/config.js` file:
```js
modules: [
	{
		module: 'MMM-SwissStationboard',
		position: 'bottom_left',
		header: 'Train Connections',
		config: {
			stop: 'Zürich HB', // Start train station
			maximumEntries: 4, // Max departures displayed
			minWalkingTime: 10 // Minimum time to get to the station
		}
	},
]
```

## Configuration options

| Option           | Description
|----------------- |-----------
| `stop`        | *Required* Departure station or its ID. can by found through <https://fahrplan.search.ch/api/stationboard.json?limit=1&stop=Einsiedeln>
| `maximumEntries `        | *Optional* Maximum number of entries in list <br><br>**Type:** `int` <br>Default 10
| `minWalkingTime `        | *Optional* Minimum time in minutes to reach the `from` station. Used to highlight a connection in red in case cannot be reached in time <br><br>**Type:** `int` <br>Default -1
| `hideTrackInfo`        | *Optional* Hide the track column <br><br>**Type:** `int` <br>Default 0
