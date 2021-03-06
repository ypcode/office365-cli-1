# spo field remove

Removes the specified list- or site column

## Usage

```sh
spo field remove [options]
```

## Options

Option|Description
------|-----------
`--help`|output usage information
`-u, --webUrl <webUrl>`|Absolute URL of the site where the field to remove is located
`-l, --listTitle [listTitle]`|Title of the list where the field is located. Specify only one of `listTitle`, `listId` or `listUrl`
`--listId [listId]`|ID of the list where the field is located. Specify only one of `listTitle`, `listId` or `listUrl`
`--listUrl [listUrl]`|Server- or web-relative URL of the list where the field is located. Specify only one of `listTitle`, `listId` or `listUrl`
`-i, --id [id]`|The ID of the field to remove. Specify `id` or `fieldTitle` but not both
`--fieldTitle [fieldTitle]`|The display name (case-sensitive) of the field to remove. Specify `id` or `fieldTitle` but not both
`--confirm`|Don't prompt for confirming removing the field
`--query [query]`|JMESPath query string. See [http://jmespath.org/](http://jmespath.org/) for more information and examples
`-o, --output [output]`|Output type. `json,text`. Default `text`
`--pretty`|Prettifies `json` output
`--verbose`|Runs command with verbose logging
`--debug`|Runs command with debug logging

## Examples

Remove the site column with the specified ID, located in site _https://contoso.sharepoint.com/sites/contoso-sales_

```sh
spo field remove --webUrl https://contoso.sharepoint.com/sites/contoso-sales --id 5ee2dd25-d941-455a-9bdb-7f2c54aed11b
```

Remove the list column with the specified ID, located in site _https://contoso.sharepoint.com/sites/contoso-sales_. Retrieves the list by its title

```sh
spo field remove --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listTitle Events --id 5ee2dd25-d941-455a-9bdb-7f2c54aed11b
```

Remove the list column with the specified display name, located in site _https://contoso.sharepoint.com/sites/contoso-sales_. Retrieves the list by its url

```sh
spo field remove --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listUrl 'Lists/Events' --fieldTitle 'Title'
```