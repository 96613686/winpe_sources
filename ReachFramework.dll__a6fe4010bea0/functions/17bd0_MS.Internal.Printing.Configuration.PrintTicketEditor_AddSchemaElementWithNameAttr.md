# MS.Internal.Printing.Configuration.PrintTicketEditor::AddSchemaElementWithNameAttr

- ea: `0x17bd0`
- end: `0x17c2b`
- name: `MS.Internal.Printing.Configuration.PrintTicketEditor::AddSchemaElementWithNameAttr`
- size: `91`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16eb0`
- `0x16f30`
- `0x16fc0`
- `0x17090`
- `0x171a0`
- `0x17560`
- `0x17630`

## callees

- `0x17bd0`
- `0x17cf0`
- `0x18220`

## string_xrefs

- `0x17bdb`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x17bee`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x17c0d`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c

```

## disassembly

```asm
0x17bd0  ldarg.0
0x17bd1  callvirt instance class [System.Xml]System.Xml.XmlDocument MS.Internal.Printing.Configuration.InternalPrintTicket::get_XmlDoc()
0x17bd6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x17bdb  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/windows/20"...
0x17be0  callvirt instance string [System.Xml]System.Xml.XmlNode::GetPrefixOfNamespace(string)
0x17be5  stloc.0
0x17be6  ldarg.0
0x17be7  callvirt instance class [System.Xml]System.Xml.XmlDocument MS.Internal.Printing.Configuration.InternalPrintTicket::get_XmlDoc()
0x17bec  ldloc.0
0x17bed  ldarg.2
0x17bee  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/windows/20"...
0x17bf3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x17bf8  stloc.1
0x17bf9  ldarg.3
0x17bfa  brfalse.s loc_17C1E
0x17bfc  ldloc.1
0x17bfd  ldstr    aName// "name"
0x17c02  ldstr    asc_41B18// ""
0x17c07  ldarg.0
0x17c08  callvirt instance class [System.Xml]System.Xml.XmlDocument MS.Internal.Printing.Configuration.InternalPrintTicket::get_XmlDoc()
0x17c0d  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x17c12  ldarg.3
0x17c13  call     string MS.Internal.Printing.Configuration.XmlDocQName::GetQName(class [System.Xml]System.Xml.XmlDocument xmlDoc, string URI, string localName)
0x17c18  callvirt instance string [System.Xml]System.Xml.XmlElement::SetAttribute(string, string, string)
0x17c1d  pop
0x17c1e  ldarg.1
0x17c1f  ldloc.1
0x17c20  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x17c25  castclass [System.Xml]System.Xml.XmlElement
0x17c2a  ret
```
