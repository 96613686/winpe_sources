# System.Windows.Xps.Serialization.VisualSerializer::PathGeometryToString

- ea: `0x37d50`
- end: `0x3812f`
- name: `System.Windows.Xps.Serialization.VisualSerializer::PathGeometryToString`
- size: `991`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x38200`

## callees

- `0x2490`
- `0x36640`
- `0x36680`
- `0x37720`
- `0x37d30`
- `0x37d40`
- `0x37d50`

## pseudocode

```c

```

## disassembly

```asm
0x37d50  ldarg.1
0x37d51  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Geometry::get_Transform()
0x37d56  brfalse.s loc_37D78
0x37d58  ldarg.1
0x37d59  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Geometry::get_Transform()
0x37d5e  call     bool Microsoft.Internal.AlphaFlattener.Utility::IsIdentity(class [PresentationCore]System.Windows.Media.Transform transform)
0x37d63  brtrue.s loc_37D78
0x37d65  ldarg.1
0x37d66  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Geometry::get_Transform()
0x37d6b  callvirt instance valuetype [WindowsBase]System.Windows.Media.Matrix [PresentationCore]System.Windows.Media.Transform::get_Value()
0x37d70  ldarg.2
0x37d71  call     valuetype [WindowsBase]System.Windows.Media.Matrix [WindowsBase]System.Windows.Media.Matrix::op_Multiply(valuetype [WindowsBase]System.Windows.Media.Matrix, valuetype [WindowsBase]System.Windows.Media.Matrix)
0x37d76  starg.s  2
0x37d78  ldarg.1
0x37d79  callvirt instance class [PresentationCore]System.Windows.Media.PathFigureCollection [PresentationCore]System.Windows.Media.PathGeometry::get_Figures()
0x37d7e  stloc.0
0x37d7f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x37d84  stloc.1
0x37d85  ldc.i4.0
0x37d86  stloc.2
0x37d87  ldloc.0
0x37d88  callvirt instance valuetype [PresentationCore]System.Windows.Media.PathFigureCollection/Enumerator [PresentationCore]System.Windows.Media.PathFigureCollection::GetEnumerator()
0x37d8d  stloc.3
0x37d8e  br       loc_380FA
0x37d93  ldloca.s 3
0x37d95  call     instance class [PresentationCore]System.Windows.Media.PathFigure [PresentationCore]System.Windows.Media.PathFigureCollection/Enumerator::get_Current()
0x37d9a  stloc.s  4
0x37d9c  ldloc.s  4
0x37d9e  callvirt instance bool [PresentationCore]System.Windows.Media.PathFigure::get_IsFilled()
0x37da3  brtrue.s loc_37DB9
0x37da5  ldarg.s  4
0x37da7  ldarg.3
0x37da8  and
0x37da9  brfalse.s loc_37DB3
0x37dab  ldnull
0x37dac  stloc.s  6
0x37dae  leave    loc_3812C
0x37db3  ldarg.3
0x37db4  brtrue   loc_380FA
0x37db9  ldloc.s  4
0x37dbb  callvirt instance class [PresentationCore]System.Windows.Media.PathSegmentCollection [PresentationCore]System.Windows.Media.PathFigure::get_Segments()
0x37dc0  stloc.s  5
0x37dc2  ldloc.1
0x37dc3  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x37dc8  brtrue.s loc_37DDE
0x37dca  ldarg.1
0x37dcb  callvirt instance valuetype [PresentationCore]System.Windows.Media.FillRule [PresentationCore]System.Windows.Media.PathGeometry::get_FillRule()
0x37dd0  brfalse.s loc_37DDE
0x37dd2  ldloc.1
0x37dd3  ldstr    aF1// "F1"
0x37dd8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x37ddd  pop
0x37dde  ldloc.1
0x37ddf  ldc.i4.s 0x4D
0x37de1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x37de6  pop
0x37de7  ldarg.0
0x37de8  ldloc.1
0x37de9  ldloc.s  4
0x37deb  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.PathFigure::get_StartPoint()
0x37df0  ldarg.2
0x37df1  call     instance void System.Windows.Xps.Serialization.VisualSerializer::AppendPoint(class [mscorlib]System.Text.StringBuilder builder, valuetype [WindowsBase]System.Windows.Point p, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x37df6  ldloc.2
0x37df7  ldc.i4.1
0x37df8  add
0x37df9  stloc.2
0x37dfa  ldloc.s  5
0x37dfc  callvirt instance valuetype [PresentationCore]System.Windows.Media.PathSegmentCollection/Enumerator [PresentationCore]System.Windows.Media.PathSegmentCollection::GetEnumerator()
0x37e01  stloc.s  7
0x37e03  br       loc_380CC
0x37e08  ldloca.s 7
0x37e0a  call     instance class [PresentationCore]System.Windows.Media.PathSegment [PresentationCore]System.Windows.Media.PathSegmentCollection/Enumerator::get_Current()
0x37e0f  stloc.s  8
0x37e11  ldarg.s  4
0x37e13  brfalse.s loc_37E2F
0x37e15  ldloc.s  8
0x37e17  callvirt instance bool [PresentationCore]System.Windows.Media.PathSegment::get_IsStroked()
0x37e1c  brfalse.s loc_37E27
0x37e1e  ldloc.s  8
0x37e20  callvirt instance bool [PresentationCore]System.Windows.Media.PathSegment::get_IsSmoothJoin()
0x37e25  brfalse.s loc_37E2F
0x37e27  ldnull
0x37e28  stloc.s  6
0x37e2a  leave    loc_3812C
0x37e2f  ldloc.s  8
0x37e31  isinst   [PresentationCore]System.Windows.Media.PolyLineSegment
0x37e36  brfalse.s loc_37E61
0x37e38  ldloc.s  8
0x37e3a  isinst   [PresentationCore]System.Windows.Media.PolyLineSegment
0x37e3f  stloc.s  9
0x37e41  ldloc.1
0x37e42  ldc.i4.s 0x4C
0x37e44  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x37e49  pop
0x37e4a  ldloc.2
0x37e4b  ldarg.0
0x37e4c  ldloc.1
0x37e4d  ldloc.s  9
0x37e4f  callvirt instance class [PresentationCore]System.Windows.Media.PointCollection [PresentationCore]System.Windows.Media.PolyLineSegment::get_Points()
0x37e54  ldarg.2
0x37e55  call     instance int32 System.Windows.Xps.Serialization.VisualSerializer::AppendPoints(class [mscorlib]System.Text.StringBuilder builder, class [PresentationCore]System.Windows.Media.PointCollection pc, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x37e5a  add
0x37e5b  stloc.2
0x37e5c  br       loc_380CC
0x37e61  ldloc.s  8
0x37e63  isinst   [PresentationCore]System.Windows.Media.PolyBezierSegment
0x37e68  brfalse.s loc_37E93
0x37e6a  ldloc.s  8
0x37e6c  isinst   [PresentationCore]System.Windows.Media.PolyBezierSegment
0x37e71  stloc.s  0xA
0x37e73  ldloc.1
0x37e74  ldc.i4.s 0x43
0x37e76  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x37e7b  pop
0x37e7c  ldloc.2
0x37e7d  ldarg.0
0x37e7e  ldloc.1
0x37e7f  ldloc.s  0xA
0x37e81  callvirt instance class [PresentationCore]System.Windows.Media.PointCollection [PresentationCore]System.Windows.Media.PolyBezierSegment::get_Points()
0x37e86  ldarg.2
0x37e87  call     instance int32 System.Windows.Xps.Serialization.VisualSerializer::AppendPoints(class [mscorlib]System.Text.StringBuilder builder, class [PresentationCore]System.Windows.Media.PointCollection pc, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x37e8c  add
0x37e8d  stloc.2
0x37e8e  br       loc_380CC
0x37e93  ldloc.s  8
0x37e95  isinst   [PresentationCore]System.Windows.Media.LineSegment
0x37e9a  brfalse.s loc_37EC6
0x37e9c  ldloc.s  8
0x37e9e  isinst   [PresentationCore]System.Windows.Media.LineSegment
0x37ea3  stloc.s  0xB
0x37ea5  ldloc.1
0x37ea6  ldc.i4.s 0x4C
0x37ea8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x37ead  pop
0x37eae  ldarg.0
0x37eaf  ldloc.1
0x37eb0  ldloc.s  0xB
0x37eb2  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.LineSegment::get_Point()
0x37eb7  ldarg.2
0x37eb8  call     instance void System.Windows.Xps.Serialization.VisualSerializer::AppendPoint(class [mscorlib]System.Text.StringBuilder builder, valuetype [WindowsBase]System.Windows.Point p, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x37ebd  ldloc.2
0x37ebe  ldc.i4.1
0x37ebf  add
0x37ec0  stloc.2
0x37ec1  br       loc_380CC
0x37ec6  ldloc.s  8
0x37ec8  isinst   [PresentationCore]System.Windows.Media.BezierSegment
0x37ecd  brfalse.s loc_37F29
0x37ecf  ldloc.s  8
0x37ed1  isinst   [PresentationCore]System.Windows.Media.BezierSegment
0x37ed6  stloc.s  0xC
0x37ed8  ldloc.1
0x37ed9  ldc.i4.s 0x43
0x37edb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x37ee0  pop
0x37ee1  ldarg.0
0x37ee2  ldloc.1
0x37ee3  ldloc.s  0xC
0x37ee5  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.BezierSegment::get_Point1()
0x37eea  ldarg.2
0x37eeb  call     instance void System.Windows.Xps.Serialization.VisualSerializer::AppendPoint(class [mscorlib]System.Text.StringBuilder builder, valuetype [WindowsBase]System.Windows.Point p, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x37ef0  ldloc.1
0x37ef1  ldc.i4.s 0x20
0x37ef3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x37ef8  pop
0x37ef9  ldarg.0
0x37efa  ldloc.1
0x37efb  ldloc.s  0xC
0x37efd  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.BezierSegment::get_Point2()
0x37f02  ldarg.2
0x37f03  call     instance void System.Windows.Xps.Serialization.VisualSerializer::AppendPoint(class [mscorlib]System.Text.StringBuilder builder, valuetype [WindowsBase]System.Windows.Point p, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x37f08  ldloc.1
0x37f09  ldc.i4.s 0x20
0x37f0b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x37f10  pop
0x37f11  ldarg.0
0x37f12  ldloc.1
0x37f13  ldloc.s  0xC
0x37f15  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.BezierSegment::get_Point3()
0x37f1a  ldarg.2
0x37f1b  call     instance void System.Windows.Xps.Serialization.VisualSerializer::AppendPoint(class [mscorlib]System.Text.StringBuilder builder, valuetype [WindowsBase]System.Windows.Point p, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x37f20  ldloc.2
0x37f21  ldc.i4.3
0x37f22  add
0x37f23  stloc.2
0x37f24  br       loc_380CC
0x37f29  ldloc.s  8
0x37f2b  isinst   [PresentationCore]System.Windows.Media.ArcSegment
0x37f30  brfalse  loc_38050
0x37f35  ldarg.2
0x37f36  call     bool System.Windows.Xps.Serialization.VisualSerializer::IsUniformScale(valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x37f3b  brfalse  loc_38048
0x37f40  ldloc.s  8
0x37f42  isinst   [PresentationCore]System.Windows.Media.ArcSegment
0x37f47  stloc.s  0xD
0x37f49  ldloc.s  0xD
0x37f4b  callvirt instance valuetype [WindowsBase]System.Windows.Size [PresentationCore]System.Windows.Media.ArcSegment::get_Size()
0x37f50  stloc.s  0xE
0x37f52  ldloca.s 0xE
0x37f54  call     instance bool [WindowsBase]System.Windows.Size::get_IsEmpty()
0x37f59  brtrue.s loc_37F7F
0x37f5b  ldloca.s 0xE
0x37f5d  call     instance float64 [WindowsBase]System.Windows.Size::get_Width()
0x37f62  ldc.r8   0.0
0x37f6b  beq.s    loc_37F7F
0x37f6d  ldloca.s 0xE
0x37f6f  call     instance float64 [WindowsBase]System.Windows.Size::get_Height()
0x37f74  ldc.r8   0.0
0x37f7d  bne.un.s loc_37FA0
0x37f7f  ldloc.1
0x37f80  ldc.i4.s 0x4C
0x37f82  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x37f87  pop
0x37f88  ldarg.0
0x37f89  ldloc.1
0x37f8a  ldloc.s  0xD
0x37f8c  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.ArcSegment::get_Point()
0x37f91  ldarg.2
0x37f92  call     instance void System.Windows.Xps.Serialization.VisualSerializer::AppendPoint(class [mscorlib]System.Text.StringBuilder builder, valuetype [WindowsBase]System.Windows.Point p, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x37f97  ldloc.2
0x37f98  ldc.i4.1
0x37f99  add
0x37f9a  stloc.2
0x37f9b  br       loc_380CC
0x37fa0  ldloc.1
0x37fa1  ldc.i4.s 0x41
0x37fa3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x37fa8  pop
0x37fa9  ldarg.0
0x37faa  ldloc.1
0x37fab  ldloca.s 0xE
0x37fad  call     instance float64 [WindowsBase]System.Windows.Size::get_Width()
0x37fb2  ldarga.s 2
0x37fb4  call     instance float64 [WindowsBase]System.Windows.Media.Matrix::get_M11()
0x37fb9  mul
0x37fba  ldloca.s 0xE
0x37fbc  call     instance float64 [WindowsBase]System.Windows.Size::get_Height()
0x37fc1  ldarga.s 2
0x37fc3  call     instance float64 [WindowsBase]System.Windows.Media.Matrix::get_M22()
0x37fc8  mul
0x37fc9  newobj   instance void [WindowsBase]System.Windows.Point::.ctor(float64, float64)
0x37fce  call     valuetype [WindowsBase]System.Windows.Media.Matrix [WindowsBase]System.Windows.Media.Matrix::get_Identity()
0x37fd3  call     instance void System.Windows.Xps.Serialization.VisualSerializer::AppendPoint(class [mscorlib]System.Text.StringBuilder builder, valuetype [WindowsBase]System.Windows.Point p, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x37fd8  ldloc.1
0x37fd9  ldc.i4.s 0x20
0x37fdb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x37fe0  pop
0x37fe1  ldloc.1
0x37fe2  ldloc.s  0xD
0x37fe4  callvirt instance float64 [PresentationCore]System.Windows.Media.ArcSegment::get_RotationAngle()
0x37fe9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(float64)
0x37fee  pop
0x37fef  ldloc.1
0x37ff0  ldc.i4.s 0x20
0x37ff2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x37ff7  pop
0x37ff8  ldloc.1
0x37ff9  ldloc.s  0xD
0x37ffb  callvirt instance bool [PresentationCore]System.Windows.Media.ArcSegment::get_IsLargeArc()
0x38000  call     char System.Windows.Xps.Serialization.VisualSerializer::Ord(bool b)
0x38005  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x3800a  pop
0x3800b  ldloc.1
0x3800c  ldc.i4.s 0x20
0x3800e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x38013  pop
0x38014  ldloc.1
0x38015  ldloc.s  0xD
0x38017  callvirt instance valuetype [PresentationCore]System.Windows.Media.SweepDirection [PresentationCore]System.Windows.Media.ArcSegment::get_SweepDirection()
0x3801c  call     char System.Windows.Xps.Serialization.VisualSerializer::Ord(valuetype [PresentationCore]System.Windows.Media.SweepDirection d)
0x38021  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x38026  pop
0x38027  ldloc.1
0x38028  ldc.i4.s 0x20
0x3802a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x3802f  pop
0x38030  ldarg.0
0x38031  ldloc.1
0x38032  ldloc.s  0xD
0x38034  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.ArcSegment::get_Point()
0x38039  ldarg.2
0x3803a  call     instance void System.Windows.Xps.Serialization.VisualSerializer::AppendPoint(class [mscorlib]System.Text.StringBuilder builder, valuetype [WindowsBase]System.Windows.Point p, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x3803f  ldloc.2
0x38040  ldc.i4.2
0x38041  add
0x38042  stloc.2
0x38043  br       loc_380CC
0x38048  ldnull
0x38049  stloc.s  6
0x3804b  leave    loc_3812C
0x38050  ldloc.s  8
0x38052  isinst   [PresentationCore]System.Windows.Media.QuadraticBezierSegment
0x38057  brfalse.s loc_38098
0x38059  ldloc.s  8
0x3805b  isinst   [PresentationCore]System.Windows.Media.QuadraticBezierSegment
0x38060  stloc.s  0xF
0x38062  ldloc.1
0x38063  ldc.i4.s 0x51
0x38065  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x3806a  pop
  ... truncated ...
```
