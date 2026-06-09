# Microsoft.SharePoint.Utilities.Mime.MimeMessageReader::GetContentStream

- ea: `0x2a2c0`
- end: `0x2a304`
- name: `Microsoft.SharePoint.Utilities.Mime.MimeMessageReader::GetContentStream`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x29cd0`
- `0x2a2c0`
- `0x2a690`
- `0x2b450`
- `0x2ca50`

## string_xrefs

- `0x2a2c8`: `MimeMessageGetContentStreamCalledAlready`

## pseudocode

```c

```

## disassembly

```asm
0x2a2c0  ldarg.0
0x2a2c1  ldfld    bool Microsoft.SharePoint.Utilities.Mime.MimeMessageReader::getContentStreamCalled
0x2a2c6  brfalse.s loc_2A2E3
0x2a2c8  ldstr    aMimemessageget// "MimeMessageGetContentStreamCalledAlread"...
0x2a2cd  ldc.i4.0
0x2a2ce  newarr   [mscorlib]System.Object
0x2a2d3  call     string Microsoft.SharePoint.Utilities.Mime.SR::GetString(string resourceId, object[] args)
0x2a2d8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2a2dd  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperError(class [mscorlib]System.Exception ex)
0x2a2e2  throw
0x2a2e3  ldarg.0
0x2a2e4  ldfld    class Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader Microsoft.SharePoint.Utilities.Mime.MimeMessageReader::mimeHeaderReader
0x2a2e9  callvirt instance void Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::Close()
0x2a2ee  ldarg.0
0x2a2ef  ldfld    class Microsoft.SharePoint.Utilities.Mime.DelimittedStreamReader Microsoft.SharePoint.Utilities.Mime.MimeMessageReader::reader
0x2a2f4  ldnull
0x2a2f5  callvirt instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.Mime.DelimittedStreamReader::GetNextStream(unsigned int8[] delimitterValue)
0x2a2fa  stloc.0
0x2a2fb  ldarg.0
0x2a2fc  ldc.i4.1
0x2a2fd  stfld    bool Microsoft.SharePoint.Utilities.Mime.MimeMessageReader::getContentStreamCalled
0x2a302  ldloc.0
0x2a303  ret
```
