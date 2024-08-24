# The Page Object Model 

![alt text](POM_0.png)

(POM) is a design pattern commonly used in test automation, particularly for web applications. It enhances test maintenance and reduces code duplication by creating an object-oriented representation of web pages. Each page of the application is represented by a corresponding class, encapsulating the page's elements and behaviors.
Key Principles of POM
### Separation of Concerns:
POM separates the test logic from the UI representation. This means that the test scripts focus on the actions and assertions, while the page classes manage the interactions with the UI elements.
### Encapsulation:
Each page class contains methods that represent user interactions with that page (like clicking buttons, entering text, etc.) and properties that represent the page elements. This encapsulation ensures that changes in the UI require minimal changes in the test code.
### Reusability:
Since each page is represented as a class, the methods can be reused across different tests. This reduces redundancy and improves maintainability.
### Readability:
Test scripts become more readable and understandable as they use high-level methods defined in the page classes rather than low-level interactions with the UI.
### Maintainability:
When the UI changes, only the page object classes need to be updated, leaving the test cases largely unaffected. This makes the tests more robust against changes.


## Project Structure

```project_folder/
│
├── tests/
│   ├── test_suite_1/
│   │   ├── test_case_1.py
│   │   ├── test_case_2.py
│   ├── test_suite_2/
│   │   ├── test_case_3.py
│   │   ├── test_case_4.py
│
├── pages/
│   ├── home_page.py
│   ├── login_page.py
│   ├── registration_page.py
│
├── utils/
│   ├── test_data.py
│   ├── configuration.py
│   ├── logger.py
│
├── reports/
│   ├── screenshots/
│   ├── videos/
│   ├── test_results.html
│
├── drivers/
│   ├── chromedriver.exe
│   ├── geckodriver.exe
│
├── main.py
├── README.md
├── conftest.py
└── pytest.ini
```

# Breakdown of Each Component

tests/: This directory contains all your test suites and individual test cases. Group related test cases into separate directories to represent different test suites, which makes it easier to organize and run tests.

pages/: This folder holds the page object classes that represent different pages or components of the web application. Each class encapsulates the elements and actions related to that page, promoting reusability and maintainability.

utils/: This directory includes utility modules that provide common functions and resources for tests, such as test data management, configuration settings, and logging functionalities.
    
reports/: This folder is used to store test reports, screenshots, videos, and other artifacts generated during test execution. Organizing files based on the type of report or resource helps maintain a clean reporting structure.
    
drivers/: This folder contains the necessary browser drivers (e.g., chromedriver, geckodriver) required for Selenium to interact with browsers. Placing the driver executables here allows for easy access.

main.py: This file serves as the entry point for running the tests. It can orchestrate test execution, import necessary modules, and define any global test configurations.

README.md: A documentation file that provides project details, installation instructions, prerequisites, and other relevant information for developers or contributors.

conftest.py: Used by pytest to define fixtures, which are reusable test resources or setups for tests.
    
pytest.ini: A configuration file for pytest to customize test execution behavior, specifying options like test discovery patterns and reporting settings.

