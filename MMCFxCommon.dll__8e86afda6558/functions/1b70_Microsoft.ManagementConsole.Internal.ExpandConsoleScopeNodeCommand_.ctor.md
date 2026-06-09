# Microsoft.ManagementConsole.Internal.ExpandConsoleScopeNodeCommand::.ctor

- ea: `0x1b70`
- end: `0x1b7e`
- name: `Microsoft.ManagementConsole.Internal.ExpandConsoleScopeNodeCommand::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1260`

## pseudocode

```c

```

## disassembly

```asm
0x1b70  ldarg.0
0x1b71  ldc.i4.m1
0x1b72  stfld    int32 Microsoft.ManagementConsole.Internal.ExpandConsoleScopeNodeCommand::_scopeNodeId
0x1b77  ldarg.0
0x1b78  call     instance void Microsoft.ManagementConsole.Internal.ViewCommand::.ctor()
0x1b7d  ret
```
