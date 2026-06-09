# System.Xml.XmlWriter::WriteLocalNamespaces

- ea: `0x40fc0`
- end: `0x41010`
- name: `System.Xml.XmlWriter::WriteLocalNamespaces`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x40da0`
- `0x40fc0`

## callees

- `0x40810`
- `0x40fc0`
- `0xee7f0`
- `0xeefd0`
- `0xef1f0`

## string_xrefs

- `0x40ff1`: `http://www.w3.org/2000/xmlns/`
- `0x41004`: `http://www.w3.org/2000/xmlns/`
- `0x40fec`: `xmlns`
- `0x40ffe`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x40fc0  ldarg.1
0x40fc1  callvirt instance string System.Xml.XPath.XPathNavigator::get_LocalName()
0x40fc6  stloc.0
0x40fc7  ldarg.1
0x40fc8  callvirt instance string System.Xml.XPath.XPathItem::get_Value()
0x40fcd  stloc.1
0x40fce  ldarg.1
0x40fcf  ldc.i4.2
0x40fd0  callvirt instance bool System.Xml.XPath.XPathNavigator::MoveToNextNamespace(valuetype System.Xml.XPath.XPathNamespaceScope namespaceScope)
0x40fd5  brfalse.s loc_40FDE
0x40fd7  ldarg.0
0x40fd8  ldarg.1
0x40fd9  call     instance void System.Xml.XmlWriter::WriteLocalNamespaces(class System.Xml.XPath.XPathNavigator nsNav)
0x40fde  ldloc.0
0x40fdf  callvirt instance int32 [mscorlib]System.String::get_Length()
0x40fe4  brtrue.s loc_40FFD
0x40fe6  ldarg.0
0x40fe7  ldsfld   string [mscorlib]System.String::Empty
0x40fec  ldstr    aXmlns// "xmlns"
0x40ff1  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x40ff6  ldloc.1
0x40ff7  call     instance void System.Xml.XmlWriter::WriteAttributeString(string prefix, string localName, string ns, string value)
0x40ffc  ret
0x40ffd  ldarg.0
0x40ffe  ldstr    aXmlns// "xmlns"
0x41003  ldloc.0
0x41004  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x41009  ldloc.1
0x4100a  call     instance void System.Xml.XmlWriter::WriteAttributeString(string prefix, string localName, string ns, string value)
0x4100f  ret
```
