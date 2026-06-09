# Microsoft.ManagementConsole.ScopeNode::set_EnabledStandardVerbs

- ea: `0x1720`
- end: `0x1741`
- name: `Microsoft.ManagementConsole.ScopeNode::set_EnabledStandardVerbs`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6f0`
- `0x1720`

## pseudocode

```c

```

## disassembly

```asm
0x1720  ldarg.0
0x1721  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x1726  callvirt instance valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.StandardVerbs [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::get_EnabledVerbs()
0x172b  ldarg.1
0x172c  beq.s    loc_1740
0x172e  ldarg.0
0x172f  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x1734  ldarg.1
0x1735  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::set_EnabledVerbs(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.StandardVerbs)
0x173a  ldarg.0
0x173b  call     instance void Microsoft.ManagementConsole.Node::Notify()
0x1740  ret
```
