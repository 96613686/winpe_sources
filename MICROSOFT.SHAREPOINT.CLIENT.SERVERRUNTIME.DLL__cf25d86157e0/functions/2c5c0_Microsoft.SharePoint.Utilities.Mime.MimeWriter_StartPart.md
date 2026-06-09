# Microsoft.SharePoint.Utilities.Mime.MimeWriter::StartPart

- ea: `0x2c5c0`
- end: `0x2c642`
- name: `Microsoft.SharePoint.Utilities.Mime.MimeWriter::StartPart`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x29cd0`
- `0x2c5c0`
- `0x2c950`
- `0x2ca50`

## string_xrefs

- `0x2c5cf`: `MimeWriterInvalidStateForStartPart`

## pseudocode

```c

```

## disassembly

```asm
0x2c5c0  ldarg.0
0x2c5c1  ldfld    valuetype Microsoft.SharePoint.Utilities.Mime.MimeWriterState Microsoft.SharePoint.Utilities.Mime.MimeWriter::state
0x2c5c6  stloc.0
0x2c5c7  ldloc.0
0x2c5c8  ldc.i4.2
0x2c5c9  beq.s    loc_2C5CF
0x2c5cb  ldloc.0
0x2c5cc  ldc.i4.5
0x2c5cd  bne.un.s loc_2C5FF
0x2c5cf  ldstr    aMimewriterinva// "MimeWriterInvalidStateForStartPart"
0x2c5d4  ldc.i4.1
0x2c5d5  newarr   [mscorlib]System.Object
0x2c5da  stloc.1
0x2c5db  ldloc.1
0x2c5dc  ldc.i4.0
0x2c5dd  ldarg.0
0x2c5de  ldfld    valuetype Microsoft.SharePoint.Utilities.Mime.MimeWriterState Microsoft.SharePoint.Utilities.Mime.MimeWriter::state
0x2c5e3  box      Microsoft.SharePoint.Utilities.Mime.MimeWriterState
0x2c5e8  callvirt instance string [mscorlib]System.Object::ToString()
0x2c5ed  stelem.ref
0x2c5ee  ldloc.1
0x2c5ef  call     string Microsoft.SharePoint.Utilities.Mime.SR::GetString(string resourceId, object[] args)
0x2c5f4  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2c5f9  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperError(class [mscorlib]System.Exception ex)
0x2c5fe  throw
0x2c5ff  ldarg.0
0x2c600  ldc.i4.2
0x2c601  stfld    valuetype Microsoft.SharePoint.Utilities.Mime.MimeWriterState Microsoft.SharePoint.Utilities.Mime.MimeWriter::state
0x2c606  ldarg.0
0x2c607  ldfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.Mime.MimeWriter::contentStream
0x2c60c  brfalse.s loc_2C620
0x2c60e  ldarg.0
0x2c60f  ldfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.Mime.MimeWriter::contentStream
0x2c614  callvirt instance void [mscorlib]System.IO.Stream::Flush()
0x2c619  ldarg.0
0x2c61a  ldnull
0x2c61b  stfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.Mime.MimeWriter::contentStream
0x2c620  ldarg.0
0x2c621  ldfld    class Microsoft.SharePoint.Utilities.Mime.BufferedWrite Microsoft.SharePoint.Utilities.Mime.MimeWriter::bufferedWrite
0x2c626  ldarg.0
0x2c627  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeWriter::boundaryBytes
0x2c62c  callvirt instance void Microsoft.SharePoint.Utilities.Mime.BufferedWrite::Write(unsigned int8[] value)
0x2c631  ldarg.0
0x2c632  ldfld    class Microsoft.SharePoint.Utilities.Mime.BufferedWrite Microsoft.SharePoint.Utilities.Mime.MimeWriter::bufferedWrite
0x2c637  ldsfld   unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeGlobals::CRLF
0x2c63c  callvirt instance void Microsoft.SharePoint.Utilities.Mime.BufferedWrite::Write(unsigned int8[] value)
0x2c641  ret
```
