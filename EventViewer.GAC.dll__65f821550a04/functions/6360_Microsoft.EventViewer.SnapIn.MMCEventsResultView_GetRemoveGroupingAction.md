# Microsoft.EventViewer.SnapIn.MMCEventsResultView::GetRemoveGroupingAction

- ea: `0x6360`
- end: `0x63a5`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsResultView::GetRemoveGroupingAction`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5d60`

## callees

- `0x8570`
- `0x8680`

## pseudocode

```c

```

## disassembly

```asm
0x6360  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Action::.ctor()
0x6365  stloc.0
0x6366  ldloc.0
0x6367  ldarg.0
0x6368  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Description()
0x636d  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x6372  ldloc.0
0x6373  ldarg.0
0x6374  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_DisplayName()
0x6379  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x637e  ldloc.0
0x637f  ldarg.0
0x6380  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x6385  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x638a  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x638f  ldarg.0
0x6390  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x6395  ldloca.s 0
0x6397  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x639c  ldloc.0
0x639d  ldarg.0
0x639e  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x63a3  ldloc.0
0x63a4  ret
```
