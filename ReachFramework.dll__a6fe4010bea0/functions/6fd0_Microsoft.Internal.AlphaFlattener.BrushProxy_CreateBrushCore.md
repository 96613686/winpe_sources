# Microsoft.Internal.AlphaFlattener.BrushProxy::CreateBrushCore

- ea: `0x6fd0`
- end: `0x704b`
- name: `Microsoft.Internal.AlphaFlattener.BrushProxy::CreateBrushCore`
- size: `123`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x7050`
- `0x7080`
- `0x70a0`
- `0x70c0`

## callees

- `0x4aa0`
- `0x4b80`
- `0x6f20`
- `0x6f80`
- `0x6fd0`
- `0x7830`

## pseudocode

```c

```

## disassembly

```asm
0x6fd0  ldarga.s 1
0x6fd2  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0x6fd7  ldc.r8   0.0
0x6fe0  beq.s    loc_6FF4
0x6fe2  ldarga.s 1
0x6fe4  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0x6fe9  ldc.r8   0.0
0x6ff2  bne.un.s loc_6FF6
0x6ff4  ldnull
0x6ff5  ret
0x6ff6  ldarg.0
0x6ff7  call     bool Microsoft.Internal.AlphaFlattener.BrushProxy::IsOpaqueWhite(class [PresentationCore]System.Windows.Media.Brush brush)
0x6ffc  brfalse.s loc_7004
0x6ffe  ldsfld   class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::_whiteBrush
0x7003  ret
0x7004  ldarg.0
0x7005  call     bool Microsoft.Internal.AlphaFlattener.BrushProxy::IsOpaqueBlack(class [PresentationCore]System.Windows.Media.Brush brush)
0x700a  brfalse.s loc_7012
0x700c  ldsfld   class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::_blackBrush
0x7011  ret
0x7012  ldarg.0
0x7013  newobj   instance void Microsoft.Internal.AlphaFlattener.BrushProxy::.ctor(class [PresentationCore]System.Windows.Media.Brush brush)
0x7018  stloc.0
0x7019  ldarga.s 1
0x701b  call     instance bool [WindowsBase]System.Windows.Rect::get_IsEmpty()
0x7020  brtrue.s loc_702D
0x7022  ldloc.0
0x7023  ldarg.1
0x7024  callvirt instance bool Microsoft.Internal.AlphaFlattener.BrushProxy::MakeBrushAbsolute(valuetype [WindowsBase]System.Windows.Rect bounds)
0x7029  brtrue.s loc_702D
0x702b  ldnull
0x702c  ret
0x702d  ldloc.0
0x702e  callvirt instance class [PresentationCore]System.Windows.Media.Brush Microsoft.Internal.AlphaFlattener.BrushProxy::get_Brush()
0x7033  isinst   [PresentationCore]System.Windows.Media.GradientBrush
0x7038  stloc.1
0x7039  ldloc.1
0x703a  pop
0x703b  ldloc.0
0x703c  callvirt instance class [PresentationCore]System.Windows.Media.Brush Microsoft.Internal.AlphaFlattener.BrushProxy::get_Brush()
0x7041  isinst   [PresentationCore]System.Windows.Media.TileBrush
0x7046  stloc.2
0x7047  ldloc.2
0x7048  pop
0x7049  ldloc.0
0x704a  ret
```
