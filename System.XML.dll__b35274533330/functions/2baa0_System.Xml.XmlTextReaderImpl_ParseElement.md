# System.Xml.XmlTextReaderImpl::ParseElement

- ea: `0x2baa0`
- end: `0x2bd7a`
- name: `System.Xml.XmlTextReaderImpl::ParseElement`
- size: `730`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x2b400`
- `0x2b7b0`

## callees

- `0x10e60`
- `0x12920`
- `0x12940`
- `0x12bc0`
- `0x131f0`
- `0x296e0`
- `0x29700`
- `0x2a510`
- `0x2baa0`
- `0x2bd80`
- `0x2c2b0`
- `0x2c760`
- `0x2fad0`
- `0x31390`
- `0xfe500`
- `0xfe510`
- `0xfe980`
- `0xfeab0`
- `0xfeb20`
- `0xfeb30`

## string_xrefs

- `0x2bb22`: `Xml_BadNameChar`
- `0x2bd49`: `Xml_BadNameChar`
- `0x2bcda`: `Xml_UnexpectedEOF`

## pseudocode

```c

```

## disassembly

```asm
0x2baa0  ldarg.0
0x2baa1  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2baa6  ldfld    int32 ParsingState::charPos
0x2baab  stloc.0
0x2baac  ldarg.0
0x2baad  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bab2  ldfld    char[] ParsingState::chars
0x2bab7  stloc.1
0x2bab8  ldc.i4.m1
0x2bab9  stloc.2
0x2baba  ldarg.0
0x2babb  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2bac0  ldarg.0
0x2bac1  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bac6  call     instance int32 ParsingState::get_LineNo()
0x2bacb  ldarg.0
0x2bacc  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bad1  call     instance int32 ParsingState::get_LinePos()
0x2bad6  callvirt instance void NodeData::SetLineInfo(int32 lineNo, int32 linePos)
0x2badb  ldarg.0
0x2badc  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x2bae1  ldfld    unsigned int8* System.Xml.XmlCharType::charProperties
0x2bae6  ldloc.1
0x2bae7  ldloc.0
0x2bae8  ldelem.u2
0x2bae9  add
0x2baea  ldind.u1
0x2baeb  ldc.i4.4
0x2baec  and
0x2baed  brfalse.s loc_2BB54
0x2baef  ldloc.0
0x2baf0  ldc.i4.1
0x2baf1  add
0x2baf2  stloc.0
0x2baf3  ldarg.0
0x2baf4  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x2baf9  ldfld    unsigned int8* System.Xml.XmlCharType::charProperties
0x2bafe  ldloc.1
0x2baff  ldloc.0
0x2bb00  ldelem.u2
0x2bb01  add
0x2bb02  ldind.u1
0x2bb03  ldc.i4.8
0x2bb04  and
0x2bb05  brfalse.s loc_2BB0D
0x2bb07  ldloc.0
0x2bb08  ldc.i4.1
0x2bb09  add
0x2bb0a  stloc.0
0x2bb0b  br.s     loc_2BAF3
0x2bb0d  ldloc.1
0x2bb0e  ldloc.0
0x2bb0f  ldelem.u2
0x2bb10  ldc.i4.s 0x3A
0x2bb12  bne.un.s loc_2BB44
0x2bb14  ldloc.2
0x2bb15  ldc.i4.m1
0x2bb16  beq.s    loc_2BB3C
0x2bb18  ldarg.0
0x2bb19  ldfld    bool System.Xml.XmlTextReaderImpl::supportNamespaces
0x2bb1e  brfalse.s loc_2BB36
0x2bb20  ldarg.0
0x2bb21  ldloc.0
0x2bb22  ldstr    aXmlBadnamechar// "Xml_BadNameChar"
0x2bb27  ldc.i4.s 0x3A
0x2bb29  ldc.i4.0
0x2bb2a  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char invChar, char nextChar)
0x2bb2f  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res, string[] args)
0x2bb34  br.s     loc_2BB54
0x2bb36  ldloc.0
0x2bb37  ldc.i4.1
0x2bb38  add
0x2bb39  stloc.0
0x2bb3a  br.s     loc_2BAF3
0x2bb3c  ldloc.0
0x2bb3d  stloc.2
0x2bb3e  ldloc.0
0x2bb3f  ldc.i4.1
0x2bb40  add
0x2bb41  stloc.0
0x2bb42  br.s     loc_2BADB
0x2bb44  ldloc.0
0x2bb45  ldc.i4.1
0x2bb46  add
0x2bb47  ldarg.0
0x2bb48  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bb4d  ldfld    int32 ParsingState::charsUsed
0x2bb52  blt.s    loc_2BB69
0x2bb54  ldarg.0
0x2bb55  ldloca.s 2
0x2bb57  call     instance int32 System.Xml.XmlTextReaderImpl::ParseQName([out] int32& colonPos)
0x2bb5c  stloc.0
0x2bb5d  ldarg.0
0x2bb5e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bb63  ldfld    char[] ParsingState::chars
0x2bb68  stloc.1
0x2bb69  ldarg.0
0x2bb6a  ldfld    class System.Xml.XmlNamespaceManager System.Xml.XmlTextReaderImpl::namespaceManager
0x2bb6f  callvirt instance void System.Xml.XmlNamespaceManager::PushScope()
0x2bb74  ldloc.2
0x2bb75  ldc.i4.m1
0x2bb76  beq.s    loc_2BB80
0x2bb78  ldarg.0
0x2bb79  ldfld    bool System.Xml.XmlTextReaderImpl::supportNamespaces
0x2bb7e  brtrue.s loc_2BBB5
0x2bb80  ldarg.0
0x2bb81  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2bb86  ldc.i4.1
0x2bb87  ldarg.0
0x2bb88  ldfld    class System.Xml.XmlNameTable System.Xml.XmlTextReaderImpl::nameTable
0x2bb8d  ldloc.1
0x2bb8e  ldarg.0
0x2bb8f  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bb94  ldfld    int32 ParsingState::charPos
0x2bb99  ldloc.0
0x2bb9a  ldarg.0
0x2bb9b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bba0  ldfld    int32 ParsingState::charPos
0x2bba5  sub
0x2bba6  callvirt instance string System.Xml.XmlNameTable::Add(char[] array, int32 offset, int32 length)
0x2bbab  callvirt instance void NodeData::SetNamedNode(valuetype System.Xml.XmlNodeType type, string localName)
0x2bbb0  br       loc_2BC5D
0x2bbb5  ldarg.0
0x2bbb6  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bbbb  ldfld    int32 ParsingState::charPos
0x2bbc0  stloc.s  5
0x2bbc2  ldloc.2
0x2bbc3  ldloc.s  5
0x2bbc5  sub
0x2bbc6  stloc.s  6
0x2bbc8  ldloc.s  6
0x2bbca  ldarg.0
0x2bbcb  ldfld    string System.Xml.XmlTextReaderImpl::lastPrefix
0x2bbd0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2bbd5  bne.un.s loc_2BC12
0x2bbd7  ldloc.1
0x2bbd8  ldloc.s  5
0x2bbda  ldloc.s  6
0x2bbdc  ldarg.0
0x2bbdd  ldfld    string System.Xml.XmlTextReaderImpl::lastPrefix
0x2bbe2  call     bool System.Xml.XmlConvert::StrEqual(char[] chars, int32 strPos1, int32 strLen1, string str2)
0x2bbe7  brfalse.s loc_2BC12
0x2bbe9  ldarg.0
0x2bbea  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2bbef  ldc.i4.1
0x2bbf0  ldarg.0
0x2bbf1  ldfld    class System.Xml.XmlNameTable System.Xml.XmlTextReaderImpl::nameTable
0x2bbf6  ldloc.1
0x2bbf7  ldloc.2
0x2bbf8  ldc.i4.1
0x2bbf9  add
0x2bbfa  ldloc.0
0x2bbfb  ldloc.2
0x2bbfc  sub
0x2bbfd  ldc.i4.1
0x2bbfe  sub
0x2bbff  callvirt instance string System.Xml.XmlNameTable::Add(char[] array, int32 offset, int32 length)
0x2bc04  ldarg.0
0x2bc05  ldfld    string System.Xml.XmlTextReaderImpl::lastPrefix
0x2bc0a  ldnull
0x2bc0b  callvirt instance void NodeData::SetNamedNode(valuetype System.Xml.XmlNodeType type, string localName, string prefix, string nameWPrefix)
0x2bc10  br.s     loc_2BC5D
0x2bc12  ldarg.0
0x2bc13  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2bc18  ldc.i4.1
0x2bc19  ldarg.0
0x2bc1a  ldfld    class System.Xml.XmlNameTable System.Xml.XmlTextReaderImpl::nameTable
0x2bc1f  ldloc.1
0x2bc20  ldloc.2
0x2bc21  ldc.i4.1
0x2bc22  add
0x2bc23  ldloc.0
0x2bc24  ldloc.2
0x2bc25  sub
0x2bc26  ldc.i4.1
0x2bc27  sub
0x2bc28  callvirt instance string System.Xml.XmlNameTable::Add(char[] array, int32 offset, int32 length)
0x2bc2d  ldarg.0
0x2bc2e  ldfld    class System.Xml.XmlNameTable System.Xml.XmlTextReaderImpl::nameTable
0x2bc33  ldloc.1
0x2bc34  ldarg.0
0x2bc35  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bc3a  ldfld    int32 ParsingState::charPos
0x2bc3f  ldloc.s  6
0x2bc41  callvirt instance string System.Xml.XmlNameTable::Add(char[] array, int32 offset, int32 length)
0x2bc46  ldnull
0x2bc47  callvirt instance void NodeData::SetNamedNode(valuetype System.Xml.XmlNodeType type, string localName, string prefix, string nameWPrefix)
0x2bc4c  ldarg.0
0x2bc4d  ldarg.0
0x2bc4e  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2bc53  ldfld    string NodeData::prefix
0x2bc58  stfld    string System.Xml.XmlTextReaderImpl::lastPrefix
0x2bc5d  ldloc.1
0x2bc5e  ldloc.0
0x2bc5f  ldelem.u2
0x2bc60  stloc.3
0x2bc61  ldarg.0
0x2bc62  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x2bc67  ldfld    unsigned int8* System.Xml.XmlCharType::charProperties
0x2bc6c  ldloc.3
0x2bc6d  add
0x2bc6e  ldind.u1
0x2bc6f  ldc.i4.1
0x2bc70  and
0x2bc71  ldc.i4.0
0x2bc72  cgt.un
0x2bc74  stloc.s  4
0x2bc76  ldloc.s  4
0x2bc78  brfalse.s loc_2BC8D
0x2bc7a  ldarg.0
0x2bc7b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bc80  ldloc.0
0x2bc81  stfld    int32 ParsingState::charPos
0x2bc86  ldarg.0
0x2bc87  call     instance void System.Xml.XmlTextReaderImpl::ParseAttributes()
0x2bc8c  ret
0x2bc8d  ldloc.3
0x2bc8e  ldc.i4.s 0x3E
0x2bc90  bne.un.s loc_2BCAC
0x2bc92  ldarg.0
0x2bc93  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bc98  ldloc.0
0x2bc99  ldc.i4.1
0x2bc9a  add
0x2bc9b  stfld    int32 ParsingState::charPos
0x2bca0  ldarg.0
0x2bca1  ldc.i4.6
0x2bca2  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x2bca7  br       loc_2BD65
0x2bcac  ldloc.3
0x2bcad  ldc.i4.s 0x2F
0x2bcaf  bne.un   loc_2BD47
0x2bcb4  ldloc.0
0x2bcb5  ldc.i4.1
0x2bcb6  add
0x2bcb7  ldarg.0
0x2bcb8  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bcbd  ldfld    int32 ParsingState::charsUsed
0x2bcc2  bne.un.s loc_2BD01
0x2bcc4  ldarg.0
0x2bcc5  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bcca  ldloc.0
0x2bccb  stfld    int32 ParsingState::charPos
0x2bcd0  ldarg.0
0x2bcd1  call     instance int32 System.Xml.XmlTextReaderImpl::ReadData()
0x2bcd6  brtrue.s loc_2BCE9
0x2bcd8  ldarg.0
0x2bcd9  ldloc.0
0x2bcda  ldstr    aXmlUnexpectede// "Xml_UnexpectedEOF"
0x2bcdf  ldstr    asc_12A30E// ">"
0x2bce4  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res, string arg)
0x2bce9  ldarg.0
0x2bcea  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bcef  ldfld    int32 ParsingState::charPos
0x2bcf4  stloc.0
0x2bcf5  ldarg.0
0x2bcf6  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bcfb  ldfld    char[] ParsingState::chars
0x2bd00  stloc.1
0x2bd01  ldloc.1
0x2bd02  ldloc.0
0x2bd03  ldc.i4.1
0x2bd04  add
0x2bd05  ldelem.u2
0x2bd06  ldc.i4.s 0x3E
0x2bd08  bne.un.s loc_2BD39
0x2bd0a  ldarg.0
0x2bd0b  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2bd10  ldc.i4.1
0x2bd11  callvirt instance void NodeData::set_IsEmptyElement(bool value)
0x2bd16  ldarg.0
0x2bd17  ldarg.0
0x2bd18  ldfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x2bd1d  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::nextParsingFunction
0x2bd22  ldarg.0
0x2bd23  ldc.i4.8
0x2bd24  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x2bd29  ldarg.0
0x2bd2a  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bd2f  ldloc.0
0x2bd30  ldc.i4.2
0x2bd31  add
0x2bd32  stfld    int32 ParsingState::charPos
0x2bd37  br.s     loc_2BD65
0x2bd39  ldarg.0
0x2bd3a  ldloc.0
0x2bd3b  ldstr    asc_12A30E// ">"
0x2bd40  call     instance void System.Xml.XmlTextReaderImpl::ThrowUnexpectedToken(int32 pos, string expectedToken)
0x2bd45  br.s     loc_2BD65
0x2bd47  ldarg.0
0x2bd48  ldloc.0
0x2bd49  ldstr    aXmlBadnamechar// "Xml_BadNameChar"
0x2bd4e  ldloc.1
0x2bd4f  ldarg.0
0x2bd50  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2bd55  ldfld    int32 ParsingState::charsUsed
0x2bd5a  ldloc.0
0x2bd5b  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char[] data, int32 length, int32 invCharIndex)
0x2bd60  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res, string[] args)
0x2bd65  ldarg.0
  ... truncated ...
```
