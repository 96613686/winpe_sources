# Microsoft.EventViewer.SnapIn.MMCRootNode::remove_RefreshSummaryPageEvent

- ea: `0x4430`
- end: `0x4459`
- name: `Microsoft.EventViewer.SnapIn.MMCRootNode::remove_RefreshSummaryPageEvent`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x4430`

## pseudocode

```c

```

## disassembly

```asm
0x4430  ldarg.0
0x4431  ldfld    class Microsoft.EventViewer.SnapIn.RefreshSummaryPageEventDelegate Microsoft.EventViewer.SnapIn.MMCRootNode::RefreshSummaryPageEvent
0x4436  stloc.0
0x4437  ldloc.0
0x4438  stloc.1
0x4439  ldloc.1
0x443a  ldarg.1
0x443b  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x4440  castclass Microsoft.EventViewer.SnapIn.RefreshSummaryPageEventDelegate
0x4445  stloc.2
0x4446  ldarg.0
0x4447  ldflda   class Microsoft.EventViewer.SnapIn.RefreshSummaryPageEventDelegate Microsoft.EventViewer.SnapIn.MMCRootNode::RefreshSummaryPageEvent
0x444c  ldloc.2
0x444d  ldloc.1
0x444e  call     T0x2B000003
0x4453  stloc.0
0x4454  ldloc.0
0x4455  ldloc.1
0x4456  bne.un.s loc_4437
0x4458  ret
```
