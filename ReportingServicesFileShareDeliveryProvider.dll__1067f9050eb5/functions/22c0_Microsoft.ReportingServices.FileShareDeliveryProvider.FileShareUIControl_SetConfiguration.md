# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::SetConfiguration

- ea: `0x22c0`
- end: `0x2347`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::SetConfiguration`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x22c0`

## string_xrefs

- `0x22d8`: `FileShareConfiguration`
- `0x230b`: `DefaultRenderingExtension`

## pseudocode

```c

```

## disassembly

```asm
0x22c0  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x22c5  stloc.0
0x22c6  ldloc.0
0x22c7  ldarg.1
0x22c8  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeOpenXmlDocumentString(class [System.Xml]System.Xml.XmlDocument, string)
0x22cd  ldloc.0
0x22ce  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x22d3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x22d8  ldstr    aFileshareconfi// "FileShareConfiguration"
0x22dd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22e2  brfalse.s loc_2341
0x22e4  ldloc.0
0x22e5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x22ea  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x22ef  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x22f4  stloc.1
0x22f5  br.s     loc_2323
0x22f7  ldloc.1
0x22f8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x22fd  castclass [System.Xml]System.Xml.XmlNode
0x2302  stloc.2
0x2303  ldloc.2
0x2304  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x2309  stloc.3
0x230a  ldloc.3
0x230b  ldstr    aDefaultrenderi// "DefaultRenderingExtension"
0x2310  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2315  brfalse.s loc_2323
0x2317  ldarg.0
0x2318  ldloc.2
0x2319  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x231e  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_defaultRenderingExtension
0x2323  ldloc.1
0x2324  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2329  brtrue.s loc_22F7
0x232b  leave.s  loc_2341
0x232d  ldloc.1
0x232e  isinst   [mscorlib]System.IDisposable
0x2333  stloc.s  4
0x2335  ldloc.s  4
0x2337  brfalse.s loc_2340
0x2339  ldloc.s  4
0x233b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2340  endfinally
0x2341  leave.s  loc_2346
0x2343  pop
0x2344  leave.s  loc_2346
0x2346  ret
```
