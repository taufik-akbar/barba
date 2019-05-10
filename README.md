# barba.js <small>[v2]</small>

![stability-wip](https://img.shields.io/badge/stability-work_in_progress-lightgrey.svg?style=flat-square)
[![CircleCI](https://img.shields.io/circleci/project/github/barbajs/barba/master.svg?style=flat-square)](https://circleci.com/gh/barbajs/barba/tree/master)
[![Coverage Status](https://img.shields.io/coveralls/github/barbajs/barba/master.svg?style=flat-square)](https://coveralls.io/github/barbajs/barba?branch=master)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg?style=flat-square)](http://commitizen.github.io/cz-cli/)
[![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-yellow.svg?style=flat-square)](https://conventionalcommits.org)
[![lerna](https://img.shields.io/badge/maintained%20with-lerna-cc00ff.svg?style=flat-square)](https://lernajs.io/)
[![License](https://img.shields.io/badge/license-MIT-green.svg?style=flat-square)](https://github.com/barbajs/barba/blob/master/LICENSE)
[![All Contributors](https://img.shields.io/badge/all_contributors-67-orange.svg?style=flat-square)](#contributors)
[![Slack channel](https://img.shields.io/badge/slack-channel-purple.svg?style=flat-square&logo=slack)](https://barbajs.slack.com)

> [Invite link to slack channel](https://join.slack.com/t/barbajs/shared_invite/enQtNTU3NTAyMjkxMzAyLTI1NDIxZDZmMGJjMDlmNzFkODZmMmVmN2U2ODg2Y2M3MzczMDdjZTk5ODQwNWZkYWVlMDM5NGZiODJmMWVhODk)

**Barba** is a small (7kb minified and compressed) and easy-to-use library that helps you creating fluid and smooth transitions between your website's pages.

It helps reducing the delay between your pages, minimizing browser HTTP requests and enhancing your user's web experience.

> This is beta version, use it at your own risks! 😱  
> Thanks in advance for reporting bugs. #sharethelove 😊
>
> [Looking for v1?](https://barba.js.org/v1) 👈

## What's new?

- Simplified API
- Hook sytem for `transitions` and `views`
- _Transition resolution_: declare your transitions and let Barba pick the right one
- Use of `data-barba` attributes
- Sync mode
- Plugin system
  - `@barba/router`: use of routes for _transition resolution_
  - `@barba/css`: automatic addition of CSS classes
  - `@barba/prefetch`: automatic pages prefetching (and caching), based on viewport
  - `@barba/head`: update your `<head>` _(coming soon)_
  - `@barba/transition`: ready-to-use basic transitions pack (fade, slide, …) _(coming soon)_

## Main changes (TL;DR)

- Barba now use `data-barba-*` attributes:
  - data-barba-container for the [container](https://barba.js.org/docs/v2/user/core.html#container)
  - data-barba-wrapper for the [wrapper](https://barba.js.org/docs/v2/user/core.html#wrapper)
  - data-barba-namespace for the [namespace](https://barba.js.org/docs/v2/user/core.html#namespace)
- 2 main methods:
  - `barba.init()` for transitions, views and Barba core settings
  - `barba.use()` for plugins (router, css, prefetch, etc.)
- [Transitions](https://barba.js.org/docs/v2/user/core.html#transition-object):
  - are plain JS objects
  - are declared via the `barba.init({ transitions })`
  - use "[hooks](https://barba.js.org/docs/v2/user/core.html#hooks)" corresponding to animation steps
    - hooks can be synchronous or asynchronous (via `this.async()` or Promise based)
    - all hooks receive same [`data` argument](https://barba.js.org/docs/v2/user/core.html#data-argument)
  - use "[rules](https://barba.js.org/docs/v2/user/core.html#rules)" to select which transition to use
    - default rules are `namespace` and `custom`
    - `@barba/router` adds `route` rule
    - they can be combined within `from` and `to` properties
- [Views](https://barba.js.org/docs/v2/user/core.html#view-object):
  - are plain JS objects
  - are declared via the `barba.init({ views })`
  - use a subset of animation "hooks":
    - `beforeAppear`, `afterAppear`, `beforeLeave`, `afterLeave`, `beforeEnter`, `afterEnter`
    - receive the same [`data` argument](https://barba.js.org/docs/v2/user/core.html#data-argument)
- [Sync mode](https://barba.js.org/docs/v2/user/core.html#sync-mode) will start `leave` and `enter` transitions concurrently

## Documentation

- [User guide](https://barba.js.org/docs/v2/user/)
- [API documentation](https://barba.js.org/docs/v2/api/)

## How to contribute

If you want to report a bug or if you just want to request for a new feature/improvement, please **follow [those instructions](CONTRIBUTING.md) before**.

Thanks for taking time to contribute to Barba :tada: :+1:

## Contributors

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore -->
<table><tr><td align="center" valign="top"><a href="http://luruke.com"><img src="https://avatars0.githubusercontent.com/u/61326?v=4" width="100px;" alt="Luigi De Rosa"/><br /><sup><b>Luigi De Rosa</b></sup></a><br /><sup><a href="#ideas-luruke" title="Ideas, Planning, & Feedback">🤔</a></sup> <sup><a href="https://github.com/barbajs/barba/commits?author=luruke" title="Code">💻</a></sup> <sup><a href="https://github.com/barbajs/barba/commits?author=luruke" title="Documentation">📖</a></sup> <sup><a href="#question-luruke" title="Answering Questions">💬</a></sup> <sup><a href="https://github.com/barbajs/barba/issues?q=author%3Aluruke" title="Bug reports">🐛</a></sup> <sup><a href="https://github.com/barbajs/barba/commits?author=luruke" title="Tests">⚠️</a></sup> <sup><a href="#review-luruke" title="Reviewed Pull Requests">👀</a></sup> <sup><a href="#infra-luruke" title="Infrastructure (Hosting, Build-Tools, etc)">🚇</a></sup></td><td align="center"><a href="http://thierrymichel.net"><img src="https://avatars2.githubusercontent.com/u/806883?v=4" width="100px;" alt="Thierry Michel"/><br /><sup><b>Thierry Michel</b></sup></a><br /><sup><a href="#ideas-thierrymichel" title="Ideas, Planning, & Feedback">🤔</a></sup> <sup><a href="https://github.com/barbajs/barba/commits?author=thierrymichel" title="Code">💻</a></sup> <sup><a href="https://github.com/barbajs/barba/commits?author=thierrymichel" title="Documentation">📖</a></sup> <sup><a href="#question-thierrymichel" title="Answering Questions">💬</a></sup> <sup><a href="https://github.com/barbajs/barba/issues?q=author%3Athierrymichel" title="Bug reports">🐛</a></sup> <sup><a href="https://github.com/barbajs/barba/commits?author=thierrymichel" title="Tests">⚠️</a></sup> <sup><a href="#review-thierrymichel" title="Reviewed Pull Requests">👀</a></sup> <sup><a href="#infra-thierrymichel" title="Infrastructure (Hosting, Build-Tools, etc)">🚇</a></sup></td><td align="center"><a href="https://www.xavierfoucrier.fr"><img src="https://avatars1.githubusercontent.com/u/2471223?v=4" width="100px;" alt="Xavier Foucrier"/><br /><sup><b>Xavier Foucrier</b></sup></a><br /><sup><a href="#ideas-xavierfoucrier" title="Ideas, Planning, & Feedback">🤔</a></sup> <sup><a href="https://github.com/barbajs/barba/commits?author=xavierfoucrier" title="Documentation">📖</a></sup> <sup><a href="#question-xavierfoucrier" title="Answering Questions">💬</a></sup> <sup><a href="https://github.com/barbajs/barba/commits?author=xavierfoucrier" title="Tests">⚠️</a></sup> <sup><a href="#review-xavierfoucrier" title="Reviewed Pull Requests">👀</a></sup></td><td align="center"><a href="http://www.thenerodesign.com"><img src="https://avatars2.githubusercontent.com/u/858150?v=4" width="100px;" alt="Marco Grimaldi"/><br /><sup><b>Marco Grimaldi</b></sup></a><br /><sup><a href="#design-markog85" title="Design">🎨</a></sup></td><td align="center"><a href="https://studio123.ca"><img src="https://avatars0.githubusercontent.com/u/22644154?v=4" width="100px;" alt="Cody Marcoux"/><br /><sup><b>Cody Marcoux</b></sup></a><br /><sup><a href="#question-c0mrx" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://philiphussak.com"><img src="https://avatars1.githubusercontent.com/u/3285136?v=4" width="100px;" alt="Phil."/><br /><sup><b>Phil.</b></sup></a><br /><sup><a href="#question-wiseoldman" title="Answering Questions">💬</a></sup></td><td align="center"><a href="http://www.fnool.com"><img src="https://avatars0.githubusercontent.com/u/5812801?v=4" width="100px;" alt="Giorgio Finulli"/><br /><sup><b>Giorgio Finulli</b></sup></a><br /><sup><a href="#question-gfnool" title="Answering Questions">💬</a></sup></td></tr><tr><td align="center" valign="top"><a href="https://www.thisisnota.studio"><img src="https://avatars2.githubusercontent.com/u/6507123?v=4" width="100px;" alt="Wouter"/><br /><sup><b>Wouter</b></sup></a><br /><sup><a href="https://github.com/barbajs/barba/issues?q=author%3AWouter125" title="Bug reports">🐛</a></sup> <sup><a href="#question-Wouter125" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://selfaware.studio"><img src="https://avatars2.githubusercontent.com/u/12376535?v=4" width="100px;" alt="Mike Wagz"/><br /><sup><b>Mike Wagz</b></sup></a><br /><sup><a href="#ideas-mikehwagz" title="Ideas, Planning, & Feedback">🤔</a></sup> <sup><a href="#question-mikehwagz" title="Answering Questions">💬</a></sup> <sup><a href="https://github.com/barbajs/barba/commits?author=mikehwagz" title="Tests">⚠️</a></sup></td><td align="center"><a href="https://www.youtube.com/c/redstapler_channel"><img src="https://avatars0.githubusercontent.com/u/16864380?v=4" width="100px;" alt="Red Stapler"/><br /><sup><b>Red Stapler</b></sup></a><br /><sup><a href="#tutorial-theredstapler" title="Tutorials">✅</a></sup> <sup><a href="#video-theredstapler" title="Videos">📹</a></sup></td><td align="center"><a href="http://www.19h47.fr"><img src="https://avatars1.githubusercontent.com/u/11242861?v=4" width="100px;" alt="Jérémy Levron"/><br /><sup><b>Jérémy Levron</b></sup></a><br /><sup><a href="#question-19h47" title="Answering Questions">💬</a></sup></td><td align="center"><a href="http://anhskohbo.github.io/"><img src="https://avatars2.githubusercontent.com/u/1529454?v=4" width="100px;" alt="Nguyen Van Anh"/><br /><sup><b>Nguyen Van Anh</b></sup></a><br /><sup><a href="https://github.com/barbajs/barba/commits?author=anhskohbo" title="Code">💻</a></sup></td><td align="center"><a href="http://www.thedanielweber.com"><img src="https://avatars1.githubusercontent.com/u/668910?v=4" width="100px;" alt="Daniel Weber"/><br /><sup><b>Daniel Weber</b></sup></a><br /><sup><a href="https://github.com/barbajs/barba/commits?author=dlwebdev" title="Code">💻</a></sup></td><td align="center"><a href="http://www.jmporchet.ch"><img src="https://avatars3.githubusercontent.com/u/3099008?v=4" width="100px;" alt="Jean-Marie Porchet"/><br /><sup><b>Jean-Marie Porchet</b></sup></a><br /><sup><a href="https://github.com/barbajs/barba/commits?author=jmporchet" title="Code">💻</a></sup></td></tr><tr><td align="center" valign="top"><a href="https://www.jamesdocherty.com/"><img src="https://avatars1.githubusercontent.com/u/325490?v=4" width="100px;" alt="James"/><br /><sup><b>James</b></sup></a><br /><sup><a href="https://github.com/barbajs/barba/commits?author=docherty" title="Code">💻</a></sup></td><td align="center"><a href="http://ruggeri.io"><img src="https://avatars0.githubusercontent.com/u/999162?v=4" width="100px;" alt="Nicholas"/><br /><sup><b>Nicholas</b></sup></a><br /><sup><a href="https://github.com/barbajs/barba/commits?author=nicholasruggeri" title="Code">💻</a></sup></td><td align="center"><a href="http://patrick.wtf"><img src="https://avatars1.githubusercontent.com/u/667029?v=4" width="100px;" alt="Patrick Arminio"/><br /><sup><b>Patrick Arminio</b></sup></a><br /><sup><a href="https://github.com/barbajs/barba/commits?author=patrick91" title="Code">💻</a></sup></td><td align="center"><a href="https://angelogulina.it"><img src="https://avatars0.githubusercontent.com/u/4223655?v=4" width="100px;" alt="A (from Sicily)"/><br /><sup><b>A (from Sicily)</b></sup></a><br /><sup><a href="https://github.com/barbajs/barba/commits?author=AngeloGulina" title="Code">💻</a></sup></td><td align="center"><a href="https://github.com/pavel-mazhuga"><img src="https://avatars3.githubusercontent.com/u/29140681?v=4" width="100px;" alt="Pavel Mazhuga"/><br /><sup><b>Pavel Mazhuga</b></sup></a><br /><sup><a href="#question-pavel-mazhuga" title="Answering Questions">💬</a></sup></td><td align="center"><a href="http://dmdcode.it"><img src="https://avatars0.githubusercontent.com/u/7113516?v=4" width="100px;" alt="Daniele De Matteo"/><br /><sup><b>Daniele De Matteo</b></sup></a><br /><sup><a href="#question-DMDc0de" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://github.com/aswinkumar863"><img src="https://avatars0.githubusercontent.com/u/32381261?v=4" width="100px;" alt="aswinkumar863"/><br /><sup><b>aswinkumar863</b></sup></a><br /><sup><a href="#question-aswinkumar863" title="Answering Questions">💬</a></sup></td></tr><tr><td align="center" valign="top"><a href="https://github.com/ghost"><img src="https://avatars3.githubusercontent.com/u/10137?v=4" width="100px;" alt="Deleted user"/><br /><sup><b>Deleted user</b></sup></a><br /><sup><a href="#question-ghost" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://github.com/BounceIncHQ"><img src="https://avatars0.githubusercontent.com/u/39249876?v=4" width="100px;" alt="BounceIncHQ"/><br /><sup><b>BounceIncHQ</b></sup></a><br /><sup><a href="#question-BounceIncHQ" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://github.com/gordonwes"><img src="https://avatars3.githubusercontent.com/u/10758596?v=4" width="100px;" alt="gordonwes"/><br /><sup><b>gordonwes</b></sup></a><br /><sup><a href="#question-gordonwes" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://github.com/evfleet"><img src="https://avatars2.githubusercontent.com/u/7504632?v=4" width="100px;" alt="Evan Fleet"/><br /><sup><b>Evan Fleet</b></sup></a><br /><sup><a href="#question-evfleet" title="Answering Questions">💬</a></sup> <sup><a href="https://github.com/barbajs/barba/issues?q=author%3Aevfleet" title="Bug reports">🐛</a></sup></td><td align="center"><a href="http://www.aligator-kom.de"><img src="https://avatars2.githubusercontent.com/u/32126746?v=4" width="100px;" alt="Jörg"/><br /><sup><b>Jörg</b></sup></a><br /><sup><a href="#example-jd4Aligator" title="Examples">💡</a></sup></td><td align="center"><a href="http://www.zaak.ch"><img src="https://avatars3.githubusercontent.com/u/12050808?v=4" width="100px;" alt="ZAAK"/><br /><sup><b>ZAAK</b></sup></a><br /><sup><a href="#example-StudioZAAK" title="Examples">💡</a></sup> <sup><a href="#question-StudioZAAK" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://leap-in.com"><img src="https://avatars1.githubusercontent.com/u/42055102?v=4" width="100px;" alt="Masahiro Tonomura"/><br /><sup><b>Masahiro Tonomura</b></sup></a><br /><sup><a href="#example-leapincorp" title="Examples">💡</a></sup></td></tr><tr><td align="center" valign="top"><a href="https://github.com/CassiusHR"><img src="https://avatars1.githubusercontent.com/u/24419585?v=4" width="100px;" alt="CassiusHR"/><br /><sup><b>CassiusHR</b></sup></a><br /><sup><a href="#question-CassiusHR" title="Answering Questions">💬</a></sup></td><td align="center"><a href="http://www.shanemurphy.me"><img src="https://avatars2.githubusercontent.com/u/3694619?v=4" width="100px;" alt="Shane Murphy"/><br /><sup><b>Shane Murphy</b></sup></a><br /><sup><a href="#question-shanewmurphy" title="Answering Questions">💬</a></sup></td><td align="center"><a href="http://www.dylanreeves.com"><img src="https://avatars3.githubusercontent.com/u/1294637?v=4" width="100px;" alt="Dylan Reeves"/><br /><sup><b>Dylan Reeves</b></sup></a><br /><sup><a href="#question-watzing" title="Answering Questions">💬</a></sup> <sup><a href="#example-watzing" title="Examples">💡</a></sup></td><td align="center"><a href="http://www.quentinneyraud.fr"><img src="https://avatars2.githubusercontent.com/u/9378568?v=4" width="100px;" alt="Quentin Neyraud"/><br /><sup><b>Quentin Neyraud</b></sup></a><br /><sup><a href="#question-quentinneyraud" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://github.com/tortilaman"><img src="https://avatars2.githubusercontent.com/u/5018268?v=4" width="100px;" alt="tortilaman"/><br /><sup><b>tortilaman</b></sup></a><br /><sup><a href="#question-tortilaman" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://github.com/psntr"><img src="https://avatars2.githubusercontent.com/u/20617539?v=4" width="100px;" alt="psntr"/><br /><sup><b>psntr</b></sup></a><br /><sup><a href="#question-psntr" title="Answering Questions">💬</a></sup></td><td align="center"><a href="http://thisbailiwick.com"><img src="https://avatars3.githubusercontent.com/u/12637253?v=4" width="100px;" alt="Kevin Clark"/><br /><sup><b>Kevin Clark</b></sup></a><br /><sup><a href="#question-thisbailiwick" title="Answering Questions">💬</a></sup></td></tr><tr><td align="center" valign="top"><a href="http://takodesign.one"><img src="https://avatars2.githubusercontent.com/u/26543624?v=4" width="100px;" alt="Tadeas Kosek"/><br /><sup><b>Tadeas Kosek</b></sup></a><br /><sup><a href="#question-Tedowski" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://github.com/gustavo-a"><img src="https://avatars2.githubusercontent.com/u/26806307?v=4" width="100px;" alt="Gustavo de Andrade"/><br /><sup><b>Gustavo de Andrade</b></sup></a><br /><sup><a href="#question-gustavo-a" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://durkangroup.com/"><img src="https://avatars0.githubusercontent.com/u/25391588?v=4" width="100px;" alt="Clinton"/><br /><sup><b>Clinton</b></sup></a><br /><sup><a href="#question-crobbinsdg" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://www.spon.io"><img src="https://avatars3.githubusercontent.com/u/3268717?v=4" width="100px;" alt="Dave Stockley"/><br /><sup><b>Dave Stockley</b></sup></a><br /><sup><a href="#question-magicspon" title="Answering Questions">💬</a></sup></td><td align="center"><a href="http://khaiknievel.carbonmade.com"><img src="https://avatars1.githubusercontent.com/u/5792500?v=4" width="100px;" alt="khaiknievel"/><br /><sup><b>khaiknievel</b></sup></a><br /><sup><a href="#question-khaiknievel" title="Answering Questions">💬</a></sup> <sup><a href="https://github.com/barbajs/barba/issues?q=author%3Akhaiknievel" title="Bug reports">🐛</a></sup></td><td align="center"><a href="http://www.francescomichelini.com/"><img src="https://avatars3.githubusercontent.com/u/5191941?v=4" width="100px;" alt="Francesco Michelini"/><br /><sup><b>Francesco Michelini</b></sup></a><br /><sup><a href="#question-kekkorider" title="Answering Questions">💬</a></sup> <sup><a href="#example-kekkorider" title="Examples">💡</a></sup></td><td align="center"><a href="https://github.com/FistMeNaruto"><img src="https://avatars1.githubusercontent.com/u/13431677?v=4" width="100px;" alt="Domantas Petrauskas"/><br /><sup><b>Domantas Petrauskas</b></sup></a><br /><sup><a href="#question-FistMeNaruto" title="Answering Questions">💬</a></sup></td></tr><tr><td align="center" valign="top"><a href="http://kylebrumm.com"><img src="https://avatars3.githubusercontent.com/u/1709677?v=4" width="100px;" alt="Kyle Brumm"/><br /><sup><b>Kyle Brumm</b></sup></a><br /><sup><a href="#question-kjbrum" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://github.com/obelmont"><img src="https://avatars3.githubusercontent.com/u/6540497?v=4" width="100px;" alt="Oliver Belmont"/><br /><sup><b>Oliver Belmont</b></sup></a><br /><sup><a href="#question-obelmont" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://lunelson.xyz/"><img src="https://avatars1.githubusercontent.com/u/1242864?v=4" width="100px;" alt="Lu Nelson"/><br /><sup><b>Lu Nelson</b></sup></a><br /><sup><a href="#question-lunelson" title="Answering Questions">💬</a></sup></td><td align="center"><a href="http://bierdb.be"><img src="https://avatars1.githubusercontent.com/u/1107185?v=4" width="100px;" alt="Bram Cordie"/><br /><sup><b>Bram Cordie</b></sup></a><br /><sup><a href="#question-bramcordie" title="Answering Questions">💬</a></sup> <sup><a href="#ideas-bramcordie" title="Ideas, Planning, & Feedback">🤔</a></sup></td><td align="center"><a href="http://portfolio.schouman.info"><img src="https://avatars1.githubusercontent.com/u/510652?v=4" width="100px;" alt="Michael Schouman"/><br /><sup><b>Michael Schouman</b></sup></a><br /><sup><a href="#question-metalmini" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://www.jumplink.eu"><img src="https://avatars2.githubusercontent.com/u/1073989?v=4" width="100px;" alt="Pascal Garber"/><br /><sup><b>Pascal Garber</b></sup></a><br /><sup><a href="#question-JumpLink" title="Answering Questions">💬</a></sup> <sup><a href="#ideas-JumpLink" title="Ideas, Planning, & Feedback">🤔</a></sup></td><td align="center"><a href="https://twitter.com/bfred_it"><img src="https://avatars3.githubusercontent.com/u/1402241?v=4" width="100px;" alt="Federico Brigante"/><br /><sup><b>Federico Brigante</b></sup></a><br /><sup><a href="#question-bfred-it" title="Answering Questions">💬</a></sup></td></tr><tr><td align="center" valign="top"><a href="http://coreylee.tokyo/"><img src="https://avatars1.githubusercontent.com/u/1465865?v=4" width="100px;" alt="Corey Lee"/><br /><sup><b>Corey Lee</b></sup></a><br /><sup><a href="#question-factorzero" title="Answering Questions">💬</a></sup></td><td align="center"><a href="http://www.imls.uzh.ch/research/vonmering/people/milan-simonovic.html"><img src="https://avatars3.githubusercontent.com/u/888008?v=4" width="100px;" alt="Milan Simonovic"/><br /><sup><b>Milan Simonovic</b></sup></a><br /><sup><a href="#question-mbsimonovic" title="Answering Questions">💬</a></sup></td><td align="center"><a href="http://djul.es"><img src="https://avatars1.githubusercontent.com/u/196644?v=4" width="100px;" alt="Julien Vasseur"/><br /><sup><b>Julien Vasseur</b></sup></a><br /><sup><a href="#question-Djules" title="Answering Questions">💬</a></sup></td><td align="center"><a href="https://github.com/panwron"><img src="https://avatars2.githubusercontent.com/u/8494786?v=4" width="100px;" alt="Maciej Wrona"/><br /><sup><b>Maciej Wrona</b></sup></a><br /><sup><a href="#question-panwron" title="Answering Questions">💬</a></sup></td><td align="center"><a href="http://terion.name"><img src="https://avatars0.githubusercontent.com/u/1060205?v=4" width="100px;" alt="Terion"/><br /><sup><b>Terion</b></sup></a><br /><sup><a href="#ideas-terion-name" title="Ideas, Planning, & Feedback">🤔</a></sup></td><td align="center"><a href="https://github.com/cartogram"><img src="https://avatars2.githubusercontent.com/u/462077?v=4" width="100px;" alt="Matt Seccafien"/><br /><sup><b>Matt Seccafien</b></sup></a><br /><sup><a href="#ideas-cartogram" title="Ideas, Planning, & Feedback">🤔</a></sup></td><td align="center"><a href="http://www.maxschulmeister.com"><img src="https://avatars2.githubusercontent.com/u/15388185?v=4" width="100px;" alt="Max Schulmeister"/><br /><sup><b>Max Schulmeister</b></sup></a><br /><sup><a href="#ideas-max-schu" title="Ideas, Planning, & Feedback">🤔</a></sup></td></tr><tr><td align="center" valign="top"><a href="https://davidaase.com"><img src="https://avatars3.githubusercontent.com/u/1521451?v=4" width="100px;" alt="David"/><br /><sup><b>David</b></sup></a><br /><sup><a href="#ideas-tipsy" title="Ideas, Planning, & Feedback">🤔</a></sup></td><td align="center"><a href="https://github.com/pierrehenri220"><img src="https://avatars3.githubusercontent.com/u/19267400?v=4" width="100px;" alt="Pierre-Henri Lavigne"/><br /><sup><b>Pierre-Henri Lavigne</b></sup></a><br /><sup><a href="#ideas-pierrehenri220" title="Ideas, Planning, & Feedback">🤔</a></sup></td><td align="center"><a href="https://github.com/lsbyerley"><img src="https://avatars0.githubusercontent.com/u/3066258?v=4" width="100px;" alt="lsbyerley"/><br /><sup><b>lsbyerley</b></sup></a><br /><sup><a href="#ideas-lsbyerley" title="Ideas, Planning, & Feedback">🤔</a></sup></td><td align="center"><a href="http://gmorisseau.com/"><img src="https://avatars2.githubusercontent.com/u/242203?v=4" width="100px;" alt="Guillaume M."/><br /><sup><b>Guillaume M.</b></sup></a><br /><sup><a href="#ideas-theamnesic" title="Ideas, Planning, & Feedback">🤔</a></sup></td><td align="center"><a href="https://oscarotero.com"><img src="https://avatars3.githubusercontent.com/u/377873?v=4" width="100px;" alt="Oscar Otero"/><br /><sup><b>Oscar Otero</b></sup></a><br /><sup><a href="#ideas-oscarotero" title="Ideas, Planning, & Feedback">🤔</a></sup></td><td align="center"><a href="http://twitter.com/nicooprat"><img src="https://avatars0.githubusercontent.com/u/645641?v=4" width="100px;" alt="Nico Prat"/><br /><sup><b>Nico Prat</b></sup></a><br /><sup><a href="#ideas-nicooprat" title="Ideas, Planning, & Feedback">🤔</a></sup></td><td align="center"><a href="http://marco.solazzi.me/"><img src="https://avatars2.githubusercontent.com/u/104721?v=4" width="100px;" alt="Marco Solazzi"/><br /><sup><b>Marco Solazzi</b></sup></a><br /><sup><a href="https://github.com/barbajs/barba/issues?q=author%3Adwightjack" title="Bug reports">🐛</a></sup></td></tr><tr><td align="center" valign="top"><a href="https://github.com/atoupet-toki"><img src="https://avatars3.githubusercontent.com/u/38693082?v=4" width="100px;" alt="atoupet-toki"/><br /><sup><b>atoupet-toki</b></sup></a><br /><sup><a href="https://github.com/barbajs/barba/issues?q=author%3Aatoupet-toki" title="Bug reports">🐛</a></sup></td><td align="center"><a href="https://github.com/josias-r"><img src="https://avatars1.githubusercontent.com/u/11424820?v=4" width="100px;" alt="Josias"/><br /><sup><b>Josias</b></sup></a><br /><sup><a href="https://github.com/barbajs/barba/issues?q=author%3Ajosias-r" title="Bug reports">🐛</a></sup></td><td align="center"><a href="https://github.com/OksanaRomaniv"><img src="https://avatars1.githubusercontent.com/u/5724727?v=4" width="100px;" alt="Oksana Romaniv"/><br /><sup><b>Oksana Romaniv</b></sup></a><br /><sup><a href="https://github.com/barbajs/barba/issues?q=author%3AOksanaRomaniv" title="Bug reports">🐛</a></sup></td><td align="center"><a href="https://www.olivier-guilleux.com"><img src="https://avatars3.githubusercontent.com/u/5804006?v=4" width="100px;" alt="Olivier Guilleux"/><br /><sup><b>Olivier Guilleux</b></sup></a><br /><sup><a href="https://github.com/barbajs/barba/issues?q=author%3Aoguilleux" title="Bug reports">🐛</a></sup></td></tr></table>

<!-- ALL-CONTRIBUTORS-LIST:END -->

## Next steps

- [x] CI setup (PR, publish, …)
- [x] Write manual documentation
- [x] Generate code documentation
- [ ] Testing, debugging, fixing, testing…
- [ ] e2e testing suite
- [ ] New website
