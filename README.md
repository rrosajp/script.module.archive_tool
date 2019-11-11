archive_tool is a set of common tools to work with the Kodi libarchive virtual file system.  This should work with any of the following archive types:
.7z, .tar.gz, .tar.bz2, .tar.xz, .zip, .rar, .tgz, .tbz2, .gz, .bz2, .xz, .cbr

Simplest usage example:
```
import archive_tool

my_archive = archive_tool.archive_tool(archive_file = 'myfile.zip',directory_out = '/my/output_directory/') #Current archive object

file_listing = my_archive.list_all() #Lists all files in the archive

file_listing_dict = my_archive.stat_all() #Dict of all files in the archive containing fullpath, filename, file size (extracted)

files_extracted, success_of_extraction = my_archive.extract()  #Extracts all files to directory_out, returns list of files extracted and True/False for extraction success.  Defaults to extract all files in the archive.

#or

files_extracted, success_of_extraction = my_archive.extract(files_to_extract=file_listing[0])  #Extracts only the listed file(s) in the archive to directory_out, returns list of files extracted and True/False for extraction success

#Additional functions:

my_archive.archive_file('myfile2.zip') #Updates the currently set archive

my_archive.directory_out('/my/output_directory2/') #Updates the currently set output directory

my_archive.files_to_extract([file_listing[0],file_listing[3]]) #Updates the currently set file(s) to extract from the archive
```