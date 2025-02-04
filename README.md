# Telesto translations

## Translators
### How to become a translator

Join us on the Telesto DAO discord server and introduce yourself in the #app-translations channel

Someone will set you up.

### How to translate

- You can open the .po file of the language of your choice directly in github
- Look at the text in each `msgid` line and translate it in the `msgstr`line just below
- You can check the live site to have some context about the texts to be translated. If in doubt, do not hesitate to leave a message on the #app-translations channel
- Commit your changes


### Checking your translations

#### On the staging area

We do not have an environment for you to check your translations immediately, you will have to wait for them to be published on the staging URL: https://staging.telesto.money

If you really want to check your translations and you have a bit of knowledge with git and npm do the following

#### Locally

```
git clone https://github.com/TelestoWorld/telesto-frontend.git
cd telesto-frontend
yarn lingui:branch:develop
yarn install
yarn start
```

Replace `yarn` with `yarn.cmd` if you are using windows
You may also need to make sure that you are not tempering with the end-line characters when cloning the repository `git config --global core.autocrlf false`

A browser showing you the site should start with the latest develop branch and your updated translations

## Developers

### How to update the translations develop branch

```
# Clone the Telesto frontend repository
git clone https://github.com/TelestoWorld/telesto-frontend.git`
cd telesto-frontend

# Switch to the translations develop branch
yarn lingui:branch:develop

# Install the application dependencies
yarn install 

# At this point your filesystem cointains the latest telesto-frontend develop branch with the latest telesto-translations develop branch as a submodule in src/locales/translations
# Extract the new translations
yarn lingui:extract

# Commit the updated translation files
cd src/locales/translations
git add .
git commit
git push origin develop
```
