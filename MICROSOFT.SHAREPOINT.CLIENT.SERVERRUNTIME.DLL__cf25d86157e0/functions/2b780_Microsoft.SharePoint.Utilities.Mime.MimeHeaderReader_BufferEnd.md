# Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::BufferEnd

- ea: `0x2b780`
- end: `0x2b7c0`
- name: `Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::BufferEnd`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2b470`

## callees

- `0x29cd0`
- `0x2b780`
- `0x2ca50`

## string_xrefs

- `0x2b79a`: `MimeReaderMalformedHeader`

## pseudocode

```c

```

## disassembly

```asm
0x2b780  ldarg.0
0x2b781  ldfld    int32 Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::maxOffset
0x2b786  brtrue.s loc_2B7BE
0x2b788  ldarg.0
0x2b789  ldfld    valuetype ReadState Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::readState
0x2b78e  ldc.i4.4
0x2b78f  beq.s    loc_2B7B5
0x2b791  ldarg.0
0x2b792  ldfld    valuetype ReadState Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::readState
0x2b797  ldc.i4.2
0x2b798  beq.s    loc_2B7B5
0x2b79a  ldstr    aMimereadermalf// "MimeReaderMalformedHeader"
0x2b79f  ldc.i4.0
0x2b7a0  newarr   [mscorlib]System.Object
0x2b7a5  call     string Microsoft.SharePoint.Utilities.Mime.SR::GetString(string resourceId, object[] args)
0x2b7aa  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2b7af  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperError(class [mscorlib]System.Exception ex)
0x2b7b4  throw
0x2b7b5  ldarg.0
0x2b7b6  ldc.i4.5
0x2b7b7  stfld    valuetype ReadState Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::readState
0x2b7bc  ldc.i4.1
0x2b7bd  ret
0x2b7be  ldc.i4.0
0x2b7bf  ret
```
