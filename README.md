# BMS-API-Documentation

### API Details

|**Host**|in.bookmyshow.com/serv/getData?cmd=|
|--------|:--------:|
|**Protocol**|SSL|

### Required Cookies

|**Cookie**|**Example**|
|--------|---------|
|Rgn|Code={RegionCode}\|text={RegionName}||

### Known Endpoints
Note: All endpoints are concatenated to the host url

|Endpoint|Purpose|Parameters|Method|
|--------|--------|--------|--------|
|`QUICKBOOK&type={TYPE}`|All open bookings in a region|TYPES: MT(Movies), CT(Events), PL(Plays), SP(Sports)|GET|
|`GETPREFERREDCINEMAS`|`VenueCode` and `VenueName` for a region|NONE|GET|
|`GETSHOWTIMESBYEVENTANDVENUE&f=json&dc={DATE}&vc={VenueCode}&ec={EventCode}`|Get show times for a particular venue|`DATE` in YYYYMMDD format. `VenueCode` & `EventCode` obtained from `GETPREFERREDCINEMAS` and `QUICKBOOK` methods respectively|GET|
|`GETSHOWINFO&vid={VenueCode}&ssid={SessionID}`|Get seat info|`VenueCode` is obtained from `GETPREFERREDCINEMAS` and `SessionID` is obtained from `GETSHOWTIMESBYEVENTANDVENUE` method|GET|


MovieURL Pattern:
`https://in.bookmyshow.com/buytickets/{EventURL}-{CITY}/movie-{CITY}-{EventCode}-MT/{DATE}`