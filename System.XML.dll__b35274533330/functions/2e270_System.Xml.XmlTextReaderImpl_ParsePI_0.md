# System.Xml.XmlTextReaderImpl::ParsePI_0

- ea: `0x2e270`
- end: `0x2e4b9`
- name: `System.Xml.XmlTextReaderImpl::ParsePI_0`
- size: `585`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x293d0`
- `0x2e260`

## callees

- `0x12920`
- `0x131f0`
- `0x29770`
- `0x297c0`
- `0x2a510`
- `0x2e270`
- `0x2e4c0`
- `0x2f3d0`
- `0x2fac0`
- `0xfe500`
- `0xfe510`
- `0xfeab0`
- `0xfeb20`
- `0xfeb70`
- `0xfeb80`

## string_xrefs

- `0x2e398`: `Xml_BadNameChar`
- `0x2e2eb`: `Xml_InvalidPIName`
- `0x2e2f2`: `Xml_XmlDeclNotFirst`

## pseudocode

```c

```

## disassembly

```asm
0x2e270  ldarg.0
0x2e271  ldfld    valuetype ParsingMode System.Xml.XmlTextReaderImpl::parsingMode
0x2e276  brtrue.s loc_2E299
0x2e278  ldarg.0
0x2e279  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2e27e  ldarg.0
0x2e27f  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e284  call     instance int32 ParsingState::get_LineNo()
0x2e289  ldarg.0
0x2e28a  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e28f  call     instance int32 ParsingState::get_LinePos()
0x2e294  callvirt instance void NodeData::SetLineInfo(int32 lineNo, int32 linePos)
0x2e299  ldarg.0
0x2e29a  call     instance int32 System.Xml.XmlTextReaderImpl::ParseName()
0x2e29f  stloc.0
0x2e2a0  ldarg.0
0x2e2a1  ldfld    class System.Xml.XmlNameTable System.Xml.XmlTextReaderImpl::nameTable
0x2e2a6  ldarg.0
0x2e2a7  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e2ac  ldfld    char[] ParsingState::chars
0x2e2b1  ldarg.0
0x2e2b2  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e2b7  ldfld    int32 ParsingState::charPos
0x2e2bc  ldloc.0
0x2e2bd  ldarg.0
0x2e2be  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e2c3  ldfld    int32 ParsingState::charPos
0x2e2c8  sub
0x2e2c9  callvirt instance string System.Xml.XmlNameTable::Add(char[] array, int32 offset, int32 length)
0x2e2ce  stloc.1
0x2e2cf  ldloc.1
0x2e2d0  ldstr    aXml// "xml"
0x2e2d5  ldc.i4.5
0x2e2d6  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2e2db  brtrue.s loc_2E2FD
0x2e2dd  ldarg.0
0x2e2de  ldloc.1
0x2e2df  ldstr    aXml// "xml"
0x2e2e4  callvirt instance bool [mscorlib]System.String::Equals(string)
0x2e2e9  brtrue.s loc_2E2F2
0x2e2eb  ldstr    aXmlInvalidpina// "Xml_InvalidPIName"
0x2e2f0  br.s     loc_2E2F7
0x2e2f2  ldstr    aXmlXmldeclnotf// "Xml_XmlDeclNotFirst"
0x2e2f7  ldloc.1
0x2e2f8  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg)
0x2e2fd  ldarg.0
0x2e2fe  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e303  ldloc.0
0x2e304  stfld    int32 ParsingState::charPos
0x2e309  ldarg.1
0x2e30a  brtrue.s loc_2E32B
0x2e30c  ldarg.0
0x2e30d  ldfld    bool System.Xml.XmlTextReaderImpl::ignorePIs
0x2e312  brtrue.s loc_2E333
0x2e314  ldarg.0
0x2e315  ldfld    valuetype ParsingMode System.Xml.XmlTextReaderImpl::parsingMode
0x2e31a  brtrue.s loc_2E333
0x2e31c  ldarg.0
0x2e31d  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2e322  ldc.i4.7
0x2e323  ldloc.1
0x2e324  callvirt instance void NodeData::SetNamedNode(valuetype System.Xml.XmlNodeType type, string localName)
0x2e329  br.s     loc_2E333
0x2e32b  ldarg.1
0x2e32c  ldloc.1
0x2e32d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2e332  pop
0x2e333  ldarg.0
0x2e334  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e339  ldfld    char[] ParsingState::chars
0x2e33e  ldarg.0
0x2e33f  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e344  ldfld    int32 ParsingState::charPos
0x2e349  ldelem.u2
0x2e34a  stloc.2
0x2e34b  ldarg.0
0x2e34c  ldarg.1
0x2e34d  call     instance int32 System.Xml.XmlTextReaderImpl::EatWhitespaces(class [mscorlib]System.Text.StringBuilder sb)
0x2e352  brtrue.s loc_2E3C8
0x2e354  ldarg.0
0x2e355  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e35a  ldfld    int32 ParsingState::charsUsed
0x2e35f  ldarg.0
0x2e360  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e365  ldfld    int32 ParsingState::charPos
0x2e36a  sub
0x2e36b  ldc.i4.2
0x2e36c  bge.s    loc_2E375
0x2e36e  ldarg.0
0x2e36f  call     instance int32 System.Xml.XmlTextReaderImpl::ReadData()
0x2e374  pop
0x2e375  ldloc.2
0x2e376  ldc.i4.s 0x3F
0x2e378  bne.un.s loc_2E397
0x2e37a  ldarg.0
0x2e37b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e380  ldfld    char[] ParsingState::chars
0x2e385  ldarg.0
0x2e386  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e38b  ldfld    int32 ParsingState::charPos
0x2e390  ldc.i4.1
0x2e391  add
0x2e392  ldelem.u2
0x2e393  ldc.i4.s 0x3E
0x2e395  beq.s    loc_2E3C8
0x2e397  ldarg.0
0x2e398  ldstr    aXmlBadnamechar// "Xml_BadNameChar"
0x2e39d  ldarg.0
0x2e39e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e3a3  ldfld    char[] ParsingState::chars
0x2e3a8  ldarg.0
0x2e3a9  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e3ae  ldfld    int32 ParsingState::charsUsed
0x2e3b3  ldarg.0
0x2e3b4  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e3b9  ldfld    int32 ParsingState::charPos
0x2e3be  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char[] data, int32 length, int32 invCharIndex)
0x2e3c3  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string[] args)
0x2e3c8  ldarg.0
0x2e3c9  ldloca.s 3
0x2e3cb  ldloca.s 4
0x2e3cd  call     instance bool System.Xml.XmlTextReaderImpl::ParsePIValue([out] int32& outStartPos, [out] int32& outEndPos)
0x2e3d2  brfalse.s loc_2E428
0x2e3d4  ldarg.1
0x2e3d5  brtrue.s loc_2E40C
0x2e3d7  ldarg.0
0x2e3d8  ldfld    bool System.Xml.XmlTextReaderImpl::ignorePIs
0x2e3dd  brfalse.s loc_2E3E1
0x2e3df  ldc.i4.0
0x2e3e0  ret
0x2e3e1  ldarg.0
0x2e3e2  ldfld    valuetype ParsingMode System.Xml.XmlTextReaderImpl::parsingMode
0x2e3e7  brtrue   loc_2E4B7
0x2e3ec  ldarg.0
0x2e3ed  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2e3f2  ldarg.0
0x2e3f3  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e3f8  ldfld    char[] ParsingState::chars
0x2e3fd  ldloc.3
0x2e3fe  ldloc.s  4
0x2e400  ldloc.3
0x2e401  sub
0x2e402  callvirt instance void NodeData::SetValue(char[] chars, int32 startPos, int32 len)
0x2e407  br       loc_2E4B7
0x2e40c  ldarg.1
0x2e40d  ldarg.0
0x2e40e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e413  ldfld    char[] ParsingState::chars
0x2e418  ldloc.3
0x2e419  ldloc.s  4
0x2e41b  ldloc.3
0x2e41c  sub
0x2e41d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char[], int32, int32)
0x2e422  pop
0x2e423  br       loc_2E4B7
0x2e428  ldarg.1
0x2e429  brtrue.s loc_2E453
0x2e42b  ldarg.0
0x2e42c  ldfld    bool System.Xml.XmlTextReaderImpl::ignorePIs
0x2e431  brtrue.s loc_2E43B
0x2e433  ldarg.0
0x2e434  ldfld    valuetype ParsingMode System.Xml.XmlTextReaderImpl::parsingMode
0x2e439  brfalse.s loc_2E449
0x2e43b  ldarg.0
0x2e43c  ldloca.s 3
0x2e43e  ldloca.s 4
0x2e440  call     instance bool System.Xml.XmlTextReaderImpl::ParsePIValue([out] int32& outStartPos, [out] int32& outEndPos)
0x2e445  brfalse.s loc_2E43B
0x2e447  ldc.i4.0
0x2e448  ret
0x2e449  ldarg.0
0x2e44a  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x2e44f  stloc.s  5
0x2e451  br.s     loc_2E456
0x2e453  ldarg.1
0x2e454  stloc.s  5
0x2e456  ldloc.s  5
0x2e458  ldarg.0
0x2e459  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e45e  ldfld    char[] ParsingState::chars
0x2e463  ldloc.3
0x2e464  ldloc.s  4
0x2e466  ldloc.3
0x2e467  sub
0x2e468  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char[], int32, int32)
0x2e46d  pop
0x2e46e  ldarg.0
0x2e46f  ldloca.s 3
0x2e471  ldloca.s 4
0x2e473  call     instance bool System.Xml.XmlTextReaderImpl::ParsePIValue([out] int32& outStartPos, [out] int32& outEndPos)
0x2e478  brfalse.s loc_2E456
0x2e47a  ldloc.s  5
0x2e47c  ldarg.0
0x2e47d  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e482  ldfld    char[] ParsingState::chars
0x2e487  ldloc.3
0x2e488  ldloc.s  4
0x2e48a  ldloc.3
0x2e48b  sub
0x2e48c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char[], int32, int32)
0x2e491  pop
0x2e492  ldarg.1
0x2e493  brtrue.s loc_2E4B7
0x2e495  ldarg.0
0x2e496  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2e49b  ldarg.0
0x2e49c  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x2e4a1  callvirt instance string [mscorlib]System.Object::ToString()
0x2e4a6  callvirt instance void NodeData::SetValue(string value)
0x2e4ab  ldarg.0
0x2e4ac  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x2e4b1  ldc.i4.0
0x2e4b2  callvirt instance void [mscorlib]System.Text.StringBuilder::set_Length(int32)
0x2e4b7  ldc.i4.1
0x2e4b8  ret
```
