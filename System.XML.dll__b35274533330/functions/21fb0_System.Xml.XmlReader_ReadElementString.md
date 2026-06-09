# System.Xml.XmlReader::ReadElementString

- ea: `0x21fb0`
- end: `0x2204c`
- name: `System.Xml.XmlReader::ReadElementString`
- size: `156`
- prototype: ``
- caller_count: `20`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18bb0`
- `0x78580`
- `0x8a4a0`
- `0xabee0`
- `0xabf50`
- `0xabfc0`
- `0xac030`
- `0xac0a0`
- `0xac110`
- `0xac180`
- `0xac1f0`
- `0xac260`
- `0xac2d0`
- `0xac340`
- `0xac3b0`
- `0xac420`
- `0xac490`
- `0xac570`
- `0xac5e0`
- `0xac680`

## callees

- `0x126c0`
- `0x12730`
- `0x214b0`
- `0x21570`
- `0x21c60`
- `0x21db0`
- `0x21e40`
- `0x21fb0`

## string_xrefs

- `0x21fbf`: `Xml_InvalidNodeType`
- `0x22004`: `Xml_UnexpectedNodeInSimpleContent`
- `0x22028`: `ReadElementString`

## pseudocode

```c

```

## disassembly

```asm
0x21fb0  ldsfld   string [mscorlib]System.String::Empty
0x21fb5  stloc.0
0x21fb6  ldarg.0
0x21fb7  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::MoveToContent()
0x21fbc  ldc.i4.1
0x21fbd  beq.s    loc_21FE4
0x21fbf  ldstr    aXmlInvalidnode// "Xml_InvalidNodeType"
0x21fc4  ldarg.0
0x21fc5  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x21fca  stloc.1
0x21fcb  ldloca.s 1
0x21fcd  constrained. System.Xml.XmlNodeType
0x21fd3  callvirt instance string [mscorlib]System.Object::ToString()
0x21fd8  ldarg.0
0x21fd9  isinst   System.Xml.IXmlLineInfo
0x21fde  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class System.Xml.IXmlLineInfo lineInfo)
0x21fe3  throw
0x21fe4  ldarg.0
0x21fe5  callvirt instance bool System.Xml.XmlReader::get_IsEmptyElement()
0x21fea  brtrue.s loc_22043
0x21fec  ldarg.0
0x21fed  callvirt instance bool System.Xml.XmlReader::Read()
0x21ff2  pop
0x21ff3  ldarg.0
0x21ff4  callvirt instance string System.Xml.XmlReader::ReadString()
0x21ff9  stloc.0
0x21ffa  ldarg.0
0x21ffb  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x22000  ldc.i4.s 0xF
0x22002  beq.s    loc_2203A
0x22004  ldstr    aXmlUnexpectedn// "Xml_UnexpectedNodeInSimpleContent"
0x22009  ldc.i4.2
0x2200a  newarr   [mscorlib]System.String
0x2200f  dup
0x22010  ldc.i4.0
0x22011  ldarg.0
0x22012  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x22017  stloc.1
0x22018  ldloca.s 1
0x2201a  constrained. System.Xml.XmlNodeType
0x22020  callvirt instance string [mscorlib]System.Object::ToString()
0x22025  stelem.ref
0x22026  dup
0x22027  ldc.i4.1
0x22028  ldstr    aReadelementstr// "ReadElementString"
0x2202d  stelem.ref
0x2202e  ldarg.0
0x2202f  isinst   System.Xml.IXmlLineInfo
0x22034  newobj   instance void System.Xml.XmlException::.ctor(string res, string[] args, class System.Xml.IXmlLineInfo lineInfo)
0x22039  throw
0x2203a  ldarg.0
0x2203b  callvirt instance bool System.Xml.XmlReader::Read()
0x22040  pop
0x22041  br.s     loc_2204A
0x22043  ldarg.0
0x22044  callvirt instance bool System.Xml.XmlReader::Read()
0x22049  pop
0x2204a  ldloc.0
0x2204b  ret
```
