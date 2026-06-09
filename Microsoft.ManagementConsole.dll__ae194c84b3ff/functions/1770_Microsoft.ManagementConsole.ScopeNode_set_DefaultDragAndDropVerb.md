# Microsoft.ManagementConsole.ScopeNode::set_DefaultDragAndDropVerb

- ea: `0x1770`
- end: `0x179b`
- name: `Microsoft.ManagementConsole.ScopeNode::set_DefaultDragAndDropVerb`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6f0`
- `0x1770`

## pseudocode

```c

```

## disassembly

```asm
0x1770  ldarg.0
0x1771  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x1776  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteTargetInfo [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::get_PasteTargetInfo()
0x177b  callvirt instance valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.DragAndDropVerb [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteTargetInfo::get_DefaultDragAndDropVerb()
0x1780  ldarg.1
0x1781  beq.s    loc_179A
0x1783  ldarg.0
0x1784  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x1789  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteTargetInfo [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::get_PasteTargetInfo()
0x178e  ldarg.1
0x178f  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteTargetInfo::set_DefaultDragAndDropVerb(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.DragAndDropVerb)
0x1794  ldarg.0
0x1795  call     instance void Microsoft.ManagementConsole.Node::Notify()
0x179a  ret
```
