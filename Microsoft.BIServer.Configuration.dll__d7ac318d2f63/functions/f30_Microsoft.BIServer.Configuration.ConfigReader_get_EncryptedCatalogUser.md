# Microsoft.BIServer.Configuration.ConfigReader::get_EncryptedCatalogUser

- ea: `0xf30`
- end: `0xf3c`
- name: `Microsoft.BIServer.Configuration.ConfigReader::get_EncryptedCatalogUser`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf40`

## callees

- `0x15d0`

## pseudocode

```c

```

## disassembly

```asm
0xf30  ldarg.0
0xf31  ldstr    aLogonuser// "LogonUser"
0xf36  call     instance string Microsoft.BIServer.Configuration.ConfigReader::ReadString(string fieldName)
0xf3b  ret
```
