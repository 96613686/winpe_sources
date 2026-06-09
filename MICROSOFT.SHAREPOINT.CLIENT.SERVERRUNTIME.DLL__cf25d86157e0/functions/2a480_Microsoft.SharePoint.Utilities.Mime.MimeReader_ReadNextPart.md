# Microsoft.SharePoint.Utilities.Mime.MimeReader::ReadNextPart

- ea: `0x2a480`
- end: `0x2a569`
- name: `Microsoft.SharePoint.Utilities.Mime.MimeReader::ReadNextPart`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x9f90`
- `0xdaf0`

## callees

- `0x29cd0`
- `0x2a3f0`
- `0x2a480`
- `0x2a5b0`
- `0x2a690`
- `0x2b400`
- `0x2b7c0`
- `0x2ca50`

## string_xrefs

- `0x2a54e`: `MimeReaderTruncated`

## pseudocode

```c

```

## disassembly

```asm
0x2a480  ldarg.0
0x2a481  call     instance string Microsoft.SharePoint.Utilities.Mime.MimeReader::get_Preface()
0x2a486  pop
0x2a487  ldarg.0
0x2a488  ldfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.Mime.MimeReader::currentStream
0x2a48d  brfalse.s loc_2A4A1
0x2a48f  ldarg.0
0x2a490  ldfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.Mime.MimeReader::currentStream
0x2a495  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x2a49a  ldarg.0
0x2a49b  ldnull
0x2a49c  stfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.Mime.MimeReader::currentStream
0x2a4a1  ldarg.0
0x2a4a2  ldfld    class Microsoft.SharePoint.Utilities.Mime.DelimittedStreamReader Microsoft.SharePoint.Utilities.Mime.MimeReader::reader
0x2a4a7  ldsfld   unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeReader::CRLFCRLF
0x2a4ac  callvirt instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.Mime.DelimittedStreamReader::GetNextStream(unsigned int8[] delimitterValue)
0x2a4b1  stloc.0
0x2a4b2  ldloc.0
0x2a4b3  brtrue.s loc_2A4B7
0x2a4b5  ldc.i4.0
0x2a4b6  ret
0x2a4b7  ldarg.0
0x2a4b8  ldloc.0
0x2a4b9  ldarg.0
0x2a4ba  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeReader::scratch
0x2a4bf  ldc.i4.0
0x2a4c0  ldc.i4.2
0x2a4c1  call     instance int32 Microsoft.SharePoint.Utilities.Mime.MimeReader::BlockRead(class [mscorlib]System.IO.Stream stream, unsigned int8[] buffer, int32 offset, int32 count)
0x2a4c6  ldc.i4.2
0x2a4c7  bne.un   loc_2A54E
0x2a4cc  ldarg.0
0x2a4cd  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeReader::scratch
0x2a4d2  ldc.i4.0
0x2a4d3  ldelem.u1
0x2a4d4  ldc.i4.s 0xD
0x2a4d6  bne.un.s loc_2A508
0x2a4d8  ldarg.0
0x2a4d9  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeReader::scratch
0x2a4de  ldc.i4.1
0x2a4df  ldelem.u1
0x2a4e0  ldc.i4.s 0xA
0x2a4e2  bne.un.s loc_2A508
0x2a4e4  ldarg.0
0x2a4e5  ldfld    class Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader Microsoft.SharePoint.Utilities.Mime.MimeReader::mimeHeaderReader
0x2a4ea  brtrue.s loc_2A4FA
0x2a4ec  ldarg.0
0x2a4ed  ldloc.0
0x2a4ee  newobj   instance void Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::.ctor(class [mscorlib]System.IO.Stream stream)
0x2a4f3  stfld    class Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader Microsoft.SharePoint.Utilities.Mime.MimeReader::mimeHeaderReader
0x2a4f8  br.s     loc_2A506
0x2a4fa  ldarg.0
0x2a4fb  ldfld    class Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader Microsoft.SharePoint.Utilities.Mime.MimeReader::mimeHeaderReader
0x2a500  ldloc.0
0x2a501  callvirt instance void Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::Reset(class [mscorlib]System.IO.Stream inputStream)
0x2a506  ldc.i4.1
0x2a507  ret
0x2a508  ldarg.0
0x2a509  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeReader::scratch
0x2a50e  ldc.i4.0
0x2a50f  ldelem.u1
0x2a510  ldc.i4.s 0x2D
0x2a512  bne.un.s loc_2A54E
0x2a514  ldarg.0
0x2a515  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeReader::scratch
0x2a51a  ldc.i4.1
0x2a51b  ldelem.u1
0x2a51c  ldc.i4.s 0x2D
0x2a51e  bne.un.s loc_2A54E
0x2a520  ldarg.0
0x2a521  ldloc.0
0x2a522  ldarg.0
0x2a523  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeReader::scratch
0x2a528  ldc.i4.0
0x2a529  ldc.i4.2
0x2a52a  call     instance int32 Microsoft.SharePoint.Utilities.Mime.MimeReader::BlockRead(class [mscorlib]System.IO.Stream stream, unsigned int8[] buffer, int32 offset, int32 count)
0x2a52f  stloc.1
0x2a530  ldloc.1
0x2a531  ldc.i4.2
0x2a532  blt.s    loc_2A54C
0x2a534  ldarg.0
0x2a535  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeReader::scratch
0x2a53a  ldc.i4.0
0x2a53b  ldelem.u1
0x2a53c  ldc.i4.s 0xD
0x2a53e  bne.un.s loc_2A54E
0x2a540  ldarg.0
0x2a541  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeReader::scratch
0x2a546  ldc.i4.1
0x2a547  ldelem.u1
0x2a548  ldc.i4.s 0xA
0x2a54a  bne.un.s loc_2A54E
0x2a54c  ldc.i4.0
0x2a54d  ret
0x2a54e  ldstr    aMimereadertrun// "MimeReaderTruncated"
0x2a553  ldc.i4.0
0x2a554  newarr   [mscorlib]System.Object
0x2a559  call     string Microsoft.SharePoint.Utilities.Mime.SR::GetString(string resourceId, object[] args)
0x2a55e  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2a563  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperError(class [mscorlib]System.Exception ex)
0x2a568  throw
```
