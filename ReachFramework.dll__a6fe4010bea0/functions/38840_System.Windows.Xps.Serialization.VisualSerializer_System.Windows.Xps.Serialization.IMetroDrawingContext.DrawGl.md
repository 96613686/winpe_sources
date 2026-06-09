# System.Windows.Xps.Serialization.VisualSerializer::System.Windows.Xps.Serialization.IMetroDrawingContext.DrawGlyphRun

- ea: `0x38840`
- end: `0x38be7`
- name: `System.Windows.Xps.Serialization.VisualSerializer::System.Windows.Xps.Serialization.IMetroDrawingContext.DrawGlyphRun`
- size: `935`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x3a60`
- `0x1fe80`
- `0x1feb0`
- `0x30590`
- `0x306b0`
- `0x365c0`
- `0x36950`
- `0x36970`
- `0x37510`
- `0x37d00`
- `0x381b0`
- `0x38400`
- `0x384c0`
- `0x384e0`
- `0x38580`
- `0x38710`
- `0x38790`
- `0x38800`
- `0x38840`
- `0x38ca0`

## string_xrefs

- `0x38948`: `FontRenderingEmSize`
- `0x389ae`: `FontUri`
- `0x38a18`: `IsSideways`

## pseudocode

```c

```

## disassembly

```asm
0x38840  ldarg.2
0x38841  brtrue.s loc_38844
0x38843  ret
0x38844  ldarg.0
0x38845  call     instance bool System.Windows.Xps.Serialization.VisualSerializer::PreserveTransparent()
0x3884a  brfalse.s loc_38858
0x3884c  ldarg.1
0x3884d  brtrue.s loc_38862
0x3884f  call     class [PresentationCore]System.Windows.Media.SolidColorBrush [PresentationCore]System.Windows.Media.Brushes::get_Transparent()
0x38854  starg.s  1
0x38856  br.s     loc_38862
0x38858  ldarg.1
0x38859  ldnull
0x3885a  call     bool System.Windows.Xps.Serialization.VisualSerializer::Visible(class [PresentationCore]System.Windows.Media.Brush brush, class [PresentationCore]System.Windows.Media.Pen pen)
0x3885f  brtrue.s loc_38862
0x38861  ret
0x38862  ldarg.2
0x38863  callvirt instance class [PresentationCore]System.Windows.Media.GlyphTypeface [PresentationCore]System.Windows.Media.GlyphRun::get_GlyphTypeface()
0x38868  call     bool System.Windows.Xps.Serialization.VisualSerializer::EmbeddingAllowed(class [PresentationCore]System.Windows.Media.GlyphTypeface typeface)
0x3886d  brtrue.s loc_38878
0x3886f  ldarg.0
0x38870  ldarg.1
0x38871  ldarg.2
0x38872  call     instance void System.Windows.Xps.Serialization.VisualSerializer::DrawGlyphRunAsImage(class [PresentationCore]System.Windows.Media.Brush foreground, class [PresentationCore]System.Windows.Media.GlyphRun glyphRun)
0x38877  ret
0x38878  ldarg.0
0x38879  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x3887e  ldstr    aGlyphs// "Glyphs"
0x38883  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x38888  ldc.r8   0.0
0x38891  stloc.0
0x38892  ldc.r8   0.0
0x3889b  stloc.1
0x3889c  ldarg.0
0x3889d  ldfld    class [PresentationCore]System.Windows.Media.Transform System.Windows.Xps.Serialization.VisualSerializer::_transform
0x388a2  stloc.2
0x388a3  call     valuetype [WindowsBase]System.Windows.Media.Matrix [WindowsBase]System.Windows.Media.Matrix::get_Identity()
0x388a8  stloc.3
0x388a9  ldarg.1
0x388aa  isinst   [PresentationCore]System.Windows.Media.SolidColorBrush
0x388af  brfalse.s loc_388FE
0x388b1  ldarg.0
0x388b2  ldfld    class [PresentationCore]System.Windows.Media.Brush System.Windows.Xps.Serialization.VisualSerializer::_opacityMask
0x388b7  brtrue.s loc_388FE
0x388b9  ldarg.0
0x388ba  ldfld    class [PresentationCore]System.Windows.Media.Transform System.Windows.Xps.Serialization.VisualSerializer::_transform
0x388bf  ldloca.s 0
0x388c1  ldloca.s 1
0x388c3  call     class [PresentationCore]System.Windows.Media.Transform System.Windows.Xps.Serialization.VisualSerializer::ExtractTranslation(class [PresentationCore]System.Windows.Media.Transform trans, [out] float64& dx, [out] float64& dy)
0x388c8  stloc.2
0x388c9  ldarg.0
0x388ca  ldfld    class [PresentationCore]System.Windows.Media.Geometry System.Windows.Xps.Serialization.VisualSerializer::_clip
0x388cf  brfalse.s loc_388FE
0x388d1  ldloca.s 3
0x388d3  ldc.r8   1.0
0x388dc  ldc.r8   0.0
0x388e5  ldc.r8   0.0
0x388ee  ldc.r8   1.0
0x388f7  ldloc.0
0x388f8  ldloc.1
0x388f9  call     instance void [WindowsBase]System.Windows.Media.Matrix::.ctor(float64, float64, float64, float64, float64, float64)
0x388fe  ldarg.0
0x388ff  ldc.i4.0
0x38900  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteCommonAttrs(bool bWriteAutomation)
0x38905  ldarg.0
0x38906  ldstr    aOriginx// "OriginX"
0x3890b  ldarg.2
0x3890c  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.GlyphRun::get_BaselineOrigin()
0x38911  stloc.s  0xD
0x38913  ldloca.s 0xD
0x38915  call     instance float64 [WindowsBase]System.Windows.Point::get_X()
0x3891a  ldloc.0
0x3891b  add
0x3891c  box      [mscorlib]System.Double
0x38921  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x38926  ldarg.0
0x38927  ldstr    aOriginy// "OriginY"
0x3892c  ldarg.2
0x3892d  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.GlyphRun::get_BaselineOrigin()
0x38932  stloc.s  0xD
0x38934  ldloca.s 0xD
0x38936  call     instance float64 [WindowsBase]System.Windows.Point::get_Y()
0x3893b  ldloc.1
0x3893c  add
0x3893d  box      [mscorlib]System.Double
0x38942  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x38947  ldarg.0
0x38948  ldstr    aFontrenderinge// "FontRenderingEmSize"
0x3894d  ldarg.2
0x3894e  callvirt instance float64 [PresentationCore]System.Windows.Media.GlyphRun::get_FontRenderingEmSize()
0x38953  box      [mscorlib]System.Double
0x38958  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x3895d  ldarg.2
0x3895e  callvirt instance class [PresentationCore]System.Windows.Media.GlyphTypeface [PresentationCore]System.Windows.Media.GlyphRun::get_GlyphTypeface()
0x38963  call     class [System]System.Uri Microsoft.Internal.AlphaFlattener.Utility::GetFontUri(class [PresentationCore]System.Windows.Media.GlyphTypeface typeface)
0x38968  stloc.s  4
0x3896a  ldarg.0
0x3896b  ldfld    class System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.Serialization.VisualSerializer::_manager
0x38970  brfalse.s loc_389AD
0x38972  ldarg.0
0x38973  ldfld    class System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.Serialization.VisualSerializer::_manager
0x38978  ldtoken  [PresentationCore]System.Windows.Media.GlyphRun
0x3897d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x38982  callvirt instance class [System]System.ComponentModel.TypeConverter System.Windows.Xps.Serialization.PackageSerializationManager::GetTypeConverter(class [mscorlib]System.Type serializedObjectType)
0x38987  stloc.s  0xE
0x38989  ldloc.s  0xE
0x3898b  brfalse.s loc_389AD
0x3898d  ldloc.s  0xE
0x3898f  ldarg.0
0x38990  ldfld    class System.Windows.Xps.Serialization.XpsTokenContext System.Windows.Xps.Serialization.VisualSerializer::_context
0x38995  ldnull
0x38996  ldarg.2
0x38997  ldtoken  [System]System.Uri
0x3899c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x389a1  callvirt instance object [System]System.ComponentModel.TypeConverter::ConvertTo(class [System]System.ComponentModel.ITypeDescriptorContext, class [mscorlib]System.Globalization.CultureInfo, object, class [mscorlib]System.Type)
0x389a6  isinst   [System]System.Uri
0x389ab  stloc.s  4
0x389ad  ldarg.0
0x389ae  ldstr    aFonturi// "FontUri"
0x389b3  ldloc.s  4
0x389b5  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x389ba  ldarg.0
0x389bb  ldstr    aStylesimulatio// "StyleSimulations"
0x389c0  ldarg.2
0x389c1  callvirt instance class [PresentationCore]System.Windows.Media.GlyphTypeface [PresentationCore]System.Windows.Media.GlyphRun::get_GlyphTypeface()
0x389c6  callvirt instance valuetype [PresentationCore]System.Windows.Media.StyleSimulations [PresentationCore]System.Windows.Media.GlyphTypeface::get_StyleSimulations()
0x389cb  box      [PresentationCore]System.Windows.Media.StyleSimulations
0x389d0  ldc.i4.0
0x389d1  box      [PresentationCore]System.Windows.Media.StyleSimulations
0x389d6  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val, object valDefault)
0x389db  ldarg.2
0x389dc  callvirt instance int32 [PresentationCore]System.Windows.Media.GlyphRun::get_BidiLevel()
0x389e1  stloc.s  5
0x389e3  ldloc.s  5
0x389e5  ldc.i4.s 0x3D
0x389e7  ble.s    loc_389EF
0x389e9  ldc.i4.s 0x3D
0x389eb  stloc.s  5
0x389ed  br.s     loc_389F7
0x389ef  ldloc.s  5
0x389f1  ldc.i4.0
0x389f2  bge.s    loc_389F7
0x389f4  ldc.i4.0
0x389f5  stloc.s  5
0x389f7  ldarg.0
0x389f8  ldstr    aBidilevel// "BidiLevel"
0x389fd  ldloc.s  5
0x389ff  box      [mscorlib]System.Int32
0x38a04  ldc.i4.0
0x38a05  box      [mscorlib]System.Int32
0x38a0a  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val, object valDefault)
0x38a0f  ldarg.2
0x38a10  callvirt instance bool [PresentationCore]System.Windows.Media.GlyphRun::get_IsSideways()
0x38a15  brfalse.s loc_38A28
0x38a17  ldarg.0
0x38a18  ldstr    aIssideways// "IsSideways"
0x38a1d  ldarg.2
0x38a1e  callvirt instance bool [PresentationCore]System.Windows.Media.GlyphRun::get_IsSideways()
0x38a23  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteBool(string attr, bool val)
0x38a28  ldarg.2
0x38a29  call     class [PresentationCore]System.Windows.Media.GlyphRun System.Windows.Xps.Serialization.VisualSerializer::FilterXmlInvalidChar(class [PresentationCore]System.Windows.Media.GlyphRun glyphRun)
0x38a2e  stloc.s  6
0x38a30  ldloc.s  6
0x38a32  newobj   instance void [PresentationCore]System.Windows.Media.GlyphsSerializer::.ctor(class [PresentationCore]System.Windows.Media.GlyphRun)
0x38a37  stloc.s  7
0x38a39  ldloc.s  7
0x38a3b  ldloca.s 8
0x38a3d  ldloca.s 9
0x38a3f  ldloca.s 0xA
0x38a41  callvirt instance void [PresentationCore]System.Windows.Media.GlyphsSerializer::ComputeContentStrings(string&, string&, string&)
0x38a46  ldc.i4.0
0x38a47  stloc.s  0xB
0x38a49  ldloc.s  8
0x38a4b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x38a50  brtrue.s loc_38A8F
0x38a52  ldloc.s  8
0x38a54  ldc.i4.0
0x38a55  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x38a5a  ldc.i4.s 0x7B
0x38a5c  bne.un.s loc_38A6C
0x38a5e  ldstr    asc_45E6C// "{}"
0x38a63  ldloc.s  8
0x38a65  call     string [mscorlib]System.String::Concat(string, string)
0x38a6a  stloc.s  8
0x38a6c  ldloc.s  6
0x38a6e  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<char> [PresentationCore]System.Windows.Media.GlyphRun::get_Characters()
0x38a73  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<char>::get_Count()
0x38a78  ldc.i4   0x1388
0x38a7d  ble.s    loc_38A82
0x38a7f  ldc.i4.1
0x38a80  stloc.s  0xB
0x38a82  ldarg.0
0x38a83  ldstr    aUnicodestring// "UnicodeString"
0x38a88  ldloc.s  8
0x38a8a  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x38a8f  ldloc.s  9
0x38a91  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x38a96  brtrue.s loc_38ABB
0x38a98  ldloc.s  6
0x38a9a  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<unsigned int16> [PresentationCore]System.Windows.Media.GlyphRun::get_GlyphIndices()
0x38a9f  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<unsigned int16>::get_Count()
0x38aa4  ldc.i4   0x1388
0x38aa9  ble.s    loc_38AAE
0x38aab  ldc.i4.1
0x38aac  stloc.s  0xB
0x38aae  ldarg.0
0x38aaf  ldstr    aIndices// "Indices"
0x38ab4  ldloc.s  9
0x38ab6  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x38abb  ldloc.s  0xA
0x38abd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x38ac2  brtrue.s loc_38AD1
0x38ac4  ldarg.0
0x38ac5  ldstr    aCaretstops// "CaretStops"
0x38aca  ldloc.s  0xA
0x38acc  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x38ad1  ldsfld   valuetype [WindowsBase]System.Windows.Rect System.Windows.Xps.Serialization.VisualSerializer::UnitRect
0x38ad6  stloc.s  0xC
0x38ad8  ldarg.0
0x38ad9  ldfld    class [PresentationCore]System.Windows.Media.Brush System.Windows.Xps.Serialization.VisualSerializer::_opacityMask
0x38ade  call     bool System.Windows.Xps.Serialization.VisualSerializer::NeedBounds(class [PresentationCore]System.Windows.Media.Brush b)
0x38ae3  brtrue.s loc_38AED
0x38ae5  ldarg.1
0x38ae6  call     bool System.Windows.Xps.Serialization.VisualSerializer::NeedBounds(class [PresentationCore]System.Windows.Media.Brush b)
0x38aeb  brfalse.s loc_38B33
0x38aed  ldarg.2
0x38aee  callvirt instance valuetype [WindowsBase]System.Windows.Rect [PresentationCore]System.Windows.Media.GlyphRun::ComputeInkBoundingBox()
0x38af3  stloc.s  0xC
0x38af5  ldloca.s 0xC
0x38af7  dup
0x38af8  call     instance float64 [WindowsBase]System.Windows.Rect::get_X()
0x38afd  ldarg.2
0x38afe  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.GlyphRun::get_BaselineOrigin()
0x38b03  stloc.s  0xD
0x38b05  ldloca.s 0xD
0x38b07  call     instance float64 [WindowsBase]System.Windows.Point::get_X()
0x38b0c  ldloc.0
0x38b0d  add
0x38b0e  add
0x38b0f  call     instance void [WindowsBase]System.Windows.Rect::set_X(float64)
0x38b14  ldloca.s 0xC
0x38b16  dup
0x38b17  call     instance float64 [WindowsBase]System.Windows.Rect::get_Y()
0x38b1c  ldarg.2
0x38b1d  callvirt instance valuetype [WindowsBase]System.Windows.Point [PresentationCore]System.Windows.Media.GlyphRun::get_BaselineOrigin()
0x38b22  stloc.s  0xD
0x38b24  ldloca.s 0xD
0x38b26  call     instance float64 [WindowsBase]System.Windows.Point::get_Y()
0x38b2b  ldloc.1
0x38b2c  add
0x38b2d  add
0x38b2e  call     instance void [WindowsBase]System.Windows.Rect::set_Y(float64)
0x38b33  ldarg.0
0x38b34  ldstr    aFill// "Fill"
0x38b39  ldarg.1
0x38b3a  ldloc.s  0xC
0x38b3c  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteBrush(string attribute, class [PresentationCore]System.Windows.Media.Brush brush, valuetype [WindowsBase]System.Windows.Rect bounds)
0x38b41  ldarg.2
0x38b42  callvirt instance class [PresentationCore]System.Windows.Markup.XmlLanguage [PresentationCore]System.Windows.Media.GlyphRun::get_Language()
0x38b47  brfalse.s loc_38B91
0x38b49  ldarg.2
0x38b4a  callvirt instance class [PresentationCore]System.Windows.Markup.XmlLanguage [PresentationCore]System.Windows.Media.GlyphRun::get_Language()
0x38b4f  ldarg.0
0x38b50  ldfld    class System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.Serialization.VisualSerializer::_manager
0x38b55  callvirt instance class [PresentationCore]System.Windows.Markup.XmlLanguage System.Windows.Xps.Serialization.PackageSerializationManager::get_Language()
0x38b5a  beq.s    loc_38B91
0x38b5c  ldarg.2
0x38b5d  callvirt instance class [PresentationCore]System.Windows.Markup.XmlLanguage [PresentationCore]System.Windows.Media.GlyphRun::get_Language()
0x38b62  call     class [PresentationCore]System.Windows.Markup.XmlLanguage [PresentationCore]System.Windows.Markup.XmlLanguage::get_Empty()
0x38b67  bne.un.s loc_38B7B
0x38b69  ldarg.0
0x38b6a  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_XmlLang()
0x38b6f  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_XmlEngLangValue()
0x38b74  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x38b79  br.s     loc_38B91
0x38b7b  ldarg.0
0x38b7c  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_XmlLang()
0x38b81  ldarg.2
0x38b82  callvirt instance class [PresentationCore]System.Windows.Markup.XmlLanguage [PresentationCore]System.Windows.Media.GlyphRun::get_Language()
0x38b87  callvirt instance string [mscorlib]System.Object::ToString()
0x38b8c  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x38b91  ldarg.0
0x38b92  ldstr    aGlyphs// "Glyphs"
0x38b97  ldloc.2
0x38b98  ldarg.0
0x38b99  ldfld    class [PresentationCore]System.Windows.Media.Geometry System.Windows.Xps.Serialization.VisualSerializer::_clip
0x38b9e  ldloc.3
0x38b9f  ldarg.0
0x38ba0  ldfld    float64 System.Windows.Xps.Serialization.VisualSerializer::_opacity
0x38ba5  ldarg.0
0x38ba6  ldfld    class [PresentationCore]System.Windows.Media.Brush System.Windows.Xps.Serialization.VisualSerializer::_opacityMask
0x38bab  ldloc.s  0xC
0x38bad  call     instance bool System.Windows.Xps.Serialization.VisualSerializer::WriteTCO(string element, class [PresentationCore]System.Windows.Media.Transform transform, class [PresentationCore]System.Windows.Media.Geometry clip, valuetype [WindowsBase]System.Windows.Media.Matrix clipMat, float64 opacity, class [PresentationCore]System.Windows.Media.Brush opacityMask, valuetype [WindowsBase]System.Windows.Rect bounds)
0x38bb2  pop
0x38bb3  ldarg.0
0x38bb4  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x38bb9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x38bbe  ldloc.s  0xB
0x38bc0  brfalse.s loc_38BD2
0x38bc2  ldarg.0
  ... truncated ...
```
