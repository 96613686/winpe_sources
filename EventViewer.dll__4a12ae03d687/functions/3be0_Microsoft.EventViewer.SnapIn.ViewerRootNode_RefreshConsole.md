# Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshConsole

- ea: `0x3be0`
- end: `0x3c48`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshConsole`
- size: `104`
- prototype: ``
- caller_count: `26`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1ae0`
- `0x1c40`
- `0x3050`
- `0x3110`
- `0x31d0`
- `0x3280`
- `0x3c50`
- `0x3e60`
- `0x3ed0`
- `0x4520`
- `0x4730`
- `0x4780`
- `0x4940`
- `0x5400`
- `0x54a0`
- `0x5710`
- `0x57a0`
- `0x5960`
- `0x5a50`
- `0x5bf0`
- `0x6810`
- `0x6960`
- `0x6f20`
- `0x7700`
- `0x7810`
- `0x97f0`

## callees

- `0x1010`
- `0x15c0`
- `0x1860`
- `0x1a00`
- `0x1b40`
- `0x2280`
- `0x3be0`

## pseudocode

```c

```

## disassembly

```asm
0x3be0  ldarg.1
0x3be1  brfalse.s loc_3BF6
0x3be3  ldarg.1
0x3be4  brfalse.s loc_3C47
0x3be6  ldarg.1
0x3be7  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_RefreshConsole()
0x3bec  brfalse.s loc_3C47
0x3bee  ldarg.0
0x3bef  call     instance bool Microsoft.EventViewer.SnapIn.ViewerRootNode::get_MarkNodeDeleted()
0x3bf4  brtrue.s loc_3C47
0x3bf6  ldarg.0
0x3bf7  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x3bfc  isinst   Microsoft.EventViewer.SnapIn.EventViewerSnapIn
0x3c01  stloc.0
0x3c02  ldloc.0
0x3c03  brfalse.s loc_3C0E
0x3c05  ldloc.0
0x3c06  ldarg.1
0x3c07  callvirt instance void Microsoft.EventViewer.SnapIn.EventViewerSnapIn::RefreshConsole(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e)
0x3c0c  br.s     loc_3C24
0x3c0e  ldarg.0
0x3c0f  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x3c14  isinst   Microsoft.EventViewer.SnapIn.EventViewerExtension
0x3c19  stloc.1
0x3c1a  ldloc.1
0x3c1b  brfalse.s loc_3C24
0x3c1d  ldloc.1
0x3c1e  ldarg.1
0x3c1f  callvirt instance void Microsoft.EventViewer.SnapIn.EventViewerExtension::RefreshConsole(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e)
0x3c24  ldarg.0
0x3c25  call     instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x3c2a  brfalse.s loc_3C47
0x3c2c  ldarg.0
0x3c2d  call     instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x3c32  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeState()
0x3c37  ldc.i4.4
0x3c38  beq.s    loc_3C47
0x3c3a  ldarg.0
0x3c3b  ldarg.0
0x3c3c  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::SelectEventsNode(class Microsoft.EventViewer.SnapIn.ViewerRootNode node)
0x3c41  ldarg.0
0x3c42  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshResultView()
0x3c47  ret
```
