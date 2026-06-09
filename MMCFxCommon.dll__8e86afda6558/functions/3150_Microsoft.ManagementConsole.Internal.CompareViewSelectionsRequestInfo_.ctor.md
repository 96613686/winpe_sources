# Microsoft.ManagementConsole.Internal.CompareViewSelectionsRequestInfo::.ctor

- ea: `0x3150`
- end: `0x315e`
- name: `Microsoft.ManagementConsole.Internal.CompareViewSelectionsRequestInfo::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2e10`

## pseudocode

```c

```

## disassembly

```asm
0x3150  ldarg.0
0x3151  ldc.i4.m1
0x3152  stfld    int32 Microsoft.ManagementConsole.Internal.CompareViewSelectionsRequestInfo::_selectionIdToCompare
0x3157  ldarg.0
0x3158  call     instance void Microsoft.ManagementConsole.Internal.ViewSelectionRequestInfo::.ctor()
0x315d  ret
```
