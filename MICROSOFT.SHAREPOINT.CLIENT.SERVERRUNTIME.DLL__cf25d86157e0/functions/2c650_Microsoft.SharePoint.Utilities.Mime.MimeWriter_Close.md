# Microsoft.SharePoint.Utilities.Mime.MimeWriter::Close

- ea: `0x2c650`
- end: `0x2c6e4`
- name: `Microsoft.SharePoint.Utilities.Mime.MimeWriter::Close`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x29cd0`
- `0x2c650`
- `0x2c6f0`
- `0x2c950`
- `0x2ca50`

## string_xrefs

- `0x2c65b`: `MimeWriterInvalidStateForClose`

## pseudocode

```c

```

## disassembly

```asm
0x2c650  ldarg.0
0x2c651  ldfld    valuetype Microsoft.SharePoint.Utilities.Mime.MimeWriterState Microsoft.SharePoint.Utilities.Mime.MimeWriter::state
0x2c656  stloc.0
0x2c657  ldloc.0
0x2c658  ldc.i4.5
0x2c659  bne.un.s loc_2C68B
0x2c65b  ldstr    aMimewriterinva_0// "MimeWriterInvalidStateForClose"
0x2c660  ldc.i4.1
0x2c661  newarr   [mscorlib]System.Object
0x2c666  stloc.1
0x2c667  ldloc.1
0x2c668  ldc.i4.0
0x2c669  ldarg.0
0x2c66a  ldfld    valuetype Microsoft.SharePoint.Utilities.Mime.MimeWriterState Microsoft.SharePoint.Utilities.Mime.MimeWriter::state
0x2c66f  box      Microsoft.SharePoint.Utilities.Mime.MimeWriterState
0x2c674  callvirt instance string [mscorlib]System.Object::ToString()
0x2c679  stelem.ref
0x2c67a  ldloc.1
0x2c67b  call     string Microsoft.SharePoint.Utilities.Mime.SR::GetString(string resourceId, object[] args)
0x2c680  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2c685  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperError(class [mscorlib]System.Exception ex)
0x2c68a  throw
0x2c68b  ldarg.0
0x2c68c  ldc.i4.5
0x2c68d  stfld    valuetype Microsoft.SharePoint.Utilities.Mime.MimeWriterState Microsoft.SharePoint.Utilities.Mime.MimeWriter::state
0x2c692  ldarg.0
0x2c693  ldfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.Mime.MimeWriter::contentStream
0x2c698  brfalse.s loc_2C6AC
0x2c69a  ldarg.0
0x2c69b  ldfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.Mime.MimeWriter::contentStream
0x2c6a0  callvirt instance void [mscorlib]System.IO.Stream::Flush()
0x2c6a5  ldarg.0
0x2c6a6  ldnull
0x2c6a7  stfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.Mime.MimeWriter::contentStream
0x2c6ac  ldarg.0
0x2c6ad  ldfld    class Microsoft.SharePoint.Utilities.Mime.BufferedWrite Microsoft.SharePoint.Utilities.Mime.MimeWriter::bufferedWrite
0x2c6b2  ldarg.0
0x2c6b3  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeWriter::boundaryBytes
0x2c6b8  callvirt instance void Microsoft.SharePoint.Utilities.Mime.BufferedWrite::Write(unsigned int8[] value)
0x2c6bd  ldarg.0
0x2c6be  ldfld    class Microsoft.SharePoint.Utilities.Mime.BufferedWrite Microsoft.SharePoint.Utilities.Mime.MimeWriter::bufferedWrite
0x2c6c3  ldsfld   unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeGlobals::DASHDASH
0x2c6c8  callvirt instance void Microsoft.SharePoint.Utilities.Mime.BufferedWrite::Write(unsigned int8[] value)
0x2c6cd  ldarg.0
0x2c6ce  ldfld    class Microsoft.SharePoint.Utilities.Mime.BufferedWrite Microsoft.SharePoint.Utilities.Mime.MimeWriter::bufferedWrite
0x2c6d3  ldsfld   unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeGlobals::CRLF
0x2c6d8  callvirt instance void Microsoft.SharePoint.Utilities.Mime.BufferedWrite::Write(unsigned int8[] value)
0x2c6dd  ldarg.0
0x2c6de  call     instance void Microsoft.SharePoint.Utilities.Mime.MimeWriter::Flush()
0x2c6e3  ret
```
