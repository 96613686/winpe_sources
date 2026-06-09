# System.Xml.XmlTextReaderImpl::ParseXmlDeclaration

- ea: `0x2ab60`
- end: `0x2b3fb`
- name: `System.Xml.XmlTextReaderImpl::ParseXmlDeclaration`
- size: `2203`
- prototype: ``
- caller_count: `4`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x27ee0`
- `0x29570`
- `0x303c0`
- `0x31360`

## callees

- `0xef80`
- `0x10e60`
- `0x29740`
- `0x29750`
- `0x29770`
- `0x2a280`
- `0x2a2e0`
- `0x2a500`
- `0x2a510`
- `0x2ab60`
- `0x2f3d0`
- `0x2fac0`
- `0x2fd60`
- `0x313a0`
- `0x313d0`
- `0xfe500`
- `0xfe510`
- `0xfeab0`
- `0xfeac0`
- `0xfeb20`
- `0xfeb70`
- `0xfeb80`

## string_xrefs

- `0x2ad51`: `Xml_EncodingSwitchAfterResetState`
- `0x2b3a7`: `Xml_EncodingSwitchAfterResetState`
- `0x2ab9e`: `<?xml`
- `0x2ac96`: `Xml_InvalidXmlDecl`
- `0x2af19`: `Xml_InvalidXmlDecl`
- `0x2b24c`: `Xml_InvalidXmlDecl`
- `0x2b308`: `Xml_InvalidXmlDecl`
- `0x2ac9d`: `Xml_InvalidTextDecl`
- `0x2acf0`: `Xml_InvalidTextDecl`
- `0x2af20`: `Xml_InvalidTextDecl`
- `0x2b30f`: `Xml_InvalidTextDecl`
- `0x2b181`: `Xml_InvalidVersionNumber`
- `0x2b2f8`: `Xml_UnclosedQuote`
- `0x2b332`: `Xml_UnexpectedEOF1`

## pseudocode

```c

