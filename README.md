# powershell-file-renamer-Chinese-prefix
A PowerShell-based solution to automate the renaming of files with non-ASCII prefixes, specifically targeting the `[电影天堂www.dytt89.com]` prefix.

**Usage**
1. Open PowerShell:
     Ensure you have PowerShell installed on your system.
2. Run the Script:
     Navigate to the directory containing the script
     Example: Set-Location "E:\1 Movies"
3. Execute the script:
     ./rename_files.ps1
4. Alternatively, run the command directly:
     Example: Get-ChildItem | Where-Object { $_.Name -match '^\[电影天堂www\.dytt89\.com]' } | Rename-Item -NewName { $_.Name -replace '^\[电影天堂www\.dytt89\.com]', '' } -Force

**Troubleshooting**
1. If the Chinese characters appear as ????, then the solution is to ensure that PowerShell is using UTF-8 encoding:
   $PSDefaultParameterValues['*:Encoding'] = 'utf8'
2. If the files are not renamed, the solution is to verify that the prefix matches exactly by using the following command to debug:
   Get-ChildItem | Where-Object { $_.Name -match '^\[电影天堂www\.dytt89\.com]' } | Select-Object Name
