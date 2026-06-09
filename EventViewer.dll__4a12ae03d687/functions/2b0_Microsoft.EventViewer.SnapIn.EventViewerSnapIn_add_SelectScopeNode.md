# Microsoft.EventViewer.SnapIn.EventViewerSnapIn::add_SelectScopeNode

- ea: `0x2b0`
- end: `0x2d9`
- name: `Microsoft.EventViewer.SnapIn.EventViewerSnapIn::add_SelectScopeNode`
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

- `0x2b0`

## pseudocode

```c

```

## disassembly

```asm
0x2b0  ldarg.0
0x2b1  ldfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerSnapIn::SelectScopeNode
0x2b6  stloc.0
0x2b7  ldloc.0
0x2b8  stloc.1
0x2b9  ldloc.1
0x2ba  ldarg.1
0x2bb  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x2c0  castclass [mscorlib]System.EventHandler
0x2c5  stloc.2
0x2c6  ldarg.0
0x2c7  ldflda   class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerSnapIn::SelectScopeNode
0x2cc  ldloc.2
0x2cd  ldloc.1
0x2ce  call     T0x2B000001
0x2d3  stloc.0
0x2d4  ldloc.0
0x2d5  ldloc.1
0x2d6  bne.un.s loc_2B7
0x2d8  ret
```
