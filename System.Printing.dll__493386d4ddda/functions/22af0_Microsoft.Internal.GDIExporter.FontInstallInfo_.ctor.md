# Microsoft.Internal.GDIExporter.FontInstallInfo::.ctor

- ea: `0x22af0`
- end: `0x22b0a`
- name: `Microsoft.Internal.GDIExporter.FontInstallInfo::.ctor`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x22c70`
- `0x22cb0`

## pseudocode

```c

```

## disassembly

```asm
0x22af0  ldarg.0
0x22af1  call     instance void [mscorlib]System.Object::.ctor()
0x22af6  ldarg.1
0x22af7  ldnull
0x22af8  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x22afd  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x22b02  ldarg.0
0x22b03  ldarg.1
0x22b04  stfld    class [System]System.Uri Microsoft.Internal.GDIExporter.FontInstallInfo::_uri
0x22b09  ret
```
