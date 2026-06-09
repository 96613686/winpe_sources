# Microsoft.BIServer.Configuration.ConfigReader::get_EncryptedCatalogDomain

- ea: `0xf70`
- end: `0xf7c`
- name: `Microsoft.BIServer.Configuration.ConfigReader::get_EncryptedCatalogDomain`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf80`

## callees

- `0x15d0`

## pseudocode

```c

```

## disassembly

```asm
0xf70  ldarg.0
0xf71  ldstr    aLogondomain// "LogonDomain"
0xf76  call     instance string Microsoft.BIServer.Configuration.ConfigReader::ReadString(string fieldName)
0xf7b  ret
```
