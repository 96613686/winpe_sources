# Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions

- ea: `0x1620`
- end: `0x163a`
- name: `Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xd60`

## callees

- `0x1620`
- `0x1640`
- `0x8ba0`

## pseudocode

```c

```

## disassembly

```asm
0x1620  ldarg.0
0x1621  ldfld    class Microsoft.ManagementConsole.ViewDescriptionCollection Microsoft.ManagementConsole.ScopeNode::_viewDescriptions
0x1626  brtrue.s loc_1633
0x1628  ldarg.0
0x1629  newobj   instance void Microsoft.ManagementConsole.ViewDescriptionCollection::.ctor()
0x162e  call     instance void Microsoft.ManagementConsole.ScopeNode::set_ViewDescriptions(class Microsoft.ManagementConsole.ViewDescriptionCollection value)
0x1633  ldarg.0
0x1634  ldfld    class Microsoft.ManagementConsole.ViewDescriptionCollection Microsoft.ManagementConsole.ScopeNode::_viewDescriptions
0x1639  ret
```
