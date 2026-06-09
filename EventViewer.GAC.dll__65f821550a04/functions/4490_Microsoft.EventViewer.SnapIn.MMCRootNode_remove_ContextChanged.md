# Microsoft.EventViewer.SnapIn.MMCRootNode::remove_ContextChanged

- ea: `0x4490`
- end: `0x44b9`
- name: `Microsoft.EventViewer.SnapIn.MMCRootNode::remove_ContextChanged`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6b30`

## callees

- `0x4490`

## pseudocode

```c

```

## disassembly

```asm
0x4490  ldarg.0
0x4491  ldfld    class ViewerContextChanged Microsoft.EventViewer.SnapIn.MMCRootNode::ContextChanged
0x4496  stloc.0
0x4497  ldloc.0
0x4498  stloc.1
0x4499  ldloc.1
0x449a  ldarg.1
0x449b  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x44a0  castclass ViewerContextChanged
0x44a5  stloc.2
0x44a6  ldarg.0
0x44a7  ldflda   class ViewerContextChanged Microsoft.EventViewer.SnapIn.MMCRootNode::ContextChanged
0x44ac  ldloc.2
0x44ad  ldloc.1
0x44ae  call     T0x2B000004
0x44b3  stloc.0
0x44b4  ldloc.0
0x44b5  ldloc.1
0x44b6  bne.un.s loc_4497
0x44b8  ret
```
