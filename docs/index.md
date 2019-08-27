Documentation Version: `3.7.0`

# Website

[Nice Sex Tracker](https://nicetracker.app)

## URL Scheme
You can access Nice Tracker via the URL Scheme:
```
nicetraker://
```

You can add a new entry by using the `add` host:
```
nicetraker://add
```

<h3>URL Parameters</h3>

|parameter| required | value | description |
|:---|:---:|:---:|:---|
|`activities`|Y| string |comma delimited, url encoded, list of activities' names |
|`date`|Y| string |`now` or in the format of `yyyy-MM-dd-HH-mm` |
|`partners`| | string | comma delimited, url encoded, list of partners' names |
|`duration`| | integer | number of minutes |
|`protection`| | integer | `1` = used, `0` = not used |
|`note`| | string | url encoded string of a note |
|`icon`| | string | name of the entry's icon |
|`location`| | string | name of a saved location |
|`latitude`| | decimal | latitude of location |
|`longitude`| | decimal | longitude of location |
|`orgasms`| | integer | number of orgasms |
|`partnerOrgasms`| | integer | number of partner orgasms |
|`rating`| | integer | rating score 1-5 |

**Note:** If `location` is set, then `latitude` and `longitude` will be _ignored_.
**Note:** You can only add `partners` and `activities` that currently exist within the app.

<h3>URL Examples</h3>
Example of adding 5 minutes if sex now
```
nicetracker://add?activities=sex&date=now&duration=5
```

Example of adding multiple activities
```
nicetracker://add?activities=sex,hand%20job,oral&date=2018-04-20-16-20&protection=0&duration=17
```

## JSON Backup
The backup JSON can be used to bulk import or edit your Nice Tracker database.

Backup files will be exported with a name in the format of: `nice-data-YYYY-MM-dd-HHmmss.json`

Please know that restoring from a backup JSON file, that all existing data will be removed and replaced with the data in the JSON file.

The format of the backup JSON file looks like:
```
{
    "version":"x.x.x",
    "activities":[
        // array of activity objects
    ],
    "partners":[
        // array of partner objects
    ],
    "locations":[
        // array of location objects
    ],
    "entries":[
        // array of entry objects
    ]
}
```

<h4>Entry JSON Object</h4>

|parameter| required | value | description |
|:---|:---:|:---:|:---|
|`activities`|Y| array of objects | array of short activity objects |
|`date`|Y| string |`now` or in the format of `yyyy-MM-dd-HH-mm` |
|`partners`| | array of objects | array of short partner objects |
|`duration`| | integer | number of minutes |
|`protection`| | boolean | `true` = used, `false` = not used |
|`note`| | string | note for the entry |
|`icon`| | string | name of the entry's icon |
|`location`| | object | location object |
|`orgasms`| | integer | number of orgasms |
|`partnerOrgasms`| | integer | number of partner orgasms |
|`rating`| | integer | rating 1-5 |

<h4>Activity JSON Object</h4>

|parameter| required | value | description |
|:---|:---:|:---:|:---|
|`name`|Y| string | unique activity name |
|`icon`|Y| string | name of icon |

**Note:** The short version of the activity object only includes the `name` parameter.

<h4>Partner JSON Object</h4>

|parameter| required | value | description |
|:---|:---:|:---:|:---|
|`name`|Y| string | unique partner name |
|`birthday`| | string | DOB in the format of `yyyy-MM-dd` |
|`sexInt`| | integer | `0` = Male, `1` = Female, `2` = Other |
|`image`| | string | base64 encoded string of png image data |
|`note`| | string | note for the partner |

**Note:** The short version of the partner object only includes the `name` parameter.

<h4>Location JSON Object</h4>

|parameter| required | value | description |
|:---|:---:|:---:|:---|
|`name`|Y| string | unique location name |
|`latitude`|Y| decimal | valid latitude |
|`longitude`|Y| decimal | valid longitude |

**Note:** In an entry object with a custom location that isn't added to the `locations`, then `latitude` and `longitude` parameters will exist, otherwise only the `name` parameter will exist.

## Siri Shortcuts

You can add now add new entries through Siri. You can do this two different ways: Through the built in Nice Sex Tracker shortcut, or through the open URL shortcut.

<h4>Nice Tracker Shortcut</h4>
Open the Shortcuts app and tap 'Create Shortcut'. Search for the Nice app in the search field and select the `New Nice Entry` shortcut.

**Note:** This shortcut only works if you have at least one default activity set inside the app.

![Nice Siri Shortcut](https://res.cloudinary.com/scottjulian/image/upload/v1541005961/nicetracker/nice-siri-shortcut.png)

<h4>URL Shortcut</h4>
Open the Shortcuts app and tap 'Create Shortcut'. Then select the 'URL' option under the 'Web' section.

Refer to the [URL Scheme Documentation](#url-scheme) to build your shortcut URL.

![Nice Siri Shortcut URL](https://res.cloudinary.com/scottjulian/image/upload/v1541005961/nicetracker/nice-siri-shortcut-url.png)

<h4>Add to Siri</h4>
After you have created the shortcut, be sure to edit the shortcut options to 'Add to Siri'. You can then record whatever voice phrase to whatever you want, e.g. "I just had sex!".

![Add to Siri](https://res.cloudinary.com/scottjulian/image/upload/v1541006400/nicetracker/siri-record.png)

## Available Icon Names

| | | | |
|--|--|--|--|
| thong | asterisk | lips | hand |
| self-hand | heart | star | condom |
|bra|heel|cherry|hotdog|
|flower|fire|boobs|vagina|
|penis|woman|man|orgy|
|fortune|beer|wine|handcuffs|
|mountains|tent|bath|strawberry|
|foot|goo|rope|briefs|
|dice|present|mask|sun|
|moon|butt|plug|exclamation|
