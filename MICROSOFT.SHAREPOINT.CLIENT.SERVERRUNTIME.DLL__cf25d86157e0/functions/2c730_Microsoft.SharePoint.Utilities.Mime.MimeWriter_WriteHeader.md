# Microsoft.SharePoint.Utilities.Mime.MimeWriter::WriteHeader

- ea: `0x2c730`
- end: `0x2c7d9`
- name: `Microsoft.SharePoint.Utilities.Mime.MimeWriter::WriteHeader`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x29cd0`
- `0x29ce0`
- `0x2c730`
- `0x2c950`
- `0x2c990`
- `0x2ca50`

## string_xrefs

- `0x2c769`: `MimeWriterInvalidStateForHeader`

## pseudocode

```c

```

## disassembly

```asm
0x2c730  ldarg.1
0x2c731  brtrue.s loc_2C73E
0x2c733  ldstr    aName_0// "name"
0x2c738  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperArgumentNull(string argumentName)
0x2c73d  throw
0x2c73e  ldarg.2
0x2c73f  brtrue.s loc_2C74C
0x2c741  ldstr    aValue// "value"
0x2c746  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperArgumentNull(string argumentName)
0x2c74b  throw
0x2c74c  ldarg.0
0x2c74d  ldfld    valuetype Microsoft.SharePoint.Utilities.Mime.MimeWriterState Microsoft.SharePoint.Utilities.Mime.MimeWriter::state
0x2c752  stloc.0
0x2c753  ldloc.0
0x2c754  ldc.i4.0
0x2c755  beq.s    loc_2C769
0x2c757  ldloc.0
0x2c758  ldc.i4.4
0x2c759  sub
0x2c75a  switch   loc_2C769, loc_2C769
0x2c767  br.s     loc_2C799
0x2c769  ldstr    aMimewriterinva_1// "MimeWriterInvalidStateForHeader"
0x2c76e  ldc.i4.1
0x2c76f  newarr   [mscorlib]System.Object
0x2c774  stloc.1
0x2c775  ldloc.1
0x2c776  ldc.i4.0
0x2c777  ldarg.0
0x2c778  ldfld    valuetype Microsoft.SharePoint.Utilities.Mime.MimeWriterState Microsoft.SharePoint.Utilities.Mime.MimeWriter::state
0x2c77d  box      Microsoft.SharePoint.Utilities.Mime.MimeWriterState
0x2c782  callvirt instance string [mscorlib]System.Object::ToString()
0x2c787  stelem.ref
0x2c788  ldloc.1
0x2c789  call     string Microsoft.SharePoint.Utilities.Mime.SR::GetString(string resourceId, object[] args)
0x2c78e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2c793  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperError(class [mscorlib]System.Exception ex)
0x2c798  throw
0x2c799  ldarg.0
0x2c79a  ldc.i4.3
0x2c79b  stfld    valuetype Microsoft.SharePoint.Utilities.Mime.MimeWriterState Microsoft.SharePoint.Utilities.Mime.MimeWriter::state
0x2c7a0  ldarg.0
0x2c7a1  ldfld    class Microsoft.SharePoint.Utilities.Mime.BufferedWrite Microsoft.SharePoint.Utilities.Mime.MimeWriter::bufferedWrite
0x2c7a6  ldarg.1
0x2c7a7  callvirt instance void Microsoft.SharePoint.Utilities.Mime.BufferedWrite::Write(string value)
0x2c7ac  ldarg.0
0x2c7ad  ldfld    class Microsoft.SharePoint.Utilities.Mime.BufferedWrite Microsoft.SharePoint.Utilities.Mime.MimeWriter::bufferedWrite
0x2c7b2  ldsfld   unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeGlobals::COLONSPACE
0x2c7b7  callvirt instance void Microsoft.SharePoint.Utilities.Mime.BufferedWrite::Write(unsigned int8[] value)
0x2c7bc  ldarg.0
0x2c7bd  ldfld    class Microsoft.SharePoint.Utilities.Mime.BufferedWrite Microsoft.SharePoint.Utilities.Mime.MimeWriter::bufferedWrite
0x2c7c2  ldarg.2
0x2c7c3  callvirt instance void Microsoft.SharePoint.Utilities.Mime.BufferedWrite::Write(string value)
0x2c7c8  ldarg.0
0x2c7c9  ldfld    class Microsoft.SharePoint.Utilities.Mime.BufferedWrite Microsoft.SharePoint.Utilities.Mime.MimeWriter::bufferedWrite
0x2c7ce  ldsfld   unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeGlobals::CRLF
0x2c7d3  callvirt instance void Microsoft.SharePoint.Utilities.Mime.BufferedWrite::Write(unsigned int8[] value)
0x2c7d8  ret
```
