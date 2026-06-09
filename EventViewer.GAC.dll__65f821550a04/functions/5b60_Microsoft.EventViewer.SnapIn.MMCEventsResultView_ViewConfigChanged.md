# Microsoft.EventViewer.SnapIn.MMCEventsResultView::ViewConfigChanged

- ea: `0x5b60`
- end: `0x5be1`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsResultView::ViewConfigChanged`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3d90`
- `0x5b60`
- `0x7cb0`

## pseudocode

```c

```

## disassembly

```asm
0x5b60  ldarg.0
0x5b61  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5b66  brfalse.s loc_5BE0
0x5b68  ldarg.0
0x5b69  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5b6e  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x5b73  brfalse.s loc_5BE0
0x5b75  ldarg.0
0x5b76  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x5b7b  brfalse.s loc_5BE0
0x5b7d  ldarg.0
0x5b7e  call     instance bool Microsoft.EventViewer.SnapIn.FormControlBase::get_ValidView()
0x5b83  brfalse.s loc_5BE0
0x5b85  ldarg.0
0x5b86  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5b8b  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x5b90  castclass Microsoft.EventViewer.SnapIn.MMCEventsNode
0x5b95  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.MMCEventsNode::get_EventsNode()
0x5b9a  ldarg.0
0x5b9b  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x5ba0  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::get_ResultsConfig()
0x5ba5  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_ResultsConfig(string)
0x5baa  ldarg.0
0x5bab  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5bb0  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x5bb5  castclass Microsoft.EventViewer.SnapIn.MMCEventsNode
0x5bba  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.MMCEventsNode::get_EventsNode()
0x5bbf  ldarg.0
0x5bc0  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x5bc5  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::get_ViewConfig()
0x5bca  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_ViewConfig(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig)
0x5bcf  ldarg.0
0x5bd0  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5bd5  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SnapIn()
0x5bda  ldc.i4.1
0x5bdb  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::set_IsModified(bool)
0x5be0  ret
```
