# Microsoft.Internal.AlphaFlattener.BrushProxy::CreateBrush

- ea: `0x7080`
- end: `0x7092`
- name: `Microsoft.Internal.AlphaFlattener.BrushProxy::CreateBrush`
- size: `18`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x260`
- `0x18f0`
- `0x35e0`
- `0x49b0`
- `0x6020`
- `0x62b0`
- `0x6910`
- `0xbcb0`
- `0xbea0`

## callees

- `0x6fd0`
- `0x7080`
- `0x70e0`

## pseudocode

```c

```

## disassembly

```asm
0x7080  ldarg.0
0x7081  call     bool Microsoft.Internal.AlphaFlattener.BrushProxy::IsEmpty(class [PresentationCore]System.Windows.Media.Brush brush)
0x7086  brfalse.s loc_708A
0x7088  ldnull
0x7089  ret
0x708a  ldarg.0
0x708b  ldarg.1
0x708c  call     class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::CreateBrushCore(class [PresentationCore]System.Windows.Media.Brush brush, valuetype [WindowsBase]System.Windows.Rect bounds)
0x7091  ret
```
