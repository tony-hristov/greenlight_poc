# Greenlight POC

Adjust the dependency to Greenlight SDK into `greenlight_plugin/android/build.gradle`:

```sh
buildscript {
    repositories {
        maven {
            url "https://dl.cloudsmith.io/XXXXXXXXXX/alkami/vendor/maven/"
            credentials {
                username = "USERNAME"
                password = "PASSWORD"
            }
        }
...

dependencies {
    implementation "org.jetbrains.kotlin:kotlin-stdlib-jdk7:$kotlin_version"
    implementation "me.greenlight:partner:2.1.1"
...
```

Edit file `greenlight_plugin/lib/constants.dart` and replace the value
of `kGLTokenValue` with valid proper user Staging token.

To adjust the release/debug gradle rules edit file `greenlight_poc/android/app/build.gradle`.

To adjust the proguard rules edit file `greenlight_poc/android/app/proguard-rules.pro`.

Run in debug mode:

```sh
cd greenlight_poc
flutter clean && flutter pub get
flutter devices # get the device id from here
flutter run -d YOUR_DEVICE_ID_HERE --debug
```

Run in release mode:

```sh
cd greenlight_poc
flutter clean && flutter pub get
flutter devices # get the device id from here
flutter run -d YOUR_DEVICE_ID_HERE --release
```

