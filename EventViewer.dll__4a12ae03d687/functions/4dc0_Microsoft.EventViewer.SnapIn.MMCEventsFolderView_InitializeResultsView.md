# Microsoft.EventViewer.SnapIn.MMCEventsFolderView::InitializeResultsView

- ea: `0x4dc0`
- end: `0x4e71`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsFolderView::InitializeResultsView`
- size: `177`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x4b80`
- `0x4bb0`
- `0x4be0`
- `0x4e80`

## callees

- `0x3d90`
- `0x4dc0`
- `0x7cb0`

## pseudocode

```c

```

## disassembly

```asm
0x4dc0  ldarg.0
0x4dc1  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x4dc6  brfalse  loc_4E70
0x4dcb  ldarg.0
0x4dcc  call     instance bool Microsoft.EventViewer.SnapIn.FormControlBase::get_ValidView()
0x4dd1  brfalse  loc_4E70
0x4dd6  ldarg.0
0x4dd7  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x4ddc  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x4de1  castclass Microsoft.EventViewer.SnapIn.MMCEventsNode
0x4de6  stloc.0
0x4de7  ldloc.0
0x4de8  brfalse  loc_4E70
0x4ded  ldarg.0
0x4dee  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl Microsoft.EventViewer.SnapIn.MMCEventsFolderView::folderViewCtl1
0x4df3  ldarg.0
0x4df4  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x4df9  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x4dfe  castclass Microsoft.EventViewer.SnapIn.MMCEventsNode
0x4e03  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.MMCEventsNode::get_EventsNode()
0x4e08  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl::set_CurrentItem(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode)
0x4e0d  ldarg.0
0x4e0e  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl Microsoft.EventViewer.SnapIn.MMCEventsFolderView::folderViewCtl1
0x4e13  ldloc.0
0x4e14  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.MMCEventsNode::get_EventsNode()
0x4e19  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Context()
0x4e1e  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl::set_Context(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext)
0x4e23  ldarg.0
0x4e24  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl Microsoft.EventViewer.SnapIn.MMCEventsFolderView::folderViewCtl1
0x4e29  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.FolderViewControl::get_CurrentItem()
0x4e2e  brfalse.s loc_4E70
0x4e30  ldarg.0
0x4e31  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x4e36  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x4e3b  castclass Microsoft.EventViewer.SnapIn.MMCEventsNode
0x4e40  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.MMCEventsNode::get_EventsNode()
0x4e45  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Config()
0x4e4a  isinst   [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder
0x4e4f  stloc.1
0x4e50  ldloc.1
0x4e51  brfalse.s loc_4E70
0x4e53  ldloc.1
0x4e54  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ConfigFolder::get_IsCorruptPublisher()
0x4e59  brfalse.s loc_4E70
0x4e5b  ldarg.0
0x4e5c  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x4e61  ldstr    aPublishermetad// "PublisherMetaDataErrorDescriptionForPub"...
0x4e66  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x4e6b  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::set_DescriptionBarText(string)
0x4e70  ret
```
