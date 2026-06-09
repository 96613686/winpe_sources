# Microsoft.EventViewer.SnapIn.ViewerRootNode::PostProcessOpenLogAction

- ea: `0x20b0`
- end: `0x20dd`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::PostProcessOpenLogAction`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1cc0`

## callees

- `0x1ae0`
- `0x1b40`
- `0x1e50`
- `0x20b0`
- `0x37c0`

## pseudocode

```c

```

## disassembly

```asm
0x20b0  ldarg.0
0x20b1  call     instance class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.ViewerRootNode::GetEventViewerRootNode()
0x20b6  stloc.0
0x20b7  ldloc.0
0x20b8  brfalse.s loc_20DC
0x20ba  ldloc.0
0x20bb  ldarg.0
0x20bc  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x20c1  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeToBeSelected()
0x20c6  callvirt instance class Microsoft.EventViewer.SnapIn.MMCEventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::AddOrGetNodeToBeSelected(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode nodeToBeSelected)
0x20cb  stloc.1
0x20cc  ldloc.1
0x20cd  brfalse.s loc_20DC
0x20cf  ldloc.1
0x20d0  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::SaveNode()
0x20d5  ldarg.0
0x20d6  ldloc.1
0x20d7  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::SelectEventsNode(class Microsoft.EventViewer.SnapIn.ViewerRootNode node)
0x20dc  ret
```
