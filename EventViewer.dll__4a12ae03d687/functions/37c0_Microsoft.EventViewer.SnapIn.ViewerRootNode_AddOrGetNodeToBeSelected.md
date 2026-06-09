# Microsoft.EventViewer.SnapIn.ViewerRootNode::AddOrGetNodeToBeSelected

- ea: `0x37c0`
- end: `0x382c`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::AddOrGetNodeToBeSelected`
- size: `108`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1e70`
- `0x2050`
- `0x20b0`
- `0x2230`

## callees

- `0x3050`
- `0x31d0`
- `0x3530`
- `0x36f0`
- `0x37c0`

## pseudocode

```c

```

## disassembly

```asm
0x37c0  ldnull
0x37c1  stloc.0
0x37c2  ldarg.0
0x37c3  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x37c8  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeState()
0x37cd  ldc.i4.1
0x37ce  bne.un.s loc_37E3
0x37d0  ldarg.0
0x37d1  call     instance class Microsoft.EventViewer.SnapIn.MMCEventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::AddNewNodes()
0x37d6  stloc.0
0x37d7  ldarg.0
0x37d8  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x37dd  ldc.i4.1
0x37de  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::set_IsModified(bool)
0x37e3  ldloc.0
0x37e4  brtrue.s loc_382A
0x37e6  ldarg.1
0x37e7  brfalse.s loc_382A
0x37e9  ldarg.1
0x37ea  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x37ef  ldc.i4.s 9
0x37f1  beq.s    loc_37FC
0x37f3  ldarg.1
0x37f4  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x37f9  ldc.i4.6
0x37fa  bne.un.s loc_382A
0x37fc  ldarg.0
0x37fd  call     instance class Microsoft.EventViewer.SnapIn.ViewerRootNode Microsoft.EventViewer.SnapIn.ViewerRootNode::GetViewsRootNode()
0x3802  stloc.1
0x3803  ldarg.1
0x3804  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x3809  ldc.i4.6
0x380a  bne.un.s loc_3813
0x380c  ldarg.0
0x380d  call     instance class Microsoft.EventViewer.SnapIn.ViewerRootNode Microsoft.EventViewer.SnapIn.ViewerRootNode::GetExportLogRootNode()
0x3812  stloc.1
0x3813  ldloc.1
0x3814  brfalse.s loc_382A
0x3816  ldloc.1
0x3817  ldarg.1
0x3818  callvirt instance class Microsoft.EventViewer.SnapIn.MMCEventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::GetSubNodeByEventsNode(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode node)
0x381d  stloc.0
0x381e  ldarg.0
0x381f  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x3824  ldc.i4.1
0x3825  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::set_IsModified(bool)
0x382a  ldloc.0
0x382b  ret
```
