# Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshResultView

- ea: `0x2280`
- end: `0x229c`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshResultView`
- size: `28`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1cc0`
- `0x1ea0`
- `0x1f40`
- `0x2050`
- `0x20e0`
- `0x33c0`
- `0x3530`
- `0x38f0`
- `0x3be0`
- `0x3c50`
- `0x3cb0`
- `0x3e00`

## callees

- `0x2280`
- `0xaaa0`

## pseudocode

```c

```

## disassembly

```asm
0x2280  ldarg.0
0x2281  ldfld    class ViewerScopeNodeChanged Microsoft.EventViewer.SnapIn.ViewerRootNode::ScopeNodeChanged
0x2286  brfalse.s loc_229B
0x2288  ldarg.0
0x2289  ldfld    class ViewerScopeNodeChanged Microsoft.EventViewer.SnapIn.ViewerRootNode::ScopeNodeChanged
0x228e  ldc.i4.s 0xA
0x2290  ldc.i4.0
0x2291  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers, valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus)
0x2296  callvirt instance void ViewerScopeNodeChanged::Invoke(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x229b  ret
```
