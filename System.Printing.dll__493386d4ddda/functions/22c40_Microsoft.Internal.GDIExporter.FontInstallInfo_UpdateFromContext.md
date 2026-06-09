# Microsoft.Internal.GDIExporter.FontInstallInfo::UpdateFromContext

- ea: `0x22c40`
- end: `0x22c55`
- name: `Microsoft.Internal.GDIExporter.FontInstallInfo::UpdateFromContext`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x22b10`
- `0x22b70`

## callees

- `0x22870`
- `0x22c40`

## pseudocode

```c

```

## disassembly

```asm
0x22c40  ldarg.0
0x22c41  ldfld    int32 Microsoft.Internal.GDIExporter.FontInstallInfo::_streamLength
0x22c46  brtrue.s loc_22C54
0x22c48  ldarg.0
0x22c49  ldarg.1
0x22c4a  call     instance int32 Microsoft.Internal.GDIExporter.FontStreamContext::get_StreamLength()
0x22c4f  stfld    int32 Microsoft.Internal.GDIExporter.FontInstallInfo::_streamLength
0x22c54  ret
```
