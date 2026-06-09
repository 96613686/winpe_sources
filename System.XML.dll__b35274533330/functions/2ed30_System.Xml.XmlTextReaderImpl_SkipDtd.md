# System.Xml.XmlTextReaderImpl::SkipDtd

- ea: `0x2ed30`
- end: `0x2efc8`
- name: `System.Xml.XmlTextReaderImpl::SkipDtd`
- size: `664`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x2eb20`

## callees

- `0x10e60`
- `0x29740`
- `0x2a510`
- `0x2ed30`
- `0x2efd0`
- `0x2f020`
- `0x2f3d0`
- `0x2fad0`
- `0x313a0`
- `0x31500`
- `0xfeb70`

## string_xrefs

- `0x2ed76`: `Xml_UnexpectedEOF1`
- `0x2ee4e`: `Xml_UnexpectedEOF1`
- `0x2ef11`: `Xml_ExpectExternalOrClose`
- `0x2efad`: `Xml_ExpectSubOrClose`

## pseudocode

```c

```

## disassembly

```asm
0x2ed30  ldarg.0
0x2ed31  ldloca.s 0
0x2ed33  call     instance int32 System.Xml.XmlTextReaderImpl::ParseQName([out] int32& colonPos)
0x2ed38  stloc.1
0x2ed39  ldarg.0
0x2ed3a  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ed3f  ldloc.1
0x2ed40  stfld    int32 ParsingState::charPos
0x2ed45  ldarg.0
0x2ed46  ldnull
0x2ed47  call     instance int32 System.Xml.XmlTextReaderImpl::EatWhitespaces(class [mscorlib]System.Text.StringBuilder sb)
0x2ed4c  pop
0x2ed4d  ldarg.0
0x2ed4e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ed53  ldfld    char[] ParsingState::chars
0x2ed58  ldarg.0
0x2ed59  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ed5e  ldfld    int32 ParsingState::charPos
0x2ed63  ldelem.u2
0x2ed64  ldc.i4.s 0x50
0x2ed66  bne.un   loc_2EE25
0x2ed6b  br.s     loc_2ED80
0x2ed6d  ldarg.0
0x2ed6e  call     instance int32 System.Xml.XmlTextReaderImpl::ReadData()
0x2ed73  brtrue.s loc_2ED80
0x2ed75  ldarg.0
0x2ed76  ldstr    aXmlUnexpectede_0// "Xml_UnexpectedEOF1"
0x2ed7b  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x2ed80  ldarg.0
0x2ed81  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ed86  ldfld    int32 ParsingState::charsUsed
0x2ed8b  ldarg.0
0x2ed8c  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ed91  ldfld    int32 ParsingState::charPos
0x2ed96  sub
0x2ed97  ldc.i4.6
0x2ed98  blt.s    loc_2ED6D
0x2ed9a  ldarg.0
0x2ed9b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2eda0  ldfld    char[] ParsingState::chars
0x2eda5  ldarg.0
0x2eda6  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2edab  ldfld    int32 ParsingState::charPos
0x2edb0  ldc.i4.6
0x2edb1  ldstr    aPublic_0// "PUBLIC"
0x2edb6  call     bool System.Xml.XmlConvert::StrEqual(char[] chars, int32 strPos1, int32 strLen1, string str2)
0x2edbb  brtrue.s loc_2EDC8
0x2edbd  ldarg.0
0x2edbe  ldstr    aPublic_0// "PUBLIC"
0x2edc3  call     instance void System.Xml.XmlTextReaderImpl::ThrowUnexpectedToken(string expectedToken1)
0x2edc8  ldarg.0
0x2edc9  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2edce  ldflda   int32 ParsingState::charPos
0x2edd3  dup
0x2edd4  ldind.i4
0x2edd5  ldc.i4.6
0x2edd6  add
0x2edd7  stind.i4
0x2edd8  ldarg.0
0x2edd9  ldnull
0x2edda  call     instance int32 System.Xml.XmlTextReaderImpl::EatWhitespaces(class [mscorlib]System.Text.StringBuilder sb)
0x2eddf  brtrue.s loc_2EDF2
0x2ede1  ldarg.0
0x2ede2  ldarg.0
0x2ede3  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ede8  ldfld    int32 ParsingState::charPos
0x2eded  call     instance void System.Xml.XmlTextReaderImpl::ThrowExpectingWhitespace(int32 pos)
0x2edf2  ldarg.0
0x2edf3  call     instance void System.Xml.XmlTextReaderImpl::SkipPublicOrSystemIdLiteral()
0x2edf8  ldarg.0
0x2edf9  ldnull
0x2edfa  call     instance int32 System.Xml.XmlTextReaderImpl::EatWhitespaces(class [mscorlib]System.Text.StringBuilder sb)
0x2edff  brtrue.s loc_2EE12
0x2ee01  ldarg.0
0x2ee02  ldarg.0
0x2ee03  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ee08  ldfld    int32 ParsingState::charPos
0x2ee0d  call     instance void System.Xml.XmlTextReaderImpl::ThrowExpectingWhitespace(int32 pos)
0x2ee12  ldarg.0
0x2ee13  call     instance void System.Xml.XmlTextReaderImpl::SkipPublicOrSystemIdLiteral()
0x2ee18  ldarg.0
0x2ee19  ldnull
0x2ee1a  call     instance int32 System.Xml.XmlTextReaderImpl::EatWhitespaces(class [mscorlib]System.Text.StringBuilder sb)
0x2ee1f  pop
0x2ee20  br       loc_2EF1B
0x2ee25  ldarg.0
0x2ee26  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ee2b  ldfld    char[] ParsingState::chars
0x2ee30  ldarg.0
0x2ee31  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ee36  ldfld    int32 ParsingState::charPos
0x2ee3b  ldelem.u2
0x2ee3c  ldc.i4.s 0x53
0x2ee3e  bne.un   loc_2EEDA
0x2ee43  br.s     loc_2EE58
0x2ee45  ldarg.0
0x2ee46  call     instance int32 System.Xml.XmlTextReaderImpl::ReadData()
0x2ee4b  brtrue.s loc_2EE58
0x2ee4d  ldarg.0
0x2ee4e  ldstr    aXmlUnexpectede_0// "Xml_UnexpectedEOF1"
0x2ee53  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x2ee58  ldarg.0
0x2ee59  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ee5e  ldfld    int32 ParsingState::charsUsed
0x2ee63  ldarg.0
0x2ee64  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ee69  ldfld    int32 ParsingState::charPos
0x2ee6e  sub
0x2ee6f  ldc.i4.6
0x2ee70  blt.s    loc_2EE45
0x2ee72  ldarg.0
0x2ee73  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ee78  ldfld    char[] ParsingState::chars
0x2ee7d  ldarg.0
0x2ee7e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ee83  ldfld    int32 ParsingState::charPos
0x2ee88  ldc.i4.6
0x2ee89  ldstr    aSystem_0// "SYSTEM"
0x2ee8e  call     bool System.Xml.XmlConvert::StrEqual(char[] chars, int32 strPos1, int32 strLen1, string str2)
0x2ee93  brtrue.s loc_2EEA0
0x2ee95  ldarg.0
0x2ee96  ldstr    aSystem_0// "SYSTEM"
0x2ee9b  call     instance void System.Xml.XmlTextReaderImpl::ThrowUnexpectedToken(string expectedToken1)
0x2eea0  ldarg.0
0x2eea1  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2eea6  ldflda   int32 ParsingState::charPos
0x2eeab  dup
0x2eeac  ldind.i4
0x2eead  ldc.i4.6
0x2eeae  add
0x2eeaf  stind.i4
0x2eeb0  ldarg.0
0x2eeb1  ldnull
0x2eeb2  call     instance int32 System.Xml.XmlTextReaderImpl::EatWhitespaces(class [mscorlib]System.Text.StringBuilder sb)
0x2eeb7  brtrue.s loc_2EECA
0x2eeb9  ldarg.0
0x2eeba  ldarg.0
0x2eebb  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2eec0  ldfld    int32 ParsingState::charPos
0x2eec5  call     instance void System.Xml.XmlTextReaderImpl::ThrowExpectingWhitespace(int32 pos)
0x2eeca  ldarg.0
0x2eecb  call     instance void System.Xml.XmlTextReaderImpl::SkipPublicOrSystemIdLiteral()
0x2eed0  ldarg.0
0x2eed1  ldnull
0x2eed2  call     instance int32 System.Xml.XmlTextReaderImpl::EatWhitespaces(class [mscorlib]System.Text.StringBuilder sb)
0x2eed7  pop
0x2eed8  br.s     loc_2EF1B
0x2eeda  ldarg.0
0x2eedb  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2eee0  ldfld    char[] ParsingState::chars
0x2eee5  ldarg.0
0x2eee6  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2eeeb  ldfld    int32 ParsingState::charPos
0x2eef0  ldelem.u2
0x2eef1  ldc.i4.s 0x5B
0x2eef3  beq.s    loc_2EF1B
0x2eef5  ldarg.0
0x2eef6  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2eefb  ldfld    char[] ParsingState::chars
0x2ef00  ldarg.0
0x2ef01  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ef06  ldfld    int32 ParsingState::charPos
0x2ef0b  ldelem.u2
0x2ef0c  ldc.i4.s 0x3E
0x2ef0e  beq.s    loc_2EF1B
0x2ef10  ldarg.0
0x2ef11  ldstr    aXmlExpectexter// "Xml_ExpectExternalOrClose"
0x2ef16  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x2ef1b  ldarg.0
0x2ef1c  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ef21  ldfld    char[] ParsingState::chars
0x2ef26  ldarg.0
0x2ef27  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ef2c  ldfld    int32 ParsingState::charPos
0x2ef31  ldelem.u2
0x2ef32  ldc.i4.s 0x5B
0x2ef34  bne.un.s loc_2EF7F
0x2ef36  ldarg.0
0x2ef37  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ef3c  ldflda   int32 ParsingState::charPos
0x2ef41  dup
0x2ef42  ldind.i4
0x2ef43  ldc.i4.1
0x2ef44  add
0x2ef45  stind.i4
0x2ef46  ldarg.0
0x2ef47  ldc.i4.s 0x5D
0x2ef49  ldc.i4.1
0x2ef4a  call     instance void System.Xml.XmlTextReaderImpl::SkipUntil(char stopChar, bool recognizeLiterals)
0x2ef4f  ldarg.0
0x2ef50  ldnull
0x2ef51  call     instance int32 System.Xml.XmlTextReaderImpl::EatWhitespaces(class [mscorlib]System.Text.StringBuilder sb)
0x2ef56  pop
0x2ef57  ldarg.0
0x2ef58  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ef5d  ldfld    char[] ParsingState::chars
0x2ef62  ldarg.0
0x2ef63  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ef68  ldfld    int32 ParsingState::charPos
0x2ef6d  ldelem.u2
0x2ef6e  ldc.i4.s 0x3E
0x2ef70  beq.s    loc_2EFB7
0x2ef72  ldarg.0
0x2ef73  ldstr    asc_12A30E// ">"
0x2ef78  call     instance void System.Xml.XmlTextReaderImpl::ThrowUnexpectedToken(string expectedToken1)
0x2ef7d  br.s     loc_2EFB7
0x2ef7f  ldarg.0
0x2ef80  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ef85  ldfld    char[] ParsingState::chars
0x2ef8a  ldarg.0
0x2ef8b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ef90  ldfld    int32 ParsingState::charPos
0x2ef95  ldelem.u2
0x2ef96  ldc.i4.s 0x3E
0x2ef98  bne.un.s loc_2EFAC
0x2ef9a  ldarg.0
0x2ef9b  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2efa0  ldsfld   string [mscorlib]System.String::Empty
0x2efa5  callvirt instance void NodeData::SetValue(string value)
0x2efaa  br.s     loc_2EFB7
0x2efac  ldarg.0
0x2efad  ldstr    aXmlExpectsubor// "Xml_ExpectSubOrClose"
0x2efb2  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x2efb7  ldarg.0
0x2efb8  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2efbd  ldflda   int32 ParsingState::charPos
0x2efc2  dup
0x2efc3  ldind.i4
0x2efc4  ldc.i4.1
0x2efc5  add
0x2efc6  stind.i4
0x2efc7  ret
```
