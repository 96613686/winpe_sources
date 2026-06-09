# Microsoft.EventViewer.SnapIn.ViewerRootNode::add_ScopeNodeChanged

- ea: `0x17c0`
- end: `0x17e9`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::add_ScopeNodeChanged`
- size: `41`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4b80`
- `0x6420`
- `0x93d0`
- `0x9620`

## callees

- `0x17c0`

## pseudocode

```c

```

## disassembly

```asm
0x17c0  ldarg.0
0x17c1  ldfld    class ViewerScopeNodeChanged Microsoft.EventViewer.SnapIn.ViewerRootNode::ScopeNodeChanged
0x17c6  stloc.0
0x17c7  ldloc.0
0x17c8  stloc.1
0x17c9  ldloc.1
0x17ca  ldarg.1
0x17cb  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x17d0  castclass ViewerScopeNodeChanged
0x17d5  stloc.2
0x17d6  ldarg.0
0x17d7  ldflda   class ViewerScopeNodeChanged Microsoft.EventViewer.SnapIn.ViewerRootNode::ScopeNodeChanged
0x17dc  ldloc.2
0x17dd  ldloc.1
0x17de  call     T0x2B000002
0x17e3  stloc.0
0x17e4  ldloc.0
0x17e5  ldloc.1
0x17e6  bne.un.s loc_17C7
0x17e8  ret
```
