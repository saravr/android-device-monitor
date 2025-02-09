# Introduction
Purpose of this library is to collect and report certain device level data that can be embedded into analytics, displayed in a status menu, so on.

This library will be further enhanced to collect and report more data useful for debugging and analysis.

# How to use

Add the gradle dependency as follows

```
repositories {
    maven { url = uri("https://jitpack.io") }
}
dependencies {
    implementation "com.sandymist.android:devicemonitor:0.0.1" // replace version as needed
}
```

Collect from flow as below
```
deviceMonitor.deviceMonitorFlow
    .collectLatest {
        data = it // JSON data in string format
    }
```

# Data

The information reported is serialized monitoring data. For example,

```
    {
      "audioStatus" : {
        "device" : "Phone Speaker"
      },
      "networkStatus" : {
        "isInAirplaneMode" : false,
        "availableConnectionStatus" : {
          "usingVPN" : false,
          "isValidated" : true,
          "isBehindCaptivePortal" : false,
          "isNotMetered" : true,
          "usingCellular" : false,
          "usingWiFi" : true
        },
        "activeConnectionStatus" : {
          "usingVPN" : false,
          "isValidated" : true,
          "isBehindCaptivePortal" : false,
          "isNotMetered" : true,
          "usingCellular" : false,
          "usingWiFi" : true
        },
        "since" : 0
      },
      "powerStatus" : {
        "isDeviceIdleMode" : false,
        "isPowerSaveMode" : false
      }
    }
```
