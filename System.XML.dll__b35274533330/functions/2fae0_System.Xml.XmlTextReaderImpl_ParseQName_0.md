# System.Xml.XmlTextReaderImpl::ParseQName_0

- ea: `0x2fae0`
- end: `0x2fc2f`
- name: `System.Xml.XmlTextReaderImpl::ParseQName_0`
- size: `335`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x2fac0`
- `0x2fad0`
- `0x30830`

## callees

- `0x12920`
- `0x12940`
- `0x296e0`
- `0x29700`
- `0x2fae0`
- `0x2fc30`

## string_xrefs

- `0x2fb52`: `Xml_BadStartNameChar`
- `0x2fba0`: `Xml_BadNameChar`
- `0x2fb32`: `Xml_UnexpectedEOF`
- `0x2fc08`: `Xml_UnexpectedEOF`

## pseudocode

```c

```

## disassembly

```asm
0x2fae0  ldc.i4.m1
0x2fae1  stloc.0
0x2fae2  ldarg.0
0x2fae3  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2fae8  ldfld    int32 ParsingState::charPos
0x2faed  ldarg.2
0x2faee  add
0x2faef  stloc.1
0x2faf0  ldarg.0
0x2faf1  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2faf6  ldfld    char[] ParsingState::chars
0x2fafb  stloc.2
0x2fafc  ldarg.0
0x2fafd  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x2fb02  ldfld    unsigned int8* System.Xml.XmlCharType::charProperties
0x2fb07  ldloc.2
0x2fb08  ldloc.1
0x2fb09  ldelem.u2
0x2fb0a  add
0x2fb0b  ldind.u1
0x2fb0c  ldc.i4.4
0x2fb0d  and
0x2fb0e  brfalse.s loc_2FB16
0x2fb10  ldloc.1
0x2fb11  ldc.i4.1
0x2fb12  add
0x2fb13  stloc.1
0x2fb14  br.s     loc_2FB6E
0x2fb16  ldloc.1
0x2fb17  ldc.i4.1
0x2fb18  add
0x2fb19  ldarg.0
0x2fb1a  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2fb1f  ldfld    int32 ParsingState::charsUsed
0x2fb24  blt.s    loc_2FB41
0x2fb26  ldarg.0
0x2fb27  ldloca.s 1
0x2fb29  call     instance bool System.Xml.XmlTextReaderImpl::ReadDataInName(int32& pos)
0x2fb2e  brtrue.s loc_2FAF0
0x2fb30  ldarg.0
0x2fb31  ldloc.1
0x2fb32  ldstr    aXmlUnexpectede// "Xml_UnexpectedEOF"
0x2fb37  ldstr    aName_0// "Name"
0x2fb3c  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res, string arg)
0x2fb41  ldloc.2
0x2fb42  ldloc.1
0x2fb43  ldelem.u2
0x2fb44  ldc.i4.s 0x3A
0x2fb46  bne.un.s loc_2FB50
0x2fb48  ldarg.0
0x2fb49  ldfld    bool System.Xml.XmlTextReaderImpl::supportNamespaces
0x2fb4e  brfalse.s loc_2FB6E
0x2fb50  ldarg.0
0x2fb51  ldloc.1
0x2fb52  ldstr    aXmlBadstartnam// "Xml_BadStartNameChar"
0x2fb57  ldloc.2
0x2fb58  ldarg.0
0x2fb59  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2fb5e  ldfld    int32 ParsingState::charsUsed
0x2fb63  ldloc.1
0x2fb64  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char[] data, int32 length, int32 invCharIndex)
0x2fb69  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res, string[] args)
0x2fb6e  ldarg.0
0x2fb6f  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x2fb74  ldfld    unsigned int8* System.Xml.XmlCharType::charProperties
0x2fb79  ldloc.2
0x2fb7a  ldloc.1
0x2fb7b  ldelem.u2
0x2fb7c  add
0x2fb7d  ldind.u1
0x2fb7e  ldc.i4.8
0x2fb7f  and
0x2fb80  brfalse.s loc_2FB88
0x2fb82  ldloc.1
0x2fb83  ldc.i4.1
0x2fb84  add
0x2fb85  stloc.1
0x2fb86  br.s     loc_2FB6E
0x2fb88  ldloc.2
0x2fb89  ldloc.1
0x2fb8a  ldelem.u2
0x2fb8b  ldc.i4.s 0x3A
0x2fb8d  bne.un.s loc_2FBDD
0x2fb8f  ldarg.0
0x2fb90  ldfld    bool System.Xml.XmlTextReaderImpl::supportNamespaces
0x2fb95  brfalse.s loc_2FBC9
0x2fb97  ldloc.0
0x2fb98  ldc.i4.m1
0x2fb99  bne.un.s loc_2FB9E
0x2fb9b  ldarg.1
0x2fb9c  brtrue.s loc_2FBB2
0x2fb9e  ldarg.0
0x2fb9f  ldloc.1
0x2fba0  ldstr    aXmlBadnamechar// "Xml_BadNameChar"
0x2fba5  ldc.i4.s 0x3A
0x2fba7  ldc.i4.0
0x2fba8  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char invChar, char nextChar)
0x2fbad  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res, string[] args)
0x2fbb2  ldloc.1
0x2fbb3  ldarg.0
0x2fbb4  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2fbb9  ldfld    int32 ParsingState::charPos
0x2fbbe  sub
0x2fbbf  stloc.0
0x2fbc0  ldloc.1
0x2fbc1  ldc.i4.1
0x2fbc2  add
0x2fbc3  stloc.1
0x2fbc4  br       loc_2FAF0
0x2fbc9  ldloc.1
0x2fbca  ldarg.0
0x2fbcb  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2fbd0  ldfld    int32 ParsingState::charPos
0x2fbd5  sub
0x2fbd6  stloc.0
0x2fbd7  ldloc.1
0x2fbd8  ldc.i4.1
0x2fbd9  add
0x2fbda  stloc.1
0x2fbdb  br.s     loc_2FB6E
0x2fbdd  ldloc.1
0x2fbde  ldarg.0
0x2fbdf  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2fbe4  ldfld    int32 ParsingState::charsUsed
0x2fbe9  bne.un.s loc_2FC17
0x2fbeb  ldarg.0
0x2fbec  ldloca.s 1
0x2fbee  call     instance bool System.Xml.XmlTextReaderImpl::ReadDataInName(int32& pos)
0x2fbf3  brfalse.s loc_2FC06
0x2fbf5  ldarg.0
0x2fbf6  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2fbfb  ldfld    char[] ParsingState::chars
0x2fc00  stloc.2
0x2fc01  br       loc_2FB6E
0x2fc06  ldarg.0
0x2fc07  ldloc.1
0x2fc08  ldstr    aXmlUnexpectede// "Xml_UnexpectedEOF"
0x2fc0d  ldstr    aName_0// "Name"
0x2fc12  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res, string arg)
0x2fc17  ldarg.3
0x2fc18  ldloc.0
0x2fc19  ldc.i4.m1
0x2fc1a  beq.s    loc_2FC2B
0x2fc1c  ldarg.0
0x2fc1d  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2fc22  ldfld    int32 ParsingState::charPos
0x2fc27  ldloc.0
0x2fc28  add
0x2fc29  br.s     loc_2FC2C
0x2fc2b  ldc.i4.m1
0x2fc2c  stind.i4
0x2fc2d  ldloc.1
0x2fc2e  ret
```
