# Microsoft.ReportingServices.Diagnostics.RSConfiguration::DecryptConfigData

- ea: `0x3b60`
- end: `0x3b75`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::DecryptConfigData`
- size: `21`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3f00`
- `0x3f20`
- `0x3f40`
- `0x3f70`
- `0x3f90`
- `0x3fb0`

## callees

- `0x3b80`

## pseudocode

```c

```

## disassembly

```asm
0x3b60  ldarg.1
0x3b61  ldstr    asc_12EC0// "\\"
0x3b66  ldarg.2
0x3b67  call     string [mscorlib]System.String::Concat(string, string, string)
0x3b6c  stloc.0
0x3b6d  ldarg.0
0x3b6e  ldloc.0
0x3b6f  call     string Microsoft.ReportingServices.Diagnostics.RSConfiguration::DecryptConfigData(string encryptedData, string element)
0x3b74  ret
```
