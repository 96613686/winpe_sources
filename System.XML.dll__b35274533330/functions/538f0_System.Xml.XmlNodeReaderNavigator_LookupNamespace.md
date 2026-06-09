# System.Xml.XmlNodeReaderNavigator::LookupNamespace

- ea: `0x538f0`
- end: `0x539c0`
- name: `System.Xml.XmlNodeReaderNavigator::LookupNamespace`
- size: `208`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x53a30`
- `0x54850`
- `0x54a80`

## callees

- `0x13200`
- `0x499d0`
- `0x4e2c0`
- `0x4e360`
- `0x51110`
- `0x51160`
- `0x51170`
- `0x538f0`

## string_xrefs

- `0x5392b`: `http://www.w3.org/XML/1998/namespace`
- `0x5390d`: `http://www.w3.org/2000/xmlns/`
- `0x538fb`: `xmlns`
- `0x53948`: `xmlns`
- `0x53950`: `xmlns:`

## pseudocode

```c

```

## disassembly

```asm
0x538f0  ldarg.0
0x538f1  ldfld    bool System.Xml.XmlNodeReaderNavigator::bCreatedOnAttribute
0x538f6  brfalse.s loc_538FA
0x538f8  ldnull
0x538f9  ret
0x538fa  ldarg.1
0x538fb  ldstr    aXmlns// "xmlns"
0x53900  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53905  brfalse.s loc_53918
0x53907  ldarg.0
0x53908  ldfld    class System.Xml.XmlNameTable System.Xml.XmlNodeReaderNavigator::nameTable
0x5390d  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x53912  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x53917  ret
0x53918  ldarg.1
0x53919  ldstr    aXml// "xml"
0x5391e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53923  brfalse.s loc_53936
0x53925  ldarg.0
0x53926  ldfld    class System.Xml.XmlNameTable System.Xml.XmlNodeReaderNavigator::nameTable
0x5392b  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x53930  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x53935  ret
0x53936  ldarg.1
0x53937  brtrue.s loc_53940
0x53939  ldsfld   string [mscorlib]System.String::Empty
0x5393e  starg.s  1
0x53940  ldarg.1
0x53941  callvirt instance int32 [mscorlib]System.String::get_Length()
0x53946  brtrue.s loc_53950
0x53948  ldstr    aXmlns// "xmlns"
0x5394d  stloc.0
0x5394e  br.s     loc_5395C
0x53950  ldstr    aXmlns_3// "xmlns:"
0x53955  ldarg.1
0x53956  call     string [mscorlib]System.String::Concat(string, string)
0x5395b  stloc.0
0x5395c  ldarg.0
0x5395d  ldfld    class System.Xml.XmlNode System.Xml.XmlNodeReaderNavigator::curNode
0x53962  stloc.1
0x53963  br.s     loc_539AD
0x53965  ldloc.1
0x53966  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlNode::get_NodeType()
0x5396b  ldc.i4.1
0x5396c  bne.un.s loc_5398F
0x5396e  ldloc.1
0x5396f  castclass System.Xml.XmlElement
0x53974  stloc.2
0x53975  ldloc.2
0x53976  callvirt instance bool System.Xml.XmlElement::get_HasAttributes()
0x5397b  brfalse.s loc_539A6
0x5397d  ldloc.2
0x5397e  ldloc.0
0x5397f  callvirt instance class System.Xml.XmlAttribute System.Xml.XmlElement::GetAttributeNode(string name)
0x53984  stloc.3
0x53985  ldloc.3
0x53986  brfalse.s loc_539A6
0x53988  ldloc.3
0x53989  callvirt instance string System.Xml.XmlNode::get_Value()
0x5398e  ret
0x5398f  ldloc.1
0x53990  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlNode::get_NodeType()
0x53995  ldc.i4.2
0x53996  bne.un.s loc_539A6
0x53998  ldloc.1
0x53999  castclass System.Xml.XmlAttribute
0x5399e  callvirt instance class System.Xml.XmlElement System.Xml.XmlAttribute::get_OwnerElement()
0x539a3  stloc.1
0x539a4  br.s     loc_539AD
0x539a6  ldloc.1
0x539a7  callvirt instance class System.Xml.XmlNode System.Xml.XmlNode::get_ParentNode()
0x539ac  stloc.1
0x539ad  ldloc.1
0x539ae  brtrue.s loc_53965
0x539b0  ldarg.1
0x539b1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x539b6  brtrue.s loc_539BE
0x539b8  ldsfld   string [mscorlib]System.String::Empty
0x539bd  ret
0x539be  ldnull
0x539bf  ret
```
