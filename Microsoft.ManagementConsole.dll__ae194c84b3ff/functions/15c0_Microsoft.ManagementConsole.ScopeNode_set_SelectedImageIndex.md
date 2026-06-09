# Microsoft.ManagementConsole.ScopeNode::set_SelectedImageIndex

- ea: `0x15c0`
- end: `0x15e1`
- name: `Microsoft.ManagementConsole.ScopeNode::set_SelectedImageIndex`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6f0`
- `0x15c0`

## pseudocode

```c

```

## disassembly

```asm
0x15c0  ldarg.0
0x15c1  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x15c6  callvirt instance int32 [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::get_SelectedImageIndex()
0x15cb  ldarg.1
0x15cc  beq.s    loc_15E0
0x15ce  ldarg.0
0x15cf  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x15d4  ldarg.1
0x15d5  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::set_SelectedImageIndex(int32)
0x15da  ldarg.0
0x15db  call     instance void Microsoft.ManagementConsole.Node::Notify()
0x15e0  ret
```
