# System.Windows.Xps.Serialization.VisualSerializer::BrushToString

- ea: `0x37110`
- end: `0x3750f`
- name: `System.Windows.Xps.Serialization.VisualSerializer::BrushToString`
- size: `1023`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x36840`

## callees

- `0x24b0`
- `0x25c0`
- `0x3a40`
- `0x36950`
- `0x36a20`
- `0x36b30`
- `0x36b80`
- `0x36e90`
- `0x36f00`
- `0x36f60`
- `0x36fb0`
- `0x37110`
- `0x38130`
- `0x38160`
- `0x39000`
- `0x393a0`
- `0x3a590`

## string_xrefs

- `0x37220`: `SpreadMethod`
- `0x372ad`: `SpreadMethod`

## pseudocode

```c

```

## disassembly

```asm
0x37110  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37115  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x3711a  stloc.0
0x3711b  ldloc.0
0x3711c  newobj   instance void [System.Xml]System.Xml.XmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x37121  stloc.1
0x37122  ldloc.1
0x37123  ldc.i4.1
0x37124  callvirt instance void [System.Xml]System.Xml.XmlTextWriter::set_Formatting(valuetype [System.Xml]System.Xml.Formatting)
0x37129  ldloc.1
0x3712a  ldc.i4.4
0x3712b  callvirt instance void [System.Xml]System.Xml.XmlTextWriter::set_Indentation(int32)
0x37130  ldarg.0
0x37131  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x37136  stloc.2
0x37137  ldarg.0
0x37138  ldloc.1
0x37139  stfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x3713e  ldarg.1
0x3713f  isinst   [PresentationCore]System.Windows.Media.SolidColorBrush
0x37144  stloc.3
0x37145  ldloc.3
0x37146  brfalse.s loc_3716F
0x37148  ldarg.0
0x37149  ldstr    aSolidcolorbrus// "SolidColorBrush"
0x3714e  ldloc.3
0x3714f  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteBrushHeader(string element, class [PresentationCore]System.Windows.Media.Brush brush)
0x37154  ldarg.0
0x37155  ldstr    aColor// "Color"
0x3715a  ldloc.3
0x3715b  callvirt instance valuetype [PresentationCore]System.Windows.Media.Color [PresentationCore]System.Windows.Media.SolidColorBrush::get_Color()
0x37160  box      [PresentationCore]System.Windows.Media.Color
0x37165  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x3716a  br       loc_374EB
0x3716f  ldarg.1
0x37170  isinst   [PresentationCore]System.Windows.Media.LinearGradientBrush
0x37175  stloc.s  4
0x37177  ldloc.s  4
0x37179  brfalse  loc_3724D
0x3717e  ldarg.0
0x3717f  ldstr    aLineargradient// "LinearGradientBrush"
0x37184  ldloc.s  4
0x37186  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteBrushHeader(string element, class [PresentationCore]System.Windows.Media.Brush brush)
0x3718b  ldarg.0
0x3718c  ldstr    aTransform// "Transform"
0x37191  ldloc.s  4
0x37193  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Brush::get_Transform()
0x37198  ldloc.s  4
0x3719a  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Brush::get_RelativeTransform()
0x3719f  ldarg.2
0x371a0  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteTransform(string attribute, class [PresentationCore]System.Windows.Media.Transform trans, class [PresentationCore]System.Windows.Media.Transform relative, valuetype [WindowsBase]System.Windows.Rect bounds)
0x371a5  ldloc.s  4
0x371a7  callvirt instance valuetype [PresentationCore]System.Windows.Media.BrushMappingMode [PresentationCore]System.Windows.Media.GradientBrush::get_MappingMode()
0x371ac  stloc.s  9
0x371ae  ldloc.s  9
0x371b0  brtrue.s loc_371B9
0x371b2  ldsfld   valuetype [WindowsBase]System.Windows.Rect System.Windows.Xps.Serialization.VisualSerializer::UnitRect
0x371b7  starg.s  2
0x371b9  ldc.i4.0
0x371ba  stloc.s  9
0x371bc  ldarg.0
0x371bd  ldstr    aStartpoint// "StartPoint"
0x371c2  ldarg.2
0x371c3  ldloc.s  4
0x371c5  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.LinearGradientBrush::get_StartPoint()
0x371ca  call     valuetype [WindowsBase]System.Windows.Point Microsoft.Internal.AlphaFlattener.Utility::MapPoint(valuetype [WindowsBase]System.Windows.Rect bounds, valuetype [WindowsBase]System.Windows.Point p)
0x371cf  box      [WindowsBase]System.Windows.Point
0x371d4  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x371d9  ldarg.0
0x371da  ldstr    aEndpoint// "EndPoint"
0x371df  ldarg.2
0x371e0  ldloc.s  4
0x371e2  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.LinearGradientBrush::get_EndPoint()
0x371e7  call     valuetype [WindowsBase]System.Windows.Point Microsoft.Internal.AlphaFlattener.Utility::MapPoint(valuetype [WindowsBase]System.Windows.Rect bounds, valuetype [WindowsBase]System.Windows.Point p)
0x371ec  box      [WindowsBase]System.Windows.Point
0x371f1  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x371f6  ldarg.0
0x371f7  ldstr    aColorinterpola// "ColorInterpolationMode"
0x371fc  ldloc.s  4
0x371fe  callvirt instance valuetype [PresentationCore]System.Windows.Media.ColorInterpolationMode [PresentationCore]System.Windows.Media.GradientBrush::get_ColorInterpolationMode()
0x37203  box      [PresentationCore]System.Windows.Media.ColorInterpolationMode
0x37208  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x3720d  ldarg.0
0x3720e  ldstr    aMappingmode// "MappingMode"
0x37213  ldloc.s  9
0x37215  box      [PresentationCore]System.Windows.Media.BrushMappingMode
0x3721a  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x3721f  ldarg.0
0x37220  ldstr    aSpreadmethod// "SpreadMethod"
0x37225  ldloc.s  4
0x37227  callvirt instance valuetype [PresentationCore]System.Windows.Media.GradientSpreadMethod [PresentationCore]System.Windows.Media.GradientBrush::get_SpreadMethod()
0x3722c  box      [PresentationCore]System.Windows.Media.GradientSpreadMethod
0x37231  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x37236  ldarg.0
0x37237  ldstr    aLineargradient// "LinearGradientBrush"
0x3723c  ldloc.s  4
0x3723e  callvirt instance class [PresentationCore]System.Windows.Media.GradientStopCollection [PresentationCore]System.Windows.Media.GradientBrush::get_GradientStops()
0x37243  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteGradientStops(string prefix, class [PresentationCore]System.Windows.Media.GradientStopCollection gsc)
0x37248  br       loc_374EB
0x3724d  ldarg.1
0x3724e  isinst   [PresentationCore]System.Windows.Media.RadialGradientBrush
0x37253  stloc.s  5
0x37255  ldloc.s  5
0x37257  brfalse  loc_37373
0x3725c  ldarg.0
0x3725d  ldstr    aRadialgradient// "RadialGradientBrush"
0x37262  ldloc.s  5
0x37264  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteBrushHeader(string element, class [PresentationCore]System.Windows.Media.Brush brush)
0x37269  ldarg.0
0x3726a  ldstr    aTransform// "Transform"
0x3726f  ldloc.s  5
0x37271  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Brush::get_Transform()
0x37276  ldloc.s  5
0x37278  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Brush::get_RelativeTransform()
0x3727d  ldarg.2
0x3727e  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteTransform(string attribute, class [PresentationCore]System.Windows.Media.Transform trans, class [PresentationCore]System.Windows.Media.Transform relative, valuetype [WindowsBase]System.Windows.Rect bounds)
0x37283  ldloc.s  5
0x37285  callvirt instance valuetype [PresentationCore]System.Windows.Media.BrushMappingMode [PresentationCore]System.Windows.Media.GradientBrush::get_MappingMode()
0x3728a  stloc.s  0xA
0x3728c  ldloc.s  0xA
0x3728e  brtrue.s loc_37297
0x37290  ldsfld   valuetype [WindowsBase]System.Windows.Rect System.Windows.Xps.Serialization.VisualSerializer::UnitRect
0x37295  starg.s  2
0x37297  ldc.i4.0
0x37298  stloc.s  0xA
0x3729a  ldarg.0
0x3729b  ldstr    aMappingmode// "MappingMode"
0x372a0  ldloc.s  0xA
0x372a2  box      [PresentationCore]System.Windows.Media.BrushMappingMode
0x372a7  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x372ac  ldarg.0
0x372ad  ldstr    aSpreadmethod// "SpreadMethod"
0x372b2  ldloc.s  5
0x372b4  callvirt instance valuetype [PresentationCore]System.Windows.Media.GradientSpreadMethod [PresentationCore]System.Windows.Media.GradientBrush::get_SpreadMethod()
0x372b9  box      [PresentationCore]System.Windows.Media.GradientSpreadMethod
0x372be  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x372c3  ldarg.0
0x372c4  ldstr    aColorinterpola// "ColorInterpolationMode"
0x372c9  ldloc.s  5
0x372cb  callvirt instance valuetype [PresentationCore]System.Windows.Media.ColorInterpolationMode [PresentationCore]System.Windows.Media.GradientBrush::get_ColorInterpolationMode()
0x372d0  box      [PresentationCore]System.Windows.Media.ColorInterpolationMode
0x372d5  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x372da  ldarg.0
0x372db  ldstr    aCenter// "Center"
0x372e0  ldarg.2
0x372e1  ldloc.s  5
0x372e3  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.RadialGradientBrush::get_Center()
0x372e8  call     valuetype [WindowsBase]System.Windows.Point Microsoft.Internal.AlphaFlattener.Utility::MapPoint(valuetype [WindowsBase]System.Windows.Rect bounds, valuetype [WindowsBase]System.Windows.Point p)
0x372ed  box      [WindowsBase]System.Windows.Point
0x372f2  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x372f7  ldarg.0
0x372f8  ldstr    aRadiusx// "RadiusX"
0x372fd  ldloc.s  5
0x372ff  callvirt instance float64 [PresentationCore]System.Windows.Media.RadialGradientBrush::get_RadiusX()
0x37304  ldarga.s 2
0x37306  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0x3730b  mul
0x3730c  call     float64 [mscorlib]System.Math::Abs(float64)
0x37311  box      [mscorlib]System.Double
0x37316  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x3731b  ldarg.0
0x3731c  ldstr    aRadiusy// "RadiusY"
0x37321  ldloc.s  5
0x37323  callvirt instance float64 [PresentationCore]System.Windows.Media.RadialGradientBrush::get_RadiusY()
0x37328  ldarga.s 2
0x3732a  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0x3732f  mul
0x37330  call     float64 [mscorlib]System.Math::Abs(float64)
0x37335  box      [mscorlib]System.Double
0x3733a  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x3733f  ldarg.0
0x37340  ldstr    aGradientorigin// "GradientOrigin"
0x37345  ldarg.2
0x37346  ldloc.s  5
0x37348  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.RadialGradientBrush::get_GradientOrigin()
0x3734d  call     valuetype [WindowsBase]System.Windows.Point Microsoft.Internal.AlphaFlattener.Utility::MapPoint(valuetype [WindowsBase]System.Windows.Rect bounds, valuetype [WindowsBase]System.Windows.Point p)
0x37352  box      [WindowsBase]System.Windows.Point
0x37357  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x3735c  ldarg.0
0x3735d  ldstr    aRadialgradient// "RadialGradientBrush"
0x37362  ldloc.s  5
0x37364  callvirt instance class [PresentationCore]System.Windows.Media.GradientStopCollection [PresentationCore]System.Windows.Media.GradientBrush::get_GradientStops()
0x37369  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteGradientStops(string prefix, class [PresentationCore]System.Windows.Media.GradientStopCollection gsc)
0x3736e  br       loc_374EB
0x37373  ldarg.1
0x37374  isinst   [PresentationCore]System.Windows.Media.ImageBrush
0x37379  stloc.s  6
0x3737b  ldloc.s  6
0x3737d  brfalse.s loc_373BE
0x3737f  ldarg.0
0x37380  ldstr    aImagebrush// "ImageBrush"
0x37385  ldloc.s  6
0x37387  ldarg.2
0x37388  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteTileBrush(string element, class [PresentationCore]System.Windows.Media.TileBrush brush, valuetype [WindowsBase]System.Windows.Rect bounds)
0x3738d  ldarg.0
0x3738e  ldstr    aImagesource// "ImageSource"
0x37393  ldloc.s  6
0x37395  callvirt instance class [PresentationCore]System.Windows.Media.ImageSource [PresentationCore]System.Windows.Media.ImageBrush::get_ImageSource()
0x3739a  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteBitmap(string attribute, class [PresentationCore]System.Windows.Media.ImageSource imageSource)
0x3739f  ldarg.0
0x373a0  ldstr    aTransform// "Transform"
0x373a5  ldloc.s  6
0x373a7  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Brush::get_Transform()
0x373ac  ldloc.s  6
0x373ae  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Brush::get_RelativeTransform()
0x373b3  ldarg.2
0x373b4  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteTransform(string attribute, class [PresentationCore]System.Windows.Media.Transform trans, class [PresentationCore]System.Windows.Media.Transform relative, valuetype [WindowsBase]System.Windows.Rect bounds)
0x373b9  br       loc_374EB
0x373be  ldarg.1
0x373bf  isinst   [PresentationCore]System.Windows.Media.DrawingBrush
0x373c4  stloc.s  7
0x373c6  ldloc.s  7
0x373c8  brfalse.s loc_3743D
0x373ca  ldarg.0
0x373cb  ldstr    aVisualbrush// "VisualBrush"
0x373d0  ldloc.s  7
0x373d2  ldarg.2
0x373d3  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteTileBrush(string element, class [PresentationCore]System.Windows.Media.TileBrush brush, valuetype [WindowsBase]System.Windows.Rect bounds)
0x373d8  ldloc.s  7
0x373da  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Brush::get_Transform()
0x373df  ldloc.s  7
0x373e1  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Brush::get_RelativeTransform()
0x373e6  ldarg.2
0x373e7  call     valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.AlphaFlattener.Utility::MergeTransform(class [PresentationCore]System.Windows.Media.Transform trans, class [PresentationCore]System.Windows.Media.Transform relative, valuetype [WindowsBase]System.Windows.Rect bounds)
0x373ec  stloc.s  0xB
0x373ee  ldarg.0
0x373ef  ldstr    aTransform// "Transform"
0x373f4  ldloc.s  0xB
0x373f6  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteTransform(string attribute, valuetype [WindowsBase]System.Windows.Media.Matrix trans)
0x373fb  ldloc.s  7
0x373fd  ldarg.2
0x373fe  call     valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.AlphaFlattener.Utility::CreateViewboxToViewportTransform(class [PresentationCore]System.Windows.Media.TileBrush brush, valuetype [WindowsBase]System.Windows.Rect bounds)
0x37403  stloc.s  0xC
0x37405  ldloca.s 0xC
0x37407  ldloc.s  0xB
0x37409  call     instance void [WindowsBase]System.Windows.Media.Matrix::Append(valuetype [WindowsBase]System.Windows.Media.Matrix)
0x3740e  ldarg.0
0x3740f  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x37414  ldstr    aVisualbrushVis// "VisualBrush.Visual"
0x37419  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3741e  ldarg.0
0x3741f  ldloc.s  7
0x37421  callvirt instance class [PresentationCore]System.Windows.Media.Drawing [PresentationCore]System.Windows.Media.DrawingBrush::get_Drawing()
0x37426  ldloc.s  0xC
0x37428  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteDrawingBody(class [PresentationCore]System.Windows.Media.Drawing drawing, valuetype [WindowsBase]System.Windows.Media.Matrix worldTransform)
0x3742d  ldarg.0
0x3742e  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x37433  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x37438  br       loc_374EB
0x3743d  ldarg.1
0x3743e  isinst   [PresentationCore]System.Windows.Media.VisualBrush
0x37443  stloc.s  8
0x37445  ldloc.s  8
0x37447  brfalse  loc_374D9
0x3744c  ldarg.0
0x3744d  call     instance void System.Windows.Xps.Serialization.VisualSerializer::SaveResetState()
0x37452  ldarg.0
0x37453  ldstr    aVisualbrush// "VisualBrush"
0x37458  ldloc.s  8
0x3745a  ldarg.2
0x3745b  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteTileBrush(string element, class [PresentationCore]System.Windows.Media.TileBrush brush, valuetype [WindowsBase]System.Windows.Rect bounds)
0x37460  ldarg.0
0x37461  ldstr    aTransform// "Transform"
0x37466  ldloc.s  8
0x37468  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Brush::get_Transform()
0x3746d  ldloc.s  8
0x3746f  callvirt instance class [PresentationCore]System.Windows.Media.Transform [PresentationCore]System.Windows.Media.Brush::get_RelativeTransform()
0x37474  ldarg.2
0x37475  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteTransform(string attribute, class [PresentationCore]System.Windows.Media.Transform trans, class [PresentationCore]System.Windows.Media.Transform relative, valuetype [WindowsBase]System.Windows.Rect bounds)
0x3747a  ldarg.0
0x3747b  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x37480  ldstr    aVisualbrushVis// "VisualBrush.Visual"
0x37485  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3748a  ldarg.0
0x3748b  ldarg.0
0x3748c  ldfld    valuetype [WindowsBase]System.Windows.Size System.Windows.Xps.Serialization.VisualSerializer::_pageSize
0x37491  newobj   instance void System.Windows.Xps.Serialization.TreeWalkProgress::.ctor()
0x37496  newobj   instance void System.Windows.Xps.Serialization.VisualTreeFlattener::.ctor(class System.Windows.Xps.Serialization.IMetroDrawingContext dc, valuetype [WindowsBase]System.Windows.Size pageSize, class System.Windows.Xps.Serialization.TreeWalkProgress treeWalkProgress)
0x3749b  stloc.s  0xD
0x3749d  ldarg.0
0x3749e  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x374a3  ldstr    aCanvas// "Canvas"
0x374a8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x374ad  ldloc.s  0xD
0x374af  ldloc.s  8
0x374b1  callvirt instance class [PresentationCore]System.Windows.Media.Visual [PresentationCore]System.Windows.Media.VisualBrush::get_Visual()
0x374b6  callvirt instance void System.Windows.Xps.Serialization.VisualTreeFlattener::VisualWalk(class [PresentationCore]System.Windows.Media.Visual visual)
0x374bb  ldarg.0
0x374bc  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x374c1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x374c6  ldarg.0
0x374c7  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x374cc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x374d1  ldarg.0
0x374d2  call     instance void System.Windows.Xps.Serialization.VisualSerializer::RestoreState()
0x374d7  br.s     loc_374EB
0x374d9  ldarg.0
0x374da  ldarg.1
0x374db  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x374e0  callvirt instance string [mscorlib]System.Object::ToString()
  ... truncated ...
```
