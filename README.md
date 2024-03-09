[![Azure Python 3.12.2](https://github.com/werthds-io/multi-cloud-exercise/actions/workflows/main.yml/badge.svg)](https://github.com/werthds-io/multi-cloud-exercise/actions/workflows/main.yml)

[![GCP Python 3.7](https://github.com/werthds-io/multi-cloud-exercise/actions/workflows/gcp.yml/badge.svg)](https://github.com/werthds-io/multi-cloud-exercise/actions/workflows/gcp.yml)

[![AWS 3.12.2](https://github.com/werthds-io/multi-cloud-exercise/actions/workflows/aws.yml/badge.svg)](https://github.com/werthds-io/multi-cloud-exercise/actions/workflows/aws.yml)

# github-actions-demo
This is a repo for building out Github Actions and Tricks.  I test multiple clouds and multiple versions of Python.


[Demo Video of this repo](https://www.youtube.com/watch?v=4gbUYOgALik)

### To use my project you can do this

Create a virtualenv
```python3 -m venv ~/.github-actions-demo```

Source it
```source ~/.github-actions-demo/bin/activate```

## Outline of Tasks
1. Fork the GitHub repo
2. Local steps:
  - Check out the forked repo
  - Review code
  - Run Makefile - install, lint, test
  - Confirm everything works locally
3. Setup GitHub Actions to install, lint, and test
4. Setup AWS CloudShell
  - Connect to GitHub repo
  - Automatically build when the repo changes
  - Validate its working
5. Setup GCP CloudShell
  - Connect to GitHub repo
  - Automatically build when the repo changes
  - Validate its working
6. Setup Azure CloudShell
  - Connect to GitHub repo
  - Automatically build when the repo changes
  - Validate its working
7. Confirm that code changes update all three cloud environemtns
8. Document process in GitHub with a README.md that describes what the project does
9. Create a Demo Video and reference it in your GitHub Project.

## Steps Taken:

GitHub:
1. forked the repo into https://github.com/werthds-io/multi-cloud-exercise

Local:
1. Cloned the repo
2. Set up venv
3. Reviewed code - very simple app and test script, has Makefile with requirements files for default, aws, and gcp
4. Run make install, lint, format, test
  - everything ran as expected, no issues
5. Ran hello.py - confirmed that 1 plus 1 equals 2
6. Review workflows in .github/workflows
  - Azure - main.yml On “push” it sets up a python3.6 env and runs install, link, and test
  - GCP - gcp.yml On “push” it sets up a python3.7 env and runs install-gcp, link, and test
  - AWS - aws.yml On “push” it sets up a python3.6 env and runs install-aws
  - AWS-Linux2 - aws-linux2.yml On “push” it sets up a python3.7.9 env and runs install-amazon-linux, link, test, and format

Setup GitHub Actions:

1. Opened actions in GitHub and disabled all workflows except Azure Python 3.6

Azure Cloud Shell:
1. Cloned the GitHub multi-cloud-exercise repo
2. Setup venv .venv and activated it
3. Ran make install, lint, format, and test
  - The format failed because black wasn’t in requirmeents.txt—it didn’t update. Formatting isn’t required for cloud environments as long as it’s on local.
  - Everything else ran as expected.

GitHub Actions:
1. Made a code change to trigger the workflow
2. Failed due to only version of python - updated workflow to python 3.12.2
3. Changed the workflow to python 3.12.2 and pushed the change 
4. Workflow ran without errors


AWS Cloud Shell
1. Cloned the GitHub multi-cloud-exercise repo
2. Setup venv .venv and activated it
3. Ran make install, lint, and test
4. Everything ran as expected.

GitHub Actions:
1. Made a code change to trigger the workflow
2. Failed due to only version of python - updated workflow to python 3.12.2
3. Changed the workflow to python 3.12.2 and pushed the change 
4. Workflow ran without errors

GCP Cloud Shell:
1. Cloned the GitHub multi-cloud-exercise repo
2. Setup venv .venv and activated it
3. Ran make install-gcp, lint, and test
4. Everything ran as expected.

