# CODECAMP
Module for creating codecamps:
* set of selected workshops and/or existing codecamps
* codecamp app
  * consists of many [workshops](https://github.com/wizardamigos/workshop/blob/master/README.md) displayed in an iframe
  * duration of a codecamp (1 day? 1 month?) - how much time does the learner need to get through all the workshops in this codecamp
* landing page
  * logo, 
  * list of organiser(s), 
  * starting date and location (if codecamp is organised as a local open event)
  * application form (if needed)

## module
```javascript
// [codecamp.js]
const bel = require('bel')
module.exports = function codecamp (codecampJson) {
  return bel`<div>${codecampJson}</div>`
}
```

## examples
### 1. wizardamigos 1 month codecamp in Taipei (6.1.-4.2.2018)
```javascript
// [codecamp.json]
{
  "title": "wizardamigos",
  "icon": "./logo.svg",
  "topics": {
    "JavaScript": [
      'github.com/serapath/workshop_app_js_variables',
      'github.com/serapath/workshop_app_js_functions',
      'github.com/serapath/codecamp_js_prototypes_and_closures',
      ...
    ],
    "SelfEmployment": [
      'github.com/ninabreznik/workshop_app_company',
      'github.com/ninabreznik/workshop_app_remote_work',
      'github.com/ninabreznik/workshop_app_co_owner_ship',
      ...
    ],
    "dat": {
      'github.com/derhuerst/codecamp_app_dat'
      ...
    }
  }
}
```
```javascript
var app = require('codecamp')
var codecamp = require('./codecamp.json')
// var theme = require('./theme.js')
var el = app(codecamp/*, theme */)
document.body.appendChild(el)
```
### 2. dat
* ...

### 3. choo
* ...
