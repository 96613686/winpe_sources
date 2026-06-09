# Microsoft.SharePoint.Utilities.Mime.MimeWriter::GetContentStream

- ea: `0x2c7e0`
- end: `0x2c85d`
- name: `Microsoft.SharePoint.Utilities.Mime.MimeWriter::GetContentStream`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x29cd0`
- `0x2c6f0`
- `0x2c7e0`
- `0x2c950`
- `0x2ca50`

## string_xrefs

- `0x2c7fd`: `MimeWriterInvalidStateForContent`

## pseudocode

```c

```

## disassembly

```asm
0x2c7e0  ldarg.0
0x2c7e1  ldfld    valuetype Microsoft.SharePoint.Utilities.Mime.MimeWriterState Microsoft.SharePoint.Utilities.Mime.MimeWriter::state
0x2c7e6  stloc.0
0x2c7e7  ldloc.0
0x2c7e8  ldc.i4.0
0x2c7e9  beq.s    loc_2C7FD
0x2c7eb  ldloc.0
0x2c7ec  ldc.i4.4
0x2c7ed  sub
0x2c7ee  switch   loc_2C7FD, loc_2C7FD
0x2c7fb  br.s     loc_2C82D
0x2c7fd  ldstr    aMimewriterinva_2// "MimeWriterInvalidStateForContent"
0x2c802  ldc.i4.1
0x2c803  newarr   [mscorlib]System.Object
0x2c808  stloc.1
0x2c809  ldloc.1
0x2c80a  ldc.i4.0
0x2c80b  ldarg.0
0x2c80c  ldfld    valuetype Microsoft.SharePoint.Utilities.Mime.MimeWriterState Microsoft.SharePoint.Utilities.Mime.MimeWriter::state
0x2c811  box      Microsoft.SharePoint.Utilities.Mime.MimeWriterState
0x2c816  callvirt instance string [mscorlib]System.Object::ToString()
0x2c81b  stelem.ref
0x2c81c  ldloc.1
0x2c81d  call     string Microsoft.SharePoint.Utilities.Mime.SR::GetString(string resourceId, object[] args)
0x2c822  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2c827  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperError(class [mscorlib]System.Exception ex)
0x2c82c  throw
0x2c82d  ldarg.0
0x2c82e  ldc.i4.4
0x2c82f  stfld    valuetype Microsoft.SharePoint.Utilities.Mime.MimeWriterState Microsoft.SharePoint.Utilities.Mime.MimeWriter::state
0x2c834  ldarg.0
0x2c835  ldfld    class Microsoft.SharePoint.Utilities.Mime.BufferedWrite Microsoft.SharePoint.Utilities.Mime.MimeWriter::bufferedWrite
0x2c83a  ldsfld   unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeGlobals::CRLF
0x2c83f  callvirt instance void Microsoft.SharePoint.Utilities.Mime.BufferedWrite::Write(unsigned int8[] value)
0x2c844  ldarg.0
0x2c845  call     instance void Microsoft.SharePoint.Utilities.Mime.MimeWriter::Flush()
0x2c84a  ldarg.0
0x2c84b  ldarg.0
0x2c84c  ldfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.Mime.MimeWriter::stream
0x2c851  stfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.Mime.MimeWriter::contentStream
0x2c856  ldarg.0
0x2c857  ldfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.Mime.MimeWriter::contentStream
0x2c85c  ret
```
