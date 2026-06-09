# Microsoft.EventViewer.SnapIn.ViewerRootNode::SaveNode

- ea: `0x1e50`
- end: `0x1e65`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::SaveNode`
- size: `21`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1e70`
- `0x2050`
- `0x20b0`

## pseudocode

```c

```

## disassembly

```asm
0x1e50  ldarg.0
0x1e51  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x1e56  ldc.i4.s 0xC
0x1e58  ldc.i4.0
0x1e59  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers, valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus)
0x1e5e  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::OnAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction)
0x1e63  pop
0x1e64  ret
```
