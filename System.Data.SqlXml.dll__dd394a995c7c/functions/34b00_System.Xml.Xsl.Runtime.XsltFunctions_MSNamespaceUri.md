# System.Xml.Xsl.Runtime.XsltFunctions::MSNamespaceUri

- ea: `0x34b00`
- end: `0x34b5b`
- name: `System.Xml.Xsl.Runtime.XsltFunctions::MSNamespaceUri`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x34b00`

## string_xrefs

- `0x34b23`: `xmlns`
- `0x34b4f`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c

```

## disassembly

```asm
0x34b00  ldarg.0
0x34b01  ldc.i4.0
0x34b02  ldloca.s 0
0x34b04  call     int32 [System.Xml]System.Xml.ValidateNames::ParseQName(string, int32, int32&)
0x34b09  stloc.1
0x34b0a  ldloc.1
0x34b0b  ldarg.0
0x34b0c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x34b11  beq.s    loc_34B19
0x34b13  ldsfld   string [mscorlib]System.String::Empty
0x34b18  ret
0x34b19  ldarg.0
0x34b1a  ldc.i4.0
0x34b1b  ldloc.0
0x34b1c  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x34b21  stloc.2
0x34b22  ldloc.2
0x34b23  ldstr    aXmlns// "xmlns"
0x34b28  call     bool [mscorlib]System.String::op_Equality(string, string)
0x34b2d  brfalse.s loc_34B35
0x34b2f  ldsfld   string [mscorlib]System.String::Empty
0x34b34  ret
0x34b35  ldarg.1
0x34b36  ldloc.2
0x34b37  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::LookupNamespace(string)
0x34b3c  stloc.3
0x34b3d  ldloc.3
0x34b3e  brfalse.s loc_34B42
0x34b40  ldloc.3
0x34b41  ret
0x34b42  ldloc.2
0x34b43  ldstr    aXml// "xml"
0x34b48  call     bool [mscorlib]System.String::op_Equality(string, string)
0x34b4d  brfalse.s loc_34B55
0x34b4f  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x34b54  ret
0x34b55  ldsfld   string [mscorlib]System.String::Empty
0x34b5a  ret
```
