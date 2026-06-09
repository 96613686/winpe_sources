# System.Xml.XmlTextReaderImpl::ParseCDataOrComment_0

- ea: `0x2e860`
- end: `0x2eb1d`
- name: `System.Xml.XmlTextReaderImpl::ParseCDataOrComment_0`
- size: `701`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2e790`
- `0x30830`

## callees

- `0xf0f0`
- `0xf110`
- `0x29720`
- `0x29770`
- `0x298f0`
- `0x2a510`
- `0x2ab40`
- `0x2e860`
- `0x2ff90`

## string_xrefs

- `0x2e883`: `Xml_UnexpectedEOF`
- `0x2e893`: `Comment`
- `0x2e958`: `Xml_InvalidCommentChars`

## pseudocode

```c

```

## disassembly

```asm
0x2e860  ldarg.0
0x2e861  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e866  ldfld    int32 ParsingState::charsUsed
0x2e86b  ldarg.0
0x2e86c  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e871  ldfld    int32 ParsingState::charPos
0x2e876  sub
0x2e877  ldc.i4.3
0x2e878  bge.s    loc_2E89D
0x2e87a  ldarg.0
0x2e87b  call     instance int32 System.Xml.XmlTextReaderImpl::ReadData()
0x2e880  brtrue.s loc_2E89D
0x2e882  ldarg.0
0x2e883  ldstr    aXmlUnexpectede// "Xml_UnexpectedEOF"
0x2e888  ldarg.1
0x2e889  ldc.i4.8
0x2e88a  beq.s    loc_2E893
0x2e88c  ldstr    aCdata_1// "CDATA"
0x2e891  br.s     loc_2E898
0x2e893  ldstr    aComment_0// "Comment"
0x2e898  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg)
0x2e89d  ldarg.0
0x2e89e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e8a3  ldfld    int32 ParsingState::charPos
0x2e8a8  stloc.0
0x2e8a9  ldarg.0
0x2e8aa  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e8af  ldfld    char[] ParsingState::chars
0x2e8b4  stloc.1
0x2e8b5  ldc.i4.0
0x2e8b6  stloc.2
0x2e8b7  ldc.i4.m1
0x2e8b8  stloc.3
0x2e8b9  ldarg.1
0x2e8ba  ldc.i4.8
0x2e8bb  beq.s    loc_2E8C1
0x2e8bd  ldc.i4.s 0x5D
0x2e8bf  br.s     loc_2E8C3
0x2e8c1  ldc.i4.s 0x2D
0x2e8c3  stloc.s  4
0x2e8c5  br.s     loc_2E8CB
0x2e8c7  ldloc.0
0x2e8c8  ldc.i4.1
0x2e8c9  add
0x2e8ca  stloc.0
0x2e8cb  ldarg.0
0x2e8cc  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x2e8d1  ldfld    unsigned int8* System.Xml.XmlCharType::charProperties
0x2e8d6  ldloc.1
0x2e8d7  ldloc.0
0x2e8d8  ldelem.u2
0x2e8d9  dup
0x2e8da  stloc.s  5
0x2e8dc  add
0x2e8dd  ldind.u1
0x2e8de  ldc.i4.s 0x40
0x2e8e0  and
0x2e8e1  brfalse.s loc_2E8E9
0x2e8e3  ldloc.s  5
0x2e8e5  ldloc.s  4
0x2e8e7  bne.un.s loc_2E8C7
0x2e8e9  ldloc.1
0x2e8ea  ldloc.0
0x2e8eb  ldelem.u2
0x2e8ec  ldloc.s  4
0x2e8ee  bne.un   loc_2E980
0x2e8f3  ldloc.1
0x2e8f4  ldloc.0
0x2e8f5  ldc.i4.1
0x2e8f6  add
0x2e8f7  ldelem.u2
0x2e8f8  ldloc.s  4
0x2e8fa  bne.un.s loc_2E964
0x2e8fc  ldloc.1
0x2e8fd  ldloc.0
0x2e8fe  ldc.i4.2
0x2e8ff  add
0x2e900  ldelem.u2
0x2e901  ldc.i4.s 0x3E
0x2e903  bne.un.s loc_2E93F
0x2e905  ldloc.2
0x2e906  ldc.i4.0
0x2e907  ble.s    loc_2E91F
0x2e909  ldarg.0
0x2e90a  ldloc.3
0x2e90b  ldloc.2
0x2e90c  add
0x2e90d  ldloc.3
0x2e90e  ldloc.0
0x2e90f  ldloc.3
0x2e910  sub
0x2e911  ldloc.2
0x2e912  sub
0x2e913  call     instance void System.Xml.XmlTextReaderImpl::ShiftBuffer(int32 sourcePos, int32 destPos, int32 count)
0x2e918  ldarg.3
0x2e919  ldloc.0
0x2e91a  ldloc.2
0x2e91b  sub
0x2e91c  stind.i4
0x2e91d  br.s     loc_2E922
0x2e91f  ldarg.3
0x2e920  ldloc.0
0x2e921  stind.i4
0x2e922  ldarg.2
0x2e923  ldarg.0
0x2e924  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e929  ldfld    int32 ParsingState::charPos
0x2e92e  stind.i4
0x2e92f  ldarg.0
0x2e930  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e935  ldloc.0
0x2e936  ldc.i4.3
0x2e937  add
0x2e938  stfld    int32 ParsingState::charPos
0x2e93d  ldc.i4.1
0x2e93e  ret
0x2e93f  ldloc.0
0x2e940  ldc.i4.2
0x2e941  add
0x2e942  ldarg.0
0x2e943  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e948  ldfld    int32 ParsingState::charsUsed
0x2e94d  beq      loc_2EAE5
0x2e952  ldarg.1
0x2e953  ldc.i4.8
0x2e954  bne.un.s loc_2E977
0x2e956  ldarg.0
0x2e957  ldloc.0
0x2e958  ldstr    aXmlInvalidcomm// "Xml_InvalidCommentChars"
0x2e95d  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res)
0x2e962  br.s     loc_2E977
0x2e964  ldloc.0
0x2e965  ldc.i4.1
0x2e966  add
0x2e967  ldarg.0
0x2e968  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e96d  ldfld    int32 ParsingState::charsUsed
0x2e972  beq      loc_2EAE5
0x2e977  ldloc.0
0x2e978  ldc.i4.1
0x2e979  add
0x2e97a  stloc.0
0x2e97b  br       loc_2E8CB
0x2e980  ldloc.1
0x2e981  ldloc.0
0x2e982  ldelem.u2
0x2e983  stloc.s  7
0x2e985  ldloc.s  7
0x2e987  ldc.i4.s 0x26
0x2e989  bgt.un.s loc_2E9B7
0x2e98b  ldloc.s  7
0x2e98d  ldc.i4.s 9
0x2e98f  sub
0x2e990  switch   loc_2EA86, loc_2E9CE, loc_2EA8F, loc_2EA8F, loc_2E9DE
0x2e9a9  ldloc.s  7
0x2e9ab  ldc.i4.s 0x26
0x2e9ad  beq      loc_2EA86
0x2e9b2  br       loc_2EA8F
0x2e9b7  ldloc.s  7
0x2e9b9  ldc.i4.s 0x3C
0x2e9bb  beq      loc_2EA86
0x2e9c0  ldloc.s  7
0x2e9c2  ldc.i4.s 0x5D
0x2e9c4  beq      loc_2EA86
0x2e9c9  br       loc_2EA8F
0x2e9ce  ldloc.0
0x2e9cf  ldc.i4.1
0x2e9d0  add
0x2e9d1  stloc.0
0x2e9d2  ldarg.0
0x2e9d3  ldloc.0
0x2e9d4  call     instance void System.Xml.XmlTextReaderImpl::OnNewLine(int32 pos)
0x2e9d9  br       loc_2E8CB
0x2e9de  ldloc.1
0x2e9df  ldloc.0
0x2e9e0  ldc.i4.1
0x2e9e1  add
0x2e9e2  ldelem.u2
0x2e9e3  ldc.i4.s 0xA
0x2e9e5  bne.un.s loc_2EA44
0x2e9e7  ldarg.0
0x2e9e8  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e9ed  ldfld    bool ParsingState::eolNormalized
0x2e9f2  brtrue.s loc_2EA3E
0x2e9f4  ldarg.0
0x2e9f5  ldfld    valuetype ParsingMode System.Xml.XmlTextReaderImpl::parsingMode
0x2e9fa  brtrue.s loc_2EA3E
0x2e9fc  ldloc.0
0x2e9fd  ldarg.0
0x2e9fe  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ea03  ldfld    int32 ParsingState::charPos
0x2ea08  sub
0x2ea09  ldc.i4.0
0x2ea0a  ble.s    loc_2EA2E
0x2ea0c  ldloc.2
0x2ea0d  brtrue.s loc_2EA15
0x2ea0f  ldc.i4.1
0x2ea10  stloc.2
0x2ea11  ldloc.0
0x2ea12  stloc.3
0x2ea13  br.s     loc_2EA3E
0x2ea15  ldarg.0
0x2ea16  ldloc.3
0x2ea17  ldloc.2
0x2ea18  add
0x2ea19  ldloc.3
0x2ea1a  ldloc.0
0x2ea1b  ldloc.3
0x2ea1c  sub
0x2ea1d  ldloc.2
0x2ea1e  sub
0x2ea1f  call     instance void System.Xml.XmlTextReaderImpl::ShiftBuffer(int32 sourcePos, int32 destPos, int32 count)
0x2ea24  ldloc.0
0x2ea25  ldloc.2
0x2ea26  sub
0x2ea27  stloc.3
0x2ea28  ldloc.2
0x2ea29  ldc.i4.1
0x2ea2a  add
0x2ea2b  stloc.2
0x2ea2c  br.s     loc_2EA3E
0x2ea2e  ldarg.0
0x2ea2f  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ea34  ldflda   int32 ParsingState::charPos
0x2ea39  dup
0x2ea3a  ldind.i4
0x2ea3b  ldc.i4.1
0x2ea3c  add
0x2ea3d  stind.i4
0x2ea3e  ldloc.0
0x2ea3f  ldc.i4.2
0x2ea40  add
0x2ea41  stloc.0
0x2ea42  br.s     loc_2EA7A
0x2ea44  ldloc.0
0x2ea45  ldc.i4.1
0x2ea46  add
0x2ea47  ldarg.0
0x2ea48  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ea4d  ldfld    int32 ParsingState::charsUsed
0x2ea52  blt.s    loc_2EA64
0x2ea54  ldarg.0
0x2ea55  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ea5a  ldfld    bool ParsingState::isEof
0x2ea5f  brfalse  loc_2EAE5
0x2ea64  ldarg.0
0x2ea65  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ea6a  ldfld    bool ParsingState::eolNormalized
0x2ea6f  brtrue.s loc_2EA76
0x2ea71  ldloc.1
0x2ea72  ldloc.0
0x2ea73  ldc.i4.s 0xA
0x2ea75  stelem.i2
0x2ea76  ldloc.0
0x2ea77  ldc.i4.1
0x2ea78  add
0x2ea79  stloc.0
0x2ea7a  ldarg.0
0x2ea7b  ldloc.0
0x2ea7c  call     instance void System.Xml.XmlTextReaderImpl::OnNewLine(int32 pos)
0x2ea81  br       loc_2E8CB
0x2ea86  ldloc.0
0x2ea87  ldc.i4.1
0x2ea88  add
0x2ea89  stloc.0
0x2ea8a  br       loc_2E8CB
0x2ea8f  ldloc.0
0x2ea90  ldarg.0
0x2ea91  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ea96  ldfld    int32 ParsingState::charsUsed
0x2ea9b  beq.s    loc_2EAE5
0x2ea9d  ldloc.1
0x2ea9e  ldloc.0
0x2ea9f  ldelem.u2
0x2eaa0  stloc.s  6
0x2eaa2  ldloc.s  6
0x2eaa4  call     bool System.Xml.XmlCharType::IsHighSurrogate(int32 ch)
0x2eaa9  brfalse.s loc_2EAD2
0x2eaab  ldloc.0
0x2eaac  ldc.i4.1
0x2eaad  add
0x2eaae  ldarg.0
0x2eaaf  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2eab4  ldfld    int32 ParsingState::charsUsed
0x2eab9  beq.s    loc_2EAE5
0x2eabb  ldloc.0
0x2eabc  ldc.i4.1
0x2eabd  add
0x2eabe  stloc.0
0x2eabf  ldloc.1
0x2eac0  ldloc.0
0x2eac1  ldelem.u2
0x2eac2  call     bool System.Xml.XmlCharType::IsLowSurrogate(int32 ch)
0x2eac7  brfalse.s loc_2EAD2
0x2eac9  ldloc.0
0x2eaca  ldc.i4.1
0x2eacb  add
0x2eacc  stloc.0
0x2eacd  br       loc_2E8CB
0x2ead2  ldarg.0
  ... truncated ...
```
