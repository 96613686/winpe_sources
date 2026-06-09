# Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectEventsNode

- ea: `0x1770`
- end: `0x17ab`
- name: `Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectEventsNode`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1b40`

## callees

- `0x1770`
- `0x1a00`

## pseudocode

```c

```

## disassembly

```asm
0x1770  ldarg.1
0x1771  brfalse.s loc_17AA
0x1773  ldarg.0
0x1774  ldfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectScopeNode
0x1779  brfalse.s loc_17AA
0x177b  ldarg.1
0x177c  isinst   Microsoft.EventViewer.SnapIn.MMCEventsNode
0x1781  brtrue.s loc_178B
0x1783  ldarg.1
0x1784  isinst   Microsoft.EventViewer.SnapIn.MMCRootNode
0x1789  brfalse.s loc_17AA
0x178b  ldarg.1
0x178c  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x1791  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeState()
0x1796  ldc.i4.4
0x1797  beq.s    loc_17AA
0x1799  ldarg.0
0x179a  ldfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectScopeNode
0x179f  ldarg.1
0x17a0  newobj   instance void [mscorlib]System.EventArgs::.ctor()
0x17a5  callvirt instance void [mscorlib]System.EventHandler::Invoke(object, class [mscorlib]System.EventArgs)
0x17aa  ret
```
