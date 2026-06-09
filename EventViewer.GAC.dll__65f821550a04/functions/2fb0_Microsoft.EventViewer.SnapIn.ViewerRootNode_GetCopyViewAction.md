# Microsoft.EventViewer.SnapIn.ViewerRootNode::GetCopyViewAction

- ea: `0x2fb0`
- end: `0x2ff5`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::GetCopyViewAction`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2630`

## callees

- `0x8570`
- `0x8680`

## pseudocode

```c

```

## disassembly

```asm
0x2fb0  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncAction::.ctor()
0x2fb5  stloc.0
0x2fb6  ldloc.0
0x2fb7  ldarg.0
0x2fb8  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Description()
0x2fbd  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x2fc2  ldloc.0
0x2fc3  ldarg.0
0x2fc4  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_DisplayName()
0x2fc9  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x2fce  ldloc.0
0x2fcf  ldarg.0
0x2fd0  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x2fd5  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x2fda  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x2fdf  ldarg.0
0x2fe0  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x2fe5  ldloca.s 0
0x2fe7  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x2fec  ldloc.0
0x2fed  ldarg.0
0x2fee  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x2ff3  ldloc.0
0x2ff4  ret
```
