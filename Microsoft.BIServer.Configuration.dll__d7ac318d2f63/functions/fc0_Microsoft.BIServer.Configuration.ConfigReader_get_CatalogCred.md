# Microsoft.BIServer.Configuration.ConfigReader::get_CatalogCred

- ea: `0xfc0`
- end: `0xfe1`
- name: `Microsoft.BIServer.Configuration.ConfigReader::get_CatalogCred`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x67f0`

## callees

- `0xfb0`
- `0xfc0`
- `0x13b0`

## pseudocode

```c

```

## disassembly

```asm
0xfc0  ldarg.0
0xfc1  call     instance string Microsoft.BIServer.Configuration.ConfigReader::get_EncryptedCatalogCred()
0xfc6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfcb  brtrue.s loc_FDF
0xfcd  ldarg.0
0xfce  ldarg.0
0xfcf  call     instance string Microsoft.BIServer.Configuration.ConfigReader::get_EncryptedCatalogCred()
0xfd4  ldstr    aLogoncred// "LogonCred"
0xfd9  call     instance string Microsoft.BIServer.Configuration.ConfigReader::DecryptConfigData(string encryptedData, string element)
0xfde  ret
0xfdf  ldnull
0xfe0  ret
```
