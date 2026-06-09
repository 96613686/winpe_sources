# Microsoft.ManagementConsole.Internal.ExtensionPagesRequestInfo::.ctor

- ea: `0x3280`
- end: `0x328e`
- name: `Microsoft.ManagementConsole.Internal.ExtensionPagesRequestInfo::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x3b0`

## pseudocode

```c

```

## disassembly

```asm
0x3280  ldarg.0
0x3281  ldc.i4.m1
0x3282  stfld    int32 Microsoft.ManagementConsole.Internal.ExtensionPagesRequestInfo::_sheetId
0x3287  ldarg.0
0x3288  call     instance void Microsoft.ManagementConsole.Internal.RequestInfo::.ctor()
0x328d  ret
```
