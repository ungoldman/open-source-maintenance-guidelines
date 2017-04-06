# Open Source Maintenance Guidelines

> How to be a Good Open Source Shepherd

![](http://www.theshepherdsdog.com/LexAndBookII2.jpg)

Creating and maintaining an open source project can be a lot of work. Making sure a project is accessible to new users, open to contributions, and maintainable by the project owner is not a trivial task. In my experience the following details make a huge difference. They help users, developers, and maintainers work better (i.e. work less).

- [README](#readme)
- [Documentation](#documentation)
- [License](#license)
- [Tagged Releases](#tagged-releases)
- [Semantic Versioning](#semantic-versioning)
- [Change Log](#change-log)
- [Tests](#tests)
- [Contributing Guidelines](#contributing-guidelines)
- [Code of Conduct](#code-of-conduct)

## <a href="#readme" name="readme">README</a>

> You *always* need a README

A **`README.md`** file at the root of your project directory is the best and most important way to make your project easier to understand and use. A good `README.md` contains:

- The project's name
- A short description
- Installation instructions
- Usage instructions
- API documentation if applicable
- Contributing information with a link to the full contributing guidelines
- License information with a link to the full license

Here's how I generally try to format a `README.md` file:

```md
# Project Name

Short description.

## About

Long description if applicable.

## Install

Installation instructions.

## Usage

Usage instructions.

## API

API documentation if applicable.

## Contributing

Contributions welcome! Please read the [contributing guidelines](CONTRIBUTING.md) before getting started.

## License

[MIT](LICENSE.md)
```

If the project has a large or complex API, it may be a good idea to keep anything more than the most basic usage information in a separate documentation file or directory (such as `API.md` or `docs/README.md`) so the `README.md` file doesn't get too bloated.

### Further reading

- [Art of README](https://github.com/noffle/art-of-readme)
- [Readme Driven Development](http://tom.preston-werner.com/2010/08/23/readme-driven-development.html)
- [common-readme project](https://github.com/noffle/common-readme)

## <a href="#documentation" name="documentation">Documentation</a>

> Always Be Documenting

**Documentation** is a critical part of any software project that is very often overlooked. If your project is well documented, people will understand what it's for and it will be easier for them to use it. This means fully documenting installation, usage, and APIs.

- Describing how something works is good
- Showing a working example is better
- Doing both is best

Even creating documentation stubs (section headers with no content) is a good start. You can encourage first time contributors to pitch in by inviting them to fill out missing pieces. That said, don't expect newcomers to understand your code the way you do. It's always better to do some basic documenting to show people how to use your project.

### Further reading

- [Contributing to Open Source Documentation](http://blog.teamtreehouse.com/contributing-open-source-documentation)

## <a href="#license" name="license">License</a>

> Can I even use this?

If you have a clearly defined **license**, it's easier for people to know if they can use your project or not and under what terms. Keeping the text of your license in a `LICENSE.md` file at the root of your project makes it easier to link to and to read on github. I like to include the name of the type of license at the top of the file with a link to its [SPDX](http://spdx.org/) definition like so:

```md
# [MIT License](https://spdx.org/licenses/MIT)

(license text)
```

### Further reading

- [Open Source Licensing](https://help.github.com/articles/open-source-licensing/#where-does-the-license-live-on-my-repository)
- [SPDX License List](http://spdx.org/licenses/)

## <a href="#change-log" name="change-log">Change Log</a>

> I have no idea what's going on right now

If you have a good **change log**, it's easier for users to know what's going on, track progress of features, and deal with breaking changes. If your project changes frequently and you don't have a change log, users will be frustrated and maintainers may find themselves a bit lost too. Keeping a frequently updated `CHANGELOG.md` file at the root of your project helps ensure changes to the project will be as painless as possible for users and maintainers.

### Further reading

- [Keep a CHANGELOG](http://keepachangelog.com/)
- [module-init change log](https://github.com/ungoldman/module-init/blob/master/CHANGELOG.md) (simple example)
- [Node.js change log](https://github.com/nodejs/node/blob/master/CHANGELOG.md) (complex example)

## <a href="#tagged-releases" name="tagged-releases">Tagged Releases</a>

> Tag!

If you have **tagged releases**, it's easier to maintain the project and to inspect code from older versions. It's generally a good idea to have a commit that increments the project version and does nothing else, and to tag that commit using [annotated tags](https://git-scm.com/book/en/v2/Git-Basics-Tagging#Annotated-Tags).

Using `git tag -a vX.Y.Z` will open your editor allowing you to write release notes that will be saved in the project's git history and can also be published as a github release. It's a good idea to have release notes match what's in the change log for that release. Consistency makes it easier to automate this process and to not have to remember differences between content in the change log, annotated tags, and github releases.

### Further reading

- [Creating Releases](https://help.github.com/articles/creating-releases/)

## <a href="#semantic-versioning" name="semantic-versioning">Semantic Versioning</a>

> Bring meaning to your versions

If you use **semantic versioning**, your project is easier to include elsewhere and to rely on. Semantic versioning makes it easier to trust that your project's changes won't break software that depends on it. Package managers like [npm](https://docs.npmjs.com/getting-started/semantic-versioning) use semantic versioning to manage [dependency graphs](https://en.wikipedia.org/wiki/Dependency_graph).

Semantic versioning is actually pretty simple, and breaks down like this:

MAJOR.MINOR.PATCH

- Breaking changes should always be a MAJOR version bump and generally should not be introduced lightly
- New features or changes that don't break backwards compatibility should be a MINOR version bump
- Bug fixes and documentation updates should be a PATCH version bump

### Further reading

- [Semantic Versioning 2.0.0](http://semver.org/)

## <a href="#tests" name="tests">Tests</a>

> There will be mistakes

If you have **tests**, it's easier for you to vet and accept contributions from contributors and it's easier to keep a project healthy and functional as it grows. Testing can mean just using a linter like [`standard`](https://github.com/feross/standard) to catch syntax errors and avoid style arguments, or going further and writing [unit tests](https://en.wikipedia.org/wiki/Unit_testing), [integration tests](https://en.wikipedia.org/wiki/Integration_testing), or whichever flavor of testing makes sense for your project.

You can go nuts and add a massive amount of tests at all levels and work yourself to death to achieve 100% test coverage, but in my experience it's best to not go nuts. Keeping projects small and focused and using tests judiciously to ensure public methods are functional and work as promised is usually adequate, at least when a project is starting out.

### Further reading

- [Testing JavaScript Modules with Tape](https://ponyfoo.com/articles/testing-javascript-modules-with-tape)
- [Software testing: Testing levels](https://en.wikipedia.org/wiki/Software_testing#Testing_levels) (Wikipedia)

## <a href="#contributing-guidelines" name="contributing-guidelines">Contributing Guidelines</a>

> Contributors! Contributors! Contributors!

If you have **contributing guidelines**, it's easier for people to participate in the project and make valuable contributions. A good set of contributing guidelines helps set the tone, frame the discussion, set expectations and ease the path towards contributors and collaborators joining the project. Keeping a `CONTRIBUTING.md` file at the root of your project and linking to it from `README.md` makes contributing to your project a lot more straightforward.

##### Further reading

- [Contributing Guidelines](https://github.com/blog/1184-contributing-guidelines)
- [OPEN Open Source Project](http://openopensource.org/)
- [jden/CONTRIBUTING.md](https://github.com/jden/CONTRIBUTING.md)
- [ungoldman/CONTRIBUTING.md](https://github.com/ungoldman/CONTRIBUTING.md)
- [ungoldman/contribs](https://github.com/ungoldman/contribs)

## <a href="#code-of-conduct" name="code-of-conduct">Code of Conduct</a>

> Don't be a jerk

A **code of conduct** helps make open an source project a safe, welcoming space for collaboration. The inclusion of a code of conduct in an open source project has at times been met with controversy, but it really shouldn't be. A code of conduct protects everyone from harassment and discrimination, and sets a minimum level of respect and civility for our fellow humans that helps grow a healthy, positive, and productive community.

The [Contributor Covenant](http://contributor-covenant.org/), a Code of Conduct for Open Source Projects, has done a great job of providing a strong template for others to use. I tend to place the following text at the top of the contributing guidelines I use for my projects:

```md
## Code of Conduct

This project is intended to be a safe, welcoming space for collaboration. All contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct. Thank you for being kind to each other!
```

If a project grows beyond a few contributors it may be a good idea to place the text of your code of conduct in a `CODE-OF-CONDUCT.md` file at the root of the project.

### Further reading

- [Contributor Covenant](http://contributor-covenant.org/)
- [The Responsible Communication Style Guide](https://www.kickstarter.com/projects/961164339/the-responsible-communication-style-guide)

## Make Life Easier

To summarize, a healthy open source project will have **all** of the following criteria:

- [README](#readme)
- [Documentation](#documentation)
- [License](#license)
- [Tagged Releases](#tagged-releases)
- [Semantic Versioning](#semantic-versioning)
- [Change Log](#change-log)
- [Tests](#tests)
- [Contributing Guidelines](#contributing-guidelines)
- [Code of Conduct](#code-of-conduct)

If you do your homework early on (and automate a lot of these processes) your life will be way easier down the road. If you wait to do these things when the project's already been out there for a while, it will be harder for you to add these things, and harder for other people to use and contribute to your project.

I've made a few tools over the years to automate some basic lifecycle tasks for [node](https://nodejs.org/en/) projects:

- [`module-init`](https://github.com/ungoldman/module-init): Create a new node module with all the right stuff.
- [`contribs`](https://github.com/ungoldman/contribs): Generate boilerplate open source contributing guidelines.
- [`gh-release`](https://github.com/hypermodules/gh-release): Create a github release for a node package.

Lots of other people have made great maintenance modules too. Max Ogden's [`maintenance-modules`](https://github.com/maxogden/maintenance-modules) is an excellent list of resources on this subject.

If you know of any other projects that are making the above processes easier or know of any other resources or links to further reading that should be added to the above sections, please [let me know](https://github.com/ungoldman/open-source-maintenance-guidelines/issues)!

![](https://camo.githubusercontent.com/b99f27dae004731e81b47fe77bd2fcf30c063dc1/68747470733a2f2f33382e6d656469612e74756d626c722e636f6d2f37626636353834613561323734666538336162346136326361663432653638302f74756d626c725f6d756c6674753649346431716173667a396f315f3530302e676966)

Do yourself a favor, make life easier!

---

> This article was originally posted here: http://ungoldman.com/articles/open-source-maintenance-guidelines/
