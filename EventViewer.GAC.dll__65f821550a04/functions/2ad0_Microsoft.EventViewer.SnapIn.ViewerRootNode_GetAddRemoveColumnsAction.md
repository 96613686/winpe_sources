# Microsoft.EventViewer.SnapIn.ViewerRootNode::GetAddRemoveColumnsAction

- ea: `0x2ad0`
- end: `0x2b02`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::GetAddRemoveColumnsAction`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x5d60`

## callees

- `0x8570`
- `0xa890`
- `0xa8b0`

## pseudocode

```c

```

## disassembly

```asm
0x2ad0  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncAction::.ctor()
0x2ad5  stloc.0
0x2ad6  ldloc.0
0x2ad7  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddRemoveColumnsDesc()
0x2adc  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x2ae1  ldloc.0
0x2ae2  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddRemoveColumns()
0x2ae7  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x2aec  ldarg.0
0x2aed  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x2af2  ldloca.s 0
0x2af4  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x2af9  ldloc.0
0x2afa  ldarg.0
0x2afb  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x2b00  ldloc.0
0x2b01  ret
```
