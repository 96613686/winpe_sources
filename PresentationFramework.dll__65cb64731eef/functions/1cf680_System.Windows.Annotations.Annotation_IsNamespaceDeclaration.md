# System.Windows.Annotations.Annotation::IsNamespaceDeclaration

- ea: `0x1cf680`
- end: `0x1cf6db`
- name: `System.Windows.Annotations.Annotation::IsNamespaceDeclaration`
- size: `91`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1cf6e0`
- `0x1cf770`
- `0x1d09f0`
- `0x1d3fe0`

## callees

- `0x1cf680`

## string_xrefs

- `0x1cf6a5`: `xmlns`
- `0x1cf6b9`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x1cf680  ldarg.0
0x1cf681  ldnull
0x1cf682  cgt.un
0x1cf684  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool)
0x1cf689  ldarg.0
0x1cf68a  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1cf68f  ldc.i4.2
0x1cf690  bne.un.s loc_1CF6D9
0x1cf692  ldarg.0
0x1cf693  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Prefix()
0x1cf698  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1cf69d  brtrue.s loc_1CF6B3
0x1cf69f  ldarg.0
0x1cf6a0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1cf6a5  ldstr    aXmlns// "xmlns"
0x1cf6aa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cf6af  brfalse.s loc_1CF6D9
0x1cf6b1  ldc.i4.1
0x1cf6b2  ret
0x1cf6b3  ldarg.0
0x1cf6b4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Prefix()
0x1cf6b9  ldstr    aXmlns// "xmlns"
0x1cf6be  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cf6c3  brtrue.s loc_1CF6D7
0x1cf6c5  ldarg.0
0x1cf6c6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Prefix()
0x1cf6cb  ldstr    aXml// "xml"
0x1cf6d0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cf6d5  brfalse.s loc_1CF6D9
0x1cf6d7  ldc.i4.1
0x1cf6d8  ret
0x1cf6d9  ldc.i4.0
0x1cf6da  ret
```
