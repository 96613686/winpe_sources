# Microsoft.BIServer.Configuration.ConfigReader::<Init>b__57_1

- ea: `0x1ba0`
- end: `0x1bac`
- name: `Microsoft.BIServer.Configuration.ConfigReader::<Init>b__57_1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x15b0`

## string_xrefs

- `0x1ba1`: `InstallationID`

## pseudocode

```c

```

## disassembly

```asm
0x1ba0  ldarg.0
0x1ba1  ldstr    aInstallationid// "InstallationID"
0x1ba6  call     instance valuetype [mscorlib]System.Guid Microsoft.BIServer.Configuration.ConfigReader::ReadGuid(string fieldName)
0x1bab  ret
```
