# Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseReportItemExtensions

- ea: `0x5a00`
- end: `0x5a67`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseReportItemExtensions`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x5bd0`

## callees

- `0x5030`
- `0x5100`
- `0x5a00`
- `0x5cf0`
- `0x5d50`

## pseudocode

```c

```

## disassembly

```asm
0x5a00  ldarg.1
0x5a01  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x5a06  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5a0b  stloc.0
0x5a0c  br.s     loc_5A4B
0x5a0e  ldloc.0
0x5a0f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5a14  castclass [System.Xml]System.Xml.XmlNode
0x5a19  stloc.1
0x5a1a  ldloc.1
0x5a1b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x5a20  ldc.i4.8
0x5a21  beq.s    loc_5A4B
0x5a23  newobj   instance void Microsoft.ReportingServices.Diagnostics.Extension::.ctor()
0x5a28  stloc.2
0x5a29  ldloc.2
0x5a2a  ldarg.1
0x5a2b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5a30  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Type(string value)
0x5a35  ldarg.0
0x5a36  ldloc.1
0x5a37  ldloca.s 2
0x5a39  ldstr    aReportitem// "ReportItem"
0x5a3e  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensionElement(class [System.Xml]System.Xml.XmlNode child, class Microsoft.ReportingServices.Diagnostics.Extension& extension, string childName)
0x5a43  ldarg.0
0x5a44  ldloc.2
0x5a45  ldarg.2
0x5a46  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::AddExtensionToArray(class Microsoft.ReportingServices.Diagnostics.Extension extension, class ExtensionArray array)
0x5a4b  ldloc.0
0x5a4c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5a51  brtrue.s loc_5A0E
0x5a53  leave.s  loc_5A66
0x5a55  ldloc.0
0x5a56  isinst   [mscorlib]System.IDisposable
0x5a5b  stloc.3
0x5a5c  ldloc.3
0x5a5d  brfalse.s loc_5A65
0x5a5f  ldloc.3
0x5a60  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a65  endfinally
0x5a66  ret
```
