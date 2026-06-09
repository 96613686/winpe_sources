# Microsoft.ReportingServices.Library.WebConfigUtil::GetWebConfigAuthenticationNode

- ea: `0x10170`
- end: `0x10201`
- name: `Microsoft.ReportingServices.Library.WebConfigUtil::GetWebConfigAuthenticationNode`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x87c20`
- `0x87c70`

## callees

- `0x10170`

## string_xrefs

- `0x10194`: `\web.config`
- `0x101d5`: `configns`
- `0x101e3`: `configns:configuration/configns:system.web/configns:authentication`
- `0x101f4`: `configuration/system.web/authentication`

## pseudocode

```c

```

## disassembly

```asm
0x10170  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RequestContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_ReqContext()
0x10175  stloc.1
0x10176  ldloc.1
0x10177  brfalse.s loc_10188
0x10179  ldloc.1
0x1017a  ldloc.1
0x1017b  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RequestContextBase::get_ApplicationPath()
0x10180  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RequestContextBase::MapPath(string)
0x10185  stloc.0
0x10186  br.s     loc_10193
0x10188  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x1018d  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ConfigFilePath()
0x10192  stloc.0
0x10193  ldloc.0
0x10194  ldstr    aWebConfig// "\\web.config"
0x10199  call     string [mscorlib]System.String::Concat(string, string)
0x1019e  stloc.3
0x1019f  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x101a4  stloc.s  4
0x101a6  ldloc.s  4
0x101a8  ldloc.3
0x101a9  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeOpenXmlDocumentFile(class [System.Xml]System.Xml.XmlDocument, string)
0x101ae  ldloc.s  4
0x101b0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x101b5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_NamespaceURI()
0x101ba  stloc.s  5
0x101bc  ldloc.s  5
0x101be  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x101c3  brtrue.s loc_101F2
0x101c5  ldloc.s  4
0x101c7  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x101cc  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x101d1  stloc.s  6
0x101d3  ldloc.s  6
0x101d5  ldstr    aConfigns// "configns"
0x101da  ldloc.s  5
0x101dc  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x101e1  ldloc.s  4
0x101e3  ldstr    aConfignsConfig// "configns:configuration/configns:system."...
0x101e8  ldloc.s  6
0x101ea  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x101ef  stloc.2
0x101f0  br.s     loc_101FF
0x101f2  ldloc.s  4
0x101f4  ldstr    aConfigurationS// "configuration/system.web/authentication"
0x101f9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x101fe  stloc.2
0x101ff  ldloc.2
0x10200  ret
```
