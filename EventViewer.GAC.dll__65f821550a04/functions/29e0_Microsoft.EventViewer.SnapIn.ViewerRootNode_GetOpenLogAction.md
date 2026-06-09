# Microsoft.EventViewer.SnapIn.ViewerRootNode::GetOpenLogAction

- ea: `0x29e0`
- end: `0x2a23`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::GetOpenLogAction`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x2630`

## callees

- `0x8570`
- `0x8680`
- `0xa170`
- `0xa190`

## pseudocode

```c

```

## disassembly

```asm
0x29e0  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncAction::.ctor()
0x29e5  stloc.0
0x29e6  ldloc.0
0x29e7  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionOpenLogDesc()
0x29ec  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x29f1  ldloc.0
0x29f2  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionOpenLog()
0x29f7  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x29fc  ldloc.0
0x29fd  ldarg.0
0x29fe  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x2a03  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x2a08  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x2a0d  ldarg.0
0x2a0e  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x2a13  ldloca.s 0
0x2a15  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x2a1a  ldloc.0
0x2a1b  ldarg.0
0x2a1c  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x2a21  ldloc.0
0x2a22  ret
```
