# Microsoft.EventViewer.SnapIn.MMCEventsResultView::CloseResultSet

- ea: `0x66c0`
- end: `0x6742`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsResultView::CloseResultSet`
- size: `130`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5780`
- `0x5790`
- `0x5a50`

## callees

- `0x3d90`
- `0x66c0`

## pseudocode

```c

```

## disassembly

```asm
0x66c0  ldarg.0
0x66c1  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x66c6  brfalse.s loc_6741
0x66c8  ldarg.0
0x66c9  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x66ce  brfalse.s loc_6736
0x66d0  ldarg.0
0x66d1  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x66d6  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x66db  brfalse.s loc_6736
0x66dd  ldarg.0
0x66de  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x66e3  brfalse.s loc_6736
0x66e5  ldarg.0
0x66e6  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x66eb  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x66f0  castclass Microsoft.EventViewer.SnapIn.MMCEventsNode
0x66f5  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.MMCEventsNode::get_EventsNode()
0x66fa  ldarg.0
0x66fb  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x6700  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::get_ViewConfig()
0x6705  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_ViewConfig(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig)
0x670a  ldarg.0
0x670b  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x6710  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x6715  castclass Microsoft.EventViewer.SnapIn.MMCEventsNode
0x671a  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.MMCEventsNode::get_EventsNode()
0x671f  ldc.i4.0
0x6720  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_NodeSelected(bool)
0x6725  ldarg.0
0x6726  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x672b  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SnapIn()
0x6730  ldc.i4.1
0x6731  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::set_IsModified(bool)
0x6736  ldarg.0
0x6737  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x673c  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::CloseResultSet()
0x6741  ret
```
