# Knowledge Management System ES6 Boilerplate

Boilerplate for an ES6 module that uses the [Knowledge Management System (KMS) REST API](https://developers.iu.edu/resources/kms-rest/public-api/).

> For use as part of the JavaScript Community Workshop at [Statewide IT 2019](https://statewideit.iu.edu/).

## How it should work

For this tutorial, create an ES6 class module that:

- Provides a `KBService` class to encapsulate functionality for fetching a public Knowledge Base article
- Provides a constructor that takes an element selector `el` as part of the `options` parameter
- Provides a `fetchArticle(articleId)` method that queries the [`GET /v1/documents/kmst` endpoint](https://developers.iu.edu/resources/kms-rest/public-api/#documents) and populates the `el` element with the XHTML content of the fetched article
- Provides a `fetchArticleFragment(articleId, fragmentId)` method that functions similar to `fetchArticle()` but only populates the `el` element with the XHTML content of the requested article fragment

### Things to consider

- The constructor should check if the given element `el` actually exists on the page and `throw` an error if it doesn't
- The `fetchArticle()` and `fetchArticleFragment()` methods should check if the given `articleId` is a valid Knowledge Base article ID and `throw` an error if it isn't (all Knowledge Base article IDs are four letters)
- The `fetchArticleFragment()` method should `throw` an error if no fragment with the given `fragmentId` exists in the fetched Knowledge Base article
- The module should not rely on an external HTTP library or jQuery to make `GET` or `POST` requests to the KMS REST API
- Include a `README.md` file that explains to developers how to use the module
- Include DocBlock-style comments for your class methods similar to those used in the [ES6 class module boilerplate](https://github.com/scottanthonymurray/es6-workshop-boilerplate/blob/master/ModuleName.js)

## Extra credit

- Allow developers to supply a `transformFn` as part of the `options` constructor parameter that transforms the XHTML content of a fetched Knowledge Base article before rendering it to `el`
- Sanitize fetched XHTML before rendering it to protect against [cross-site scripting (XSS)](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.md)