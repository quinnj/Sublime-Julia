Sublime-Julia for SublimeText2
============================

Installation
============

1. Install Package Control. [http://wbond.net/sublime_packages/package_control](http://wbond.net/sublime_packages/package_control)
2. Navigate to your `Sublime Text 2/Packages` folder on the command line
  * `~/AppData/Roaming/Sublime Text 2/Packages` on Windows
  * `~/.config/sublime-text-2/Packages` on Linux
  * `~/Library/Application Support/Sublime Text 2/Packages` on OSX
3. Run the command `git clone https://github.com/karbarcca/Sublime-Julia.git Sublime-Julia`
4. Make any additional path or key binding configurations mentioned below

Features
--------

#### Common Sublime Features
 * Adds Julia build system file: Defaults to running `julia` with the current file on the command line; Note that users without julia or julia.bat (windows) in their system PATH need to manually specify julia's path/filename (e.g. "Preferences -> Browse Packages -> Julia -> Build -> Julia.sublime-build", edit "julia" to aboslute path/filename)
 * Adds common Julia snippets for convenience and for those hard-to-remember commands (e.g. `ccall`): ccall, for/while loops, list comprehensions, function/macro/type definitions, if/ifelse blocks
 * Julia language syntax: Note this is different than the other Julia Language sublime package; this package mirrors the official JuliaLang/julia github language syntax, with a few tweaks added for console use within sublime; To explicitly use this syntax, navigate to Julia REPL or .jl file and navigate the menus "View -> Syntax -> Sublime-Julia -> Julia"

#### SublimeREPL-Julia
 * Includes a forked SublimeREPL package tailored specifically for Julia; built to exist exclusive of SublimeREPL (meaning you may or may not have SublimeREPL installed and this will still work)
 * Creates a "SublimeREPL-Julia" menu under "Tools" to start the Julia REPL, and transfer commands
 * Adds REPL specific key bindings for REPL-like functionality (enter runs text in the buffer, esc clears buffer, etc.)
 * Also adds key bindings for Julia (.jl) files, `ctrl+enter` will send selected text or current line if no text is selected to the repl, `ctrl+shift+enter` runs the entire file
 * Included in package is the "Sublime User Key Bindings.txt" file with a command a user may optionally paste into "Preferences -> Key Bindings - User" to be able to open the REPL with `ctrl+j` (or any other command you may desire); Note using `ctrl+j` will replace the default key binding that joins lines
 * REPL is set to run the `julia-release-basic` version of Julia, so

#### SETTING REPL PATH: 
 The REPL is set to run `julia-basic.bat` (windows), `julia-release-basic` (linux,osx)  to open the Julia REPL; the following steps explain how to ensure your setup works correctly
 1. WINDOWS ONLY: Included in the repo is the file "julia-basic.bat"; copy and paste the file to your Julia directory (where your regular "julia.bat" file resides); this .bat file just changes your Julia installation to use the julia-release-basic.exe REPL instead of julia-release-readline.exe
 2. Open the SublimeREPL-Julia default settings "Preferences -> Package Settings -> SublimeREPL-Julia -> Settings - Default"
 3. Copy the file's contents
 4. Open the SublimeREPL-Julia user settings "Preferences -> Package Settings -> SublimeREPL-Julia -> Settings - User"
 5. Paste the default settings contents
 6. The first key is:  "default_extend_env": {},
 7. WINDOWS ONLY:
   1. Add your absolute Julia path (where your "julia-basic.bat" file now resides) inside the curly braces with the key "PATH"
   2. Your edited key should look like: "default_extend_env": {"PATH": "path to your julia-basic.bat"}, (*Note: just include the -path- to your julia-basic.bat file, not the filename itself)
 8. LINUX/OSX ONLY:
   1. Add your absolute Julia path (where your "julia-release-x" files are) inside the curly braces with the key "PATH"
   2. Your edited key should look like: "default_extend_env": {"PATH": "path to your julia dir/usr/bin"}, (*Note: just include the -path- to your julia-release-x files, not a filename itself)


License and Price
=================

Sublime-Julia is licensed under GPL.

Since version 1.2.0 SublimeREPL is licensed under GPL. Previous versions were licensed under BSD.
If you're using SublimeREPL in commercial environment a donation is strongly encouraged ;-)
see https://github.com/wuub/SublimeREPL for additional licensing info on SublimeREPL
