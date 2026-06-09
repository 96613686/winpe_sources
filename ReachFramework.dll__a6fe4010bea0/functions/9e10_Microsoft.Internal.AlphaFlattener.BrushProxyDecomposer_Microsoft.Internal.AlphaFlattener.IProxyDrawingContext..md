# Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::Microsoft.Internal.AlphaFlattener.IProxyDrawingContext.DrawGeometry

- ea: `0x9e10`
- end: `0xa00d`
- name: `Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::Microsoft.Internal.AlphaFlattener.IProxyDrawingContext.DrawGeometry`
- size: `509`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x2b70`
- `0x4880`
- `0x48d0`
- `0x4e90`
- `0x54e0`
- `0x76a0`
- `0x7830`
- `0x78a0`
- `0x9b00`
- `0x9c10`
- `0x9ca0`
- `0x9d30`
- `0x9e10`

## pseudocode

```c

```

## disassembly

```asm
0x9e10  ldarg.1
0x9e11  brtrue.s loc_9E17
0x9e13  ldarg.2
0x9e14  brtrue.s loc_9E17
0x9e16  ret
0x9e17  ldarg.0
0x9e18  ldfld    bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_costing
0x9e1d  brtrue.s loc_9E30
0x9e1f  ldarg.s  4
0x9e21  brfalse.s loc_9E30
0x9e23  ldarg.0
0x9e24  ldfld    class [System.Printing]System.Printing.ILegacyDevice Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_dc
0x9e29  ldarg.s  4
0x9e2b  callvirt instance void [System.Printing]System.Printing.ILegacyDevice::PushClip(class [PresentationCore]System.Windows.Media.Geometry)
0x9e30  ldarg.1
0x9e31  brfalse.s loc_9E42
0x9e33  ldc.i4.0
0x9e34  call     valuetype [PresentationCore]System.Windows.Media.Color [PresentationCore]System.Windows.Media.Colors::get_White()
0x9e39  ldarg.1
0x9e3a  ldc.i4.0
0x9e3b  call     class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::BlendColorWithBrush(bool opacityOnly, valuetype [PresentationCore]System.Windows.Media.Color colorA, class Microsoft.Internal.AlphaFlattener.BrushProxy brushB, bool reverse)
0x9e40  starg.s  1
0x9e42  ldarg.3
0x9e43  isinst   [PresentationCore]System.Windows.Media.LineGeometry
0x9e48  brfalse.s loc_9E9F
0x9e4a  ldarg.3
0x9e4b  callvirt instance class [PresentationCore]System.Windows.Media.Geometry [PresentationCore]System.Windows.Media.Geometry::CloneCurrentValue()
0x9e50  isinst   [PresentationCore]System.Windows.Media.LineGeometry
0x9e55  stloc.0
0x9e56  ldloc.0
0x9e57  ldarg.3
0x9e58  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Geometry::get_Transform()
0x9e5d  callvirt instance valuetype [WindowsBase]System.Windows.Media.Matrix [PresentationCore]System.Windows.Media.Transform::get_Value()
0x9e62  stloc.1
0x9e63  ldloca.s 1
0x9e65  ldloc.0
0x9e66  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.LineGeometry::get_StartPoint()
0x9e6b  call     instance valuetype [WindowsBase]System.Windows.Point [WindowsBase]System.Windows.Media.Matrix::Transform(valuetype [WindowsBase]System.Windows.Point)
0x9e70  callvirt instance void [PresentationCore]System.Windows.Media.LineGeometry::set_StartPoint(valuetype [WindowsBase]System.Windows.Point)
0x9e75  ldloc.0
0x9e76  ldarg.3
0x9e77  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Geometry::get_Transform()
0x9e7c  callvirt instance valuetype [WindowsBase]System.Windows.Media.Matrix [PresentationCore]System.Windows.Media.Transform::get_Value()
0x9e81  stloc.1
0x9e82  ldloca.s 1
0x9e84  ldloc.0
0x9e85  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.LineGeometry::get_EndPoint()
0x9e8a  call     instance valuetype [WindowsBase]System.Windows.Point [WindowsBase]System.Windows.Media.Matrix::Transform(valuetype [WindowsBase]System.Windows.Point)
0x9e8f  callvirt instance void [PresentationCore]System.Windows.Media.LineGeometry::set_EndPoint(valuetype [WindowsBase]System.Windows.Point)
0x9e94  ldloc.0
0x9e95  call     class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Transform::get_Identity()
0x9e9a  callvirt instance void [PresentationCore]System.Windows.Media.Geometry::set_Transform(class [PresentationCore]System.Windows.Media.Transform)
0x9e9f  ldarg.1
0x9ea0  brfalse  loc_9F3C
0x9ea5  ldarg.1
0x9ea6  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Internal.AlphaFlattener.BrushProxy::get_BrushList()
0x9eab  brfalse  loc_9F3C
0x9eb0  ldarg.0
0x9eb1  ldfld    bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_costing
0x9eb6  brfalse.s loc_9EDD
0x9eb8  ldarg.0
0x9eb9  ldarg.1
0x9eba  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Internal.AlphaFlattener.BrushProxy::get_BrushList()
0x9ebf  ldc.i4.0
0x9ec0  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x9ec5  isinst   Microsoft.Internal.AlphaFlattener.BrushProxy
0x9eca  ldarg.1
0x9ecb  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Internal.AlphaFlattener.BrushProxy::get_BrushList()
0x9ed0  ldc.i4.1
0x9ed1  ldarg.3
0x9ed2  call     instance bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::FillGeometry(class Microsoft.Internal.AlphaFlattener.BrushProxy one, class [mscorlib]System.Collections.ArrayList brushes, int32 from, class [PresentationCore]System.Windows.Media.Geometry geometry)
0x9ed7  pop
0x9ed8  br       loc_9FF5
0x9edd  ldarg.0
0x9ede  ldarg.1
0x9edf  ldarg.3
0x9ee0  call     instance bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::BetterRasterize(class Microsoft.Internal.AlphaFlattener.BrushProxy brush, class [PresentationCore]System.Windows.Media.Geometry shape)
0x9ee5  stloc.2
0x9ee6  ldloc.2
0x9ee7  brtrue.s loc_9F0C
0x9ee9  ldarg.0
0x9eea  ldarg.1
0x9eeb  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Internal.AlphaFlattener.BrushProxy::get_BrushList()
0x9ef0  ldc.i4.0
0x9ef1  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x9ef6  isinst   Microsoft.Internal.AlphaFlattener.BrushProxy
0x9efb  ldarg.1
0x9efc  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Internal.AlphaFlattener.BrushProxy::get_BrushList()
0x9f01  ldc.i4.1
0x9f02  ldarg.3
0x9f03  call     instance bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::FillGeometry(class Microsoft.Internal.AlphaFlattener.BrushProxy one, class [mscorlib]System.Collections.ArrayList brushes, int32 from, class [PresentationCore]System.Windows.Media.Geometry geometry)
0x9f08  ldc.i4.0
0x9f09  ceq
0x9f0b  stloc.2
0x9f0c  ldloc.2
0x9f0d  brfalse  loc_9FF5
0x9f12  ldc.i4.0
0x9f13  stloc.3
0x9f14  ldarg.s  4
0x9f16  brfalse.s loc_9F29
0x9f18  ldarg.3
0x9f19  ldarg.s  4
0x9f1b  call     valuetype [WindowsBase]System.Windows.Media.Matrix [WindowsBase]System.Windows.Media.Matrix::get_Identity()
0x9f20  ldloca.s 3
0x9f22  call     class [PresentationCore]System.Windows.Media.Geometry Microsoft.Internal.AlphaFlattener.Utility::Intersect(class [PresentationCore]System.Windows.Media.Geometry one, class [PresentationCore]System.Windows.Media.Geometry two, valuetype [WindowsBase]System.Windows.Media.Matrix mat, [out] bool& empty)
0x9f27  starg.s  3
0x9f29  ldloc.3
0x9f2a  brtrue   loc_9FF5
0x9f2f  ldarg.0
0x9f30  ldarg.1
0x9f31  ldarg.3
0x9f32  call     instance void Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::RasterizeGeometry(class Microsoft.Internal.AlphaFlattener.BrushProxy brush, class [PresentationCore]System.Windows.Media.Geometry shape)
0x9f37  br       loc_9FF5
0x9f3c  ldnull
0x9f3d  stloc.s  4
0x9f3f  ldnull
0x9f40  stloc.s  5
0x9f42  ldarg.2
0x9f43  brfalse.s loc_9F6F
0x9f45  ldarg.2
0x9f46  ldc.i4.1
0x9f47  callvirt instance class [PresentationCore]System.Windows.Media.Pen Microsoft.Internal.AlphaFlattener.PenProxy::GetPen(bool ignoreBrushProxy)
0x9f4c  stloc.s  4
0x9f4e  ldarg.2
0x9f4f  callvirt instance class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.PenProxy::get_StrokeBrush()
0x9f54  stloc.s  5
0x9f56  ldloc.s  5
0x9f58  callvirt instance bool Microsoft.Internal.AlphaFlattener.BrushProxy::IsOpaque()
0x9f5d  brtrue.s loc_9F6F
0x9f5f  ldc.i4.0
0x9f60  call     valuetype [PresentationCore]System.Windows.Media.Color [PresentationCore]System.Windows.Media.Colors::get_White()
0x9f65  ldloc.s  5
0x9f67  ldc.i4.0
0x9f68  call     class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::BlendColorWithBrush(bool opacityOnly, valuetype [PresentationCore]System.Windows.Media.Color colorA, class Microsoft.Internal.AlphaFlattener.BrushProxy brushB, bool reverse)
0x9f6d  stloc.s  5
0x9f6f  ldnull
0x9f70  stloc.s  6
0x9f72  ldarg.0
0x9f73  ldfld    bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_costing
0x9f78  brfalse.s loc_9FBD
0x9f7a  ldarg.1
0x9f7b  brfalse.s loc_9FA4
0x9f7d  ldarg.1
0x9f7e  callvirt instance class [PresentationCore]System.Windows.Media.Brush Microsoft.Internal.AlphaFlattener.BrushProxy::get_Brush()
0x9f83  brfalse.s loc_9F9C
0x9f85  ldarg.1
0x9f86  callvirt instance class [PresentationCore]System.Windows.Media.Brush Microsoft.Internal.AlphaFlattener.BrushProxy::get_Brush()
0x9f8b  isinst   [PresentationCore]System.Windows.Media.DrawingBrush
0x9f90  brfalse.s loc_9F9C
0x9f92  ldarg.1
0x9f93  callvirt instance class [PresentationCore]System.Windows.Media.Brush Microsoft.Internal.AlphaFlattener.BrushProxy::get_Brush()
0x9f98  stloc.s  6
0x9f9a  br.s     loc_9FA4
0x9f9c  ldarg.1
0x9f9d  callvirt instance class [PresentationCore]System.Windows.Media.Brush Microsoft.Internal.AlphaFlattener.BrushProxy::GetRealBrush()
0x9fa2  stloc.s  6
0x9fa4  ldarg.0
0x9fa5  ldarg.0
0x9fa6  ldfld    float64 Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_cost
0x9fab  ldloc.s  6
0x9fad  ldloc.s  4
0x9faf  ldarg.3
0x9fb0  call     float64 Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::DrawGeometryCost(class [PresentationCore]System.Windows.Media.Brush b, class [PresentationCore]System.Windows.Media.Pen p, class [PresentationCore]System.Windows.Media.Geometry g)
0x9fb5  add
0x9fb6  stfld    float64 Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_cost
0x9fbb  br.s     loc_9FF5
0x9fbd  ldarg.1
0x9fbe  brfalse.s loc_9FC8
0x9fc0  ldarg.1
0x9fc1  callvirt instance class [PresentationCore]System.Windows.Media.Brush Microsoft.Internal.AlphaFlattener.BrushProxy::GetRealBrush()
0x9fc6  stloc.s  6
0x9fc8  ldloc.s  4
0x9fca  brtrue.s loc_9FDE
0x9fcc  ldarg.0
0x9fcd  ldfld    class [System.Printing]System.Printing.ILegacyDevice Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_dc
0x9fd2  ldloc.s  6
0x9fd4  ldnull
0x9fd5  ldnull
0x9fd6  ldarg.3
0x9fd7  callvirt instance void [System.Printing]System.Printing.ILegacyDevice::DrawGeometry(class [PresentationCore]System.Windows.Media.Brush, class [PresentationCore]System.Windows.Media.Pen, class [PresentationCore]System.Windows.Media.Brush, class [PresentationCore]System.Windows.Media.Geometry)
0x9fdc  br.s     loc_9FF5
0x9fde  ldarg.0
0x9fdf  ldfld    class [System.Printing]System.Printing.ILegacyDevice Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_dc
0x9fe4  ldloc.s  6
0x9fe6  ldloc.s  4
0x9fe8  ldloc.s  5
0x9fea  callvirt instance class [PresentationCore]System.Windows.Media.Brush Microsoft.Internal.AlphaFlattener.BrushProxy::GetRealBrush()
0x9fef  ldarg.3
0x9ff0  callvirt instance void [System.Printing]System.Printing.ILegacyDevice::DrawGeometry(class [PresentationCore]System.Windows.Media.Brush, class [PresentationCore]System.Windows.Media.Pen, class [PresentationCore]System.Windows.Media.Brush, class [PresentationCore]System.Windows.Media.Geometry)
0x9ff5  ldarg.0
0x9ff6  ldfld    bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_costing
0x9ffb  brtrue.s loc_A00C
0x9ffd  ldarg.s  4
0x9fff  brfalse.s loc_A00C
0xa001  ldarg.0
0xa002  ldfld    class [System.Printing]System.Printing.ILegacyDevice Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_dc
0xa007  callvirt instance void [System.Printing]System.Printing.ILegacyDevice::PopClip()
0xa00c  ret
```
