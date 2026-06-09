# Microsoft.EventViewer.SnapIn.MMCEventsResultView::RefreshResults

- ea: `0x64e0`
- end: `0x65cf`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsResultView::RefreshResults`
- size: `239`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x54a0`
- `0x5560`
- `0x5960`
- `0x5a50`
- `0x5bf0`

## callees

- `0x1a00`
- `0x3d90`
- `0x64e0`
- `0x6620`
- `0x7cb0`

## pseudocode

```c

```

## disassembly

```asm
0x64e0  ldarg.0
0x64e1  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x64e6  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x64eb  castclass Microsoft.EventViewer.SnapIn.MMCEventsNode
0x64f0  stloc.0
0x64f1  ldloc.0
0x64f2  brfalse  loc_65CE
0x64f7  ldarg.0
0x64f8  call     instance bool Microsoft.EventViewer.SnapIn.FormControlBase::get_ValidView()
0x64fd  brfalse  loc_65CE
0x6502  ldarg.0
0x6503  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x6508  brfalse  loc_65CE
0x650d  ldarg.0
0x650e  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x6513  ldloc.0
0x6514  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.MMCEventsNode::get_EventsNode()
0x6519  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Context()
0x651e  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::set_Context(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext)
0x6523  ldarg.0
0x6524  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x6529  ldloc.0
0x652a  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.MMCEventsNode::get_EventsNode()
0x652f  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_ChannelPath()
0x6534  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::set_Channel(string)
0x6539  ldarg.0
0x653a  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x653f  ldloc.0
0x6540  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.MMCEventsNode::get_EventsNode()
0x6545  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Query()
0x654a  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::set_Query(string)
0x654f  ldarg.0
0x6550  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x6555  ldloc.0
0x6556  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.MMCEventsNode::get_EventsNode()
0x655b  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Filtered()
0x6560  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::set_Filtered(bool)
0x6565  ldloc.0
0x6566  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.MMCEventsNode::get_EventsNode()
0x656b  ldc.i4.1
0x656c  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_NodeSelected(bool)
0x6571  ldarg.0
0x6572  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x6577  ldarg.0
0x6578  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x657d  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x6582  castclass Microsoft.EventViewer.SnapIn.ViewerRootNode
0x6587  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x658c  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_QueryHeaderString()
0x6591  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::set_QueryHeaderString(string)
0x6596  ldarg.0
0x6597  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x659c  ldloc.0
0x659d  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.MMCEventsNode::get_EventsNode()
0x65a2  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_ResultsConfig()
0x65a7  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::set_ResultsConfig(string)
0x65ac  ldarg.0
0x65ad  call     instance bool Microsoft.EventViewer.SnapIn.FormControlBase::get_ValidView()
0x65b2  brfalse.s loc_65CE
0x65b4  ldarg.0
0x65b5  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl Microsoft.EventViewer.SnapIn.MMCEventsResultView::eventDetailControl1
0x65ba  ldc.i4.s 0xA
0x65bc  ldc.i4.0
0x65bd  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers, valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus)
0x65c2  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::OnAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction)
0x65c7  pop
0x65c8  ldarg.0
0x65c9  call     instance void Microsoft.EventViewer.SnapIn.MMCEventsResultView::UpdateMMCMessages()
0x65ce  ret
```
