# gptel-autocomplete

`gptel-autocomplete` is an Emacs package that provides inline code completion using the [`gptel`](https://github.com/karthink/gptel) package. It displays AI-generated completions as ghost text at the cursor position, allowing you to preview and accept suggestions while coding.

## Features

- Request completions from LLMs with context around the cursor (context window size is configurable).
- Display inline ghost text completions.
- Accept completions to insert them into your buffer.
- Provide additional context using standard `gptel` features (e.g. `gptel-add`).

## Requirements

- Emacs 27.2 or newer
- [`gptel`](https://github.com/karthink/gptel) package properly installed and configured

## Installation

First, follow the [gptel setup instructions](https://github.com/karthink/gptel) to install and configure `gptel` and set your OpenAI API key.

Then, install `gptel-autocomplete` using `straight.el` by adding the following to your Emacs config:

```elisp
(straight-use-package
 '(gptel-autocomplete :type git :host github :repo "JDNdeveloper/gptel-autocomplete"))
```

After installation, require and enable the package as needed:

```elisp
(require 'gptel-autocomplete)
```

## Configuration

You can customize the amount of context sent before and after the cursor:

```elisp
(setq gptel-autocomplete-before-context 10000)
(setq gptel-autocomplete-after-context 1000)
```

Set a custom temperature (lower values tend to yield better results):

```elisp
(setq gptel-autocomplete-temperature 0.1)
```

Enable debug messages if you want detailed logs:

```elisp
(setq gptel-autocomplete-debug t)
```

## Usage

- `M-x gptel-complete` — Request a completion at point and display it as ghost text.
- `M-x gptel-accept-completion` — Accept the currently displayed completion and insert it.

You can bind these commands to convenient keys in your preferred programming modes.
