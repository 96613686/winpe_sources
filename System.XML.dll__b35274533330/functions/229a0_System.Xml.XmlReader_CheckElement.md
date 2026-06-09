# System.Xml.XmlReader::CheckElement

- ea: `0x229a0`
- end: `0x22a2f`
- name: `System.Xml.XmlReader::CheckElement`
- size: `143`
- prototype: ``
- caller_count: `10`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x218d0`
- `0x21910`
- `0x21950`
- `0x21990`
- `0x219d0`
- `0x21a10`
- `0x21a50`
- `0x21a90`
- `0x21ad0`
- `0x21b30`

## callees

- `0x11380`
- `0x126c0`
- `0x12730`
- `0x214b0`
- `0x21500`
- `0x21510`
- `0x229a0`

## string_xrefs

- `0x229ba`: `namespaceURI`
- `0x229ce`: `Xml_InvalidNodeType`
- `0x22a0f`: `Xml_ElementNotFoundNs`

## pseudocode

```c

```

## disassembly

```asm
0x229a0  ldarg.1
0x229a1  brfalse.s loc_229AB
0x229a3  ldarg.1
0x229a4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x229a9  brtrue.s loc_229B7
0x229ab  ldarg.1
0x229ac  ldstr    aLocalname// "localName"
0x229b1  call     class [mscorlib]System.ArgumentException System.Xml.XmlConvert::CreateInvalidNameArgumentException(string name, string argumentName)
0x229b6  throw
0x229b7  ldarg.2
0x229b8  brtrue.s loc_229C5
0x229ba  ldstr    aNamespaceuri// "namespaceURI"
0x229bf  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x229c4  throw
0x229c5  ldarg.0
0x229c6  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x229cb  ldc.i4.1
0x229cc  beq.s    loc_229F3
0x229ce  ldstr    aXmlInvalidnode// "Xml_InvalidNodeType"
0x229d3  ldarg.0
0x229d4  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x229d9  stloc.0
0x229da  ldloca.s 0
0x229dc  constrained. System.Xml.XmlNodeType
0x229e2  callvirt instance string [mscorlib]System.Object::ToString()
0x229e7  ldarg.0
0x229e8  isinst   System.Xml.IXmlLineInfo
0x229ed  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class System.Xml.IXmlLineInfo lineInfo)
0x229f2  throw
0x229f3  ldarg.0
0x229f4  callvirt instance string System.Xml.XmlReader::get_LocalName()
0x229f9  ldarg.1
0x229fa  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x229ff  brtrue.s loc_22A0F
0x22a01  ldarg.0
0x22a02  callvirt instance string System.Xml.XmlReader::get_NamespaceURI()
0x22a07  ldarg.2
0x22a08  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x22a0d  brfalse.s loc_22A2E
0x22a0f  ldstr    aXmlElementnotf_0// "Xml_ElementNotFoundNs"
0x22a14  ldc.i4.2
0x22a15  newarr   [mscorlib]System.String
0x22a1a  dup
0x22a1b  ldc.i4.0
0x22a1c  ldarg.1
0x22a1d  stelem.ref
0x22a1e  dup
0x22a1f  ldc.i4.1
0x22a20  ldarg.2
0x22a21  stelem.ref
0x22a22  ldarg.0
0x22a23  isinst   System.Xml.IXmlLineInfo
0x22a28  newobj   instance void System.Xml.XmlException::.ctor(string res, string[] args, class System.Xml.IXmlLineInfo lineInfo)
0x22a2d  throw
0x22a2e  ret
```
