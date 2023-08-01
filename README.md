 # Browserstack
Testing a web bro
invitation link : https://accounts.browserstack.com/jointeam/bfe7a056d4144a84307e010b7211d85c
# =============================
# Set BrowserStack Credentials
# =============================
# Add your BrowserStack userName and acccessKey here or set BROWSERSTACK_USERNAME and
# BROWSERSTACK_ACCESS_KEY as env variables
userName: YOUR_USERNAME
accessKey: YOUR_ACCESS_KEY

example : 

# ======================
# BrowserStack Reporting
# ======================
# The following capabilities are used to set up reporting on BrowserStack:
# Set 'projectName' to the name of your project. Example, Marketing Website
projectName: BrowserStack Samples
# Set `buildName` as the name of the job / testsuite being run
buildName: browserstack build
# `buildIdentifier` is a unique id to differentiate every execution that gets appended to
# buildName. Choose your buildIdentifier format from the available expressions:
# ${BUILD_NUMBER} (Default): Generates an incremental counter with every execution
# ${DATE_TIME}: Generates a Timestamp with every execution. Eg. 05-Nov-19:30
# Read more about buildIdentifiers here -> https://www.browserstack.com/docs/automate/selenium/organize-tests
buildIdentifier: '#${BUILD_NUMBER}' # Supports strings along with either/both ${expression}
# Set `source` in the syntax `<fw-name>:sample-<branch-name>:<version-number>
source: jest-js:sample-main:v1.0

# =======================================
# Platforms (Browsers / Devices to test)
# =======================================
# Platforms object contains all the browser / device combinations you want to test on.
# Entire list available here -> (https://www.browserstack.com/list-of-browsers-and-platforms/automate)
platforms:
  - os: OS X
    osVersion: Big Sur
    browserName: Chrome
    browserVersion: latest
  - os: Windows
    osVersion: 10
    browserName: Edge
    browserVersion: latest
  - deviceName: Samsung Galaxy S22 Ultra
    browserName: chrome # Try 'samsung' for Samsung browser
    osVersion: 12.0

# =======================
# Parallels per Platform
# =======================
# The number of parallel threads to be used for each platform set.
# BrowserStack's SDK runner will select the best strategy based on the configured value
#
# Example 1 - If you have configured 3 platforms and set `parallelsPerPlatform` as 2, a total of 6 (2 * 3) parallel threads will be used on BrowserStack
#
# Example 2 - If you have configured 1 platform and set `parallelsPerPlatform` as 5, a total of 5 (1 * 5) parallel threads will be used on BrowserStack
parallelsPerPlatform: 1

# ==========================================
# BrowserStack Local
# (For localhost, staging/private websites)
# ==========================================
# Set browserStackLocal to true if your website under test is not accessible publicly over the internet
# Learn more about how BrowserStack Local works here -> https://www.browserstack.com/docs/automate/selenium/local-testing-introduction
browserstackLocal: true # <boolean> (Default false)

# browserStackLocalOptions:
# Options to be passed to BrowserStack local in-case of advanced configurations
  # localIdentifier: # <string> (Default: null) Needed if you need to run multiple instances of local.
  # forceLocal: true  # <boolean> (Default: false) Set to true if you need to resolve all your traffic via BrowserStack Local tunnel.
  # Entire list of arguments availabe here -> https://www.browserstack.com/docs/automate/selenium/manage-incoming-connections

# ===================
# Debugging features
# ===================
debug: false # <boolean> # Set to true if you need screenshots for every selenium command ran
networkLogs: false # <boolean> Set to true to enable HAR logs capturing
consoleLogs: errors # <string> Remote browser's console debug levels to be printed (Default: errors)
# Available options are `disable`, `errors`, `warnings`, `info`, `verbose` (Default: errors)
