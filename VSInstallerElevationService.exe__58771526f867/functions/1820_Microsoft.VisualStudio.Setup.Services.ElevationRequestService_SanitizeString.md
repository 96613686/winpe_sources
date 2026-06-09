# Microsoft.VisualStudio.Setup.Services.ElevationRequestService::SanitizeString

- ea: `0x1820`
- end: `0x1840`
- name: `Microsoft.VisualStudio.Setup.Services.ElevationRequestService::SanitizeString`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800`

## callees

- `0x1820`

## pseudocode

```c

```

## disassembly

```asm
0x1820  ldarg.0
0x1821  ldstr    asc_39B2// "\""
0x1826  callvirt instance bool [mscorlib]System.String::Contains(string)
0x182b  brtrue.s loc_182F
0x182d  ldarg.0
0x182e  ret
0x182f  ldarg.0
0x1830  ldstr    asc_39B2// "\""
0x1835  ldstr    asc_39B6// "\\\""
0x183a  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x183f  ret
```
