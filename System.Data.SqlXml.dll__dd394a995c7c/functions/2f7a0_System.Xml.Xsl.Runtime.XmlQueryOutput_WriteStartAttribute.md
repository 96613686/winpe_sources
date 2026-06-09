# System.Xml.Xsl.Runtime.XmlQueryOutput::WriteStartAttribute

- ea: `0x2f7a0`
- end: `0x2f7e9`
- name: `System.Xml.Xsl.Runtime.XmlQueryOutput::WriteStartAttribute`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x2f7a0`
- `0x2fac0`
- `0x2fd90`
- `0x303c0`
- `0x30460`

## string_xrefs

- `0x2f7aa`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x2f7a0  ldarg.1
0x2f7a1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2f7a6  ldc.i4.5
0x2f7a7  bne.un.s loc_2F7BE
0x2f7a9  ldarg.1
0x2f7aa  ldstr    aXmlns// "xmlns"
0x2f7af  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f7b4  brfalse.s loc_2F7BE
0x2f7b6  ldarg.0
0x2f7b7  ldarg.2
0x2f7b8  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteStartNamespace(string prefix)
0x2f7bd  ret
0x2f7be  ldarg.0
0x2f7bf  ldc.i4.2
0x2f7c0  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::ConstructInEnumAttrs(valuetype [System.Xml]System.Xml.XPath.XPathNodeType rootType)
0x2f7c5  ldarg.3
0x2f7c6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2f7cb  brfalse.s loc_2F7DF
0x2f7cd  ldarg.0
0x2f7ce  ldfld    int32 System.Xml.Xsl.Runtime.XmlQueryOutput::depth
0x2f7d3  brfalse.s loc_2F7DF
0x2f7d5  ldarg.0
0x2f7d6  ldarg.1
0x2f7d7  ldarg.3
0x2f7d8  call     instance string System.Xml.Xsl.Runtime.XmlQueryOutput::CheckAttributePrefix(string prefix, string ns)
0x2f7dd  starg.s  1
0x2f7df  ldarg.0
0x2f7e0  ldarg.1
0x2f7e1  ldarg.2
0x2f7e2  ldarg.3
0x2f7e3  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteStartAttributeUnchecked(string prefix, string localName, string ns)
0x2f7e8  ret
```
