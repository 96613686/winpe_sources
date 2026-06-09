# Microsoft.EventViewer.SnapIn.ViewerRootNode::GetEventViewerRootNode

- ea: `0x1ae0`
- end: `0x1b36`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::GetEventViewerRootNode`
- size: `86`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x20b0`
- `0x3050`
- `0x3110`
- `0x31d0`
- `0x7d50`

## callees

- `0x1ae0`
- `0x3be0`
- `0x3d70`
- `0x9120`

## pseudocode

```c

```

## disassembly

```asm
0x1ae0  ldarg.0
0x1ae1  stloc.0
0x1ae2  br.s     loc_1AEB
0x1ae4  ldloc.0
0x1ae5  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Parent()
0x1aea  stloc.0
0x1aeb  ldloc.0
0x1aec  isinst   Microsoft.EventViewer.SnapIn.MMCRootNode
0x1af1  brtrue.s loc_1AF6
0x1af3  ldloc.0
0x1af4  brtrue.s loc_1AE4
0x1af6  nop
0x1af7  ldloc.0
0x1af8  castclass Microsoft.EventViewer.SnapIn.MMCRootNode
0x1afd  stloc.1
0x1afe  ldloc.1
0x1aff  brfalse.s loc_1B0B
0x1b01  ldloc.1
0x1b02  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::ExpandNode()
0x1b07  ldloc.1
0x1b08  stloc.2
0x1b09  leave.s  loc_1B34
0x1b0b  leave.s  loc_1B32
0x1b0d  stloc.3
0x1b0e  ldloc.3
0x1b0f  ldarg.0
0x1b10  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x1b15  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_Console()
0x1b1a  call     bool Microsoft.EventViewer.SnapIn.ViewerCommon::HandleException(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console con)
0x1b1f  brfalse.s loc_1B29
0x1b21  ldloc.3
0x1b22  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_RefreshConsole()
0x1b27  brfalse.s loc_1B30
0x1b29  ldarg.0
0x1b2a  ldloc.3
0x1b2b  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshConsole(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e)
0x1b30  leave.s  loc_1B32
0x1b32  ldnull
0x1b33  ret
0x1b34  ldloc.2
0x1b35  ret
```
