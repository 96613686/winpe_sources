# Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::Reset

- ea: `0x2b7c0`
- end: `0x2b80f`
- name: `Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::Reset`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x2a480`

## callees

- `0x29cd0`
- `0x29ce0`
- `0x2b7c0`
- `0x2ca50`

## string_xrefs

- `0x2b7d7`: `MimeReaderResetCalledBeforeEOF`

## pseudocode

```c

```

## disassembly

```asm
0x2b7c0  ldarg.1
0x2b7c1  brtrue.s loc_2B7CE
0x2b7c3  ldstr    aInputstream// "inputStream"
0x2b7c8  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperArgumentNull(string argumentName)
0x2b7cd  throw
0x2b7ce  ldarg.0
0x2b7cf  ldfld    valuetype ReadState Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::readState
0x2b7d4  ldc.i4.5
0x2b7d5  beq.s    loc_2B7F2
0x2b7d7  ldstr    aMimereaderrese// "MimeReaderResetCalledBeforeEOF"
0x2b7dc  ldc.i4.0
0x2b7dd  newarr   [mscorlib]System.Object
0x2b7e2  call     string Microsoft.SharePoint.Utilities.Mime.SR::GetString(string resourceId, object[] args)
0x2b7e7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2b7ec  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperError(class [mscorlib]System.Exception ex)
0x2b7f1  throw
0x2b7f2  ldarg.0
0x2b7f3  ldarg.1
0x2b7f4  stfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::stream
0x2b7f9  ldarg.0
0x2b7fa  ldc.i4.0
0x2b7fb  stfld    valuetype ReadState Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::readState
0x2b800  ldarg.0
0x2b801  ldc.i4.0
0x2b802  stfld    int32 Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::maxOffset
0x2b807  ldarg.0
0x2b808  ldc.i4.0
0x2b809  stfld    int32 Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::offset
0x2b80e  ret
```
