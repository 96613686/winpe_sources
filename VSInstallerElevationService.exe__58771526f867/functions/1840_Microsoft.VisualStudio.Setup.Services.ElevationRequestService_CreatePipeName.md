# Microsoft.VisualStudio.Setup.Services.ElevationRequestService::CreatePipeName

- ea: `0x1840`
- end: `0x1853`
- name: `Microsoft.VisualStudio.Setup.Services.ElevationRequestService::CreatePipeName`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1860`

## pseudocode

```c

```

## disassembly

```asm
0x1840  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1845  stloc.0
0x1846  ldloca.s 0
0x1848  ldstr    aN// "N"
0x184d  call     instance string [mscorlib]System.Guid::ToString(string)
0x1852  ret
```
