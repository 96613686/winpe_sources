# System.Xml.XmlReader::ReadElementString_1

- ea: `0x22100`
- end: `0x221bf`
- name: `System.Xml.XmlReader::ReadElementString_1`
- size: `191`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18bf0`
- `0x785c0`

## callees

- `0x126c0`
- `0x12730`
- `0x214b0`
- `0x21500`
- `0x21510`
- `0x21570`
- `0x21c60`
- `0x21db0`
- `0x21e40`
- `0x22100`

## string_xrefs

- `0x2210f`: `Xml_InvalidNodeType`
- `0x22188`: `Xml_InvalidNodeType`
- `0x22150`: `Xml_ElementNotFoundNs`

## pseudocode

```c

```

## disassembly

```asm
0x22100  ldsfld   string [mscorlib]System.String::Empty
0x22105  stloc.0
0x22106  ldarg.0
0x22107  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::MoveToContent()
0x2210c  ldc.i4.1
0x2210d  beq.s    loc_22134
0x2210f  ldstr    aXmlInvalidnode// "Xml_InvalidNodeType"
0x22114  ldarg.0
0x22115  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x2211a  stloc.1
0x2211b  ldloca.s 1
0x2211d  constrained. System.Xml.XmlNodeType
0x22123  callvirt instance string [mscorlib]System.Object::ToString()
0x22128  ldarg.0
0x22129  isinst   System.Xml.IXmlLineInfo
0x2212e  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class System.Xml.IXmlLineInfo lineInfo)
0x22133  throw
0x22134  ldarg.0
0x22135  callvirt instance string System.Xml.XmlReader::get_LocalName()
0x2213a  ldarg.1
0x2213b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x22140  brtrue.s loc_22150
0x22142  ldarg.0
0x22143  callvirt instance string System.Xml.XmlReader::get_NamespaceURI()
0x22148  ldarg.2
0x22149  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2214e  brfalse.s loc_2216F
0x22150  ldstr    aXmlElementnotf_0// "Xml_ElementNotFoundNs"
0x22155  ldc.i4.2
0x22156  newarr   [mscorlib]System.String
0x2215b  dup
0x2215c  ldc.i4.0
0x2215d  ldarg.1
0x2215e  stelem.ref
0x2215f  dup
0x22160  ldc.i4.1
0x22161  ldarg.2
0x22162  stelem.ref
0x22163  ldarg.0
0x22164  isinst   System.Xml.IXmlLineInfo
0x22169  newobj   instance void System.Xml.XmlException::.ctor(string res, string[] args, class System.Xml.IXmlLineInfo lineInfo)
0x2216e  throw
0x2216f  ldarg.0
0x22170  callvirt instance bool System.Xml.XmlReader::get_IsEmptyElement()
0x22175  brtrue.s loc_221B6
0x22177  ldarg.0
0x22178  callvirt instance string System.Xml.XmlReader::ReadString()
0x2217d  stloc.0
0x2217e  ldarg.0
0x2217f  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x22184  ldc.i4.s 0xF
0x22186  beq.s    loc_221AD
0x22188  ldstr    aXmlInvalidnode// "Xml_InvalidNodeType"
0x2218d  ldarg.0
0x2218e  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x22193  stloc.1
0x22194  ldloca.s 1
0x22196  constrained. System.Xml.XmlNodeType
0x2219c  callvirt instance string [mscorlib]System.Object::ToString()
0x221a1  ldarg.0
0x221a2  isinst   System.Xml.IXmlLineInfo
0x221a7  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class System.Xml.IXmlLineInfo lineInfo)
0x221ac  throw
0x221ad  ldarg.0
0x221ae  callvirt instance bool System.Xml.XmlReader::Read()
0x221b3  pop
0x221b4  br.s     loc_221BD
0x221b6  ldarg.0
0x221b7  callvirt instance bool System.Xml.XmlReader::Read()
0x221bc  pop
0x221bd  ldloc.0
0x221be  ret
```
