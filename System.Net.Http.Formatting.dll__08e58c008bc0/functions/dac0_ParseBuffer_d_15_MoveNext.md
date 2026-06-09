# <ParseBuffer>d__15::MoveNext

- ea: `0xdac0`
- end: `0xdd61`
- name: `<ParseBuffer>d__15::MoveNext`
- size: `673`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x27d0`
- `0x2810`
- `0x2860`
- `0x2890`
- `0x28b0`
- `0x38d0`
- `0x38f0`
- `0x3970`
- `0xa550`
- `0xa9e0`
- `0xaac0`
- `0xaae0`
- `0xab00`
- `0xb4b0`
- `0xdac0`

## pseudocode

```c

```

## disassembly

```asm
0xdac0  ldarg.0
0xdac1  ldfld    int32 <ParseBuffer>d__15::<>1__state
0xdac6  stloc.0
0xdac7  ldarg.0
0xdac8  ldfld    class System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser <ParseBuffer>d__15::<>4__this
0xdacd  stloc.1
0xdace  ldloc.0
0xdacf  switch   loc_DAE2, loc_DD1E, loc_DD3C
0xdae0  ldc.i4.0
0xdae1  ret
0xdae2  ldarg.0
0xdae3  ldc.i4.m1
0xdae4  stfld    int32 <ParseBuffer>d__15::<>1__state
0xdae9  ldarg.0
0xdaea  ldc.i4.0
0xdaeb  stfld    int32 <ParseBuffer>d__15::<bytesConsumed>5__2
0xdaf0  ldc.i4.0
0xdaf1  stloc.2
0xdaf2  ldarg.0
0xdaf3  ldfld    int32 <ParseBuffer>d__15::bytesRead
0xdaf8  brtrue.s loc_DB18
0xdafa  ldloc.1
0xdafb  ldfld    class System.Net.Http.Formatting.Parsers.MimeMultipartParser System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_mimeParser
0xdb00  callvirt instance bool System.Net.Http.Formatting.Parsers.MimeMultipartParser::get_IsWaitingForEndOfMessage()
0xdb05  brtrue.s loc_DB18
0xdb07  ldloc.1
0xdb08  call     instance void System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::CleanupCurrentBodyPart()
0xdb0d  call     string System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartUnexpectedTermination()
0xdb12  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0xdb17  throw
0xdb18  ldloc.1
0xdb19  ldfld    class System.Net.Http.MimeBodyPart System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_currentBodyPart
0xdb1e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>> System.Net.Http.MimeBodyPart::get_Segments()
0xdb23  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>>::Clear()
0xdb28  br       loc_DD43
0xdb2d  ldloc.1
0xdb2e  ldloc.1
0xdb2f  ldfld    class System.Net.Http.Formatting.Parsers.MimeMultipartParser System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_mimeParser
0xdb34  ldarg.0
0xdb35  ldfld    unsigned int8[] <ParseBuffer>d__15::data
0xdb3a  ldarg.0
0xdb3b  ldfld    int32 <ParseBuffer>d__15::bytesRead
0xdb40  ldarg.0
0xdb41  ldflda   int32 <ParseBuffer>d__15::<bytesConsumed>5__2
0xdb46  ldloc.1
0xdb47  ldfld    valuetype [mscorlib]System.ArraySegment`1<unsigned int8>[] System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_parsedBodyPart
0xdb4c  ldc.i4.0
0xdb4d  ldelema  valuetype [mscorlib]System.ArraySegment`1<unsigned int8>
0xdb52  ldloc.1
0xdb53  ldfld    valuetype [mscorlib]System.ArraySegment`1<unsigned int8>[] System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_parsedBodyPart
0xdb58  ldc.i4.1
0xdb59  ldelema  valuetype [mscorlib]System.ArraySegment`1<unsigned int8>
0xdb5e  ldloca.s 2
0xdb60  callvirt instance valuetype State System.Net.Http.Formatting.Parsers.MimeMultipartParser::ParseBuffer(unsigned int8[] buffer, int32 bytesReady, int32& bytesConsumed, [out] valuetype [mscorlib]System.ArraySegment`1<unsigned int8>& remainingBodyPart, [out] valuetype [mscorlib]System.ArraySegment`1<unsigned int8>& bodyPart, [out] bool& isFinalBodyPart)
0xdb65  stfld    valuetype State System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_mimeStatus
0xdb6a  ldloc.1
0xdb6b  ldfld    valuetype State System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_mimeStatus
0xdb70  ldc.i4.1
0xdb71  beq.s    loc_DBA9
0xdb73  ldloc.1
0xdb74  ldfld    valuetype State System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_mimeStatus
0xdb79  brfalse.s loc_DBA9
0xdb7b  ldloc.1
0xdb7c  call     instance void System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::CleanupCurrentBodyPart()
0xdb81  call     string System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartParseError()
0xdb86  ldc.i4.2
0xdb87  newarr   [mscorlib]System.Object
0xdb8c  dup
0xdb8d  ldc.i4.0
0xdb8e  ldarg.0
0xdb8f  ldfld    int32 <ParseBuffer>d__15::<bytesConsumed>5__2
0xdb94  box      [mscorlib]System.Int32
0xdb99  stelem.ref
0xdb9a  dup
0xdb9b  ldc.i4.1
0xdb9c  ldarg.0
0xdb9d  ldfld    unsigned int8[] <ParseBuffer>d__15::data
0xdba2  stelem.ref
0xdba3  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0xdba8  throw
0xdba9  ldloc.1
0xdbaa  ldfld    bool System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_isFirst
0xdbaf  brfalse.s loc_DBC9
0xdbb1  ldloc.1
0xdbb2  ldfld    valuetype State System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_mimeStatus
0xdbb7  ldc.i4.1
0xdbb8  bne.un   loc_DD43
0xdbbd  ldloc.1
0xdbbe  ldc.i4.0
0xdbbf  stfld    bool System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_isFirst
0xdbc4  br       loc_DD43
0xdbc9  ldloc.1
0xdbca  ldfld    valuetype [mscorlib]System.ArraySegment`1<unsigned int8>[] System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_parsedBodyPart
0xdbcf  stloc.3
0xdbd0  ldc.i4.0
0xdbd1  stloc.s  4
0xdbd3  br       loc_DCB7
0xdbd8  ldloc.3
0xdbd9  ldloc.s  4
0xdbdb  ldelem   valuetype [mscorlib]System.ArraySegment`1<unsigned int8>
0xdbe0  stloc.s  5
0xdbe2  ldloca.s 5
0xdbe4  call     instance int32 valuetype [mscorlib]System.ArraySegment`1<unsigned int8>::get_Count()
0xdbe9  brfalse  loc_DCB1
0xdbee  ldloc.1
0xdbef  ldfld    valuetype System.Net.Http.Formatting.Parsers.ParserState System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_bodyPartHeaderStatus
0xdbf4  ldc.i4.1
0xdbf5  beq      loc_DC9F
0xdbfa  ldloca.s 5
0xdbfc  call     instance int32 valuetype [mscorlib]System.ArraySegment`1<unsigned int8>::get_Offset()
0xdc01  stloc.s  6
0xdc03  ldloc.1
0xdc04  ldloc.1
0xdc05  ldfld    class System.Net.Http.MimeBodyPart System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_currentBodyPart
0xdc0a  callvirt instance class System.Net.Http.Formatting.Parsers.InternetMessageFormatHeaderParser System.Net.Http.MimeBodyPart::get_HeaderParser()
0xdc0f  ldloca.s 5
0xdc11  call     instance var<u1>[] valuetype [mscorlib]System.ArraySegment`1<unsigned int8>::get_Array()
0xdc16  ldloca.s 5
0xdc18  call     instance int32 valuetype [mscorlib]System.ArraySegment`1<unsigned int8>::get_Count()
0xdc1d  ldloca.s 5
0xdc1f  call     instance int32 valuetype [mscorlib]System.ArraySegment`1<unsigned int8>::get_Offset()
0xdc24  add
0xdc25  ldloca.s 6
0xdc27  callvirt instance valuetype System.Net.Http.Formatting.Parsers.ParserState System.Net.Http.Formatting.Parsers.InternetMessageFormatHeaderParser::ParseBuffer(unsigned int8[] buffer, int32 bytesReady, int32& bytesConsumed)
0xdc2c  stfld    valuetype System.Net.Http.Formatting.Parsers.ParserState System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_bodyPartHeaderStatus
0xdc31  ldloc.1
0xdc32  ldfld    valuetype System.Net.Http.Formatting.Parsers.ParserState System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_bodyPartHeaderStatus
0xdc37  ldc.i4.1
0xdc38  bne.un.s loc_DC6C
0xdc3a  ldloc.1
0xdc3b  ldfld    class System.Net.Http.MimeBodyPart System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_currentBodyPart
0xdc40  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>> System.Net.Http.MimeBodyPart::get_Segments()
0xdc45  ldloca.s 5
0xdc47  call     instance var<u1>[] valuetype [mscorlib]System.ArraySegment`1<unsigned int8>::get_Array()
0xdc4c  ldloc.s  6
0xdc4e  ldloca.s 5
0xdc50  call     instance int32 valuetype [mscorlib]System.ArraySegment`1<unsigned int8>::get_Count()
0xdc55  ldloca.s 5
0xdc57  call     instance int32 valuetype [mscorlib]System.ArraySegment`1<unsigned int8>::get_Offset()
0xdc5c  add
0xdc5d  ldloc.s  6
0xdc5f  sub
0xdc60  newobj   instance void valuetype [mscorlib]System.ArraySegment`1<unsigned int8>::.ctor(var<u1>[], !!T0, int32)
0xdc65  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>>::Add(var<u1>)
0xdc6a  br.s     loc_DCB1
0xdc6c  ldloc.1
0xdc6d  ldfld    valuetype System.Net.Http.Formatting.Parsers.ParserState System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_bodyPartHeaderStatus
0xdc72  brfalse.s loc_DCB1
0xdc74  ldloc.1
0xdc75  call     instance void System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::CleanupCurrentBodyPart()
0xdc7a  call     string System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartHeaderParseError()
0xdc7f  ldc.i4.2
0xdc80  newarr   [mscorlib]System.Object
0xdc85  dup
0xdc86  ldc.i4.0
0xdc87  ldloc.s  6
0xdc89  box      [mscorlib]System.Int32
0xdc8e  stelem.ref
0xdc8f  dup
0xdc90  ldc.i4.1
0xdc91  ldloca.s 5
0xdc93  call     instance var<u1>[] valuetype [mscorlib]System.ArraySegment`1<unsigned int8>::get_Array()
0xdc98  stelem.ref
0xdc99  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0xdc9e  throw
0xdc9f  ldloc.1
0xdca0  ldfld    class System.Net.Http.MimeBodyPart System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_currentBodyPart
0xdca5  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>> System.Net.Http.MimeBodyPart::get_Segments()
0xdcaa  ldloc.s  5
0xdcac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>>::Add(var<u1>)
0xdcb1  ldloc.s  4
0xdcb3  ldc.i4.1
0xdcb4  add
0xdcb5  stloc.s  4
0xdcb7  ldloc.s  4
0xdcb9  ldloc.3
0xdcba  ldlen
0xdcbb  conv.i4
0xdcbc  blt      loc_DBD8
0xdcc1  ldloc.1
0xdcc2  ldfld    valuetype State System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_mimeStatus
0xdcc7  ldc.i4.1
0xdcc8  bne.un.s loc_DD27
0xdcca  ldloc.1
0xdccb  ldfld    class System.Net.Http.MimeBodyPart System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_currentBodyPart
0xdcd0  stloc.s  7
0xdcd2  ldloc.s  7
0xdcd4  ldc.i4.1
0xdcd5  callvirt instance void System.Net.Http.MimeBodyPart::set_IsComplete(bool value)
0xdcda  ldloc.s  7
0xdcdc  ldloc.2
0xdcdd  callvirt instance void System.Net.Http.MimeBodyPart::set_IsFinal(bool value)
0xdce2  ldloc.1
0xdce3  ldloc.1
0xdce4  ldfld    class System.Net.Http.MultipartStreamProvider System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_streamProvider
0xdce9  ldloc.1
0xdcea  ldfld    int32 System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_maxBodyPartHeaderSize
0xdcef  ldloc.1
0xdcf0  ldfld    class [System.Net.Http]System.Net.Http.HttpContent System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_content
0xdcf5  newobj   instance void System.Net.Http.MimeBodyPart::.ctor(class System.Net.Http.MultipartStreamProvider streamProvider, int32 maxBodyPartHeaderSize, class [System.Net.Http]System.Net.Http.HttpContent parentContent)
0xdcfa  stfld    class System.Net.Http.MimeBodyPart System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_currentBodyPart
0xdcff  ldloc.1
0xdd00  ldc.i4.0
0xdd01  stfld    valuetype State System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_mimeStatus
0xdd06  ldloc.1
0xdd07  ldc.i4.0
0xdd08  stfld    valuetype System.Net.Http.Formatting.Parsers.ParserState System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_bodyPartHeaderStatus
0xdd0d  ldarg.0
0xdd0e  ldloc.s  7
0xdd10  stfld    class System.Net.Http.MimeBodyPart <ParseBuffer>d__15::<>2__current
0xdd15  ldarg.0
0xdd16  ldc.i4.1
0xdd17  stfld    int32 <ParseBuffer>d__15::<>1__state
0xdd1c  ldc.i4.1
0xdd1d  ret
0xdd1e  ldarg.0
0xdd1f  ldc.i4.m1
0xdd20  stfld    int32 <ParseBuffer>d__15::<>1__state
0xdd25  br.s     loc_DD43
0xdd27  ldarg.0
0xdd28  ldloc.1
0xdd29  ldfld    class System.Net.Http.MimeBodyPart System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_currentBodyPart
0xdd2e  stfld    class System.Net.Http.MimeBodyPart <ParseBuffer>d__15::<>2__current
0xdd33  ldarg.0
0xdd34  ldc.i4.2
0xdd35  stfld    int32 <ParseBuffer>d__15::<>1__state
0xdd3a  ldc.i4.1
0xdd3b  ret
0xdd3c  ldarg.0
0xdd3d  ldc.i4.m1
0xdd3e  stfld    int32 <ParseBuffer>d__15::<>1__state
0xdd43  ldloc.1
0xdd44  ldfld    class System.Net.Http.Formatting.Parsers.MimeMultipartParser System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::_mimeParser
0xdd49  ldarg.0
0xdd4a  ldfld    int32 <ParseBuffer>d__15::bytesRead
0xdd4f  ldarg.0
0xdd50  ldfld    int32 <ParseBuffer>d__15::<bytesConsumed>5__2
0xdd55  callvirt instance bool System.Net.Http.Formatting.Parsers.MimeMultipartParser::CanParseMore(int32 bytesRead, int32 bytesConsumed)
0xdd5a  brtrue   loc_DB2D
0xdd5f  ldc.i4.0
0xdd60  ret
```
