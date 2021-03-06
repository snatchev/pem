<h3 align="center">
  <a href="https://github.com/fastlane/fastlane">
    <img src="assets/fastlane.png" width="150" />
    <br />
    fastlane
  </a>
</h3>
<p align="center">
  <a href="https://github.com/fastlane/deliver">deliver</a> &bull; 
  <a href="https://github.com/fastlane/snapshot">snapshot</a> &bull; 
  <a href="https://github.com/fastlane/frameit">frameit</a> &bull; 
  <b>pem</b> &bull; 
  <a href="https://github.com/fastlane/sigh">sigh</a> &bull; 
  <a href="https://github.com/fastlane/produce">produce</a> &bull;
  <a href="https://github.com/fastlane/cert">cert</a> &bull;
  <a href="https://github.com/fastlane/spaceship">spaceship</a> &bull;
  <a href="https://github.com/fastlane/pilot">pilot</a> &bull;
  <a href="https://github.com/fastlane/boarding">boarding</a> &bull;
  <a href="https://github.com/fastlane/gym">gym</a> &bull;
  <a href="https://github.com/fastlane/scan">scan</a> &bull;
  <a href="https://github.com/fastlane/match">match</a>
</p>
-------

<p align="center">
  <img src="assets/pem.png" height="110">
</p>

pem
============

[![Twitter: @KauseFx](https://img.shields.io/badge/contact-@KrauseFx-blue.svg?style=flat)](https://twitter.com/KrauseFx)
[![License](https://img.shields.io/badge/license-MIT-green.svg?style=flat)](https://github.com/KrauseFx/pem/blob/master/LICENSE)
[![Gem](https://img.shields.io/gem/v/pem.svg?style=flat)](http://rubygems.org/gems/pem)

###### Automatically generate and renew your push notification profiles

Tired of manually creating and maintaining your push notification profiles for your iOS apps? Tired of generating a `pem` file for your server? 

`pem` does all that for, just by running `pem`.

To automate iOS Provisioning profiles you can use [sigh](https://github.com/fastlane/sigh).

Get in contact with the developer on Twitter: [@KrauseFx](https://twitter.com/KrauseFx)

-------
<p align="center">
    <a href="#features">Features</a> &bull; 
    <a href="#installation">Installation</a> &bull; 
    <a href="#usage">Usage</a> &bull; 
    <a href="#how-does-it-work">How does it work?</a> &bull; 
    <a href="#tips">Tips</a> &bull; 
    <a href="#need-help">Need help?</a>
</p>

-------

<h5 align="center"><code>pem</code> is part of <a href="https://fastlane.tools">fastlane</a>: connect all deployment tools into one streamlined workflow.</h5>

# Features
Well, it's actually just one: Generate the ```pem``` file for your server.


Check out this gif:

![assets/PEMRecording.gif](assets/PEMRecording.gif)

# Installation
    sudo gem install pem

Make sure, you have the latest version of the Xcode command line tools installed:

    xcode-select --install

# Usage

    pem

Yes, that's the whole command!

This does the following:

- Create a new signing request
- Create a new push certification
- Downloads the certificate
- Generates a new ```.pem``` file in the current working directory, which you can upload to your server

```pem``` will never revoke your existing certificates. 

If you already have a push certificate enabled, which is active for at least 30 more days, `pem` will not create a new certificate. If you still want to create one, use the `force`:

    pem --force

You can pass parameters like this:

    pem -a com.krausefx.app -u username

If you want to generate a development certificate instead:

    pem --development

Set a password for your `p12` file:

    pem -p "MyPass"

You can specify a name for the output file:

    pem -o my.pem

To get a list of available options run:

    pem --help
    

##### [Like this tool? Be the first to know about updates and new fastlane tools](https://tinyletter.com/krausefx)

## Environment Variables

Run `pem --help` to get a list of available environment variables.

# How does it work?

`pem` uses [spaceship](https://spaceship.airforce) to communicate with the Apple Developer Portal to request a new push certificate for you.

## How is my password stored?
```pem``` uses the [password manager](https://github.com/fastlane/credentials_manager) from `fastlane`. Take a look the [CredentialsManager README](https://github.com/fastlane/credentials_manager) for more information.

# Tips

## [`fastlane`](https://fastlane.tools) Toolchain

- [`fastlane`](https://fastlane.tools): Connect all deployment tools into one streamlined workflow
- [`deliver`](https://github.com/fastlane/deliver): Upload screenshots, metadata and your app to the App Store
- [`snapshot`](https://github.com/fastlane/snapshot): Automate taking localized screenshots of your iOS app on every device
- [`frameit`](https://github.com/fastlane/frameit): Quickly put your screenshots into the right device frames
- [`sigh`](https://github.com/fastlane/sigh): Because you would rather spend your time building stuff than fighting provisioning
- [`produce`](https://github.com/fastlane/produce): Create new iOS apps on iTunes Connect and Dev Portal using the command line
- [`cert`](https://github.com/fastlane/cert): Automatically create and maintain iOS code signing certificates
- [`spaceship`](https://github.com/fastlane/spaceship): Ruby library to access the Apple Dev Center and iTunes Connect
- [`pilot`](https://github.com/fastlane/pilot): The best way to manage your TestFlight testers and builds from your terminal
- [`boarding`](https://github.com/fastlane/boarding): The easiest way to invite your TestFlight beta testers 
- [`gym`](https://github.com/fastlane/gym): Building your iOS app has never been easier
- [`scan`](https://github.com/fastlane/scan): The easiest way to run tests of your iOS and Mac app
- [`match`](https://github.com/fastlane/match): Easily sync your certificates and profiles across your team using git

##### [Like this tool? Be the first to know about updates and new fastlane tools](https://tinyletter.com/krausefx)

## Use the 'Provisioning Quicklook plugin'
Download and install the [Provisioning Plugin](https://github.com/chockenberry/Provisioning).

It will show you the ```pem``` files like this: 
![assets/QuickLookScreenshot.png](assets/QuickLookScreenshot.png)


# Need help?
Please submit an issue on GitHub and provide information about your setup

# License
This project is licensed under the terms of the MIT license. See the LICENSE file.

> This project and all fastlane tools are in no way affiliated with Apple Inc. This project is open source under the MIT license, which means you have full access to the source code and can modify it to fit your own needs. All fastlane tools run on your own computer or server, so your credentials or other sensitive information will never leave your own computer. You are responsible for how you use fastlane tools.
