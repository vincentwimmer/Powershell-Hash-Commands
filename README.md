# Powershell-Hash-Commands

### Search for specific hash under location:
> Get-ChildItem "C:\PATH\" -Recurse |
	Get-FileHash |
	Where-Object hash -eq HASH |
	Select path
 
### Get all hashes under location and append CSV file:
> Get-ChildItem -path "C:\PATH\" -Recurse -Force -File | 
	Get-FileHash | 
	Sort-Object -Property 'Path' |
	Export-Csv -Path "C:\REPORT.CSV" -NoTypeInformation
	
#### Get-FileHash -Algorithm \<String> |
> Added with one of these arguments below will pull specific types of hashes.

- SHA1
- SHA256
- SHA384
- SHA512
- MD5
