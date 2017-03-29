# History

This is a fork of a [fork](
https://github.com/grittathh/Evernote2AnkiMac) of a [fork](https://github.com/rbuc/Evernote2AnkiMac) and it seems to have all stared [here](https://github.com/brumar/anknotes).

# Functionality

Honestly, I'm not even sure what exactly this thing does. Here's what I've used it for:

* Tag a note in Evernote with the `Anki` tag
* This addon will create, update, and delete Anki notes as appropriate with an `Evernote` Anki note type
* It'll convert single-page PDFs to images (see below for caveat)

# Limitations

1. Multi-page PDFs cause the import to fail, but single-page PDFs 
2. Since the addon's goal is to sync with Evernote, it deletes notes from Anki that are no longer present in Evernote (or no longer tagged with the tag you specify). Thus, if you use Anki Desktop on two machines, and you run the import before Evernote syncs, the Evernote2AnkiMac addon will delete the Anki note. You can automatically regenerate those notes by syncing Evernote and re-running the Evernote2AnkiMac import, but you will have lost the history of those notes.

# Installation (Mac)

Since it converts PDFs in Evernote to PNG in Anki. You need to install ImageMagick (and some accompanying tools).

### If you haven't installed ImageMagic

> You'll need to install homebrew first

```
brew install libtiff
brew install fontconfig
brew install ghostscript
brew install imagemagick --with-fontconfig --with-ghostscript --with-libtiff
```

### If you've installed ImageMagick without any of the extra options, you can do this:

```
brew list      # to see what you have got
brew install <whatever is missing out of libtiff, fontconfig, ghostscript>
brew reinstall imagemagick --with-fontconfig --with-ghostscript --with-libtiff
```

> [source](http://stackoverflow.com/a/24882401/670400) for ImageMagick installation help

# Setup

* In Anki’s preferences, go to the Evernote Importer tab and make sure each text field has some text (otherwise you’ll experience an error).
* I had to check “Keep Evernote Tags” otherwise I got an error

# Usage

Tools → Import from Evernote
