# Next.js gh-pages Hello World example

This repository is a gh-pages example built with Next.js

https://thierryc.github.io/Next-gh-page-example/

Install it and run:

```bash
npm install
npm run dev
```

Deploy it to github

Edit ```env-config.js``` and replace ```'Next-gh-page-example'``` by your project name.

Edit ```next.config.js``` and replace ```'Next-gh-page-example'``` by your project name.

1. Create repository.
2. Link it to your github account.
3. Publish your master branch.

```bash
npm run deploy
```

Test it:

Replace 'github-user-name' and 'github-project-name'

```bash

https://github-user-name.github.io/github-project-name/

```

## Custom domain setting

You can add on to the deploy command to create the CNAME file for you. GitHub detects this file and automatically updates the custom domain setting. Edit the package.json deploy script and replace example.com with your custom domain. (Thank you to @jabacchetta)

```bash

rm -rf node_modules/.cache 
&& rimraf out 
&& next build 
&& next export 
&& touch out/.nojekyll 
&& touch out/CNAME
&& echo \"example.com\" >> out/CNAME
&& gh-pages -d out

```

Example:

```bash

https://github.com/thierryc/Next-gh-page-example/

https://thierryc.github.io/Next-gh-page-example/

```


## The idea behind the example

This example shows the most basic idea behind Next. We have 2 pages: `pages/index.js` and `pages/about.js`. The former responds to `/` requests and the latter to `/about`. Using `next/link` you can add hyperlinks between them with universal routing capabilities.
