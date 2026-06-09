# Microsoft.ManagementConsole.ScopeNode::.ctor_1

- ea: `0x1920`
- end: `0x1933`
- name: `Microsoft.ManagementConsole.ScopeNode::.ctor_1`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18a0`

## pseudocode

```c

```

## disassembly

```asm
0x1920  ldarg.0
0x1921  call     instance void Microsoft.ManagementConsole.ScopeNode::.ctor()
0x1926  ldarg.0
0x1927  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x192c  ldarg.1
0x192d  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::set_HideExpandIcon(bool)
0x1932  ret
```
