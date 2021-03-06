# autodbg

A JavaScript debugger/REPL for Apple UI Automation.  It has been tested against iOS 6 and 7.

## Purpose

The UI Automation framework Apple provides does not come with a debugger.  The best you can do when debugging your JavaScript is to use UIALogger.logDebug (and friends) to print messages to the Instruments console.
This is limited and time-consuming.  The purpose of this project is to develop a debugger that can be used with Apples UI Automation framework.

## Installing

Clone the repository to your system, open a terminal, navigate to the repo, and enter the following command:

    ./install.sh

This will install the debugger.  To uninstall, simply enter:

    ./uninstall.sh

## Usage

1. Import debugger.js into your JavaScript source file.

        #import "debugger.js"

2. Call eval(breakpoint()); in your test where you would like to have a breakpoint.  You can add as many breakpoints as you want.  You can also optionally name them.

        eval(breakpoint());
        eval(breakpoint('my_breakpoint'));
        eval(breakpoint(123));

3. Start a debug session by opening a terminal and entering:

        autodbg

4. Run your automation test as usual.  When a breakpoint is hit, the terminal you launched the debugger in (in step #3) will allow you to enter JavaScript code to execute.  You will know its OK to start entering code in the debugger when you see a right arrow ```>``` appear.

When your ready to continue execution of your test, type ```cont``` in the debugger.

## FAQ

Q: I receive the following debug message when I execute my script: ```Debugger error: python: can't open file '/usr/local/bin/debugframe.py': [Errno 2] No such file or directory.```

A: Make sure you run the installation script first.  See the **Installing** section for details.

Q: I receive the following debug message when I call eval(breakpoint()): ```Debugger error: [Errno 61] Connection refused```

A: You may see this message if you have not started a debugging session or killed an existing one.  See the **Usage** section of this README for details on how to launch the debugger.

Q: Do I have to restart the debugger between test runs?

A: No, when a test completes, you may leave the debugger running.

## Contributing

If you would like to contribute, please fork the project, make your changes on a branch, and submit a pull request.

## License

MIT License.

Please see LICENSE for details.