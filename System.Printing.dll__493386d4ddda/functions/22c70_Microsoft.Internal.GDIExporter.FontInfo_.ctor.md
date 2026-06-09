# Microsoft.Internal.GDIExporter.FontInfo::.ctor

- ea: `0x22c70`
- end: `0x22c94`
- name: `Microsoft.Internal.GDIExporter.FontInfo::.ctor`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14f0`

## callees

- `0x22af0`

## string_xrefs

- `0x22c7d`: `System font URI can't be null`

## pseudocode

```c

```

## disassembly

```asm
0x22c70  ldarg.0
0x22c71  call     instance void [mscorlib]System.Object::.ctor()
0x22c76  ldarg.1
0x22c77  ldnull
0x22c78  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x22c7d  ldstr    aSystemFontUriC// "System font URI can't be null"
0x22c82  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x22c87  ldarg.0
0x22c88  ldarg.1
0x22c89  newobj   instance void Microsoft.Internal.GDIExporter.FontInstallInfo::.ctor(class [System]System.Uri uri)
0x22c8e  stfld    class Microsoft.Internal.GDIExporter.FontInstallInfo Microsoft.Internal.GDIExporter.FontInfo::_systemInstall
0x22c93  ret
```
