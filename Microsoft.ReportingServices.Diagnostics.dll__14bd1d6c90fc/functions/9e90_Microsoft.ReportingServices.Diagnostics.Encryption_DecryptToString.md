# Microsoft.ReportingServices.Diagnostics.Encryption::DecryptToString

- ea: `0x9e90`
- end: `0x9e9e`
- name: `Microsoft.ReportingServices.Diagnostics.Encryption::DecryptToString`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3b80`

## callees

- `0x9cf0`
- `0x9eb0`

## pseudocode

```c

```

## disassembly

```asm
0x9e90  ldarg.0
0x9e91  call     int32 Microsoft.ReportingServices.Diagnostics.Encryption::get_CurrentVersion()
0x9e96  ldarg.1
0x9e97  ldnull
0x9e98  call     instance string Microsoft.ReportingServices.Diagnostics.Encryption::DecryptToString(int32 version, string protectedData, string tag)
0x9e9d  ret
```
