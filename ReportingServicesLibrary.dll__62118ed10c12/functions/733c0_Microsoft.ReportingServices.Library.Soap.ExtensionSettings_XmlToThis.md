# Microsoft.ReportingServices.Library.Soap.ExtensionSettings::XmlToThis

- ea: `0x733c0`
- end: `0x73407`
- name: `Microsoft.ReportingServices.Library.Soap.ExtensionSettings::XmlToThis`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x44220`
- `0x44f30`

## callees

- `0x70f70`
- `0x73330`
- `0x733c0`

## string_xrefs

- `0x733d3`: `/ExtensionSettings/Extension`
- `0x733ed`: `/ExtensionSettings/ParameterValues/ParameterValue`

## pseudocode

```c

```

## disassembly

```asm
0x733c0  newobj   instance void Microsoft.ReportingServices.Library.Soap.ExtensionSettings::.ctor()
0x733c5  stloc.0
0x733c6  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x733cb  dup
0x733cc  ldarg.0
0x733cd  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeOpenXmlDocumentString(class [System.Xml]System.Xml.XmlDocument, string)
0x733d2  dup
0x733d3  ldstr    aExtensionsetti_1// "/ExtensionSettings/Extension"
0x733d8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x733dd  stloc.1
0x733de  ldloc.1
0x733df  brfalse.s loc_733ED
0x733e1  ldloc.0
0x733e2  ldloc.1
0x733e3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x733e8  stfld    string Microsoft.ReportingServices.Library.Soap.ExtensionSettings::Extension
0x733ed  ldstr    aExtensionsetti_2// "/ExtensionSettings/ParameterValues/Para"...
0x733f2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x733f7  stloc.2
0x733f8  ldloc.0
0x733f9  ldloc.2
0x733fa  ldc.i4.0
0x733fb  call     class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference::XmlNodesToThisArray(class [System.Xml]System.Xml.XmlNodeList nodes, bool createParameterValueArray)
0x73400  stfld    class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.Soap.ExtensionSettings::ParameterValues
0x73405  ldloc.0
0x73406  ret
```
