# Microsoft.EventViewer.SnapIn.ViewerRootNode::GetAddTaskAction

- ea: `0x2d30`
- end: `0x2d9d`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::GetAddTaskAction`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x2630`

## callees

- `0x2d30`
- `0x8570`
- `0x8680`
- `0x9ef0`
- `0x9f10`
- `0x9f70`
- `0x9f90`

## pseudocode

```c

```

## disassembly

```asm
0x2d30  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncAction::.ctor()
0x2d35  stloc.0
0x2d36  ldloc.0
0x2d37  ldarg.0
0x2d38  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x2d3d  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x2d42  ldc.i4.1
0x2d43  beq.s    loc_2D4C
0x2d45  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTaskToViewDesc()
0x2d4a  br.s     loc_2D51
0x2d4c  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTaskDesc()
0x2d51  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x2d56  ldloc.0
0x2d57  ldarg.0
0x2d58  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x2d5d  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x2d62  ldc.i4.1
0x2d63  beq.s    loc_2D6C
0x2d65  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTaskToView()
0x2d6a  br.s     loc_2D71
0x2d6c  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTask()
0x2d71  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x2d76  ldloc.0
0x2d77  ldarg.1
0x2d78  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x2d7d  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x2d82  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x2d87  ldarg.1
0x2d88  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x2d8d  ldloca.s 0
0x2d8f  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x2d94  ldloc.0
0x2d95  ldarg.1
0x2d96  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x2d9b  ldloc.0
0x2d9c  ret
```
