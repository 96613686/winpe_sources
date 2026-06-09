# Microsoft.ManagementConsole.ScopeNode::get_Children

- ea: `0x15f0`
- end: `0x1616`
- name: `Microsoft.ManagementConsole.ScopeNode::get_Children`
- size: `38`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1000`
- `0x10b0`
- `0x11f0`
- `0x1230`
- `0x1350`
- `0xc750`

## callees

- `0x15f0`
- `0x5a10`
- `0x5a60`

## pseudocode

```c

```

## disassembly

```asm
0x15f0  ldarg.0
0x15f1  ldfld    class Microsoft.ManagementConsole.ScopeNodeCollection Microsoft.ManagementConsole.ScopeNode::_children
0x15f6  brtrue.s loc_160F
0x15f8  ldarg.0
0x15f9  newobj   instance void Microsoft.ManagementConsole.ScopeNodeCollection::.ctor()
0x15fe  stfld    class Microsoft.ManagementConsole.ScopeNodeCollection Microsoft.ManagementConsole.ScopeNode::_children
0x1603  ldarg.0
0x1604  ldfld    class Microsoft.ManagementConsole.ScopeNodeCollection Microsoft.ManagementConsole.ScopeNode::_children
0x1609  ldarg.0
0x160a  callvirt instance void Microsoft.ManagementConsole.ScopeNodeCollection::set_ContainerNode(class Microsoft.ManagementConsole.ScopeNode value)
0x160f  ldarg.0
0x1610  ldfld    class Microsoft.ManagementConsole.ScopeNodeCollection Microsoft.ManagementConsole.ScopeNode::_children
0x1615  ret
```
