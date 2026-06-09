# System.Windows.Documents.RtfToXamlReader::ProcessImage

- ea: `0xf6d10`
- end: `0xf7041`
- name: `System.Windows.Documents.RtfToXamlReader::ProcessImage`
- size: `817`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0xf5f30`

## callees

- `0xee4f0`
- `0xee530`
- `0xf05d0`
- `0xf0600`
- `0xf0610`
- `0xf0630`
- `0xf0650`
- `0xf0670`
- `0xf0690`
- `0xf06b0`
- `0xf06d0`
- `0xf2c30`
- `0xf4310`
- `0xf4430`
- `0xf48c0`
- `0xf4dc0`
- `0xf5db0`
- `0xf6d10`
- `0x12d110`

## string_xrefs

- `0xf6fab`: `UriSource="`
- `0xf6fce`: `CacheOption="OnLoad" `

## pseudocode

```c

```

## disassembly

```asm
0xf6d10  ldarg.1
0xf6d11  callvirt instance valuetype System.Windows.Documents.RtfImageFormat System.Windows.Documents.FormatState::get_ImageFormat()
0xf6d16  stloc.3
0xf6d17  ldloc.3
0xf6d18  ldc.i4.6
0xf6d19  sub
0xf6d1a  switch   loc_F6D39, loc_F6D31, loc_F6D41, loc_F6D31
0xf6d2f  br.s     loc_F6D41
0xf6d31  ldstr    aImagePng// "image/png"
0xf6d36  stloc.0
0xf6d37  br.s     loc_F6D47
0xf6d39  ldstr    aImageJpeg// "image/jpeg"
0xf6d3e  stloc.0
0xf6d3f  br.s     loc_F6D47
0xf6d41  ldsfld   string [mscorlib]System.String::Empty
0xf6d46  stloc.0
0xf6d47  ldarg.1
0xf6d48  callvirt instance float64 System.Windows.Documents.FormatState::get_ImageScaleWidth()
0xf6d4d  ldc.r8   0.0
0xf6d56  blt.s    loc_F6D6B
0xf6d58  ldarg.1
0xf6d59  callvirt instance float64 System.Windows.Documents.FormatState::get_ImageScaleHeight()
0xf6d5e  ldc.r8   0.0
0xf6d67  clt
0xf6d69  br.s     loc_F6D6C
0xf6d6b  ldc.i4.1
0xf6d6c  stloc.2
0xf6d6d  ldarg.0
0xf6d6e  ldfld    class System.Windows.Documents.WpfPayload System.Windows.Documents.RtfToXamlReader::_wpfPayload
0xf6d73  brfalse  loc_F7035
0xf6d78  ldloc.0
0xf6d79  ldsfld   string [mscorlib]System.String::Empty
0xf6d7e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xf6d83  brfalse  loc_F7035
0xf6d88  ldloc.2
0xf6d89  brtrue   loc_F7035
0xf6d8e  ldarg.0
0xf6d8f  ldfld    class System.Windows.Documents.WpfPayload System.Windows.Documents.RtfToXamlReader::_wpfPayload
0xf6d94  ldarg.0
0xf6d95  ldfld    int32 System.Windows.Documents.RtfToXamlReader::_imageCount
0xf6d9a  ldloc.0
0xf6d9b  ldloca.s 1
0xf6d9d  callvirt instance class [mscorlib]System.IO.Stream System.Windows.Documents.WpfPayload::CreateImageStream(int32 imageCount, string contentType, [out] string& imagePartUriString)
0xf6da2  stloc.s  4
0xf6da4  ldloc.s  4
0xf6da6  stloc.s  0xA
0xf6da8  ldarg.1
0xf6da9  callvirt instance valuetype System.Windows.Documents.RtfImageFormat System.Windows.Documents.FormatState::get_ImageFormat()
0xf6dae  ldc.i4.s 9
0xf6db0  beq.s    loc_F6DC7
0xf6db2  ldarg.0
0xf6db3  ldfld    class System.Windows.Documents.RtfToXamlLexer System.Windows.Documents.RtfToXamlReader::_lexer
0xf6db8  ldloc.s  4
0xf6dba  ldarg.1
0xf6dbb  callvirt instance bool System.Windows.Documents.FormatState::get_IsImageDataBinary()
0xf6dc0  callvirt instance void System.Windows.Documents.RtfToXamlLexer::WriteImageData(class [mscorlib]System.IO.Stream imageStream, bool isBinary)
0xf6dc5  leave.s  loc_F6E11
0xf6dc7  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0xf6dcc  stloc.s  0xB
0xf6dce  ldloc.s  0xB
0xf6dd0  stloc.s  0xC
0xf6dd2  ldarg.0
0xf6dd3  ldfld    class System.Windows.Documents.RtfToXamlLexer System.Windows.Documents.RtfToXamlReader::_lexer
0xf6dd8  ldloc.s  0xB
0xf6dda  ldarg.1
0xf6ddb  callvirt instance bool System.Windows.Documents.FormatState::get_IsImageDataBinary()
0xf6de0  callvirt instance void System.Windows.Documents.RtfToXamlLexer::WriteImageData(class [mscorlib]System.IO.Stream imageStream, bool isBinary)
0xf6de5  ldloc.s  0xB
0xf6de7  ldc.i4.0
0xf6de8  conv.i8
0xf6de9  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0xf6dee  ldloc.s  0xB
0xf6df0  ldloc.s  4
0xf6df2  call     void [PresentationCore]MS.Internal.SystemDrawingHelper::SaveMetafileToImageStream(class [mscorlib]System.IO.MemoryStream, class [mscorlib]System.IO.Stream)
0xf6df7  leave.s  loc_F6E11
0xf6df9  ldloc.s  0xC
0xf6dfb  brfalse.s loc_F6E04
0xf6dfd  ldloc.s  0xC
0xf6dff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf6e04  endfinally
0xf6e05  ldloc.s  0xA
0xf6e07  brfalse.s loc_F6E10
0xf6e09  ldloc.s  0xA
0xf6e0b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf6e10  endfinally
0xf6e11  ldarg.0
0xf6e12  ldarg.0
0xf6e13  ldfld    int32 System.Windows.Documents.RtfToXamlReader::_imageCount
0xf6e18  ldc.i4.1
0xf6e19  add
0xf6e1a  stfld    int32 System.Windows.Documents.RtfToXamlReader::_imageCount
0xf6e1f  ldarg.1
0xf6e20  ldloc.1
0xf6e21  callvirt instance void System.Windows.Documents.FormatState::set_ImageSource(string value)
0xf6e26  ldc.i4.8
0xf6e27  newobj   instance void System.Windows.Documents.DocumentNode::.ctor(valuetype System.Windows.Documents.DocumentNodeType documentNodeType)
0xf6e2c  stloc.s  5
0xf6e2e  ldloc.s  5
0xf6e30  ldarg.1
0xf6e31  callvirt instance void System.Windows.Documents.DocumentNode::set_FormatState(class System.Windows.Documents.FormatState value)
0xf6e36  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xf6e3b  stloc.s  6
0xf6e3d  ldloc.s  6
0xf6e3f  ldstr    aImage_1// "<Image "
0xf6e44  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6e49  pop
0xf6e4a  ldloc.s  6
0xf6e4c  ldstr    aWidth_1// " Width=\""
0xf6e51  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6e56  pop
0xf6e57  ldarg.1
0xf6e58  callvirt instance float64 System.Windows.Documents.FormatState::get_ImageScaleWidth()
0xf6e5d  ldc.r8   0.0
0xf6e66  beq.s    loc_F6E83
0xf6e68  ldarg.1
0xf6e69  callvirt instance float64 System.Windows.Documents.FormatState::get_ImageWidth()
0xf6e6e  ldarg.1
0xf6e6f  callvirt instance float64 System.Windows.Documents.FormatState::get_ImageScaleWidth()
0xf6e74  ldc.r8   100.0
0xf6e7d  div
0xf6e7e  mul
0xf6e7f  stloc.s  7
0xf6e81  br.s     loc_F6E8B
0xf6e83  ldarg.1
0xf6e84  callvirt instance float64 System.Windows.Documents.FormatState::get_ImageWidth()
0xf6e89  stloc.s  7
0xf6e8b  ldloc.s  6
0xf6e8d  ldloca.s 7
0xf6e8f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf6e94  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xf6e99  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6e9e  pop
0xf6e9f  ldloc.s  6
0xf6ea1  ldstr    asc_29CCCE// "\""
0xf6ea6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6eab  pop
0xf6eac  ldloc.s  6
0xf6eae  ldstr    aHeight_1// " Height=\""
0xf6eb3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6eb8  pop
0xf6eb9  ldarg.1
0xf6eba  callvirt instance float64 System.Windows.Documents.FormatState::get_ImageHeight()
0xf6ebf  ldarg.1
0xf6ec0  callvirt instance float64 System.Windows.Documents.FormatState::get_ImageScaleHeight()
0xf6ec5  ldc.r8   100.0
0xf6ece  div
0xf6ecf  mul
0xf6ed0  stloc.s  8
0xf6ed2  ldarg.1
0xf6ed3  callvirt instance float64 System.Windows.Documents.FormatState::get_ImageScaleHeight()
0xf6ed8  ldc.r8   0.0
0xf6ee1  beq.s    loc_F6EFE
0xf6ee3  ldarg.1
0xf6ee4  callvirt instance float64 System.Windows.Documents.FormatState::get_ImageHeight()
0xf6ee9  ldarg.1
0xf6eea  callvirt instance float64 System.Windows.Documents.FormatState::get_ImageScaleHeight()
0xf6eef  ldc.r8   100.0
0xf6ef8  div
0xf6ef9  mul
0xf6efa  stloc.s  8
0xf6efc  br.s     loc_F6F06
0xf6efe  ldarg.1
0xf6eff  callvirt instance float64 System.Windows.Documents.FormatState::get_ImageHeight()
0xf6f04  stloc.s  8
0xf6f06  ldloc.s  6
0xf6f08  ldloca.s 8
0xf6f0a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf6f0f  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xf6f14  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6f19  pop
0xf6f1a  ldloc.s  6
0xf6f1c  ldstr    asc_29CCCE// "\""
0xf6f21  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6f26  pop
0xf6f27  ldarg.1
0xf6f28  callvirt instance bool System.Windows.Documents.FormatState::get_IncludeImageBaselineOffset()
0xf6f2d  brfalse.s loc_F6F68
0xf6f2f  ldloc.s  8
0xf6f31  ldarg.1
0xf6f32  callvirt instance float64 System.Windows.Documents.FormatState::get_ImageBaselineOffset()
0xf6f37  sub
0xf6f38  stloc.s  0xD
0xf6f3a  ldloc.s  6
0xf6f3c  ldstr    aTextblockBasel// " TextBlock.BaselineOffset=\""
0xf6f41  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6f46  pop
0xf6f47  ldloc.s  6
0xf6f49  ldloca.s 0xD
0xf6f4b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf6f50  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xf6f55  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6f5a  pop
0xf6f5b  ldloc.s  6
0xf6f5d  ldstr    asc_29CCCE// "\""
0xf6f62  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6f67  pop
0xf6f68  ldloc.s  6
0xf6f6a  ldstr    aStretchFill// " Stretch=\"Fill"
0xf6f6f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6f74  pop
0xf6f75  ldloc.s  6
0xf6f77  ldstr    asc_29CCCE// "\""
0xf6f7c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6f81  pop
0xf6f82  ldloc.s  6
0xf6f84  ldstr    asc_2A887A// ">"
0xf6f89  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6f8e  pop
0xf6f8f  ldloc.s  6
0xf6f91  ldstr    aImageSource// "<Image.Source>"
0xf6f96  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6f9b  pop
0xf6f9c  ldloc.s  6
0xf6f9e  ldstr    aBitmapimage_0// "<BitmapImage "
0xf6fa3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6fa8  pop
0xf6fa9  ldloc.s  6
0xf6fab  ldstr    aUrisource_0// "UriSource=\""
0xf6fb0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6fb5  pop
0xf6fb6  ldloc.s  6
0xf6fb8  ldloc.1
0xf6fb9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6fbe  pop
0xf6fbf  ldloc.s  6
0xf6fc1  ldstr    asc_2A903C// "\" "
0xf6fc6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6fcb  pop
0xf6fcc  ldloc.s  6
0xf6fce  ldstr    aCacheoptionOnl// "CacheOption=\"OnLoad\" "
0xf6fd3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6fd8  pop
0xf6fd9  ldloc.s  6
0xf6fdb  ldstr    asc_2A906E// "/>"
0xf6fe0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6fe5  pop
0xf6fe6  ldloc.s  6
0xf6fe8  ldstr    aImageSource_0// "</Image.Source>"
0xf6fed  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6ff2  pop
0xf6ff3  ldloc.s  6
0xf6ff5  ldstr    aImage_2// "</Image>"
0xf6ffa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6fff  pop
0xf7000  ldloc.s  5
0xf7002  ldloc.s  6
0xf7004  callvirt instance string [mscorlib]System.Object::ToString()
0xf7009  callvirt instance void System.Windows.Documents.DocumentNode::set_Xaml(string value)
0xf700e  ldarg.0
0xf700f  ldfld    class System.Windows.Documents.ConverterState System.Windows.Documents.RtfToXamlReader::_converterState
0xf7014  callvirt instance class System.Windows.Documents.DocumentNodeArray System.Windows.Documents.ConverterState::get_DocumentNodeArray()
0xf7019  stloc.s  9
0xf701b  ldloc.s  9
0xf701d  ldloc.s  5
0xf701f  callvirt instance void System.Windows.Documents.DocumentNodeArray::Push(class System.Windows.Documents.DocumentNode documentNode)
0xf7024  ldloc.s  9
0xf7026  ldloc.s  9
0xf7028  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xf702d  ldc.i4.1
0xf702e  sub
0xf702f  callvirt instance void System.Windows.Documents.DocumentNodeArray::CloseAt(int32 index)
0xf7034  ret
0xf7035  ldarg.0
0xf7036  ldfld    class System.Windows.Documents.RtfToXamlLexer System.Windows.Documents.RtfToXamlReader::_lexer
0xf703b  callvirt instance void System.Windows.Documents.RtfToXamlLexer::AdvanceForImageData()
0xf7040  ret
```
