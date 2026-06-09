# Microsoft.ManagementConsole.Internal.FindPropertySheetForScopeNodeCommand::.ctor

- ea: `0x2300`
- end: `0x230e`
- name: `Microsoft.ManagementConsole.Internal.FindPropertySheetForScopeNodeCommand::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2280`

## pseudocode

```c

```

## disassembly

```asm
0x2300  ldarg.0
0x2301  ldc.i4.m1
0x2302  stfld    int32 Microsoft.ManagementConsole.Internal.FindPropertySheetForScopeNodeCommand::_scopeNodeId
0x2307  ldarg.0
0x2308  call     instance void Microsoft.ManagementConsole.Internal.FindPropertySheetCommand::.ctor()
0x230d  ret
```
