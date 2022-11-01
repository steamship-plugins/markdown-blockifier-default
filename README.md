# markdown-blockifier-default Blockifier Plugin - Steamship

This project documents a Steamship Blockifier plugin that converts Markdown text into Steamship format.

This repository is documentation only: this particular plugin is built in to the Steamship Engine directly.

## Usage

```python

from steamship import Steamship, File, MimeTypes

client = Steamship()

file = File.create(client, markdown_content, mime_type=MimeTypes.MKD)
blockifier = client.use_plugin("markdown-blockifier-default")
task = file.blockify(blockifier.handle)
task.wait()

```

## Input

The input should be a file whose content is Markdown text.

## Output

The output is one Steamship Block per block element of markdown, along with tags for span elements:

The list of tags used are those in the `DocTag` class
[defined in the Steamship Python Client](https://github.com/steamship-core/python-client/blob/main/src/steamship/data/tags/tag_constants.py#L23)
