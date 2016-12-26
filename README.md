# Cordova Sensors Plugin
## Extended the cordova sensor plugin to work based on the `TYPE_SENSOR` being an integer, instead of a string.

At this moment this plugin is implemented only for Android!

## Install

    $ cordova plugin add https://github.com/theiotsuitcase/cordova-plugin-sensors.git

## Methods    

#### sensors.enableSensor(TYPE_SENSOR) // Integer

Enable sensor.

#### sensors.disableSensor()

Disable sensor.

#### sensors.getState(sucessCallBack)

Get values sensor.

## Using in Ionic

```js
  APP.controller("indexController", function ($scope, $interval){

      function onSuccess(values) {
          $scope.state = values[0];
      };

      document.addEventListener("deviceready", function () {
        
        sensors.enableSensor(1);

        $interval(function(){
          sensors.getState(onSuccess);
        }, 100);


      }, false);

  });
```

## Type sensors

You can get the type of sensors from the plugin : https://github.com/theiotsuitcase/cordova-plugin-sensorlist


For more information about sensors **Android** see [Android Sensors Overview](http://developer.android.com/guide/topics/sensors/sensors_overview.html)