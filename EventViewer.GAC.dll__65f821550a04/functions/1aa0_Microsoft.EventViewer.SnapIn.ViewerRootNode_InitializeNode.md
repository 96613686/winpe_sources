# Microsoft.EventViewer.SnapIn.ViewerRootNode::InitializeNode

- ea: `0x1aa0`
- end: `0x1ac6`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::InitializeNode`
- size: `38`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3da0`
- `0x3dd0`
- `0x4520`
- `0x4780`

## callees

- `0x1aa0`
- `0x22a0`

## pseudocode

```c

```

## disassembly

```asm
0x1aa0  ldarg.0
0x1aa1  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x1aa6  brfalse.s loc_1AC5
0x1aa8  ldarg.0
0x1aa9  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x1aae  ldarg.0
0x1aaf  ldftn    instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::ActionsChangedHandler(object sender, class [mscorlib]System.EventArgs e)
0x1ab5  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1aba  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::add_ActionsChanged(class [mscorlib]System.EventHandler)
0x1abf  ldarg.0
0x1ac0  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::UpdateActions()
0x1ac5  ret
```
