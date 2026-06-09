# Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensions

- ea: `0x5bd0`
- end: `0x5ced`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensions`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x52e0`

## callees

- `0x5030`
- `0x5100`
- `0x55b0`
- `0x56c0`
- `0x57d0`
- `0x5a00`
- `0x5b60`
- `0x5bd0`
- `0x5cf0`
- `0x5d50`

## string_xrefs

- `0x5bd0`: `Extension`

## pseudocode

```c

```

## disassembly

```asm
0x5bd0  ldstr    aExtension// "Extension"
0x5bd5  stloc.0
0x5bd6  ldarg.1
0x5bd7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5bdc  ldstr    aDelivery// "Delivery"
0x5be1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5be6  brtrue.s loc_5BFA
0x5be8  ldarg.1
0x5be9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5bee  ldstr    aDeliveryui// "DeliveryUI"
0x5bf3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5bf8  brfalse.s loc_5C03
0x5bfa  ldarg.0
0x5bfb  ldarg.1
0x5bfc  ldarg.2
0x5bfd  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseDeliveryExtensions(class [System.Xml]System.Xml.XmlNode child, class ExtensionArray array)
0x5c02  ret
0x5c03  ldarg.1
0x5c04  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5c09  ldstr    aEventprocessin// "EventProcessing"
0x5c0e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5c13  brfalse.s loc_5C1E
0x5c15  ldarg.0
0x5c16  ldarg.1
0x5c17  ldarg.2
0x5c18  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseEventExtensions(class [System.Xml]System.Xml.XmlNode child, class ExtensionArray array)
0x5c1d  ret
0x5c1e  ldarg.1
0x5c1f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5c24  ldstr    aRender// "Render"
0x5c29  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5c2e  brfalse.s loc_5C39
0x5c30  ldarg.0
0x5c31  ldarg.1
0x5c32  ldarg.2
0x5c33  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseRenderExtensions(class [System.Xml]System.Xml.XmlNode child, class ExtensionArray array)
0x5c38  ret
0x5c39  ldarg.1
0x5c3a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5c3f  ldstr    aData// "Data"
0x5c44  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5c49  brfalse.s loc_5C54
0x5c4b  ldarg.0
0x5c4c  ldarg.1
0x5c4d  ldarg.2
0x5c4e  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseDataExtensions(class [System.Xml]System.Xml.XmlNode child, class ExtensionArray array)
0x5c53  ret
0x5c54  ldarg.1
0x5c55  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5c5a  ldstr    aReportitems// "ReportItems"
0x5c5f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5c64  brfalse.s loc_5C6F
0x5c66  ldarg.0
0x5c67  ldarg.1
0x5c68  ldarg.2
0x5c69  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseReportItemExtensions(class [System.Xml]System.Xml.XmlNode child, class ExtensionArray array)
0x5c6e  ret
0x5c6f  ldarg.1
0x5c70  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5c75  ldstr    aReportitemdesi// "ReportItemDesigner"
0x5c7a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5c7f  brfalse.s loc_5C87
0x5c81  ldstr    aReportitem// "ReportItem"
0x5c86  stloc.0
0x5c87  ldarg.1
0x5c88  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x5c8d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5c92  stloc.1
0x5c93  br.s     loc_5CCE
0x5c95  ldloc.1
0x5c96  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5c9b  castclass [System.Xml]System.Xml.XmlNode
0x5ca0  stloc.2
0x5ca1  ldloc.2
0x5ca2  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x5ca7  ldc.i4.8
0x5ca8  beq.s    loc_5CCE
0x5caa  newobj   instance void Microsoft.ReportingServices.Diagnostics.Extension::.ctor()
0x5caf  stloc.3
0x5cb0  ldloc.3
0x5cb1  ldarg.1
0x5cb2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5cb7  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Type(string value)
0x5cbc  ldarg.0
0x5cbd  ldloc.2
0x5cbe  ldloca.s 3
0x5cc0  ldloc.0
0x5cc1  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensionElement(class [System.Xml]System.Xml.XmlNode child, class Microsoft.ReportingServices.Diagnostics.Extension& extension, string childName)
0x5cc6  ldarg.0
0x5cc7  ldloc.3
0x5cc8  ldarg.2
0x5cc9  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::AddExtensionToArray(class Microsoft.ReportingServices.Diagnostics.Extension extension, class ExtensionArray array)
0x5cce  ldloc.1
0x5ccf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5cd4  brtrue.s loc_5C95
0x5cd6  leave.s  loc_5CEC
0x5cd8  ldloc.1
0x5cd9  isinst   [mscorlib]System.IDisposable
0x5cde  stloc.s  4
0x5ce0  ldloc.s  4
0x5ce2  brfalse.s loc_5CEB
0x5ce4  ldloc.s  4
0x5ce6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ceb  endfinally
0x5cec  ret
```
