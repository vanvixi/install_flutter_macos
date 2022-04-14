# Install Flutter on macOS (intel)

## Install Homebrew:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## Install FVM (Flutter Version Management):

```
brew tap leoafarias/fvm
```
```
brew install fvm
```
##### [Read the FVM documentation](https://fvm.app/)

## Install FlutterSDK:

```
fvm install flutter_version
```
`eg: fvm install 1.22.6`
## Sets Flutter SDK Version as a global:

```
fvm global flutter_version
```
`eg: fvm global 1.22.6`
## Install Java:

```
brew install java
```
```
sudo ln -sfn /usr/local/opt/openjdk/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk.jdk
```
## Install Android Studio (AS):

##### [Download and install Android Studio](https://developer.android.com/studio)

##### Opent AS

	1. Go to the: Preferences -> Appearance & Behavio -> System Settings -> Android SDK 
		-> Click tab SDK Tools -> click “Android SDK Command-line Tools” and “Android SDK Build-Tools”
		-> Apply (wait install) -> OK.

	2. Go to the: Preferences -> Plugins: search and install “Dart”, “Flutter”, “Flutter Intl”.

	3. Restart AS.

## Install Xcode:

##### Install from Mac App Store

```
sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
```
```
sudo xcodebuild -runFirstLaunch
```
```
sudo xcodebuild -license
```
```
sudo gem install cocoapods
```
## Add path to .zshrc (macOS Big Sur) file:

##### Opent .zshrc file:

```
nano .zshrc
````
##### Copy and paste:

```
export PATH="$PATH":"$HOME/.pub-cache/bin"
export PATH="$PATH":"$HOME/fvm/default/bin"
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/platform-tools
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export JAVA_HOME=$(/usr/libexec/java_home)
```
##### Save and exit (control + o -> Enter -> control + x)

##### Enter the value:

```
source .zshrc
```

## Run flutter doctor

```
flutter doctor
```

##### Fix error "Android licenses status unknown"
```
flutter doctor --android-licenses
```

##### Fix error "Unable to find bundled Java version":
```
cd /Applications/Android\ Studio.app/Contents/jre
```
```
ln -s ../jre jdk
```
```
ln -s ../jre jdk
ln -s "/Library/Internet Plug-Ins/JavaAppletPlugin.plugin" jdk
```
##### Fix error "Flutter plugin not installed" and "Dart plugin not installed":
```
ln -s ~/Library/Application\ Support/Google/AndroidStudio4.1/plugins ~/Library/Application\ Support/AndroidStudio4.1
```
