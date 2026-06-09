# Microsoft.VisualStudio.Setup.ElevationServiceManager::GeneratePipeName

- ea: `0xf00`
- end: `0xf13`
- name: `Microsoft.VisualStudio.Setup.ElevationServiceManager::GeneratePipeName`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xd60`

## pseudocode

```c

```

## disassembly

```asm
0xf00  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xf05  stloc.0
0xf06  ldloca.s 0
0xf08  ldstr    aN// "N"
0xf0d  call     instance string [mscorlib]System.Guid::ToString(string)
0xf12  ret
```
