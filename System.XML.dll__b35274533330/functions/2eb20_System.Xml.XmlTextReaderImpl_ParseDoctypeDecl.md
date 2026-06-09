# System.Xml.XmlTextReaderImpl::ParseDoctypeDecl

- ea: `0x2eb20`
- end: `0x2ec9a`
- name: `System.Xml.XmlTextReaderImpl::ParseDoctypeDecl`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x2b400`

## callees

- `0xef40`
- `0x10e60`
- `0x29720`
- `0x29770`
- `0x29890`
- `0x2a510`
- `0x2eb20`
- `0x2eca0`
- `0x2ed30`
- `0x2f3d0`
- `0x313a0`
- `0x31500`
- `0xfe500`
- `0xfe510`
- `0xfeab0`

## string_xrefs

- `0x2eb31`: `Xml_DtdIsProhibitedEx`
- `0x2eb4d`: `Xml_UnexpectedEOF`
- `0x2eb38`: `Xml_DtdIsProhibited`
- `0x2ec0a`: `Xml_MultipleDTDsProvided`
- `0x2ec2a`: `Xml_DtdAfterRootElement`

## pseudocode

```c

```

## disassembly

```asm
0x2eb20  ldarg.0
0x2eb21  ldfld    valuetype System.Xml.DtdProcessing System.Xml.XmlTextReaderImpl::dtdProcessing
0x2eb26  brtrue.s loc_2EB5C
0x2eb28  ldarg.0
0x2eb29  ldarg.0
0x2eb2a  ldfld    bool System.Xml.XmlTextReaderImpl::v1Compat
0x2eb2f  brtrue.s loc_2EB38
0x2eb31  ldstr    aXmlDtdisprohib// "Xml_DtdIsProhibitedEx"
0x2eb36  br.s     loc_2EB3D
0x2eb38  ldstr    aXmlDtdisprohib_0// "Xml_DtdIsProhibited"
0x2eb3d  call     instance void System.Xml.XmlTextReaderImpl::ThrowWithoutLineInfo(string res)
0x2eb42  br.s     loc_2EB5C
0x2eb44  ldarg.0
0x2eb45  call     instance int32 System.Xml.XmlTextReaderImpl::ReadData()
0x2eb4a  brtrue.s loc_2EB5C
0x2eb4c  ldarg.0
0x2eb4d  ldstr    aXmlUnexpectede// "Xml_UnexpectedEOF"
0x2eb52  ldstr    aDoctype_0// "DOCTYPE"
0x2eb57  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg)
0x2eb5c  ldarg.0
0x2eb5d  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2eb62  ldfld    int32 ParsingState::charsUsed
0x2eb67  ldarg.0
0x2eb68  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2eb6d  ldfld    int32 ParsingState::charPos
0x2eb72  sub
0x2eb73  ldc.i4.8
0x2eb74  blt.s    loc_2EB44
0x2eb76  ldarg.0
0x2eb77  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2eb7c  ldfld    char[] ParsingState::chars
0x2eb81  ldarg.0
0x2eb82  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2eb87  ldfld    int32 ParsingState::charPos
0x2eb8c  ldc.i4.7
0x2eb8d  ldstr    aDoctype_0// "DOCTYPE"
0x2eb92  call     bool System.Xml.XmlConvert::StrEqual(char[] chars, int32 strPos1, int32 strLen1, string str2)
0x2eb97  brtrue.s loc_2EBBB
0x2eb99  ldarg.0
0x2eb9a  ldarg.0
0x2eb9b  ldfld    bool System.Xml.XmlTextReaderImpl::rootElementParsed
0x2eba0  brtrue.s loc_2EBAA
0x2eba2  ldarg.0
0x2eba3  ldfld    class System.Xml.IDtdInfo System.Xml.XmlTextReaderImpl::dtdInfo
0x2eba8  brfalse.s loc_2EBB1
0x2ebaa  ldstr    asc_12B44E// "<!--"
0x2ebaf  br.s     loc_2EBB6
0x2ebb1  ldstr    aDoctype_0// "DOCTYPE"
0x2ebb6  call     instance void System.Xml.XmlTextReaderImpl::ThrowUnexpectedToken(string expectedToken1)
0x2ebbb  ldarg.0
0x2ebbc  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x2ebc1  ldarg.0
0x2ebc2  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ebc7  ldfld    char[] ParsingState::chars
0x2ebcc  ldarg.0
0x2ebcd  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ebd2  ldfld    int32 ParsingState::charPos
0x2ebd7  ldc.i4.7
0x2ebd8  add
0x2ebd9  ldelem.u2
0x2ebda  call     instance bool System.Xml.XmlCharType::IsWhiteSpace(char ch)
0x2ebdf  brtrue.s loc_2EBF4
0x2ebe1  ldarg.0
0x2ebe2  ldarg.0
0x2ebe3  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ebe8  ldfld    int32 ParsingState::charPos
0x2ebed  ldc.i4.7
0x2ebee  add
0x2ebef  call     instance void System.Xml.XmlTextReaderImpl::ThrowExpectingWhitespace(int32 pos)
0x2ebf4  ldarg.0
0x2ebf5  ldfld    class System.Xml.IDtdInfo System.Xml.XmlTextReaderImpl::dtdInfo
0x2ebfa  brfalse.s loc_2EC14
0x2ebfc  ldarg.0
0x2ebfd  ldarg.0
0x2ebfe  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ec03  ldfld    int32 ParsingState::charPos
0x2ec08  ldc.i4.2
0x2ec09  sub
0x2ec0a  ldstr    aXmlMultipledtd// "Xml_MultipleDTDsProvided"
0x2ec0f  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res)
0x2ec14  ldarg.0
0x2ec15  ldfld    bool System.Xml.XmlTextReaderImpl::rootElementParsed
0x2ec1a  brfalse.s loc_2EC34
0x2ec1c  ldarg.0
0x2ec1d  ldarg.0
0x2ec1e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ec23  ldfld    int32 ParsingState::charPos
0x2ec28  ldc.i4.2
0x2ec29  sub
0x2ec2a  ldstr    aXmlDtdafterroo// "Xml_DtdAfterRootElement"
0x2ec2f  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res)
0x2ec34  ldarg.0
0x2ec35  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ec3a  ldflda   int32 ParsingState::charPos
0x2ec3f  dup
0x2ec40  ldind.i4
0x2ec41  ldc.i4.8
0x2ec42  add
0x2ec43  stind.i4
0x2ec44  ldarg.0
0x2ec45  ldnull
0x2ec46  call     instance int32 System.Xml.XmlTextReaderImpl::EatWhitespaces(class [mscorlib]System.Text.StringBuilder sb)
0x2ec4b  pop
0x2ec4c  ldarg.0
0x2ec4d  ldfld    valuetype System.Xml.DtdProcessing System.Xml.XmlTextReaderImpl::dtdProcessing
0x2ec52  ldc.i4.2
0x2ec53  bne.un.s loc_2EC92
0x2ec55  ldarg.0
0x2ec56  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2ec5b  ldarg.0
0x2ec5c  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ec61  call     instance int32 ParsingState::get_LineNo()
0x2ec66  ldarg.0
0x2ec67  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ec6c  call     instance int32 ParsingState::get_LinePos()
0x2ec71  callvirt instance void NodeData::SetLineInfo(int32 lineNo, int32 linePos)
0x2ec76  ldarg.0
0x2ec77  call     instance void System.Xml.XmlTextReaderImpl::ParseDtd()
0x2ec7c  ldarg.0
0x2ec7d  ldarg.0
0x2ec7e  ldfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x2ec83  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::nextParsingFunction
0x2ec88  ldarg.0
0x2ec89  ldc.i4.s 9
0x2ec8b  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x2ec90  ldc.i4.1
0x2ec91  ret
0x2ec92  ldarg.0
0x2ec93  call     instance void System.Xml.XmlTextReaderImpl::SkipDtd()
0x2ec98  ldc.i4.0
0x2ec99  ret
```
