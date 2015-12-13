# Travis CI support scripts

## Usage

Add `uetchy/travis-scripts` as git submodules to your project.

```
git submodule add https://github.com/uetchy/travis-scripts.git
```

Write .travis.yml as you like. Also you can see the [one of the real world examples](https://github.com/randompaper/randompaper.co/blob/master/.travis.yml).

```yml
env:
  global:
    - GH_PAGES_REPO=randompaper/randompaper.github.io
    - GH_PAGES_PATH=public
    - GH_PAGES_DOMAIN=randompaper.co
before_install:
  - travis-scripts/install-hugo # install Hugo for build phase
script:
  - hugo --theme hugo-paper --buildDrafts=false # build sites
after_success:
  - travis-scripts/deploy-to-github-pages # Deploy to Github Pages
```
