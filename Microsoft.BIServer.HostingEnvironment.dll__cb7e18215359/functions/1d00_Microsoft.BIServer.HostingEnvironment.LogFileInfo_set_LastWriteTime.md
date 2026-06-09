# Microsoft.BIServer.HostingEnvironment.LogFileInfo::set_LastWriteTime

- ea: `0x1d00`
- end: `0x1d08`
- name: `Microsoft.BIServer.HostingEnvironment.LogFileInfo::set_LastWriteTime`
- size: `8`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1c90`
- `0x1cb0`

## pseudocode

```c

```

## disassembly

```asm
0x1d00  ldarg.0
0x1d01  ldarg.1
0x1d02  stfld    valuetype [mscorlib]System.DateTime Microsoft.BIServer.HostingEnvironment.LogFileInfo::<LastWriteTime>k__BackingField
0x1d07  ret
```
