# System.Windows.Xps.Serialization.VisualSerializer::WritePathFigureCollection

- ea: `0x37870`
- end: `0x37cf6`
- name: `System.Windows.Xps.Serialization.VisualSerializer::WritePathFigureCollection`
- size: `1158`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x38200`

## callees

- `0x36640`
- `0x36950`
- `0x37870`
- `0x381b0`

## string_xrefs

- `0x3789d`: `PathFigure`
- `0x37c7d`: `PathSegment not handled`

## pseudocode

```c

```

## disassembly

```asm
0x37870  ldc.i4.0
0x37871  stloc.0
0x37872  ldarg.1
0x37873  callvirt instance valuetype [PresentationCore]System.Windows.Media.PathFigureCollection/Enumerator [PresentationCore]System.Windows.Media.PathFigureCollection::GetEnumerator()
0x37878  stloc.1
0x37879  br       loc_37CCA
0x3787e  ldloca.s 1
0x37880  call     instance class [PresentationCore]System.Windows.Media.PathFigure [PresentationCore]System.Windows.Media.PathFigureCollection/Enumerator::get_Current()
0x37885  stloc.2
0x37886  ldarg.2
0x37887  brfalse.s loc_37897
0x37889  ldarg.3
0x3788a  brtrue.s loc_37897
0x3788c  ldloc.2
0x3788d  callvirt instance bool [PresentationCore]System.Windows.Media.PathFigure::get_IsFilled()
0x37892  brfalse  loc_37CCA
0x37897  ldarg.0
0x37898  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x3789d  ldstr    aPathfigure// "PathFigure"
0x378a2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x378a7  ldloc.0
0x378a8  ldc.i4.1
0x378a9  add
0x378aa  stloc.0
0x378ab  ldarg.0
0x378ac  ldstr    aStartpoint// "StartPoint"
0x378b1  ldloc.2
0x378b2  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.PathFigure::get_StartPoint()
0x378b7  box      [WindowsBase]System.Windows.Point
0x378bc  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x378c1  ldarg.0
0x378c2  ldstr    aIsclosed// "IsClosed"
0x378c7  ldloc.2
0x378c8  callvirt instance bool [PresentationCore]System.Windows.Media.PathFigure::get_IsClosed()
0x378cd  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteBool(string attr, bool val)
0x378d2  ldloc.2
0x378d3  callvirt instance bool [PresentationCore]System.Windows.Media.PathFigure::get_IsFilled()
0x378d8  brtrue.s loc_378EA
0x378da  ldarg.0
0x378db  ldstr    aIsfilled// "IsFilled"
0x378e0  ldstr    aFalse// "false"
0x378e5  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x378ea  ldloc.2
0x378eb  callvirt instance class [PresentationCore]System.Windows.Media.PathSegmentCollection [PresentationCore]System.Windows.Media.PathFigure::get_Segments()
0x378f0  stloc.3
0x378f1  ldloc.3
0x378f2  callvirt instance int32 [PresentationCore]System.Windows.Media.PathSegmentCollection::get_Count()
0x378f7  stloc.s  4
0x378f9  ldc.i4.0
0x378fa  stloc.s  5
0x378fc  br       loc_37CB6
0x37901  ldloc.3
0x37902  ldloc.s  5
0x37904  callvirt instance class [PresentationCore]System.Windows.Media.PathSegment [PresentationCore]System.Windows.Media.PathSegmentCollection::get_Item(int32)
0x37909  stloc.s  6
0x3790b  ldarg.3
0x3790c  brfalse.s loc_37936
0x3790e  ldarg.2
0x3790f  brtrue.s loc_37936
0x37911  ldloc.s  6
0x37913  callvirt instance bool [PresentationCore]System.Windows.Media.PathSegment::get_IsStroked()
0x37918  brtrue.s loc_37936
0x3791a  ldloc.s  5
0x3791c  ldloc.s  4
0x3791e  ldc.i4.1
0x3791f  sub
0x37920  bge.s    loc_37936
0x37922  ldloc.3
0x37923  ldloc.s  5
0x37925  ldc.i4.1
0x37926  add
0x37927  callvirt instance class [PresentationCore]System.Windows.Media.PathSegment [PresentationCore]System.Windows.Media.PathSegmentCollection::get_Item(int32)
0x3792c  callvirt instance bool [PresentationCore]System.Windows.Media.PathSegment::get_IsStroked()
0x37931  brfalse  loc_37CB0
0x37936  ldloc.s  6
0x37938  isinst   [PresentationCore]System.Windows.Media.PolyLineSegment
0x3793d  stloc.s  7
0x3793f  ldloc.s  7
0x37941  brfalse.s loc_37979
0x37943  ldarg.0
0x37944  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x37949  ldstr    aPolylinesegmen// "PolyLineSegment"
0x3794e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x37953  ldarg.0
0x37954  ldstr    aPoints// "Points"
0x37959  ldloc.s  7
0x3795b  callvirt instance class [PresentationCore]System.Windows.Media.PointCollection [PresentationCore]System.Windows.Media.PolyLineSegment::get_Points()
0x37960  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x37965  ldloc.0
0x37966  ldloc.s  7
0x37968  callvirt instance class [PresentationCore]System.Windows.Media.PointCollection [PresentationCore]System.Windows.Media.PolyLineSegment::get_Points()
0x3796d  callvirt instance int32 [PresentationCore]System.Windows.Media.PointCollection::get_Count()
0x37972  add
0x37973  stloc.0
0x37974  br       loc_37C8C
0x37979  ldloc.s  6
0x3797b  isinst   [PresentationCore]System.Windows.Media.PolyBezierSegment
0x37980  brfalse.s loc_379C1
0x37982  ldloc.s  6
0x37984  isinst   [PresentationCore]System.Windows.Media.PolyBezierSegment
0x37989  stloc.s  8
0x3798b  ldarg.0
0x3798c  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x37991  ldstr    aPolybeziersegm// "PolyBezierSegment"
0x37996  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3799b  ldarg.0
0x3799c  ldstr    aPoints// "Points"
0x379a1  ldloc.s  8
0x379a3  callvirt instance class [PresentationCore]System.Windows.Media.PointCollection [PresentationCore]System.Windows.Media.PolyBezierSegment::get_Points()
0x379a8  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x379ad  ldloc.0
0x379ae  ldloc.s  8
0x379b0  callvirt instance class [PresentationCore]System.Windows.Media.PointCollection [PresentationCore]System.Windows.Media.PolyBezierSegment::get_Points()
0x379b5  callvirt instance int32 [PresentationCore]System.Windows.Media.PointCollection::get_Count()
0x379ba  add
0x379bb  stloc.0
0x379bc  br       loc_37C8C
0x379c1  ldloc.s  6
0x379c3  isinst   [PresentationCore]System.Windows.Media.LineSegment
0x379c8  brfalse.s loc_37A03
0x379ca  ldloc.s  6
0x379cc  isinst   [PresentationCore]System.Windows.Media.LineSegment
0x379d1  stloc.s  9
0x379d3  ldarg.0
0x379d4  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x379d9  ldstr    aPolylinesegmen// "PolyLineSegment"
0x379de  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x379e3  ldarg.0
0x379e4  ldstr    aPoints// "Points"
0x379e9  ldloc.s  9
0x379eb  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.LineSegment::get_Point()
0x379f0  box      [WindowsBase]System.Windows.Point
0x379f5  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x379fa  ldloc.0
0x379fb  ldc.i4.1
0x379fc  add
0x379fd  stloc.0
0x379fe  br       loc_37C8C
0x37a03  ldloc.s  6
0x37a05  isinst   [PresentationCore]System.Windows.Media.BezierSegment
0x37a0a  brfalse  loc_37A9F
0x37a0f  ldloc.s  6
0x37a11  isinst   [PresentationCore]System.Windows.Media.BezierSegment
0x37a16  stloc.s  0xA
0x37a18  ldarg.0
0x37a19  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x37a1e  ldstr    aPolybeziersegm// "PolyBezierSegment"
0x37a23  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x37a28  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x37a2d  stloc.s  0xB
0x37a2f  ldarg.0
0x37a30  ldloc.s  0xB
0x37a32  ldloc.s  0xA
0x37a34  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.BezierSegment::get_Point1()
0x37a39  call     valuetype [WindowsBase]System.Windows.Media.Matrix [WindowsBase]System.Windows.Media.Matrix::get_Identity()
0x37a3e  call     instance void System.Windows.Xps.Serialization.VisualSerializer::AppendPoint(class [mscorlib]System.Text.StringBuilder builder, valuetype [WindowsBase]System.Windows.Point p, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x37a43  ldloc.s  0xB
0x37a45  ldc.i4.s 0x20
0x37a47  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x37a4c  pop
0x37a4d  ldarg.0
0x37a4e  ldloc.s  0xB
0x37a50  ldloc.s  0xA
0x37a52  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.BezierSegment::get_Point2()
0x37a57  call     valuetype [WindowsBase]System.Windows.Media.Matrix [WindowsBase]System.Windows.Media.Matrix::get_Identity()
0x37a5c  call     instance void System.Windows.Xps.Serialization.VisualSerializer::AppendPoint(class [mscorlib]System.Text.StringBuilder builder, valuetype [WindowsBase]System.Windows.Point p, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x37a61  ldloc.s  0xB
0x37a63  ldc.i4.s 0x20
0x37a65  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x37a6a  pop
0x37a6b  ldarg.0
0x37a6c  ldloc.s  0xB
0x37a6e  ldloc.s  0xA
0x37a70  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.BezierSegment::get_Point3()
0x37a75  call     valuetype [WindowsBase]System.Windows.Media.Matrix [WindowsBase]System.Windows.Media.Matrix::get_Identity()
0x37a7a  call     instance void System.Windows.Xps.Serialization.VisualSerializer::AppendPoint(class [mscorlib]System.Text.StringBuilder builder, valuetype [WindowsBase]System.Windows.Point p, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x37a7f  ldarg.0
0x37a80  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x37a85  ldstr    aPoints// "Points"
0x37a8a  ldloc.s  0xB
0x37a8c  callvirt instance string [mscorlib]System.Object::ToString()
0x37a91  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x37a96  ldloc.0
0x37a97  ldc.i4.3
0x37a98  add
0x37a99  stloc.0
0x37a9a  br       loc_37C8C
0x37a9f  ldloc.s  6
0x37aa1  isinst   [PresentationCore]System.Windows.Media.ArcSegment
0x37aa6  brfalse  loc_37BB3
0x37aab  ldloc.s  6
0x37aad  isinst   [PresentationCore]System.Windows.Media.ArcSegment
0x37ab2  stloc.s  0xC
0x37ab4  ldloc.s  0xC
0x37ab6  callvirt instance valuetype [WindowsBase]System.Windows.Size [PresentationCore]System.Windows.Media.ArcSegment::get_Size()
0x37abb  stloc.s  0xD
0x37abd  ldloca.s 0xD
0x37abf  call     instance bool [WindowsBase]System.Windows.Size::get_IsEmpty()
0x37ac4  brtrue.s loc_37AFC
0x37ac6  ldloc.s  0xC
0x37ac8  callvirt instance valuetype [WindowsBase]System.Windows.Size [PresentationCore]System.Windows.Media.ArcSegment::get_Size()
0x37acd  stloc.s  0xD
0x37acf  ldloca.s 0xD
0x37ad1  call     instance float64 [WindowsBase]System.Windows.Size::get_Width()
0x37ad6  ldc.r8   0.0
0x37adf  beq.s    loc_37AFC
0x37ae1  ldloc.s  0xC
0x37ae3  callvirt instance valuetype [WindowsBase]System.Windows.Size [PresentationCore]System.Windows.Media.ArcSegment::get_Size()
0x37ae8  stloc.s  0xD
0x37aea  ldloca.s 0xD
0x37aec  call     instance float64 [WindowsBase]System.Windows.Size::get_Height()
0x37af1  ldc.r8   0.0
0x37afa  bne.un.s loc_37B2C
0x37afc  ldarg.0
0x37afd  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x37b02  ldstr    aPolylinesegmen// "PolyLineSegment"
0x37b07  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x37b0c  ldarg.0
0x37b0d  ldstr    aPoints// "Points"
0x37b12  ldloc.s  0xC
0x37b14  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.ArcSegment::get_Point()
0x37b19  box      [WindowsBase]System.Windows.Point
0x37b1e  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x37b23  ldloc.0
0x37b24  ldc.i4.1
0x37b25  add
0x37b26  stloc.0
0x37b27  br       loc_37C8C
0x37b2c  ldarg.0
0x37b2d  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x37b32  ldstr    aArcsegment// "ArcSegment"
0x37b37  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x37b3c  ldarg.0
0x37b3d  ldstr    aPoint// "Point"
0x37b42  ldloc.s  0xC
0x37b44  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.ArcSegment::get_Point()
0x37b49  box      [WindowsBase]System.Windows.Point
0x37b4e  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x37b53  ldarg.0
0x37b54  ldstr    aSize// "Size"
0x37b59  ldloc.s  0xC
0x37b5b  callvirt instance valuetype [WindowsBase]System.Windows.Size [PresentationCore]System.Windows.Media.ArcSegment::get_Size()
0x37b60  box      [WindowsBase]System.Windows.Size
0x37b65  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x37b6a  ldarg.0
0x37b6b  ldstr    aRotationangle// "RotationAngle"
0x37b70  ldloc.s  0xC
0x37b72  callvirt instance float64 [PresentationCore]System.Windows.Media.ArcSegment::get_RotationAngle()
0x37b77  box      [mscorlib]System.Double
0x37b7c  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x37b81  ldarg.0
0x37b82  ldstr    aIslargearc// "IsLargeArc"
0x37b87  ldloc.s  0xC
0x37b89  callvirt instance bool [PresentationCore]System.Windows.Media.ArcSegment::get_IsLargeArc()
0x37b8e  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteBool(string attr, bool val)
0x37b93  ldarg.0
0x37b94  ldstr    aSweepdirection// "SweepDirection"
0x37b99  ldloc.s  0xC
0x37b9b  callvirt instance valuetype [PresentationCore]System.Windows.Media.SweepDirection [PresentationCore]System.Windows.Media.ArcSegment::get_SweepDirection()
0x37ba0  box      [PresentationCore]System.Windows.Media.SweepDirection
0x37ba5  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x37baa  ldloc.0
0x37bab  ldc.i4.2
0x37bac  add
0x37bad  stloc.0
0x37bae  br       loc_37C8C
0x37bb3  ldloc.s  6
0x37bb5  isinst   [PresentationCore]System.Windows.Media.QuadraticBezierSegment
0x37bba  brfalse.s loc_37C2B
0x37bbc  ldloc.s  6
0x37bbe  isinst   [PresentationCore]System.Windows.Media.QuadraticBezierSegment
0x37bc3  stloc.s  0xE
0x37bc5  ldarg.0
0x37bc6  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x37bcb  ldstr    aPolyquadraticb// "PolyQuadraticBezierSegment"
0x37bd0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x37bd5  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x37bda  stloc.s  0xF
0x37bdc  ldarg.0
0x37bdd  ldloc.s  0xF
0x37bdf  ldloc.s  0xE
0x37be1  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.QuadraticBezierSegment::get_Point1()
0x37be6  call     valuetype [WindowsBase]System.Windows.Media.Matrix [WindowsBase]System.Windows.Media.Matrix::get_Identity()
0x37beb  call     instance void System.Windows.Xps.Serialization.VisualSerializer::AppendPoint(class [mscorlib]System.Text.StringBuilder builder, valuetype [WindowsBase]System.Windows.Point p, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x37bf0  ldloc.s  0xF
0x37bf2  ldc.i4.s 0x20
0x37bf4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x37bf9  pop
0x37bfa  ldarg.0
0x37bfb  ldloc.s  0xF
0x37bfd  ldloc.s  0xE
0x37bff  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.QuadraticBezierSegment::get_Point2()
0x37c04  call     valuetype [WindowsBase]System.Windows.Media.Matrix [WindowsBase]System.Windows.Media.Matrix::get_Identity()
0x37c09  call     instance void System.Windows.Xps.Serialization.VisualSerializer::AppendPoint(class [mscorlib]System.Text.StringBuilder builder, valuetype [WindowsBase]System.Windows.Point p, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x37c0e  ldarg.0
0x37c0f  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x37c14  ldstr    aPoints// "Points"
0x37c19  ldloc.s  0xF
0x37c1b  callvirt instance string [mscorlib]System.Object::ToString()
0x37c20  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
  ... truncated ...
```
