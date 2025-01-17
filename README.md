# React App

## Package.json
- your entry point to any app 
- holds configuration, metadata (version, name, etc), dependencies and scripts

### Dependencies
- npm -> Node Package Manager
- command line tool that installs, updates or uninstalls Node.js packages in your application
- online repository for open-source Node.js packages
- https://npmjs.com/
- Install locally: `npm install <package name>`
- Install globally: `npm install -g <package name>`
- Install and Save to package.json: `npm install <package name> --save`
- Uninstall `npm uninstall <package name>`

### BrowsersList
- defines what browsers our app can run on. That is, the build process makes sure the 
  output artifact can run in the specified browsers
- to check what each query means, run `npx browserslist <query>`

## index.html
- traditional html file
- you can add dependencies here too (not recommended)
- PUBLIC_URL -> use this instead of ./ to avoid problems

# Building
- simply run `npm run build`
- `yarn global add serve`
- `serve -s build`

# Deployment

## Github Actions

- create your Github repo
- add a new folder `.github/workflows`
- copy the `build-deploy.yml` file in this project into your repo under `.github/workflows/build-deploy.yml`
- in `package.json`, add a new key/value as:
  `"homepage": "https://prof-tejera.github.io/$YOUR_REPO_NAME"`. Replace `$YOUR_REPO_NAME` with the name of your repo
- commit your files (make sure package-lock.json is there)
- If you don't have a `gh-pages` branch you will have to create one and push it to Github. You can find instructions on how to create a branch [here](https://www.howtogeek.com/714112/how-to-create-a-new-branch-in-github/). You don't commit anything else to `gh-pages` branch. It is just used by Github to deploy.

### In Github
- Go to `Settings`
- Go to `Pages`
- in `Source`, select `gh-pages` branch
- Click Save

Once the `build-deploy` action finishes running, the app should be live
at `https://prof-tejera.github.io/<repo>`
