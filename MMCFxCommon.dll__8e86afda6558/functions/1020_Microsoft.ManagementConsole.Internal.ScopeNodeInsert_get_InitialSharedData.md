# Microsoft.ManagementConsole.Internal.ScopeNodeInsert::get_InitialSharedData

- ea: `0x1020`
- end: `0x103a`
- name: `Microsoft.ManagementConsole.Internal.ScopeNodeInsert::get_InitialSharedData`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x58d0`
- `0x6f20`

## callees

- `0xdf0`
- `0x1020`

## pseudocode

```c

```

## disassembly

```asm
0x1020  ldarg.0
0x1021  ldfld    class Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate Microsoft.ManagementConsole.Internal.ScopeNodeInsert::_initialSharedData
0x1026  brtrue.s loc_1033
0x1028  ldarg.0
0x1029  newobj   instance void Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate::.ctor()
0x102e  stfld    class Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate Microsoft.ManagementConsole.Internal.ScopeNodeInsert::_initialSharedData
0x1033  ldarg.0
0x1034  ldfld    class Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate Microsoft.ManagementConsole.Internal.ScopeNodeInsert::_initialSharedData
0x1039  ret
```
