# Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::Microsoft.Internal.AlphaFlattener.IProxyDrawingContext.DrawImage

- ea: `0xa010`
- end: `0xa1a9`
- name: `Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::Microsoft.Internal.AlphaFlattener.IProxyDrawingContext.DrawImage`
- size: `409`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x26f0`
- `0x3d00`
- `0x8c40`
- `0x8c70`
- `0x8c80`
- `0x8c90`
- `0x8ca0`
- `0x8f40`
- `0x9220`
- `0xa010`

## pseudocode

```c

```

## disassembly

```asm
0xa010  ldarg.0
0xa011  ldfld    bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_costing
0xa016  brfalse.s loc_A036
0xa018  ldarg.0
0xa019  ldarg.0
0xa01a  ldfld    float64 Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_cost
0xa01f  ldarg.1
0xa020  callvirt instance int32 Microsoft.Internal.AlphaFlattener.ImageProxy::get_PixelWidth()
0xa025  ldarg.1
0xa026  callvirt instance int32 Microsoft.Internal.AlphaFlattener.ImageProxy::get_PixelHeight()
0xa02b  mul
0xa02c  ldc.i4.3
0xa02d  mul
0xa02e  conv.r8
0xa02f  add
0xa030  stfld    float64 Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_cost
0xa035  ret
0xa036  ldarg.3
0xa037  brfalse  loc_A134
0xa03c  ldarg.3
0xa03d  callvirt instance valuetype [WindowsBase]System.Windows.Rect [PresentationCore]System.Windows.Media.Geometry::get_Bounds()
0xa042  call     bool Microsoft.Internal.AlphaFlattener.Utility::IsRenderVisible(valuetype [WindowsBase]System.Windows.Rect rect)
0xa047  brtrue.s loc_A04A
0xa049  ret
0xa04a  ldloca.s 0
0xa04c  initobj  [WindowsBase]System.Windows.Media.Matrix
0xa052  ldloca.s 0
0xa054  ldarga.s 2
0xa056  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0xa05b  ldarg.1
0xa05c  callvirt instance class [PresentationCore]System.Windows.Media.Imaging.BitmapSource Microsoft.Internal.AlphaFlattener.ImageProxy::get_Image()
0xa061  callvirt instance float64 [PresentationCore]System.Windows.Media.ImageSource::get_Width()
0xa066  div
0xa067  ldarga.s 2
0xa069  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0xa06e  ldarg.1
0xa06f  callvirt instance class [PresentationCore]System.Windows.Media.Imaging.BitmapSource Microsoft.Internal.AlphaFlattener.ImageProxy::get_Image()
0xa074  callvirt instance float64 [PresentationCore]System.Windows.Media.ImageSource::get_Height()
0xa079  div
0xa07a  call     instance void [WindowsBase]System.Windows.Media.Matrix::Scale(float64, float64)
0xa07f  ldloca.s 0
0xa081  ldarga.s 2
0xa083  call     instance float64 [WindowsBase]System.Windows.Rect::get_X()
0xa088  ldarga.s 2
0xa08a  call     instance float64 [WindowsBase]System.Windows.Rect::get_Y()
0xa08f  call     instance void [WindowsBase]System.Windows.Media.Matrix::Translate(float64, float64)
0xa094  ldloca.s 0
0xa096  ldarg.s  4
0xa098  call     instance void [WindowsBase]System.Windows.Media.Matrix::Append(valuetype [WindowsBase]System.Windows.Media.Matrix)
0xa09d  ldloca.s 0
0xa09f  call     instance void [WindowsBase]System.Windows.Media.Matrix::Invert()
0xa0a4  ldarg.3
0xa0a5  ldloc.0
0xa0a6  call     class [PresentationCore]System.Windows.Media.Geometry Microsoft.Internal.AlphaFlattener.Utility::TransformGeometry(class [PresentationCore]System.Windows.Media.Geometry g, valuetype [WindowsBase]System.Windows.Media.Matrix t)
0xa0ab  stloc.1
0xa0ac  ldarg.1
0xa0ad  ldloc.1
0xa0ae  callvirt instance valuetype [WindowsBase]System.Windows.Rect [PresentationCore]System.Windows.Media.Geometry::get_Bounds()
0xa0b3  ldloca.s 2
0xa0b5  callvirt instance class [PresentationCore]System.Windows.Media.Imaging.BitmapSource Microsoft.Internal.AlphaFlattener.ImageProxy::GetClippedImage(valuetype [WindowsBase]System.Windows.Rect bounds, [out] valuetype [WindowsBase]System.Windows.Rect& clipBounds)
0xa0ba  stloc.3
0xa0bb  ldloc.3
0xa0bc  brtrue.s loc_A0BF
0xa0be  ret
0xa0bf  ldloc.3
0xa0c0  newobj   instance void Microsoft.Internal.AlphaFlattener.ImageProxy::.ctor(class [PresentationCore]System.Windows.Media.Imaging.BitmapSource image)
0xa0c5  stloc.s  4
0xa0c7  ldarga.s 2
0xa0c9  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0xa0ce  ldarg.1
0xa0cf  callvirt instance class [PresentationCore]System.Windows.Media.Imaging.BitmapSource Microsoft.Internal.AlphaFlattener.ImageProxy::get_Image()
0xa0d4  callvirt instance float64 [PresentationCore]System.Windows.Media.ImageSource::get_Width()
0xa0d9  div
0xa0da  stloc.s  5
0xa0dc  ldarga.s 2
0xa0de  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0xa0e3  ldarg.1
0xa0e4  callvirt instance class [PresentationCore]System.Windows.Media.Imaging.BitmapSource Microsoft.Internal.AlphaFlattener.ImageProxy::get_Image()
0xa0e9  callvirt instance float64 [PresentationCore]System.Windows.Media.ImageSource::get_Height()
0xa0ee  div
0xa0ef  stloc.s  6
0xa0f1  ldarga.s 2
0xa0f3  ldloca.s 2
0xa0f5  call     instance float64 [WindowsBase]System.Windows.Rect::get_X()
0xa0fa  ldloc.s  5
0xa0fc  mul
0xa0fd  ldarga.s 2
0xa0ff  call     instance float64 [WindowsBase]System.Windows.Rect::get_X()
0xa104  add
0xa105  ldloca.s 2
0xa107  call     instance float64 [WindowsBase]System.Windows.Rect::get_Y()
0xa10c  ldloc.s  6
0xa10e  mul
0xa10f  ldarga.s 2
0xa111  call     instance float64 [WindowsBase]System.Windows.Rect::get_Y()
0xa116  add
0xa117  ldloca.s 2
0xa119  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0xa11e  ldloc.s  5
0xa120  mul
0xa121  ldloca.s 2
0xa123  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0xa128  ldloc.s  6
0xa12a  mul
0xa12b  call     instance void [WindowsBase]System.Windows.Rect::.ctor(float64, float64, float64, float64)
0xa130  ldloc.s  4
0xa132  starg.s  1
0xa134  ldarg.1
0xa135  call     valuetype [PresentationCore]System.Windows.Media.Color [PresentationCore]System.Windows.Media.Colors::get_White()
0xa13a  ldc.r8   1.0
0xa143  ldc.i4.0
0xa144  callvirt instance void Microsoft.Internal.AlphaFlattener.ImageProxy::BlendOverColor(valuetype [PresentationCore]System.Windows.Media.Color color, float64 opacity, bool opacityOnly)
0xa149  ldarg.3
0xa14a  brfalse.s loc_A158
0xa14c  ldarg.0
0xa14d  ldfld    class [System.Printing]System.Printing.ILegacyDevice Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_dc
0xa152  ldarg.3
0xa153  callvirt instance void [System.Printing]System.Printing.ILegacyDevice::PushClip(class [PresentationCore]System.Windows.Media.Geometry)
0xa158  ldarga.s 4
0xa15a  call     instance bool [WindowsBase]System.Windows.Media.Matrix::get_IsIdentity()
0xa15f  brtrue.s loc_A16E
0xa161  ldarg.0
0xa162  ldfld    class [System.Printing]System.Printing.ILegacyDevice Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_dc
0xa167  ldarg.s  4
0xa169  callvirt instance void [System.Printing]System.Printing.ILegacyDevice::PushTransform(valuetype [WindowsBase]System.Windows.Media.Matrix)
0xa16e  ldarg.0
0xa16f  ldfld    class [System.Printing]System.Printing.ILegacyDevice Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_dc
0xa174  ldarg.1
0xa175  callvirt instance class [PresentationCore]System.Windows.Media.Imaging.BitmapSource Microsoft.Internal.AlphaFlattener.ImageProxy::get_Image()
0xa17a  ldarg.1
0xa17b  callvirt instance unsigned int8[] Microsoft.Internal.AlphaFlattener.ImageProxy::get_Buffer()
0xa180  ldarg.2
0xa181  callvirt instance void [System.Printing]System.Printing.ILegacyDevice::DrawImage(class [PresentationCore]System.Windows.Media.Imaging.BitmapSource, unsigned int8[], valuetype [WindowsBase]System.Windows.Rect)
0xa186  ldarga.s 4
0xa188  call     instance bool [WindowsBase]System.Windows.Media.Matrix::get_IsIdentity()
0xa18d  brtrue.s loc_A19A
0xa18f  ldarg.0
0xa190  ldfld    class [System.Printing]System.Printing.ILegacyDevice Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_dc
0xa195  callvirt instance void [System.Printing]System.Printing.ILegacyDevice::PopTransform()
0xa19a  ldarg.3
0xa19b  brfalse.s loc_A1A8
0xa19d  ldarg.0
0xa19e  ldfld    class [System.Printing]System.Printing.ILegacyDevice Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_dc
0xa1a3  callvirt instance void [System.Printing]System.Printing.ILegacyDevice::PopClip()
0xa1a8  ret
```
