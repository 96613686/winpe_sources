# System.Windows.Xps.Serialization.VisualSerializer::WriteGeometry

- ea: `0x38200`
- end: `0x382fc`
- name: `System.Windows.Xps.Serialization.VisualSerializer::WriteGeometry`
- size: `252`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x385c0`
- `0x38ca0`
- `0x39670`

## callees

- `0x27d0`
- `0x37870`
- `0x37d50`
- `0x38130`
- `0x38190`
- `0x381d0`
- `0x38200`
- `0x38390`
- `0x38e00`
- `0x38e70`

## string_xrefs

- `0x38260`: `PathGeometry`

## pseudocode

```c

```

## disassembly

```asm
0x38200  ldnull
0x38201  stloc.0
0x38202  ldnull
0x38203  stloc.1
0x38204  ldarg.3
0x38205  call     class [PresentationCore]System.Windows.Media.PathGeometry Microsoft.Internal.AlphaFlattener.Utility::GetAsPathGeometry(class [PresentationCore]System.Windows.Media.Geometry geo)
0x3820a  stloc.0
0x3820b  ldloc.0
0x3820c  ldarg.s  6
0x3820e  ldarg.s  7
0x38210  call     bool System.Windows.Xps.Serialization.VisualSerializer::IsPathGeometryEmpty(class [PresentationCore]System.Windows.Media.PathGeometry pg, bool forFill, bool forStroke)
0x38215  brfalse.s loc_38219
0x38217  ldc.i4.0
0x38218  ret
0x38219  ldarg.2
0x3821a  brfalse.s loc_3825A
0x3821c  ldarg.s  5
0x3821e  brtrue.s loc_38243
0x38220  ldloc.0
0x38221  brfalse.s loc_38243
0x38223  ldarg.0
0x38224  ldloc.0
0x38225  ldarg.s  4
0x38227  ldarg.s  6
0x38229  ldarg.s  7
0x3822b  call     instance string System.Windows.Xps.Serialization.VisualSerializer::PathGeometryToString(class [PresentationCore]System.Windows.Media.PathGeometry path, valuetype [WindowsBase]System.Windows.Media.Matrix map, bool forFill, bool forStroke)
0x38230  stloc.1
0x38231  ldloc.1
0x38232  brfalse.s loc_38243
0x38234  ldarg.0
0x38235  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x3823a  ldarg.2
0x3823b  ldloc.1
0x3823c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x38241  ldc.i4.0
0x38242  ret
0x38243  ldarg.0
0x38244  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x38249  ldarg.1
0x3824a  ldstr    asc_422A4// "."
0x3824f  ldarg.2
0x38250  call     string [mscorlib]System.String::Concat(string, string, string)
0x38255  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3825a  ldarg.0
0x3825b  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x38260  ldstr    aPathgeometry// "PathGeometry"
0x38265  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3826a  ldloc.0
0x3826b  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Geometry::get_Transform()
0x38270  ldarg.s  4
0x38272  call     class [PresentationCore]System.Windows.Media.Transform System.Windows.Xps.Serialization.VisualSerializer::Append(class [PresentationCore]System.Windows.Media.Transform trans, valuetype [WindowsBase]System.Windows.Media.Matrix mat)
0x38277  stloc.2
0x38278  ldarg.0
0x38279  ldloc.0
0x3827a  callvirt instance valuetype [PresentationCore]System.Windows.Media.FillRule [PresentationCore]System.Windows.Media.PathGeometry::get_FillRule()
0x3827f  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteFillRule(valuetype [PresentationCore]System.Windows.Media.FillRule rule)
0x38284  ldarg.0
0x38285  ldloc.0
0x38286  ldloc.2
0x38287  callvirt instance valuetype [WindowsBase]System.Windows.Media.Matrix [PresentationCore]System.Windows.Media.Transform::get_Value()
0x3828c  ldarg.s  6
0x3828e  ldarg.s  7
0x38290  call     instance string System.Windows.Xps.Serialization.VisualSerializer::PathGeometryToString(class [PresentationCore]System.Windows.Media.PathGeometry path, valuetype [WindowsBase]System.Windows.Media.Matrix map, bool forFill, bool forStroke)
0x38295  stloc.1
0x38296  ldloc.1
0x38297  brfalse.s loc_382B2
0x38299  ldarg.0
0x3829a  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x3829f  ldstr    aFigures// "Figures"
0x382a4  ldloc.1
0x382a5  ldc.i4.3
0x382a6  callvirt instance string [mscorlib]System.String::Substring(int32)
0x382ab  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x382b0  br.s     loc_382E1
0x382b2  ldarg.0
0x382b3  ldloc.2
0x382b4  call     instance void System.Windows.Xps.Serialization.VisualSerializer::PushCoordinateScope(class [PresentationCore]System.Windows.Media.Transform transform)
0x382b9  ldarg.0
0x382ba  ldstr    aTransform// "Transform"
0x382bf  ldloc.2
0x382c0  ldnull
0x382c1  call     valuetype [WindowsBase]System.Windows.Rect [WindowsBase]System.Windows.Rect::get_Empty()
0x382c6  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteTransform(string attribute, class [PresentationCore]System.Windows.Media.Transform trans, class [PresentationCore]System.Windows.Media.Transform relative, valuetype [WindowsBase]System.Windows.Rect bounds)
0x382cb  ldarg.0
0x382cc  ldloc.0
0x382cd  callvirt instance class [PresentationCore]System.Windows.Media.PathFigureCollection [PresentationCore]System.Windows.Media.PathGeometry::get_Figures()
0x382d2  ldarg.s  6
0x382d4  ldarg.s  7
0x382d6  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WritePathFigureCollection(class [PresentationCore]System.Windows.Media.PathFigureCollection figures, bool forFill, bool forStroke)
0x382db  ldarg.0
0x382dc  call     instance void System.Windows.Xps.Serialization.VisualSerializer::PopCoordinateScope()
0x382e1  ldarg.0
0x382e2  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x382e7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x382ec  ldarg.2
0x382ed  brfalse.s loc_382FA
0x382ef  ldarg.0
0x382f0  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x382f5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x382fa  ldc.i4.1
0x382fb  ret
```
