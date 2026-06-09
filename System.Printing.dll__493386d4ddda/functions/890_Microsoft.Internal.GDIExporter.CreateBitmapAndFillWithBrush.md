# ::Microsoft.Internal.GDIExporter.CreateBitmapAndFillWithBrush

- ea: `0x890`
- end: `0x8e4`
- name: `::Microsoft.Internal.GDIExporter.CreateBitmapAndFillWithBrush`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1fbb0`

## callees

- `0x890`
- `0x217c0`

## pseudocode

```c

```

## disassembly

```asm
0x890  ldarg.2
0x891  ldnull
0x892  bne.un.s loc_897
0x894  ldc.i4.0
0x895  br.s     loc_898
0x897  ldc.i4.1
0x898  stloc.3
0x899  ldloc.3
0x89a  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x89f  ldarg.0
0x8a0  ldc.i4.0
0x8a1  ble.s    loc_8AB
0x8a3  ldarg.1
0x8a4  ldc.i4.0
0x8a5  ble.s    loc_8AB
0x8a7  ldc.i4.1
0x8a8  stloc.1
0x8a9  br.s     loc_8AD
0x8ab  ldc.i4.0
0x8ac  stloc.1
0x8ad  ldloc.1
0x8ae  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x8b3  ldarg.0
0x8b4  ldarg.1
0x8b5  ldc.r8   96.0
0x8be  ldc.r8   96.0
0x8c7  ldarg.s  5
0x8c9  newobj   instance void [PresentationCore]System.Windows.Media.Imaging.RenderTargetBitmap::.ctor(int32, int32, float64, float64, valuetype [PresentationCore]System.Windows.Media.PixelFormat)
0x8ce  stloc.0
0x8cf  ldarg.0
0x8d0  ldarg.1
0x8d1  ldarg.2
0x8d2  ldarg.3
0x8d3  ldarg.s  4
0x8d5  newobj   instance void Microsoft.Internal.GDIExporter.GeometryVisual::.ctor(int32 bitmapWidth, int32 bitmapHeight, class [PresentationCore]System.Windows.Media.Brush brush, valuetype [WindowsBase]System.Windows.Rect rect, class [PresentationCore]System.Windows.Media.Transform transform)
0x8da  stloc.2
0x8db  ldloc.0
0x8dc  ldloc.2
0x8dd  call     instance void [PresentationCore]System.Windows.Media.Imaging.RenderTargetBitmap::Render(class [PresentationCore]System.Windows.Media.Visual)
0x8e2  ldloc.0
0x8e3  ret
```
