# Name Generator

This is a name generator for fictional characters. It's first and
foremost a library that can be added to other projects. It also
has a `namegen` command line utility for generating names.

## Building

Use the `./build.sh` bash script to build the binary for your
system.

## Adding a new name generator

There are 4 steps to adding a new name generator to this project.

### Step one: add name lists as global variables

First, create a new .go file for your name lists. Within it,
create three new global variables - one for male first names,
one for female first names, and one for family names. They
should be named appropriately (see existing files for reference).

### Step two: add a new name generator to the map

In namegen.go, add your name generator to the map of name
generators in the NameGeneratorFromType function. It should
reference the global variables you created in step one.

### Step three: add the name type to the CLI program's code

In cmd/namegen/main.go, add the name type to the `nameLists`
array.

### Step four: build and test your addition

Run `./build.sh` and test out your new name generator.

Parameters:

`-n N` where N is the number of names to generate.

`-g male|female|both` Gender of the names to generate.

`-o language` Origin of the names to generate. List with `-l`.

`-s A` Random generator seed. A is an alphanumeric string.

`-m full` Mode of generation.

`-l` Print available name lists.
