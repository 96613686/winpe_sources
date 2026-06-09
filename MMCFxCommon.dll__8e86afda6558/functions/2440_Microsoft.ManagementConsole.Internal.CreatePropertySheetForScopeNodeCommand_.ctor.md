# Microsoft.ManagementConsole.Internal.CreatePropertySheetForScopeNodeCommand::.ctor

- ea: `0x2440`
- end: `0x244e`
- name: `Microsoft.ManagementConsole.Internal.CreatePropertySheetForScopeNodeCommand::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x23c0`

## pseudocode

```c

```

## disassembly

```asm
0x2440  ldarg.0
0x2441  ldc.i4.m1
0x2442  stfld    int32 Microsoft.ManagementConsole.Internal.CreatePropertySheetForScopeNodeCommand::_scopeNodeId
0x2447  ldarg.0
0x2448  call     instance void Microsoft.ManagementConsole.Internal.CreatePropertySheetCommand::.ctor()
0x244d  ret
```