```

## disassembly

```asm
0x2ab60  br.s     loc_2AB6D
0x2ab62  ldarg.0
0x2ab63  call     instance int32 System.Xml.XmlTextReaderImpl::ReadData()
0x2ab68  brfalse  loc_2B341
0x2ab6d  ldarg.0
0x2ab6e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ab73  ldfld    int32 ParsingState::charsUsed
0x2ab78  ldarg.0
0x2ab79  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ab7e  ldfld    int32 ParsingState::charPos
0x2ab83  sub
0x2ab84  ldc.i4.6
0x2ab85  blt.s    loc_2AB62
0x2ab87  ldarg.0
0x2ab88  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ab8d  ldfld    char[] ParsingState::chars
0x2ab92  ldarg.0
0x2ab93  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ab98  ldfld    int32 ParsingState::charPos
0x2ab9d  ldc.i4.5
0x2ab9e  ldstr    aXml_1// "<?xml"
0x2aba3  call     bool System.Xml.XmlConvert::StrEqual(char[] chars, int32 strPos1, int32 strLen1, string str2)
0x2aba8  brfalse  loc_2B341
0x2abad  ldarg.0
0x2abae  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x2abb3  ldarg.0
0x2abb4  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2abb9  ldfld    char[] ParsingState::chars
0x2abbe  ldarg.0
0x2abbf  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2abc4  ldfld    int32 ParsingState::charPos
0x2abc9  ldc.i4.5
0x2abca  add
0x2abcb  ldelem.u2
0x2abcc  call     instance bool System.Xml.XmlCharType::IsNameSingleChar(char ch)
0x2abd1  brtrue   loc_2B341
0x2abd6  ldarg.1
0x2abd7  brtrue.s loc_2AC0F
0x2abd9  ldarg.0
0x2abda  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2abdf  ldarg.0
0x2abe0  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2abe5  call     instance int32 ParsingState::get_LineNo()
0x2abea  ldarg.0
0x2abeb  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2abf0  call     instance int32 ParsingState::get_LinePos()
0x2abf5  ldc.i4.2
0x2abf6  add
0x2abf7  callvirt instance void NodeData::SetLineInfo(int32 lineNo, int32 linePos)
0x2abfc  ldarg.0
0x2abfd  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2ac02  ldc.i4.s 0x11
0x2ac04  ldarg.0
0x2ac05  ldfld    string System.Xml.XmlTextReaderImpl::Xml
0x2ac0a  callvirt instance void NodeData::SetNamedNode(valuetype System.Xml.XmlNodeType type, string localName)
0x2ac0f  ldarg.0
0x2ac10  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ac15  ldflda   int32 ParsingState::charPos
0x2ac1a  dup
0x2ac1b  ldind.i4
0x2ac1c  ldc.i4.5
0x2ac1d  add
0x2ac1e  stind.i4
0x2ac1f  ldarg.1
0x2ac20  brtrue.s loc_2AC2A
0x2ac22  ldarg.0
0x2ac23  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x2ac28  br.s     loc_2AC2F
0x2ac2a  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2ac2f  stloc.0
0x2ac30  ldc.i4.0
0x2ac31  stloc.1
0x2ac32  ldnull
0x2ac33  stloc.2
0x2ac34  ldloc.0
0x2ac35  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x2ac3a  stloc.3
0x2ac3b  ldarg.0
0x2ac3c  ldloc.1
0x2ac3d  brfalse.s loc_2AC42
0x2ac3f  ldloc.0
0x2ac40  br.s     loc_2AC43
0x2ac42  ldnull
0x2ac43  call     instance int32 System.Xml.XmlTextReaderImpl::EatWhitespaces(class [mscorlib]System.Text.StringBuilder sb)
0x2ac48  stloc.s  4
0x2ac4a  ldarg.0
0x2ac4b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ac50  ldfld    char[] ParsingState::chars
0x2ac55  ldarg.0
0x2ac56  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ac5b  ldfld    int32 ParsingState::charPos
0x2ac60  ldelem.u2
0x2ac61  ldc.i4.s 0x3F
0x2ac63  bne.un   loc_2ADD6
0x2ac68  ldloc.0
0x2ac69  ldloc.3
0x2ac6a  callvirt instance void [mscorlib]System.Text.StringBuilder::set_Length(int32)
0x2ac6f  ldarg.0
0x2ac70  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ac75  ldfld    char[] ParsingState::chars
0x2ac7a  ldarg.0
0x2ac7b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ac80  ldfld    int32 ParsingState::charPos
0x2ac85  ldc.i4.1
0x2ac86  add
0x2ac87  ldelem.u2
0x2ac88  ldc.i4.s 0x3E
0x2ac8a  bne.un   loc_2ADAE
0x2ac8f  ldloc.1
0x2ac90  brtrue.s loc_2ACA7
0x2ac92  ldarg.0
0x2ac93  ldarg.1
0x2ac94  brtrue.s loc_2AC9D
0x2ac96  ldstr    aXmlInvalidxmld// "Xml_InvalidXmlDecl"
0x2ac9b  br.s     loc_2ACA2
0x2ac9d  ldstr    aXmlInvalidtext// "Xml_InvalidTextDecl"
0x2aca2  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x2aca7  ldarg.0
0x2aca8  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2acad  ldflda   int32 ParsingState::charPos
0x2acb2  dup
0x2acb3  ldind.i4
0x2acb4  ldc.i4.2
0x2acb5  add
0x2acb6  stind.i4
0x2acb7  ldarg.1
0x2acb8  brtrue.s loc_2ACE6
0x2acba  ldarg.0
0x2acbb  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2acc0  ldloc.0
0x2acc1  callvirt instance string [mscorlib]System.Object::ToString()
0x2acc6  callvirt instance void NodeData::SetValue(string value)
0x2accb  ldloc.0
0x2accc  ldc.i4.0
0x2accd  callvirt instance void [mscorlib]System.Text.StringBuilder::set_Length(int32)
0x2acd2  ldarg.0
0x2acd3  ldarg.0
0x2acd4  ldfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x2acd9  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::nextParsingFunction
0x2acde  ldarg.0
0x2acdf  ldc.i4.s 9
0x2ace1  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x2ace6  ldloc.2
0x2ace7  brtrue   loc_2AD99
0x2acec  ldarg.1
0x2aced  brfalse.s loc_2ACFA
0x2acef  ldarg.0
0x2acf0  ldstr    aXmlInvalidtext// "Xml_InvalidTextDecl"
0x2acf5  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x2acfa  ldarg.0
0x2acfb  ldfld    bool System.Xml.XmlTextReaderImpl::afterResetState
0x2ad00  brfalse.s loc_2AD7F
0x2ad02  ldarg.0
0x2ad03  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ad08  ldfld    class [mscorlib]System.Text.Encoding ParsingState::encoding
0x2ad0d  callvirt instance string [mscorlib]System.Text.Encoding::get_WebName()
0x2ad12  stloc.s  0xA
0x2ad14  ldloc.s  0xA
0x2ad16  ldstr    aUtf8// "utf-8"
0x2ad1b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2ad20  brfalse.s loc_2AD7F
0x2ad22  ldloc.s  0xA
0x2ad24  ldstr    aUtf16// "utf-16"
0x2ad29  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2ad2e  brfalse.s loc_2AD7F
0x2ad30  ldloc.s  0xA
0x2ad32  ldstr    aUtf16be// "utf-16BE"
0x2ad37  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2ad3c  brfalse.s loc_2AD7F
0x2ad3e  ldarg.0
0x2ad3f  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ad44  ldfld    class [mscorlib]System.Text.Encoding ParsingState::encoding
0x2ad49  isinst   System.Xml.Ucs4Encoding
0x2ad4e  brtrue.s loc_2AD7F
0x2ad50  ldarg.0
0x2ad51  ldstr    aXmlEncodingswi// "Xml_EncodingSwitchAfterResetState"
0x2ad56  ldarg.0
0x2ad57  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ad5c  ldfld    class [mscorlib]System.Text.Encoding ParsingState::encoding
0x2ad61  ldstr    aA// "A"
0x2ad66  callvirt instance int32 [mscorlib]System.Text.Encoding::GetByteCount(string)
0x2ad6b  ldc.i4.1
0x2ad6c  beq.s    loc_2AD75
0x2ad6e  ldstr    aUtf16_0// "UTF-16"
0x2ad73  br.s     loc_2AD7A
0x2ad75  ldstr    aUtf8_0// "UTF-8"
0x2ad7a  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg)
0x2ad7f  ldarg.0
0x2ad80  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ad85  ldfld    class [mscorlib]System.Text.Decoder ParsingState::decoder
0x2ad8a  isinst   System.Xml.SafeAsciiDecoder
0x2ad8f  brfalse.s loc_2ADA0
0x2ad91  ldarg.0
0x2ad92  call     instance void System.Xml.XmlTextReaderImpl::SwitchEncodingToUTF8()
0x2ad97  br.s     loc_2ADA0
0x2ad99  ldarg.0
0x2ad9a  ldloc.2
0x2ad9b  call     instance void System.Xml.XmlTextReaderImpl::SwitchEncoding(class [mscorlib]System.Text.Encoding newEncoding)
0x2ada0  ldarg.0
0x2ada1  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ada6  ldc.i4.0
0x2ada7  stfld    bool ParsingState::appendMode
0x2adac  ldc.i4.1
0x2adad  ret
0x2adae  ldarg.0
0x2adaf  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2adb4  ldfld    int32 ParsingState::charPos
0x2adb9  ldc.i4.1
0x2adba  add
0x2adbb  ldarg.0
0x2adbc  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2adc1  ldfld    int32 ParsingState::charsUsed
0x2adc6  beq      loc_2B319
0x2adcb  ldarg.0
0x2adcc  ldstr    asc_12B326// "'>'"
0x2add1  call     instance void System.Xml.XmlTextReaderImpl::ThrowUnexpectedToken(string expectedToken1)
0x2add6  ldloc.s  4
0x2add8  brtrue.s loc_2ADE8
0x2adda  ldloc.1
0x2addb  brfalse.s loc_2ADE8
0x2addd  ldarg.0
0x2adde  ldstr    asc_12AF48// "?>"
0x2ade3  call     instance void System.Xml.XmlTextReaderImpl::ThrowUnexpectedToken(string expectedToken1)
0x2ade8  ldarg.0
0x2ade9  call     instance int32 System.Xml.XmlTextReaderImpl::ParseName()
0x2adee  stloc.s  5
0x2adf0  ldnull
0x2adf1  stloc.s  6
0x2adf3  ldarg.0
0x2adf4  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2adf9  ldfld    char[] ParsingState::chars
0x2adfe  ldarg.0
0x2adff  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ae04  ldfld    int32 ParsingState::charPos
0x2ae09  ldelem.u2
0x2ae0a  stloc.s  0xB
0x2ae0c  ldloc.s  0xB
0x2ae0e  ldc.i4.s 0x65
0x2ae10  beq.s    loc_2AE76
0x2ae12  ldloc.s  0xB
0x2ae14  ldc.i4.s 0x73
0x2ae16  beq      loc_2AEC5
0x2ae1b  ldloc.s  0xB
0x2ae1d  ldc.i4.s 0x76
0x2ae1f  bne.un   loc_2AF15
0x2ae24  ldarg.0
0x2ae25  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ae2a  ldfld    char[] ParsingState::chars
0x2ae2f  ldarg.0
0x2ae30  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ae35  ldfld    int32 ParsingState::charPos
0x2ae3a  ldloc.s  5
0x2ae3c  ldarg.0
0x2ae3d  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ae42  ldfld    int32 ParsingState::charPos
0x2ae47  sub
0x2ae48  ldstr    aVersion_0// "version"
0x2ae4d  call     bool System.Xml.XmlConvert::StrEqual(char[] chars, int32 strPos1, int32 strLen1, string str2)
0x2ae52  brfalse  loc_2AF15
0x2ae57  ldloc.1
0x2ae58  brtrue   loc_2AF15
0x2ae5d  ldarg.1
0x2ae5e  brtrue   loc_2AF2A
0x2ae63  ldarg.0
0x2ae64  ldstr    aVersion_0// "version"
0x2ae69  ldc.i4.1
0x2ae6a  call     instance class NodeData System.Xml.XmlTextReaderImpl::AddAttributeNoChecks(string name, int32 attrDepth)
0x2ae6f  stloc.s  6
0x2ae71  br       loc_2AF2A
0x2ae76  ldarg.0
0x2ae77  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ae7c  ldfld    char[] ParsingState::chars
0x2ae81  ldarg.0
0x2ae82  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ae87  ldfld    int32 ParsingState::charPos
0x2ae8c  ldloc.s  5
0x2ae8e  ldarg.0
0x2ae8f  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ae94  ldfld    int32 ParsingState::charPos
0x2ae99  sub
0x2ae9a  ldstr    aEncoding_0// "encoding"
0x2ae9f  call     bool System.Xml.XmlConvert::StrEqual(char[] chars, int32 strPos1, int32 strLen1, string str2)
0x2aea4  brfalse.s loc_2AF15
0x2aea6  ldloc.1
0x2aea7  ldc.i4.1
0x2aea8  beq.s    loc_2AEB0
0x2aeaa  ldarg.1
0x2aeab  brfalse.s loc_2AF15
0x2aead  ldloc.1
0x2aeae  brtrue.s loc_2AF15
0x2aeb0  ldarg.1
0x2aeb1  brtrue.s loc_2AEC1
0x2aeb3  ldarg.0
0x2aeb4  ldstr    aEncoding_0// "encoding"
0x2aeb9  ldc.i4.1
0x2aeba  call     instance class NodeData System.Xml.XmlTextReaderImpl::AddAttributeNoChecks(string name, int32 attrDepth)
0x2aebf  stloc.s  6
0x2aec1  ldc.i4.1
0x2aec2  stloc.1
0x2aec3  br.s     loc_2AF2A
  ... truncated ...
```
