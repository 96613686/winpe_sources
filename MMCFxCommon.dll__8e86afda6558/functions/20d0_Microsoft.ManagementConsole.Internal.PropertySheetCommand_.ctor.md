# Microsoft.ManagementConsole.Internal.PropertySheetCommand::.ctor

- ea: `0x20d0`
- end: `0x20e5`
- name: `Microsoft.ManagementConsole.Internal.PropertySheetCommand::.ctor`
- size: `21`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2100`
- `0x2120`
- `0x2140`
- `0x2180`
- `0x21c0`

## callees

- `0x370`

## pseudocode

```c

```

## disassembly

```asm
0x20d0  ldarg.0
0x20d1  ldc.i4.m1
0x20d2  stfld    int32 Microsoft.ManagementConsole.Internal.PropertySheetCommand::_sheetId
0x20d7  ldarg.0
0x20d8  ldc.i4.m1
0x20d9  stfld    int32 Microsoft.ManagementConsole.Internal.PropertySheetCommand::_pageId
0x20de  ldarg.0
0x20df  call     instance void Microsoft.ManagementConsole.Internal.Command::.ctor()
0x20e4  ret
```
