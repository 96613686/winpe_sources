# Microsoft.ManagementConsole.ScopeNode::.ctor_2

- ea: `0x1940`
- end: `0x1954`
- name: `Microsoft.ManagementConsole.ScopeNode::.ctor_2`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1900`

## pseudocode

```c

```

## disassembly

```asm
0x1940  ldarg.0
0x1941  ldarg.1
0x1942  call     instance void Microsoft.ManagementConsole.ScopeNode::.ctor(valuetype [mscorlib]System.Guid nodeType)
0x1947  ldarg.0
0x1948  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x194d  ldarg.2
0x194e  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::set_HideExpandIcon(bool)
0x1953  ret
```
