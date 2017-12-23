## Project 3: Requirements Dependency based on Use Case Diagram
```
This project develops a Computer Aided Software Engineering (CASE) Tool that helps requirements engineer in analyzing the dependency between requirements within a software.
The dependencies are derived from the dependencies resided in other UML diagram during the design process.
In this version (1.0), we use UC diagram.

The software should be developed using Java language and deployed as a desktop application.
```

## Software Requirements Specification

### 1. Introduction
This section provide an overview of the entire document.
It includes decription about the purpose, scope, definitions, acronyms, abbreviations, references and overview of the document.

#### 1.1. Purpose
The purpose of this document is to describe the basic needs of end users that the system should provide and attributes, properties, constraints, and qualities that the system should meet in order the system to achieve the goal of the system, i.e. to enable software engineer to analyze the dependency between requirements given the artifacts and deliverables of the project.
The document also describes the external behavior of the application or subsystem identified.
It also describes nonfunctional requirements, design constraints and other factors necessary to provide a complete and comprehensive description of the requirements for the software.

#### 1.2. Scope
The software application should allow the end user, i.e. the software engineer, to create project and to check the dependencies within the software requirements, given the artifacts and deliverables of an existing project.

#### 1.3. Definitions, Acronyms and Abbreviations
n.a.

#### 1.4. References
- [Use Case Specification Document of 'Create a New Project'](#use-case-specification-create-new-project)
- [Use Case Specification Document of 'Open an Existing Project'](#use-case-specification-open-existing-project)

#### 1.5. Overview
The rest of the document is organized as follows.
The second section explain the overal description of the system to be implemented, i.e. the scenario and the context diagram of the system.
The last setion describes the list of all functional and non-functional requirements.

### 2. Overall Description

#### 2.1. Scenario
Rivo is a requirements engineer working at ID-ITS.
He is reponsible for analyzing the impact of requirements changes on other requirements during project iteration.
Today, he has to come up with the result of their company on going project, i.e. SIDATA, an management information system for managing environmental parameter measurements on food and drinks.
The application was ordered by the beaurau of environmental services, East Java Province.
It is a huge and long project.
Change requests from end users immerged in every iteration which may cause domino-like changes on other requirements.
The company needs to make a quick financial analysis in each new iteration in order to respond to the changes.
Luckily, he has been using Ranalyzer to help him.
He adds the necessary documents of the last working iteration on the existing project.
Then, he executes the dependency analyzer module to triggered the process.
Within a minutes, he get the result.
He download the result, compose them into a document, and send it to the project leader from the email services.
And he is done.

#### 2.2. Context Diagram
ID | UC Name | UC Description
--- | --- | ---
UC01 | Create a New Project | Requirements Engineer can create a new project.
UC02 | Open an Existing Project | Requirements Engineer can open an existing project

### 3. Specific Requirements
This section contains all the software requirements to a level of detail sufficient to enable designers to design a system to satisfy those requirements, and testers to test that the system satisfies those requirements.

#### 3.1. Functionality
ID | Statement | UC | Priority
:---: | --- | :---: | :---:
F01 | Requirements Engineer can create a new project. | UC01 | Must
F02 | Requirements Engineer can open an existing project. | UC02 | Must
F03 | Requirements Engineer can add a design document. | UC01 UC02 | Must
F04 | Requirements Engineer can add a requirement statement. | UC01 UC02 | Must
F05 | Requirements Engineer can view requirements dependency of a project. | UC01 UC02 | Must
F06 | Requirements Engineer can check the dependency between requirements within a project. | UC01 UC02 | Must
F07 | Requirements Engineer can edit a requirement statement. | UC01 UC02 | Must
F08 | Requirements Engineer can delete a requirement statement. | UC01 UC02 | Must
F09 | Requirements Engineer can remove a document. | UC01 UC02 | Must
F10 | Requirements Engineer can view a list of requirement statements. | UC01 UC02 | Must
F11 | Requirements Engineer can save the project | UC01 UC02 | Must
F12 | Requirements Engineer can export the dependency graph into other format, i.e. jpg, bmp, and png | UC01 UC02 | Optional
F13 | The system shall be able to show a worksheet of a project | UC01 UC02 | Must 
F14 | Requirements Engineer can add use case description. | UC01 UC02 | Must

#### 3.2. Non-Functionality
ID | Statement | Quality | Priority
:---: | --- | :---: | :---:
NF01 | Only authorized and authenticated user may use the application. | Security | Must
NF02 | The system shall be able to accept the following design document: use case diagram. | Portability | Must
NF03 | The design document is in XMI format | Operability | Must
NF04 | The design document is in jpg format | Operability | Optional
NF05 | The system shall be deployed as a desktop application | Portability | Must
NF06 | The system shall open one project at a time. | Extendibiliy | Must
NF07 | The project shall be stored in a file with a .ran extension. | Portability | Must
NF08 | The project shall be stored in xml format. | Portability | Must
NF09 | The default name for the file being saved is 'Untitled'. If there is an existing file with the same name, a incrementaly number is added at the end, e.g. 'Untitled1', 'Untitled2', etc. | Operability | Must
NF10 | Project worksheet contains two child windows, i.e. Statements List Window and UML Diagram Windows | Operability | Must
NF11 | The system can only open a project file with a .ran extension that complies with the software | Operability | Must
NF12 | The use case description should be written in XML Format | Operability | Optional
NF13 | The use case description should contains at least the Followig information: basic Flow, exceptions, alternatives, and extensions. | Operability | Optional

### 4. Supporting Information
n.a.

## [Use Case Specification: Create New Project](Documents/UCS_CreateNewProject_ver-1.0.pdf)

### 1. Create New Project

#### 1.1. Brief Description
This use case describe how the requirements engineer create a new 
project in RAnalyzer.

### 2. Flow of Events

#### 2.1. Basic Flow 
1. The requirements engineer clicks on a menu to create a new project.
2. The system shows a project description window.
3. The requirements engineer fills in the necessary data. After he finish, he click on a Continue Button to proceed to the next step.
4. The system **Shows Project Worksheet**.
5. The requirements engineer clicks on Save menu.

#### 2.2. Alternative Flows
n.a.

#### 2.3. Exceptions

##### 4i. Closing the worksheet without saving change on the project. This event occurs whenever the requirements engineer close the worksheet while a previous change has not been saved.
1. The system shows a dialog box to ask whether to proceed closing the window without saving the change.
2. Requirements enginer click on proceed.

### 3. Special Requirements
1. The project shall be stored in a file with a .ran extension.
2. The project shall be stored in xml format. 
3. The default name for the file being saved is 'Untitled'. If there is an existing file with the same name, a incrementaly number is added at the end, e.g. 'Untitled1', 'Untitled2', etc.
4. Project worksheet contains two child windows, i.e. Statements List Window and UML Diagram Windows

### 4. Pre-Conditions
n.a.

### 5. Post-Conditions
5.1. The new project with extension .ran is created.

### 6. Extension Points
##### 4a. Requirements engineer can **Add Document** of a design artifacts.
1. Requirements engineer clicks on Add Document button.
2. The system opens a window explorer.
3. Requirements engineer selects a use case diagram file with an .xmi extension. He clicks on Open button.
4. The system show a loading in progress message.
5. The system add the use case diagram on the use case diagram list.
6. Requirements Engineer clicks on Add Description button.
7. The system shows a Use Case Description form.
8. Requirements Engineer paste the use case description to the given field. He clicks on the submit buton.
9. The system shows a progress information.
10. The system returns to the project worksheet window.

##### 4b. Requirements engineer can **Add Statement** of requirements.
1. Requirements engineer clicks on Add Statement button.
2. The system opens a requirements statement form.
3. Requirements engineer types the statement and other relevant metadata on the given field. He clicks on Add button.
4. The system add the new statement into the statement list.

##### 4c. Add any given time, the requiremens engineer can click on **Save** menu to save any change that has been made.

##### 4d. Requirements engineer can **View Dependency** of a current project.
1. Requirements engineer clicks on View Dependency button.
2. The system opens a dependency window and show the dependency graph.
3. Requirmeents engineer close the window.
4. The system close the window and return to worksheet.

##### 4e. Requirements engineer can **Check Dependency** of a current project.
1. Requirements engineer clicks on Check Dependency button.
2. The system shows a progress bar.
3. The system **View Dependency**.

##### 4f. Requirements engineer can **Edit Statement** of requirements.
1. Requirements engineer clicks on selected statement within the Statement Window.
2. The system opens a requirements statement form in a new window and shows the respected statement.
3. Requirements engineer edit the statement and other relevant metadata on the given field. He clicks Save button.
4. The system return to the worksheet.

##### 4g. Requirements engineer can **Delete Statement** of requirements.
1. Requirements engineer clicks on Delete button of respected statement within the Statement Window.
2. The system opens a dialog box asking for confirmation.
3. Requirements engineer clicks on OK to persue the deletion of the statement.
4. The system return to the worksheet.

##### 4h. Requirements engineer can **Remove Document** of requirements.
1. Requirements engineer clicks on Delete button of respected document within the UML Diagram Window.
2. The system opens a dialog box asking for confirmation.
3. Requirements engineer clicks on OK to persue the deletion of the document.
4. The system return to the worksheet.

## [Use Case Specification: Open Existing Project](Documents/UCS_OpenExistingProject_ver-1.0.pdf)

### 1. Open an Existing Project

#### 1.1. Brief Description
This use case describe how the Requirements Engineer open an existing project in RAnalyzer.

### 2. Flow of Events

#### 2.1. Basic Flow 
1. The requirements engineer clicks on a menu to open an existing project.
2. The system opens a window explorer.
3. The requirements engineer selects a use case diagram file with an .xmi extension. He clicks on Open button.
4. The system shows a loading progress
5. The system Shows Project Worksheet that contains the project.

#### 2.2. Alternative Flows
n.a.

#### 2.3. Exceptions
n.a.

### 3. Special Requirements
3.1. The system can only open a project file with a .ran extension that complies with the software.

### 4. Pre-Conditions
n.a.

### 5. Post-Conditions
n.a.

### 6. Extension Points
n.a.
