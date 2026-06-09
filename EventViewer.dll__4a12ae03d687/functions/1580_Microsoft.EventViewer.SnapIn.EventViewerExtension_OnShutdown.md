# Microsoft.EventViewer.SnapIn.EventViewerExtension::OnShutdown

- ea: `0x1580`
- end: `0x15ba`
- name: `Microsoft.EventViewer.SnapIn.EventViewerExtension::OnShutdown`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1290`
- `0x1580`
- `0x1a00`

## pseudocode

```c

```

## disassembly

```asm
0x1580  ldarg.0
0x1581  ldfld    bool Microsoft.EventViewer.SnapIn.EventViewerExtension::initializationSucceeded
0x1586  brfalse.s loc_15B4
0x1588  ldarg.0
0x1589  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x158e  brfalse.s loc_15A9
0x1590  ldarg.0
0x1591  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x1596  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x159b  ldc.i4.s 0xC
0x159d  ldc.i4.0
0x159e  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers, valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus)
0x15a3  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::OnAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction)
0x15a8  pop
0x15a9  ldarg.0
0x15aa  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ShowHelpTopicDelegate Microsoft.EventViewer.SnapIn.EventViewerExtension::showHelpTopicDelegate
0x15af  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::RemoveShowEventViewerHelpTopicDelegate(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ShowHelpTopicDelegate)
0x15b4  call     void Microsoft.EventViewer.SnapIn.EventViewerSnapIn::ShutdownTrace()
0x15b9  ret
```
