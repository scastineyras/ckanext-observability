# ckanext-observability
Observability plugin

# Getting Started
1.  Install the extension on your virtualenv:

        (pyenv) $ pip install -e git+https://github.com/OpenGov-OpenData/ckanext-observability.git#egg=ckanext-observability

2.  Install the extension requirements:

        (pyenv) $ pip install -r ckanext-observability/requirements.txt


## Installation

To install ckanext-observablity:

1. Activate your CKAN virtual environment, for example:

     . /usr/lib/ckan/default/bin/activate

2. Clone the source and install it on the virtualenv

    git clone https://github.com/scastineyras/ckanext-observablity.git
    cd ckanext-observablity
    pip install -e .
	pip install -r requirements.txt

3. Add `observablity` to the `ckan.plugins` setting in your CKAN
   config file (by default the config file is located at
   `/etc/ckan/default/ckan.ini`).

4. Restart CKAN. For example if you've deployed CKAN with Apache on Ubuntu:

     sudo service apache2 reload


## Config settings

None at present

**TODO:** Document any optional config settings here. For example:

	# The minimum number of hours to wait before re-checking a resource
	# (optional, default: 24).
	ckanext.observablity.some_setting = some_default_value


## Developer installation

To install ckanext-observablity for development, activate your CKAN virtualenv and
do:

    git clone https://github.com/scastineyras/ckanext-observablity.git
    cd ckanext-observablity
    python setup.py develop
    pip install -r dev-requirements.txt


## Tests

To run the tests, do:

    pytest --ckan-ini=test.ini


## Releasing a new version of ckanext-observablity

If ckanext-observablity should be available on PyPI you can follow these steps to publish a new version:

1. Update the version number in the `setup.py` file. See [PEP 440](http://legacy.python.org/dev/peps/pep-0440/#public-version-identifiers) for how to choose version numbers.

2. Make sure you have the latest version of necessary packages:

    pip install --upgrade setuptools wheel twine

3. Create a source and binary distributions of the new version:

       python setup.py sdist bdist_wheel && twine check dist/*

   Fix any errors you get.

4. Upload the source distribution to PyPI:

       twine upload dist/*

5. Commit any outstanding changes:

       git commit -a
       git push

6. Tag the new release of the project on GitHub with the version number from
   the `setup.py` file. For example if the version number in `setup.py` is
   0.0.1 then do:

       git tag 0.0.1
       git push --tags

## License

[AGPL](https://www.gnu.org/licenses/agpl-3.0.en.html)
