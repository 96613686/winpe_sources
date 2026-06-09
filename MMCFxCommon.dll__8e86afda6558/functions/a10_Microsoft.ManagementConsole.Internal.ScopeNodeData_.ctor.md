# Microsoft.ManagementConsole.Internal.ScopeNodeData::.ctor

- ea: `0xa10`
- end: `0xa29`
- name: `Microsoft.ManagementConsole.Internal.ScopeNodeData::.ctor`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5970`

## callees

- `0x800`

## pseudocode

```c

```

## disassembly

```asm
0xa10  ldarg.0
0xa11  ldc.i4.m1
0xa12  stfld    int32 Microsoft.ManagementConsole.Internal.ScopeNodeData::_viewSetId
0xa17  ldarg.0
0xa18  ldsfld   string [mscorlib]System.String::Empty
0xa1d  stfld    string Microsoft.ManagementConsole.Internal.ScopeNodeData::_languageIndependentName
0xa22  ldarg.0
0xa23  call     instance void Microsoft.ManagementConsole.Internal.NodeData::.ctor()
0xa28  ret
```
