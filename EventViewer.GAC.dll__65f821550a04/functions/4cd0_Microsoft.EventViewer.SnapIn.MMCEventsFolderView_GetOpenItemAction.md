# Microsoft.EventViewer.SnapIn.MMCEventsFolderView::GetOpenItemAction

- ea: `0x4cd0`
- end: `0x4d13`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsFolderView::GetOpenItemAction`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x4c40`

## callees

- `0x8570`
- `0x8680`
- `0xa810`
- `0xa830`

## pseudocode

```c

```

## disassembly

```asm
0x4cd0  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Action::.ctor()
0x4cd5  stloc.0
0x4cd6  ldloc.0
0x4cd7  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionOpenItemDesc()
0x4cdc  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x4ce1  ldloc.0
0x4ce2  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionOpenItem()
0x4ce7  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x4cec  ldloc.0
0x4ced  ldarg.0
0x4cee  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x4cf3  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x4cf8  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x4cfd  ldarg.0
0x4cfe  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x4d03  ldloca.s 0
0x4d05  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x4d0a  ldloc.0
0x4d0b  ldarg.0
0x4d0c  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x4d11  ldloc.0
0x4d12  ret
```
