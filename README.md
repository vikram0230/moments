# Moments

A photo sharing social networking app built with Python and Flask. The example application for the book *[Python Web Development with Flask (2nd edition)](https://helloflask.com/en/book/4)* (《[Flask Web 开发实战（第 2 版）](https://helloflask.com/book/4)》).

Demo: http://moments.helloflask.com

![Screenshot](demo.png)

## Installation

Clone the repo:

```
$ git clone https://github.com/greyli/moments
$ cd moments
```

Install dependencies with [PDM](https://pdm.fming.dev):

```
$ pdm install
```

> [!TIP]
> If you don't have PDM installed, you can create a virtual environment with `venv` and install dependencies with `pip install -r requirements.txt`.


## Setting up Azure Vision API and Storing Credentials in secrets.txt

**Step 1: Create an Azure Vision API Resource**

1. Log in to the Azure portal at <https://portal.azure.com/>
2. Click on "Create a resource" and search for "Computer Vision"
3. Select "Computer Vision" and click on "Create"
4. Fill in the required information, such as resource name, subscription, and location
5. Click on "Create" to create the resource

**Step 2: Get the API Key and Endpoint**

1. Go to the "Keys and Endpoint" section of your Computer Vision resource
2. Copy the "KEY 1" value, this will be your API key
3. Copy the "Endpoint" value, this will be your API endpoint

**Step 3: Create a secrets.txt File**

1. Create a new file named `secrets.txt` in the root directory of your project
2. Add the following lines to the file, replacing `<API_KEY>` and `<ENDPOINT>` with the values you copied earlier:
```
[DEFAULT]
ENDPOINT = <ENDPOINT>
KEY = <API_KEY>
```
*Example secrets.txt File*
```bash
[DEFAULT]
ENDPOINT = https://ocr-rai.cognitiveservices.azure.com/
KEY = 8nXmAVWY1EDBty8K3gTP7ZnpZxQRIZT58fJIJYzc4RySJr1uJQQJ99BAACYeBjw3AAAFACOGqjzK
```

**Step 4: Store the secrets.txt File Securely**

1. Make sure to add the `secrets.txt` file to your `.gitignore` file to prevent it from being committed to your version control system
2. Store the `secrets.txt` file securely, such as in an encrypted file or a secure environment variable

## Running the app

To initialize the app, run the `flask init-app` command:

```
$ pdm run flask init-app
```

If you just want to try it out, generate fake data with `flask lorem` command then run the app:

```
$ pdm run flask lorem
```

It will create a test account:

* email: `admin@helloflask.com`
* password: `moments`

Now you can run the app:

```
$ pdm run flask run
* Running on http://127.0.0.1:5000/
```

## License

This project is licensed under the MIT License (see the
[LICENSE](LICENSE) file for details).
