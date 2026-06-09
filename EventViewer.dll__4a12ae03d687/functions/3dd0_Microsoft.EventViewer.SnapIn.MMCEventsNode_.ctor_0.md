# Microsoft.EventViewer.SnapIn.MMCEventsNode::.ctor_0

- ea: `0x3dd0`
- end: `0x3df7`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsNode::.ctor_0`
- size: `39`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x33c0`
- `0x3530`
- `0x3f40`
- `0x4970`

## callees

- `0x1a80`
- `0x1aa0`
- `0x4090`

## pseudocode

```c

```

## disassembly

```asm
0x3dd0  ldarg.0
0x3dd1  ldarg.2
0x3dd2  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::.ctor(bool expandChildren)
0x3dd7  ldarg.0
0x3dd8  ldarg.1
0x3dd9  stfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x3dde  ldarg.0
0x3ddf  call     instance void Microsoft.EventViewer.SnapIn.MMCEventsNode::SetDefaultView()
0x3de4  ldarg.0
0x3de5  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::InitializeNode()
0x3dea  ldarg.0
0x3deb  ldarg.1
0x3dec  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_LanguageNeutralName()
0x3df1  call     instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::set_LanguageIndependentName(string)
0x3df6  ret
```
