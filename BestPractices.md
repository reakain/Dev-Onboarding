# Best Practices for Coding and Git
This document keeps a listing of best practices and good methods for working with git and general coding expectations.

 - [Git Specific Housekeeping](#git-specific-housekeeping)
 - [Coding Practices](#coding)
 - [Documentation](#documentation)


## Git Specific Housekeeping
These are practices and info specific to working with git.

### Git Ignore File
A ```.gitignore``` file determines what files and folders should be ignored when doing revision tracking. These files are incredibly powerful, and can lead to unintended outcomes where things that should be tracked aren't tracked. Alternatively, not having a proper ```.gitignore``` can result in a lot of extra garbage or build files being added that are unnecessary or simply clutter the space. When added folders and file structures, it is important to make sure they wont accidentally be ignored. However, be sure to use these files with your code. Most languages have good generic starting versions on github that can be downloaded and renamed.

### Commit Messages
When commiting changes, best practice would be to commit changes regularly, and to describe what you changed, why you changed it, and the expected result clearly and completely in the commit message. Committing changes often prevents large scale commits, which can easily hide smaller changes that could have introduced bugs, or not be intended.

### Branches
Working in branches is good. Use branches when working on new changes or edits, and don't be afraid to push to your branches a lot. When you have your change or multiple changes ready for prime time, you then merge it into main (or master if historical naming) and add a [tag](#tags) to the merge so you know what markes this new version of master.

### Tags
Specifically, tags are a great tool for labeling certain commits in the git revision history, which is useful for tracking past revisions of software, or versions that have been used in different studies or with specific research papers. When making a tag, the tag should also have a clear and complete description about what is contained in this version of the project.

Pushing tags is a little different, as after you've made a tag using ```git tag``` you need to specifically push the tags to the remote using ```git push origin --tags```


## Coding
All variables and functions should be descriptively named.

For code commenting, see [comments](#code-comments)



## Documentation
Documentation is hugely important. Your colleagues and future self with be very greatful later down the line if your documentation is setup, as it will make life muuuuch easier.

### README
Programming projects should have a README file that lists at minimum:

 - Purpose of code
 - How to install the code or any setup necessary before the code can be installed or run
 - How to use the code (including format and content of any inputs, and descriptions of format and content of any outputs)
 - Descriptions of files
 - Names, links, and versions of any [software dependencies](#dependencies)
 - Known bugs or issues
 - Operating system/programming language and version code was written/tested/compiled on

 A [Template README file](./media/README_template.md) is available as a starting point. A good reference for using markdown is [here](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

### Dependencies
For python in particular, keeping a requirements.txt file using ```pip freeze``` will track all package dependencies and their versions.

For other software, or non-pip dependencies, all versions and links must be listed. If no version information can be found, keeping a copy of the dependency with the drive will allow for future rebuilding even if that dependency is changed.

### Hardware
If software has associated hardware, the bill of materials should be included with enough information to get specific part quantities, dimensions, and versions (in the case of items like microcontrollers). 

If any wiring is necessary, include the circuit schematic and wiring. 

If any part fabrication is done, the dimensional drawings and base materials for that fabrication should be included.

Finally, if hardware must be assembled, assembly instructions should be provided, and if hardware requires additional code flashed to other components, that code should be linked, documented, or added to the project repository.

### Code Comments
All functions should have descriptions detailing what it does, what the inputs are, and what the outputs are.

Clean comments should be added throughout code to describe flow and improve code legibility. Any known lacking items or areas with issues should be marked with comments starting with ```TODO: ```