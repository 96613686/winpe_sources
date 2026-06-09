# Microsoft.BIServer.Configuration.ConfigReader::get_EncryptedCatalogCred

- ea: `0xfb0`
- end: `0xfbc`
- name: `Microsoft.BIServer.Configuration.ConfigReader::get_EncryptedCatalogCred`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xfc0`

## callees

- `0x15d0`

## pseudocode

```c

```

## disassembly

```asm
0xfb0  ldarg.0
0xfb1  ldstr    aLogoncred// "LogonCred"
0xfb6  call     instance string Microsoft.BIServer.Configuration.ConfigReader::ReadString(string fieldName)
0xfbb  ret
```
