# Microsoft.EventViewer.SnapIn.MMCEventsResultView::GetRemoveSortingAction

- ea: `0x63b0`
- end: `0x63f5`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsResultView::GetRemoveSortingAction`
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
0x63b0  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Action::.ctor()
0x63b5  stloc.0
0x63b6  ldloc.0
0x63b7  ldarg.0
0x63b8  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Description()
0x63bd  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x63c2  ldloc.0
0x63c3  ldarg.0
0x63c4  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_DisplayName()
0x63c9  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x63ce  ldloc.0
0x63cf  ldarg.0
0x63d0  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x63d5  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x63da  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x63df  ldarg.0
0x63e0  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x63e5  ldloca.s 0
0x63e7  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x63ec  ldloc.0
0x63ed  ldarg.0
0x63ee  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x63f3  ldloc.0
0x63f4  ret
```
