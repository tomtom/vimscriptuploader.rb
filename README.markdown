vimscriptuploader.rb -- Upload files to http://www.vim.org
==========================================================

This ruby script uploads vim plugins to http://www.vim.org\. You have to 
provide a script definition YAML file that has the following fields:

* id: The plugin's script ID on www.vim.org
* version: The plugin version number
* file: The filename that should be uploaded
* message: The version comment

Example YAML file:

    --- 
    id: "123"
    version: "0.01"
    file: /home/moi/.vim/vimballs/foo.vba
    message: |-
      Fixed this
      Done that

[vimball.rb](http://github.org/tomtom/vimball.rb) can generate such YAML 
files from a vimball recipe.

Those values can also be provided on the command line.


Example use
-----------

Load the user name and the password from a YAML file:

    vimscriptuploader.rb --config vim_org.yml myplugin.yml

where vim\_org.yml could look like:

    ---
    username: foo
    password: bar

Provide all arguments on the command line:

    vimscriptuploader.rb --username foo --password bar \\
        --id 123 --version 0.01 --message "Updated this and that" \\
        --file myplugin.vba


Dependencies
------------

* ruby 1.8
* www/mechanize

