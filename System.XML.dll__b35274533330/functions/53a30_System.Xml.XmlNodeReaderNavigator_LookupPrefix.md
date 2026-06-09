# System.Xml.XmlNodeReaderNavigator::LookupPrefix

- ea: `0x53a30`
- end: `0x53b88`
- name: `System.Xml.XmlNodeReaderNavigator::LookupPrefix`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x54a70`

## callees

- `0xdc70`
- `0x13200`
- `0x499d0`
- `0x49b60`
- `0x4e2c0`
- `0x51110`
- `0x51160`
- `0x51170`
- `0x511f0`
- `0x51cc0`
- `0x51ce0`
- `0x538f0`
- `0x53a30`

## string_xrefs

- `0x53a5c`: `http://www.w3.org/XML/1998/namespace`
- `0x53a3e`: `http://www.w3.org/2000/xmlns/`
- `0x53a50`: `xmlns`
- `0x53af1`: `xmlns`
- `0x53b1d`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x53a30  ldarg.0
0x53a31  ldfld    bool System.Xml.XmlNodeReaderNavigator::bCreatedOnAttribute
0x53a36  brtrue.s loc_53A3B
0x53a38  ldarg.1
0x53a39  brtrue.s loc_53A3D
0x53a3b  ldnull
0x53a3c  ret
0x53a3d  ldarg.1
0x53a3e  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x53a43  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53a48  brfalse.s loc_53A5B
0x53a4a  ldarg.0
0x53a4b  ldfld    class System.Xml.XmlNameTable System.Xml.XmlNodeReaderNavigator::nameTable
0x53a50  ldstr    aXmlns// "xmlns"
0x53a55  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x53a5a  ret
0x53a5b  ldarg.1
0x53a5c  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x53a61  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53a66  brfalse.s loc_53A79
0x53a68  ldarg.0
0x53a69  ldfld    class System.Xml.XmlNameTable System.Xml.XmlNodeReaderNavigator::nameTable
0x53a6e  ldstr    aXml// "xml"
0x53a73  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x53a78  ret
0x53a79  ldarg.1
0x53a7a  ldsfld   string [mscorlib]System.String::Empty
0x53a7f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53a84  brfalse.s loc_53A8C
0x53a86  ldsfld   string [mscorlib]System.String::Empty
0x53a8b  ret
0x53a8c  ldarg.0
0x53a8d  ldfld    class System.Xml.XmlNode System.Xml.XmlNodeReaderNavigator::curNode
0x53a92  stloc.0
0x53a93  br       loc_53B80
0x53a98  ldloc.0
0x53a99  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlNode::get_NodeType()
0x53a9e  ldc.i4.1
0x53a9f  bne.un   loc_53B62
0x53aa4  ldloc.0
0x53aa5  castclass System.Xml.XmlElement
0x53aaa  stloc.1
0x53aab  ldloc.1
0x53aac  callvirt instance bool System.Xml.XmlElement::get_HasAttributes()
0x53ab1  brfalse  loc_53B79
0x53ab6  ldloc.1
0x53ab7  callvirt instance class System.Xml.XmlAttributeCollection System.Xml.XmlNode::get_Attributes()
0x53abc  stloc.2
0x53abd  ldc.i4.0
0x53abe  stloc.3
0x53abf  br       loc_53B54
0x53ac4  ldloc.2
0x53ac5  ldloc.3
0x53ac6  callvirt instance class System.Xml.XmlAttribute System.Xml.XmlAttributeCollection::get_ItemOf(int32 i)
0x53acb  stloc.s  4
0x53acd  ldloc.s  4
0x53acf  callvirt instance string System.Xml.XmlNode::get_Value()
0x53ad4  ldarg.1
0x53ad5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53ada  brfalse.s loc_53B50
0x53adc  ldloc.s  4
0x53ade  callvirt instance string System.Xml.XmlNode::get_Prefix()
0x53ae3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x53ae8  brtrue.s loc_53B16
0x53aea  ldloc.s  4
0x53aec  callvirt instance string System.Xml.XmlNode::get_LocalName()
0x53af1  ldstr    aXmlns// "xmlns"
0x53af6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53afb  brfalse.s loc_53B16
0x53afd  ldarg.0
0x53afe  ldsfld   string [mscorlib]System.String::Empty
0x53b03  call     instance string System.Xml.XmlNodeReaderNavigator::LookupNamespace(string prefix)
0x53b08  ldarg.1
0x53b09  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53b0e  brfalse.s loc_53B50
0x53b10  ldsfld   string [mscorlib]System.String::Empty
0x53b15  ret
0x53b16  ldloc.s  4
0x53b18  callvirt instance string System.Xml.XmlNode::get_Prefix()
0x53b1d  ldstr    aXmlns// "xmlns"
0x53b22  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53b27  brfalse.s loc_53B50
0x53b29  ldloc.s  4
0x53b2b  callvirt instance string System.Xml.XmlNode::get_LocalName()
0x53b30  stloc.s  5
0x53b32  ldarg.0
0x53b33  ldloc.s  5
0x53b35  call     instance string System.Xml.XmlNodeReaderNavigator::LookupNamespace(string prefix)
0x53b3a  ldarg.1
0x53b3b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53b40  brfalse.s loc_53B50
0x53b42  ldarg.0
0x53b43  ldfld    class System.Xml.XmlNameTable System.Xml.XmlNodeReaderNavigator::nameTable
0x53b48  ldloc.s  5
0x53b4a  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x53b4f  ret
0x53b50  ldloc.3
0x53b51  ldc.i4.1
0x53b52  add
0x53b53  stloc.3
0x53b54  ldloc.3
0x53b55  ldloc.2
0x53b56  callvirt instance int32 System.Xml.XmlNamedNodeMap::get_Count()
0x53b5b  blt      loc_53AC4
0x53b60  br.s     loc_53B79
0x53b62  ldloc.0
0x53b63  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlNode::get_NodeType()
0x53b68  ldc.i4.2
0x53b69  bne.un.s loc_53B79
0x53b6b  ldloc.0
0x53b6c  castclass System.Xml.XmlAttribute
0x53b71  callvirt instance class System.Xml.XmlElement System.Xml.XmlAttribute::get_OwnerElement()
0x53b76  stloc.0
0x53b77  br.s     loc_53B80
0x53b79  ldloc.0
0x53b7a  callvirt instance class System.Xml.XmlNode System.Xml.XmlNode::get_ParentNode()
0x53b7f  stloc.0
0x53b80  ldloc.0
0x53b81  brtrue   loc_53A98
0x53b86  ldnull
0x53b87  ret
```
