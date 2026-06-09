# Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::ProcessBuffer

- ea: `0x2b4e0`
- end: `0x2b77c`
- name: `Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::ProcessBuffer`
- size: `668`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x2b470`

## callees

- `0x29cd0`
- `0x2b4e0`
- `0x2b810`
- `0x2b850`
- `0x2ca50`

## string_xrefs

- `0x2b59e`: `MimeReaderMalformedHeader`
- `0x2b6a3`: `MimeReaderMalformedHeader`
- `0x2b6fe`: `MimeReaderMalformedHeader`

## pseudocode

```c

```

## disassembly

```asm
0x2b4e0  ldarg.0
0x2b4e1  ldfld    int32 Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::offset
0x2b4e6  stloc.0
0x2b4e7  ldarg.0
0x2b4e8  ldfld    int32 Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::maxOffset
0x2b4ed  stloc.1
0x2b4ee  ldloc.0
0x2b4ef  stloc.2
0x2b4f0  ldarg.0
0x2b4f1  ldfld    valuetype ReadState Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::readState
0x2b4f6  stloc.s  5
0x2b4f8  ldloc.s  5
0x2b4fa  switch   loc_2B60C, loc_2B657, loc_2B667, loc_2B6EE, loc_2B728, loc_2B763
0x2b517  br       loc_2B773
0x2b51c  ldarg.0
0x2b51d  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::buffer
0x2b522  ldloc.2
0x2b523  ldelem.u1
0x2b524  stloc.3
0x2b525  ldloc.3
0x2b526  ldc.i4.s 0x3A
0x2b528  bne.un.s loc_2B54F
0x2b52a  ldarg.0
0x2b52b  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x2b530  ldarg.0
0x2b531  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::buffer
0x2b536  ldloc.0
0x2b537  ldloc.2
0x2b538  ldloc.0
0x2b539  sub
0x2b53a  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[], int32, int32)
0x2b53f  ldarg.1
0x2b540  ldarg.2
0x2b541  call     instance void Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::AppendName(string headerName, int32 maxBuffer, int32& remaining)
0x2b546  ldloc.2
0x2b547  ldc.i4.1
0x2b548  add
0x2b549  stloc.2
0x2b54a  br       loc_2B657
0x2b54f  ldloc.3
0x2b550  ldc.i4.s 0x41
0x2b552  blt.s    loc_2B56D
0x2b554  ldloc.3
0x2b555  ldc.i4.s 0x5A
0x2b557  bgt.s    loc_2B56D
0x2b559  ldloc.3
0x2b55a  ldc.i4.s 0x20
0x2b55c  add
0x2b55d  conv.u1
0x2b55e  stloc.3
0x2b55f  ldarg.0
0x2b560  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::buffer
0x2b565  ldloc.2
0x2b566  ldloc.3
0x2b567  stelem.i1
0x2b568  br       loc_2B608
0x2b56d  ldloc.3
0x2b56e  ldc.i4.s 0x21
0x2b570  blt.s    loc_2B57A
0x2b572  ldloc.3
0x2b573  ldc.i4.s 0x7E
0x2b575  ble      loc_2B608
0x2b57a  ldarg.0
0x2b57b  ldfld    string Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::name
0x2b580  brtrue.s loc_2B5B9
0x2b582  ldloc.3
0x2b583  ldc.i4.s 0xD
0x2b585  bne.un.s loc_2B5B9
0x2b587  ldloc.2
0x2b588  ldc.i4.1
0x2b589  add
0x2b58a  stloc.2
0x2b58b  ldloc.2
0x2b58c  ldloc.1
0x2b58d  bge.s    loc_2B59E
0x2b58f  ldarg.0
0x2b590  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::buffer
0x2b595  ldloc.2
0x2b596  ldelem.u1
0x2b597  ldc.i4.s 0xA
0x2b599  beq      loc_2B763
0x2b59e  ldstr    aMimereadermalf// "MimeReaderMalformedHeader"
0x2b5a3  ldc.i4.0
0x2b5a4  newarr   [mscorlib]System.Object
0x2b5a9  call     string Microsoft.SharePoint.Utilities.Mime.SR::GetString(string resourceId, object[] args)
0x2b5ae  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2b5b3  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperError(class [mscorlib]System.Exception ex)
0x2b5b8  throw
0x2b5b9  ldstr    aMimeheaderinva// "MimeHeaderInvalidCharacter"
0x2b5be  ldc.i4.2
0x2b5bf  newarr   [mscorlib]System.Object
0x2b5c4  stloc.s  6
0x2b5c6  ldloc.s  6
0x2b5c8  ldc.i4.0
0x2b5c9  ldarg.0
0x2b5ca  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::buffer
0x2b5cf  ldloc.2
0x2b5d0  ldelem.u1
0x2b5d1  box      [mscorlib]System.Byte
0x2b5d6  stelem.ref
0x2b5d7  ldloc.s  6
0x2b5d9  ldc.i4.1
0x2b5da  ldarg.0
0x2b5db  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::buffer
0x2b5e0  ldloc.2
0x2b5e1  ldelem.u1
0x2b5e2  stloc.s  7
0x2b5e4  ldloca.s 7
0x2b5e6  ldstr    aX_0// "X"
0x2b5eb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2b5f0  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x2b5f5  stelem.ref
0x2b5f6  ldloc.s  6
0x2b5f8  call     string Microsoft.SharePoint.Utilities.Mime.SR::GetString(string resourceId, object[] args)
0x2b5fd  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2b602  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperError(class [mscorlib]System.Exception ex)
0x2b607  throw
0x2b608  ldloc.2
0x2b609  ldc.i4.1
0x2b60a  add
0x2b60b  stloc.2
0x2b60c  ldloc.2
0x2b60d  ldloc.1
0x2b60e  blt      loc_2B51C
0x2b613  ldarg.0
0x2b614  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x2b619  ldarg.0
0x2b61a  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::buffer
0x2b61f  ldloc.0
0x2b620  ldloc.2
0x2b621  ldloc.0
0x2b622  sub
0x2b623  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[], int32, int32)
0x2b628  ldarg.1
0x2b629  ldarg.2
0x2b62a  call     instance void Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::AppendName(string headerName, int32 maxBuffer, int32& remaining)
0x2b62f  ldarg.0
0x2b630  ldc.i4.0
0x2b631  stfld    valuetype ReadState Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::readState
0x2b636  br       loc_2B773
0x2b63b  ldarg.0
0x2b63c  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::buffer
0x2b641  ldloc.2
0x2b642  ldelem.u1
0x2b643  ldc.i4.s 9
0x2b645  beq.s    loc_2B653
0x2b647  ldarg.0
0x2b648  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::buffer
0x2b64d  ldloc.2
0x2b64e  ldelem.u1
0x2b64f  ldc.i4.s 0x20
0x2b651  bne.un.s loc_2B667
0x2b653  ldloc.2
0x2b654  ldc.i4.1
0x2b655  add
0x2b656  stloc.2
0x2b657  ldloc.2
0x2b658  ldloc.1
0x2b659  blt.s    loc_2B63B
0x2b65b  ldarg.0
0x2b65c  ldc.i4.1
0x2b65d  stfld    valuetype ReadState Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::readState
0x2b662  br       loc_2B773
0x2b667  ldloc.2
0x2b668  stloc.0
0x2b669  br.s     loc_2B6C2
0x2b66b  ldarg.0
0x2b66c  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::buffer
0x2b671  ldloc.2
0x2b672  ldelem.u1
0x2b673  stloc.s  4
0x2b675  ldloc.s  4
0x2b677  ldc.i4.s 0xD
0x2b679  bne.un.s loc_2B69D
0x2b67b  ldarg.0
0x2b67c  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x2b681  ldarg.0
0x2b682  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::buffer
0x2b687  ldloc.0
0x2b688  ldloc.2
0x2b689  ldloc.0
0x2b68a  sub
0x2b68b  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[], int32, int32)
0x2b690  ldarg.1
0x2b691  ldarg.2
0x2b692  call     instance void Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::AppendValue(string headerValue, int32 maxBuffer, int32& remaining)
0x2b697  ldloc.2
0x2b698  ldc.i4.1
0x2b699  add
0x2b69a  stloc.2
0x2b69b  br.s     loc_2B6EE
0x2b69d  ldloc.s  4
0x2b69f  ldc.i4.s 0xA
0x2b6a1  bne.un.s loc_2B6BE
0x2b6a3  ldstr    aMimereadermalf// "MimeReaderMalformedHeader"
0x2b6a8  ldc.i4.0
0x2b6a9  newarr   [mscorlib]System.Object
0x2b6ae  call     string Microsoft.SharePoint.Utilities.Mime.SR::GetString(string resourceId, object[] args)
0x2b6b3  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2b6b8  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperError(class [mscorlib]System.Exception ex)
0x2b6bd  throw
0x2b6be  ldloc.2
0x2b6bf  ldc.i4.1
0x2b6c0  add
0x2b6c1  stloc.2
0x2b6c2  ldloc.2
0x2b6c3  ldloc.1
0x2b6c4  blt.s    loc_2B66B
0x2b6c6  ldarg.0
0x2b6c7  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x2b6cc  ldarg.0
0x2b6cd  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::buffer
0x2b6d2  ldloc.0
0x2b6d3  ldloc.2
0x2b6d4  ldloc.0
0x2b6d5  sub
0x2b6d6  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[], int32, int32)
0x2b6db  ldarg.1
0x2b6dc  ldarg.2
0x2b6dd  call     instance void Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::AppendValue(string headerValue, int32 maxBuffer, int32& remaining)
0x2b6e2  ldarg.0
0x2b6e3  ldc.i4.2
0x2b6e4  stfld    valuetype ReadState Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::readState
0x2b6e9  br       loc_2B773
0x2b6ee  ldloc.2
0x2b6ef  ldloc.1
0x2b6f0  bge.s    loc_2B71F
0x2b6f2  ldarg.0
0x2b6f3  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::buffer
0x2b6f8  ldloc.2
0x2b6f9  ldelem.u1
0x2b6fa  ldc.i4.s 0xA
0x2b6fc  beq.s    loc_2B719
0x2b6fe  ldstr    aMimereadermalf// "MimeReaderMalformedHeader"
0x2b703  ldc.i4.0
0x2b704  newarr   [mscorlib]System.Object
0x2b709  call     string Microsoft.SharePoint.Utilities.Mime.SR::GetString(string resourceId, object[] args)
0x2b70e  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2b713  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperError(class [mscorlib]System.Exception ex)
0x2b718  throw
0x2b719  ldloc.2
0x2b71a  ldc.i4.1
0x2b71b  add
0x2b71c  stloc.2
0x2b71d  br.s     loc_2B728
0x2b71f  ldarg.0
0x2b720  ldc.i4.3
0x2b721  stfld    valuetype ReadState Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::readState
0x2b726  br.s     loc_2B773
0x2b728  ldloc.2
0x2b729  ldloc.1
0x2b72a  bge.s    loc_2B75A
0x2b72c  ldarg.0
0x2b72d  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::buffer
0x2b732  ldloc.2
0x2b733  ldelem.u1
0x2b734  ldc.i4.s 0x20
0x2b736  beq      loc_2B667
0x2b73b  ldarg.0
0x2b73c  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::buffer
0x2b741  ldloc.2
0x2b742  ldelem.u1
0x2b743  ldc.i4.s 9
0x2b745  beq      loc_2B667
0x2b74a  ldarg.0
0x2b74b  ldc.i4.0
0x2b74c  stfld    valuetype ReadState Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::readState
0x2b751  ldarg.0
0x2b752  ldloc.2
0x2b753  stfld    int32 Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::offset
0x2b758  ldc.i4.1
0x2b759  ret
0x2b75a  ldarg.0
0x2b75b  ldc.i4.4
0x2b75c  stfld    valuetype ReadState Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::readState
0x2b761  br.s     loc_2B773
0x2b763  ldarg.0
0x2b764  ldc.i4.5
0x2b765  stfld    valuetype ReadState Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::readState
0x2b76a  ldarg.0
0x2b76b  ldloc.2
0x2b76c  stfld    int32 Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::offset
0x2b771  ldc.i4.1
0x2b772  ret
0x2b773  ldarg.0
0x2b774  ldloc.2
0x2b775  stfld    int32 Microsoft.SharePoint.Utilities.Mime.MimeHeaderReader::offset
0x2b77a  ldc.i4.0
0x2b77b  ret
```
