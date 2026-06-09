# Microsoft.ReportingServices.Diagnostics.Encryption::DecryptToString_2

- ea: `0x9ed0`
- end: `0x9ede`
- name: `Microsoft.ReportingServices.Diagnostics.Encryption::DecryptToString_2`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9c30`

## callees

- `0x9cf0`
- `0x9ee0`

## pseudocode

```c

```

## disassembly

```asm
0x9ed0  ldarg.0
0x9ed1  call     int32 Microsoft.ReportingServices.Diagnostics.Encryption::get_CurrentVersion()
0x9ed6  ldarg.1
0x9ed7  ldarg.2
0x9ed8  call     instance string Microsoft.ReportingServices.Diagnostics.Encryption::DecryptToString(int32 version, unsigned int8[] protectedData, string tag)
0x9edd  ret
```
