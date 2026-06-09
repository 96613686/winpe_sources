# Microsoft.EventViewer.SnapIn.MMCEventsResultView::ScopeNodeChanged

- ea: `0x5a50`
- end: `0x5b12`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsResultView::ScopeNodeChanged`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1860`
- `0x3be0`
- `0x5a50`
- `0x6400`
- `0x64e0`
- `0x66c0`
- `0x91b0`

## pseudocode

```c

```

## disassembly

```asm
0x5a50  ldc.i4.0
0x5a51  stloc.0
0x5a52  ldarg.1
0x5a53  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x5a58  ldc.i4.s 0x1F
0x5a5a  bne.un.s loc_5A65
0x5a5c  ldarg.0
0x5a5d  ldarg.1
0x5a5e  call     instance void Microsoft.EventViewer.SnapIn.MMCEventsResultView::OnAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction mmcAction)
0x5a63  ldc.i4.1
0x5a64  stloc.0
0x5a65  ldarg.1
0x5a66  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x5a6b  ldc.i4.s 0xA
0x5a6d  ceq
0x5a6f  ldloc.0
0x5a70  or
0x5a71  brfalse.s loc_5A7B
0x5a73  ldarg.0
0x5a74  call     instance void Microsoft.EventViewer.SnapIn.MMCEventsResultView::RefreshResults()
0x5a79  br.s     loc_5A94
0x5a7b  ldarg.1
0x5a7c  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x5a81  ldc.i4.s 0xD
0x5a83  bne.un.s loc_5A8D
0x5a85  ldarg.0
0x5a86  call     instance void Microsoft.EventViewer.SnapIn.MMCEventsResultView::CloseResultSet()
0x5a8b  br.s     loc_5A94
0x5a8d  ldarg.0
0x5a8e  ldarg.1
0x5a8f  call     instance void Microsoft.EventViewer.SnapIn.MMCEventsResultView::OnAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction mmcAction)
0x5a94  leave.s  loc_5B11
0x5a96  stloc.1
0x5a97  ldarg.0
0x5a98  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5a9d  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x5aa2  isinst   Microsoft.EventViewer.SnapIn.ViewerRootNode
0x5aa7  stloc.2
0x5aa8  ldloc.1
0x5aa9  ldloc.2
0x5aaa  ldarg.0
0x5aab  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5ab0  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SnapIn()
0x5ab5  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_Console()
0x5aba  call     bool Microsoft.EventViewer.SnapIn.ViewerCommon::HandleException(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e, class Microsoft.EventViewer.SnapIn.ViewerRootNode viewerNode, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console con)
0x5abf  brfalse.s loc_5AC9
0x5ac1  ldloc.1
0x5ac2  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_RefreshConsole()
0x5ac7  brfalse.s loc_5B0F
0x5ac9  ldloc.2
0x5aca  brfalse.s loc_5B0F
0x5acc  ldloc.2
0x5acd  ldloc.1
0x5ace  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshConsole(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException e)
0x5ad3  ldloc.2
0x5ad4  callvirt instance bool Microsoft.EventViewer.SnapIn.ViewerRootNode::get_MarkNodeDeleted()
0x5ad9  brtrue.s loc_5B0F
0x5adb  ldarg.0
0x5adc  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5ae1  ldarg.0
0x5ae2  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5ae7  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x5aec  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::SelectScopeNode(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x5af1  ldloc.2
0x5af2  callvirt instance bool Microsoft.EventViewer.SnapIn.ViewerRootNode::get_MarkNodeDeleted()
0x5af7  brtrue.s loc_5B0F
0x5af9  ldarg.0
0x5afa  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5aff  ldarg.0
0x5b00  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x5b05  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x5b0a  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::SelectScopeNode(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x5b0f  leave.s  loc_5B11
0x5b11  ret
```
