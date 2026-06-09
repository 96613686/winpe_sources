# System.Xml.XmlTextReaderImpl::AddNamespace

- ea: `0x30050`
- end: `0x3015a`
- name: `System.Xml.XmlTextReaderImpl::AddNamespace`
- size: `266`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x2c9b0`
- `0x2ca10`

## callees

- `0xe6c0`
- `0x12c50`
- `0x29750`
- `0x297a0`
- `0x29870`
- `0x30050`

## string_xrefs

- `0x300b3`: `http://www.w3.org/XML/1998/namespace`
- `0x30051`: `http://www.w3.org/2000/xmlns/`
- `0x3006c`: `Xml_XmlnsPrefix`
- `0x3008f`: `Xml_NamespaceDeclXmlXmlns`
- `0x300d6`: `Xml_NamespaceDeclXmlXmlns`
- `0x30109`: `Xml_BadNamespaceDecl`

## pseudocode

```c

```

## disassembly

```asm
0x30050  ldarg.2
0x30051  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x30056  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3005b  brfalse.s loc_300B2
0x3005d  ldarg.1
0x3005e  ldarg.0
0x3005f  ldfld    string System.Xml.XmlTextReaderImpl::XmlNs
0x30064  call     bool System.Xml.Ref::Equal(string strA, string strB)
0x30069  brfalse.s loc_3008E
0x3006b  ldarg.0
0x3006c  ldstr    aXmlXmlnsprefix// "Xml_XmlnsPrefix"
0x30071  ldarg.3
0x30072  ldflda   valuetype System.Xml.LineInfo NodeData::lineInfo2
0x30077  ldfld    int32 System.Xml.LineInfo::lineNo
0x3007c  ldarg.3
0x3007d  ldflda   valuetype System.Xml.LineInfo NodeData::lineInfo2
0x30082  ldfld    int32 System.Xml.LineInfo::linePos
0x30087  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, int32 lineNo, int32 linePos)
0x3008c  br.s     loc_300F7
0x3008e  ldarg.0
0x3008f  ldstr    aXmlNamespacede// "Xml_NamespaceDeclXmlXmlns"
0x30094  ldarg.1
0x30095  ldarg.3
0x30096  ldflda   valuetype System.Xml.LineInfo NodeData::lineInfo2
0x3009b  ldfld    int32 System.Xml.LineInfo::lineNo
0x300a0  ldarg.3
0x300a1  ldflda   valuetype System.Xml.LineInfo NodeData::lineInfo2
0x300a6  ldfld    int32 System.Xml.LineInfo::linePos
0x300ab  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg, int32 lineNo, int32 linePos)
0x300b0  br.s     loc_300F7
0x300b2  ldarg.2
0x300b3  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x300b8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x300bd  brfalse.s loc_300F7
0x300bf  ldarg.1
0x300c0  ldarg.0
0x300c1  ldfld    string System.Xml.XmlTextReaderImpl::Xml
0x300c6  call     bool System.Xml.Ref::Equal(string strA, string strB)
0x300cb  brtrue.s loc_300F7
0x300cd  ldarg.0
0x300ce  ldfld    bool System.Xml.XmlTextReaderImpl::v1Compat
0x300d3  brtrue.s loc_300F7
0x300d5  ldarg.0
0x300d6  ldstr    aXmlNamespacede// "Xml_NamespaceDeclXmlXmlns"
0x300db  ldarg.1
0x300dc  ldarg.3
0x300dd  ldflda   valuetype System.Xml.LineInfo NodeData::lineInfo2
0x300e2  ldfld    int32 System.Xml.LineInfo::lineNo
0x300e7  ldarg.3
0x300e8  ldflda   valuetype System.Xml.LineInfo NodeData::lineInfo2
0x300ed  ldfld    int32 System.Xml.LineInfo::linePos
0x300f2  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg, int32 lineNo, int32 linePos)
0x300f7  ldarg.2
0x300f8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x300fd  brtrue.s loc_30129
0x300ff  ldarg.1
0x30100  callvirt instance int32 [mscorlib]System.String::get_Length()
0x30105  ldc.i4.0
0x30106  ble.s    loc_30129
0x30108  ldarg.0
0x30109  ldstr    aXmlBadnamespac// "Xml_BadNamespaceDecl"
0x3010e  ldarg.3
0x3010f  ldflda   valuetype System.Xml.LineInfo NodeData::lineInfo
0x30114  ldfld    int32 System.Xml.LineInfo::lineNo
0x30119  ldarg.3
0x3011a  ldflda   valuetype System.Xml.LineInfo NodeData::lineInfo
0x3011f  ldfld    int32 System.Xml.LineInfo::linePos
0x30124  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, int32 lineNo, int32 linePos)
0x30129  nop
0x3012a  ldarg.0
0x3012b  ldfld    class System.Xml.XmlNamespaceManager System.Xml.XmlTextReaderImpl::namespaceManager
0x30130  ldarg.1
0x30131  ldarg.2
0x30132  callvirt instance void System.Xml.XmlNamespaceManager::AddNamespace(string prefix, string uri)
0x30137  leave.s  loc_30159
0x30139  stloc.0
0x3013a  ldarg.0
0x3013b  ldloc.0
0x3013c  ldarg.3
0x3013d  ldflda   valuetype System.Xml.LineInfo NodeData::lineInfo
0x30142  ldfld    int32 System.Xml.LineInfo::lineNo
0x30147  ldarg.3
0x30148  ldflda   valuetype System.Xml.LineInfo NodeData::lineInfo
0x3014d  ldfld    int32 System.Xml.LineInfo::linePos
0x30152  call     instance void System.Xml.XmlTextReaderImpl::ReThrow(class [mscorlib]System.Exception e, int32 lineNo, int32 linePos)
0x30157  leave.s  loc_30159
0x30159  ret
```
