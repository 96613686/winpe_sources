# Microsoft.EventViewer.SnapIn.ViewerRootNode::remove_ScopeNodeChanged

- ea: `0x17f0`
- end: `0x1819`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::remove_ScopeNodeChanged`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x93d0`

## callees

- `0x17f0`

## pseudocode

```c

```

## disassembly

```asm
0x17f0  ldarg.0
0x17f1  ldfld    class ViewerScopeNodeChanged Microsoft.EventViewer.SnapIn.ViewerRootNode::ScopeNodeChanged
0x17f6  stloc.0
0x17f7  ldloc.0
0x17f8  stloc.1
0x17f9  ldloc.1
0x17fa  ldarg.1
0x17fb  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x1800  castclass ViewerScopeNodeChanged
0x1805  stloc.2
0x1806  ldarg.0
0x1807  ldflda   class ViewerScopeNodeChanged Microsoft.EventViewer.SnapIn.ViewerRootNode::ScopeNodeChanged
0x180c  ldloc.2
0x180d  ldloc.1
0x180e  call     T0x2B000002
0x1813  stloc.0
0x1814  ldloc.0
0x1815  ldloc.1
0x1816  bne.un.s loc_17F7
0x1818  ret
```
