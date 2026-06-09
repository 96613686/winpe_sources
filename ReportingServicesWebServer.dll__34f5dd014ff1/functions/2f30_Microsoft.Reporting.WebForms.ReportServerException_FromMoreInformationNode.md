# Microsoft.Reporting.WebForms.ReportServerException::FromMoreInformationNode

- ea: `0x2f30`
- end: `0x2fcd`
- name: `Microsoft.Reporting.WebForms.ReportServerException::FromMoreInformationNode`
- size: `157`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ef0`
- `0x2f30`
- `0x22db0`

## callees

- `0x130`
- `0x2e60`
- `0x2f30`
- `0x2fd0`

## string_xrefs

- `0x2f4c`: `http://www.microsoft.com/sql/reportingservices`
- `0x2f7d`: `http://www.microsoft.com/sql/reportingservices`

## pseudocode

```c

```

## disassembly

```asm
0x2f30  ldarg.0
0x2f31  brtrue.s loc_2F35
0x2f33  ldnull
0x2f34  ret
0x2f35  ldarg.0
0x2f36  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x2f3b  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x2f40  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x2f45  stloc.0
0x2f46  ldloc.0
0x2f47  ldstr    aRs// "rs"
0x2f4c  ldstr    aHttpWwwMicroso// "http://www.microsoft.com/sql/reportings"...
0x2f51  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x2f56  ldnull
0x2f57  stloc.1
0x2f58  ldnull
0x2f59  stloc.2
0x2f5a  ldarg.0
0x2f5b  ldstr    aRsMessage// "rs:Message"
0x2f60  ldloc.0
0x2f61  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x2f66  stloc.3
0x2f67  ldloc.3
0x2f68  brfalse.s loc_2FAB
0x2f6a  ldloc.3
0x2f6b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2f70  stloc.s  5
0x2f72  ldloc.3
0x2f73  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2f78  ldstr    aErrorcode// "ErrorCode"
0x2f7d  ldstr    aHttpWwwMicroso// "http://www.microsoft.com/sql/reportings"...
0x2f82  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string, string)
0x2f87  stloc.s  6
0x2f89  ldloc.s  6
0x2f8b  brfalse.s loc_2F95
0x2f8d  ldloc.s  6
0x2f8f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2f94  stloc.2
0x2f95  ldloc.2
0x2f96  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2f9b  brfalse.s loc_2FA2
0x2f9d  ldloc.s  5
0x2f9f  stloc.1
0x2fa0  br.s     loc_2FAB
0x2fa2  ldloc.s  5
0x2fa4  ldloc.2
0x2fa5  call     string Microsoft.SqlServer.ReportingServices.SoapExceptionStrings::RSSoapMessageFormat(string message, string errorCode)
0x2faa  stloc.1
0x2fab  ldarg.0
0x2fac  call     class [System.Xml]System.Xml.XmlNode Microsoft.Reporting.WebForms.ReportServerException::GetNestedMoreInformationNode(class [System.Xml]System.Xml.XmlNode node)
0x2fb1  call     class Microsoft.Reporting.WebForms.ReportServerException Microsoft.Reporting.WebForms.ReportServerException::FromMoreInformationNode(class [System.Xml]System.Xml.XmlNode moreInfoNode)
0x2fb6  stloc.s  4
0x2fb8  ldloc.1
0x2fb9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2fbe  brfalse.s loc_2FC3
0x2fc0  ldloc.s  4
0x2fc2  ret
0x2fc3  ldloc.1
0x2fc4  ldloc.2
0x2fc5  ldloc.s  4
0x2fc7  newobj   instance void Microsoft.Reporting.WebForms.ReportServerException::.ctor(string message, string errorCode, class [mscorlib]System.Exception innerException)
0x2fcc  ret
```
