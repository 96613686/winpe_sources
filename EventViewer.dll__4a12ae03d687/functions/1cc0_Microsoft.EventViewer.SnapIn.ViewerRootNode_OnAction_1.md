# Microsoft.EventViewer.SnapIn.ViewerRootNode::OnAction_1

- ea: `0x1cc0`
- end: `0x1e4d`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::OnAction_1`
- size: `397`
- prototype: ``
- caller_count: `4`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1c40`
- `0x1ca0`
- `0x7bd0`
- `0x83f0`

## callees

- `0x1cc0`
- `0x1e70`
- `0x1ea0`
- `0x1f40`
- `0x1fd0`
- `0x2050`
- `0x2090`
- `0x20b0`
- `0x20e0`
- `0x2230`
- `0x2260`
- `0x2280`
- `0x3050`
- `0x3110`
- `0x31d0`
- `0x38f0`
- `0x39e0`
- `0xaaa0`

## pseudocode

```c

```

## disassembly

```asm
0x1cc0  ldc.i4.0
0x1cc1  stloc.0
0x1cc2  ldarg.1
0x1cc3  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x1cc8  ldc.i4.s 0x20
0x1cca  bne.un.s loc_1CE8
0x1ccc  ldarg.0
0x1ccd  ldfld    class ViewerScopeNodeChanged Microsoft.EventViewer.SnapIn.ViewerRootNode::ScopeNodeChanged
0x1cd2  brfalse  loc_1E47
0x1cd7  ldarg.0
0x1cd8  ldfld    class ViewerScopeNodeChanged Microsoft.EventViewer.SnapIn.ViewerRootNode::ScopeNodeChanged
0x1cdd  ldarg.1
0x1cde  callvirt instance void ViewerScopeNodeChanged::Invoke(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x1ce3  br       loc_1E47
0x1ce8  ldarg.1
0x1ce9  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x1cee  stloc.1
0x1cef  ldloc.1
0x1cf0  switch   loc_1D13, loc_1D23, loc_1D13, loc_1D23, loc_1D1C
0x1d09  ldloc.1
0x1d0a  ldc.i4.s 0x11
0x1d0c  beq.s    loc_1D13
0x1d0e  ldloc.1
0x1d0f  ldc.i4.s 0x23
0x1d11  bne.un.s loc_1D23
0x1d13  ldarg.0
0x1d14  call     instance class Microsoft.EventViewer.SnapIn.ViewerRootNode Microsoft.EventViewer.SnapIn.ViewerRootNode::GetViewsRootNode()
0x1d19  pop
0x1d1a  br.s     loc_1D23
0x1d1c  ldarg.0
0x1d1d  call     instance class Microsoft.EventViewer.SnapIn.ViewerRootNode Microsoft.EventViewer.SnapIn.ViewerRootNode::GetExportLogRootNode()
0x1d22  pop
0x1d23  ldarg.0
0x1d24  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x1d29  ldarg.1
0x1d2a  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::OnAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction)
0x1d2f  stloc.0
0x1d30  ldarg.1
0x1d31  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x1d36  stloc.1
0x1d37  ldloc.1
0x1d38  switch   loc_1DD3, loc_1DDB, loc_1DED, loc_1DF6, loc_1DFE, loc_1E47, loc_1E06, loc_1E0F, loc_1E47, loc_1E47, loc_1E47, loc_1E18, loc_1E47, loc_1E23, loc_1E47, loc_1E47, loc_1E47, loc_1E2B, loc_1E47, loc_1E47, loc_1E47, loc_1E47, loc_1E33, loc_1E47, loc_1E47, loc_1E47, loc_1E47, loc_1E47, loc_1E47, loc_1E47, loc_1E3C, loc_1DE4, loc_1E47, loc_1E47, loc_1E47, loc_1DD3, loc_1DD3
0x1dd1  br.s     loc_1E47
0x1dd3  ldarg.0
0x1dd4  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::PostProcessNewQueryAction()
0x1dd9  br.s     loc_1E47
0x1ddb  ldarg.0
0x1ddc  ldloc.0
0x1ddd  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::PostProcessFilterAction(bool actionReturnValue)
0x1de2  br.s     loc_1E47
0x1de4  ldarg.0
0x1de5  ldarg.1
0x1de6  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::PostProcessClearFilterAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x1deb  br.s     loc_1E47
0x1ded  ldarg.0
0x1dee  ldloc.0
0x1def  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::PostProcessSaveAsViewAction(bool actionReturnValue)
0x1df4  br.s     loc_1E47
0x1df6  ldarg.0
0x1df7  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::PostProcessPreviewAction()
0x1dfc  br.s     loc_1E47
0x1dfe  ldarg.0
0x1dff  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::PostProcessOpenLogAction()
0x1e04  br.s     loc_1E47
0x1e06  ldarg.0
0x1e07  ldloc.0
0x1e08  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::PostProcessNodeProperties(bool actionReturnValue)
0x1e0d  br.s     loc_1E47
0x1e0f  ldarg.0
0x1e10  ldloc.0
0x1e11  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::PostEnableDisableLog(bool actionReturnValue)
0x1e16  br.s     loc_1E47
0x1e18  ldloc.0
0x1e19  brfalse.s loc_1E47
0x1e1b  ldarg.0
0x1e1c  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshResultView()
0x1e21  br.s     loc_1E47
0x1e23  ldarg.0
0x1e24  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::DeleteNode()
0x1e29  br.s     loc_1E47
0x1e2b  ldarg.0
0x1e2c  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::PostProcessAddApplictaionViewAction()
0x1e31  br.s     loc_1E47
0x1e33  ldarg.0
0x1e34  call     instance bool Microsoft.EventViewer.SnapIn.ViewerRootNode::ProcessRemoteConnect()
0x1e39  stloc.0
0x1e3a  br.s     loc_1E47
0x1e3c  ldarg.0
0x1e3d  call     instance class Microsoft.EventViewer.SnapIn.ViewerRootNode Microsoft.EventViewer.SnapIn.ViewerRootNode::GetApplicationsLogNode()
0x1e42  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshAllSubNodes()
0x1e47  leave.s  loc_1E4C
0x1e49  pop
0x1e4a  leave.s  loc_1E4C
0x1e4c  ret
```
