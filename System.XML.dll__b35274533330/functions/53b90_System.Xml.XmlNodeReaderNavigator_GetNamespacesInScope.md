# System.Xml.XmlNodeReaderNavigator::GetNamespacesInScope

- ea: `0x53b90`
- end: `0x53d22`
- name: `System.Xml.XmlNodeReaderNavigator::GetNamespacesInScope`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x54a60`

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
- `0x53b90`

## string_xrefs

- `0x53d11`: `http://www.w3.org/XML/1998/namespace`
- `0x53bea`: `xmlns`
- `0x53c42`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x53b90  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x53b95  stloc.0
0x53b96  ldarg.0
0x53b97  ldfld    bool System.Xml.XmlNodeReaderNavigator::bCreatedOnAttribute
0x53b9c  brfalse.s loc_53BA0
0x53b9e  ldloc.0
0x53b9f  ret
0x53ba0  ldarg.0
0x53ba1  ldfld    class System.Xml.XmlNode System.Xml.XmlNodeReaderNavigator::curNode
0x53ba6  stloc.1
0x53ba7  br       loc_53CBD
0x53bac  ldloc.1
0x53bad  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlNode::get_NodeType()
0x53bb2  ldc.i4.1
0x53bb3  bne.un   loc_53C9F
0x53bb8  ldloc.1
0x53bb9  castclass System.Xml.XmlElement
0x53bbe  stloc.2
0x53bbf  ldloc.2
0x53bc0  callvirt instance bool System.Xml.XmlElement::get_HasAttributes()
0x53bc5  brfalse  loc_53C99
0x53bca  ldloc.2
0x53bcb  callvirt instance class System.Xml.XmlAttributeCollection System.Xml.XmlNode::get_Attributes()
0x53bd0  stloc.3
0x53bd1  ldc.i4.0
0x53bd2  stloc.s  4
0x53bd4  br       loc_53C8C
0x53bd9  ldloc.3
0x53bda  ldloc.s  4
0x53bdc  callvirt instance class System.Xml.XmlAttribute System.Xml.XmlAttributeCollection::get_ItemOf(int32 i)
0x53be1  stloc.s  5
0x53be3  ldloc.s  5
0x53be5  callvirt instance string System.Xml.XmlNode::get_LocalName()
0x53bea  ldstr    aXmlns// "xmlns"
0x53bef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53bf4  brfalse.s loc_53C3B
0x53bf6  ldloc.s  5
0x53bf8  callvirt instance string System.Xml.XmlNode::get_Prefix()
0x53bfd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x53c02  brtrue.s loc_53C3B
0x53c04  ldloc.0
0x53c05  ldsfld   string [mscorlib]System.String::Empty
0x53c0a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x53c0f  brtrue.s loc_53C86
0x53c11  ldloc.0
0x53c12  ldarg.0
0x53c13  ldfld    class System.Xml.XmlNameTable System.Xml.XmlNodeReaderNavigator::nameTable
0x53c18  ldsfld   string [mscorlib]System.String::Empty
0x53c1d  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x53c22  ldarg.0
0x53c23  ldfld    class System.Xml.XmlNameTable System.Xml.XmlNodeReaderNavigator::nameTable
0x53c28  ldloc.s  5
0x53c2a  callvirt instance string System.Xml.XmlNode::get_Value()
0x53c2f  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x53c34  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x53c39  br.s     loc_53C86
0x53c3b  ldloc.s  5
0x53c3d  callvirt instance string System.Xml.XmlNode::get_Prefix()
0x53c42  ldstr    aXmlns// "xmlns"
0x53c47  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53c4c  brfalse.s loc_53C86
0x53c4e  ldloc.s  5
0x53c50  callvirt instance string System.Xml.XmlNode::get_LocalName()
0x53c55  stloc.s  6
0x53c57  ldloc.0
0x53c58  ldloc.s  6
0x53c5a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x53c5f  brtrue.s loc_53C86
0x53c61  ldloc.0
0x53c62  ldarg.0
0x53c63  ldfld    class System.Xml.XmlNameTable System.Xml.XmlNodeReaderNavigator::nameTable
0x53c68  ldloc.s  6
0x53c6a  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x53c6f  ldarg.0
0x53c70  ldfld    class System.Xml.XmlNameTable System.Xml.XmlNodeReaderNavigator::nameTable
0x53c75  ldloc.s  5
0x53c77  callvirt instance string System.Xml.XmlNode::get_Value()
0x53c7c  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x53c81  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x53c86  ldloc.s  4
0x53c88  ldc.i4.1
0x53c89  add
0x53c8a  stloc.s  4
0x53c8c  ldloc.s  4
0x53c8e  ldloc.3
0x53c8f  callvirt instance int32 System.Xml.XmlNamedNodeMap::get_Count()
0x53c94  blt      loc_53BD9
0x53c99  ldarg.1
0x53c9a  ldc.i4.2
0x53c9b  bne.un.s loc_53CB6
0x53c9d  br.s     loc_53CC3
0x53c9f  ldloc.1
0x53ca0  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlNode::get_NodeType()
0x53ca5  ldc.i4.2
0x53ca6  bne.un.s loc_53CB6
0x53ca8  ldloc.1
0x53ca9  castclass System.Xml.XmlAttribute
0x53cae  callvirt instance class System.Xml.XmlElement System.Xml.XmlAttribute::get_OwnerElement()
0x53cb3  stloc.1
0x53cb4  br.s     loc_53CBD
0x53cb6  ldloc.1
0x53cb7  callvirt instance class System.Xml.XmlNode System.Xml.XmlNode::get_ParentNode()
0x53cbc  stloc.1
0x53cbd  ldloc.1
0x53cbe  brtrue   loc_53BAC
0x53cc3  ldarg.1
0x53cc4  ldc.i4.2
0x53cc5  beq.s    loc_53D20
0x53cc7  ldloc.0
0x53cc8  ldsfld   string [mscorlib]System.String::Empty
0x53ccd  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x53cd2  brfalse.s loc_53CF7
0x53cd4  ldloc.0
0x53cd5  ldsfld   string [mscorlib]System.String::Empty
0x53cda  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x53cdf  ldsfld   string [mscorlib]System.String::Empty
0x53ce4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53ce9  brfalse.s loc_53CF7
0x53ceb  ldloc.0
0x53cec  ldsfld   string [mscorlib]System.String::Empty
0x53cf1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Remove(var<u1>)
0x53cf6  pop
0x53cf7  ldarg.1
0x53cf8  brtrue.s loc_53D20
0x53cfa  ldloc.0
0x53cfb  ldarg.0
0x53cfc  ldfld    class System.Xml.XmlNameTable System.Xml.XmlNodeReaderNavigator::nameTable
0x53d01  ldstr    aXml// "xml"
0x53d06  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x53d0b  ldarg.0
0x53d0c  ldfld    class System.Xml.XmlNameTable System.Xml.XmlNodeReaderNavigator::nameTable
0x53d11  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x53d16  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x53d1b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x53d20  ldloc.0
0x53d21  ret
```
