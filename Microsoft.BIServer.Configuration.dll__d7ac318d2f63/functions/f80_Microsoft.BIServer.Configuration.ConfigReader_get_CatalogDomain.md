# Microsoft.BIServer.Configuration.ConfigReader::get_CatalogDomain

- ea: `0xf80`
- end: `0xfa1`
- name: `Microsoft.BIServer.Configuration.ConfigReader::get_CatalogDomain`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x67f0`

## callees

- `0xf70`
- `0xf80`
- `0x13b0`

## pseudocode

```c

```

## disassembly

```asm
0xf80  ldarg.0
0xf81  call     instance string Microsoft.BIServer.Configuration.ConfigReader::get_EncryptedCatalogDomain()
0xf86  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf8b  brtrue.s loc_F9F
0xf8d  ldarg.0
0xf8e  ldarg.0
0xf8f  call     instance string Microsoft.BIServer.Configuration.ConfigReader::get_EncryptedCatalogDomain()
0xf94  ldstr    aLogondomain// "LogonDomain"
0xf99  call     instance string Microsoft.BIServer.Configuration.ConfigReader::DecryptConfigData(string encryptedData, string element)
0xf9e  ret
0xf9f  ldnull
0xfa0  ret
```
