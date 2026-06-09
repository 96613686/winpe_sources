# Microsoft.Reporting.WebForms.ReportServerException::GetNestedMoreInformationNode

- ea: `0x2fd0`
- end: `0x3003`
- name: `Microsoft.Reporting.WebForms.ReportServerException::GetNestedMoreInformationNode`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ef0`
- `0x2f30`

## callees

- `0x2fd0`

## string_xrefs

- `0x2fec`: `http://www.microsoft.com/sql/reportingservices`

## pseudocode

```c

```

## disassembly

```asm
0x2fd0  ldarg.0
0x2fd1  brtrue.s loc_2FD5
0x2fd3  ldnull
0x2fd4  ret
0x2fd5  ldarg.0
0x2fd6  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x2fdb  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x2fe0  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x2fe5  stloc.0
0x2fe6  ldloc.0
0x2fe7  ldstr    aRs// "rs"
0x2fec  ldstr    aHttpWwwMicroso// "http://www.microsoft.com/sql/reportings"...
0x2ff1  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x2ff6  ldarg.0
0x2ff7  ldstr    aRsMoreinformat// "rs:MoreInformation"
0x2ffc  ldloc.0
0x2ffd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x3002  ret
```
