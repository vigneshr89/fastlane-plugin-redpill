# A Fastlane Plugin for running Bluepill

## Getting Started

This project is a [fastlane](https://github.com/fastlane/fastlane) plugin. To get started with `redpill`, add it to your project by running:

```bash
fastlane add_plugin redpill
```

## About Bluepill

[Bluepill](https://github.com/linkedin/bluepill) is powered by LinkedIn. By using this plugin, you can run iOS tests in parallel using multiple simulators.

## Example

Here is some example code with all the available options listed. Not all are required; see Bluepill's docs for details and defaults:

```ruby
lane :test do

  # do any build phase work required before running redpill. For instance, consider using
  # scan to create an xctestrun file...

  redpill(

    # The path to the host application to execute (your .app)
    app: 'path/to/SomeApp.app',

    # The path to the .xctestrun file that xcode leaves when you build-for-testing.
    xctestrun_path: 'path/to/SomeApp.xctestrun',

    # Directory where to put output log files (bluepill only)
    output_dir: 'path/to/logs',

    # On which device to run the app.
    device: 'iPhone 6',

    # Exclude a testcase in the set of tests to run (takes priority over include).
    exclude: ['SomeApp/SomeTestSuite/testSomeCase'],

    # Run in headless mode (no GUI).
    headless: false,

    # Path to xcode app.
    xcode_path: `xcode-select -p`,

    # Include a testcase in the set of tests to run (unless specified in exclude).
    include: ['SomeApp/SomeTestSuite/testSomeCase'],

    # Print test timing information in JSON format.
    json_output: false,

    # Print results in JUnit format.
    junit_output: true,

    # Only list tests in bundle
    list_tests: false,

    # Number of simulators to run in parallel
    num_sims: 4,

    # Print results in plain text.
    plain_output: false,

    # Number of times to recover from simulator/app crashing/hanging and continue running
    error_retries: 5,

    # Number of times to retry on test failures
    failure_tolerance: 0,

    # When failure_tolerance > 0, only retry tests that failed
    only_retry_failed: false,

    # What runtime to use.
    runtime: 'iOS 11.1',

    # Timeout in seconds for a test that seems stuck (no output).
    stuck_timeout: '300s',

    # Timeout in seconds for a test that is producing output.
    test_timeout: '300s',

    # Number of times we'll run the entire test suite (used for load testing).
    repeat_count: 1,

    # Enable reusing simulators between test bundles
    reuse_simulator: false

    # Enable collection of diagnostics in outputDir in case of test failures
    diagnostics: false,

    # Directory where simulator screenshots for failed ui tests will be stored
    screenshots_directory: 'path/to/screenshots',

  )

end
```

## Issues and Feedback

For any other issues and feedback about this plugin, please submit it to this repository.

## Troubleshooting

If you have trouble using plugins, check out the [Plugins Troubleshooting](https://docs.fastlane.tools/plugins/plugins-troubleshooting/) guide.

## Using `fastlane` Plugins

For more information about how the `fastlane` plugin system works, check out the [Plugins documentation](https://docs.fastlane.tools/plugins/create-plugin/).

## About `fastlane`

`fastlane` is the easiest way to automate beta deployments and releases for your iOS and Android apps. To learn more, check out [fastlane.tools](https://fastlane.tools).

## License of Bluepill

BSD 2-CLAUSE LICENSE

Copyright 2016 LinkedIn Corporation.
All Rights Reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
