# Microsoft.EventViewer.SnapIn.EventViewerSnapIn::remove_SelectScopeNode

- ea: `0x2e0`
- end: `0x309`
- name: `Microsoft.EventViewer.SnapIn.EventViewerSnapIn::remove_SelectScopeNode`
- size: `41`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6c40`
- `0x7ec0`
- `0x93d0`

## callees

- `0x2e0`

## pseudocode

```c

```

## disassembly

```asm
0x2e0  ldarg.0
0x2e1  ldfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerSnapIn::SelectScopeNode
0x2e6  stloc.0
0x2e7  ldloc.0
0x2e8  stloc.1
0x2e9  ldloc.1
0x2ea  ldarg.1
0x2eb  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x2f0  castclass [mscorlib]System.EventHandler
0x2f5  stloc.2
0x2f6  ldarg.0
0x2f7  ldflda   class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerSnapIn::SelectScopeNode
0x2fc  ldloc.2
0x2fd  ldloc.1
0x2fe  call     T0x2B000001
0x303  stloc.0
0x304  ldloc.0
0x305  ldloc.1
0x306  bne.un.s loc_2E7
0x308  ret
```
