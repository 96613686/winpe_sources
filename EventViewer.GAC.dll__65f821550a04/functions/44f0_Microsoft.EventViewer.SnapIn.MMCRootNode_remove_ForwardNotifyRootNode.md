# Microsoft.EventViewer.SnapIn.MMCRootNode::remove_ForwardNotifyRootNode

- ea: `0x44f0`
- end: `0x4519`
- name: `Microsoft.EventViewer.SnapIn.MMCRootNode::remove_ForwardNotifyRootNode`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6b30`

## callees

- `0x44f0`

## pseudocode

```c

```

## disassembly

```asm
0x44f0  ldarg.0
0x44f1  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.NotifyRootNodeEventHandler Microsoft.EventViewer.SnapIn.MMCRootNode::ForwardNotifyRootNode
0x44f6  stloc.0
0x44f7  ldloc.0
0x44f8  stloc.1
0x44f9  ldloc.1
0x44fa  ldarg.1
0x44fb  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x4500  castclass [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.NotifyRootNodeEventHandler
0x4505  stloc.2
0x4506  ldarg.0
0x4507  ldflda   class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.NotifyRootNodeEventHandler Microsoft.EventViewer.SnapIn.MMCRootNode::ForwardNotifyRootNode
0x450c  ldloc.2
0x450d  ldloc.1
0x450e  call     T0x2B000005
0x4513  stloc.0
0x4514  ldloc.0
0x4515  ldloc.1
0x4516  bne.un.s loc_44F7
0x4518  ret
```
