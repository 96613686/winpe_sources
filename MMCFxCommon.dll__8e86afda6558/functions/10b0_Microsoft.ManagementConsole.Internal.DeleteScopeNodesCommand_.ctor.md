# Microsoft.ManagementConsole.Internal.DeleteScopeNodesCommand::.ctor

- ea: `0x10b0`
- end: `0x10c3`
- name: `Microsoft.ManagementConsole.Internal.DeleteScopeNodesCommand::.ctor`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x370`

## pseudocode

```c

```

## disassembly

```asm
0x10b0  ldarg.0
0x10b1  ldc.i4.0
0x10b2  newarr   [mscorlib]System.Int32
0x10b7  stfld    int32[] Microsoft.ManagementConsole.Internal.DeleteScopeNodesCommand::_ids
0x10bc  ldarg.0
0x10bd  call     instance void Microsoft.ManagementConsole.Internal.Command::.ctor()
0x10c2  ret
```
