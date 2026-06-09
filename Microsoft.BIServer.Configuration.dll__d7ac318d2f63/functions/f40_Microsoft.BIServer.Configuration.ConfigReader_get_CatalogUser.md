# Microsoft.BIServer.Configuration.ConfigReader::get_CatalogUser

- ea: `0xf40`
- end: `0xf61`
- name: `Microsoft.BIServer.Configuration.ConfigReader::get_CatalogUser`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x67f0`

## callees

- `0xf30`
- `0xf40`
- `0x13b0`

## pseudocode

```c

```

## disassembly

```asm
0xf40  ldarg.0
0xf41  call     instance string Microsoft.BIServer.Configuration.ConfigReader::get_EncryptedCatalogUser()
0xf46  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf4b  brtrue.s loc_F5F
0xf4d  ldarg.0
0xf4e  ldarg.0
0xf4f  call     instance string Microsoft.BIServer.Configuration.ConfigReader::get_EncryptedCatalogUser()
0xf54  ldstr    aLogonuser// "LogonUser"
0xf59  call     instance string Microsoft.BIServer.Configuration.ConfigReader::DecryptConfigData(string encryptedData, string element)
0xf5e  ret
0xf5f  ldnull
0xf60  ret
```
