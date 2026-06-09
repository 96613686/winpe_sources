# Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ExtractRenderingExtensionDeviceInfo

- ea: `0x5920`
- end: `0x59f9`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ExtractRenderingExtensionDeviceInfo`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x57d0`

## callees

- `0x5920`
- `0x63a0`

## string_xrefs

- `0x5921`: `Configuration`

## pseudocode

```c

```

## disassembly

```asm
0x5920  ldarg.1
0x5921  ldstr    aConfiguration// "Configuration"
0x5926  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x592b  stloc.0
0x592c  ldloc.0
0x592d  brtrue.s loc_5930
0x592f  ret
0x5930  ldloc.0
0x5931  ldstr    aDeviceinfo// "DeviceInfo"
0x5936  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x593b  stloc.1
0x593c  ldloc.1
0x593d  brtrue.s loc_5940
0x593f  ret
0x5940  ldloc.1
0x5941  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x5946  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x594b  stloc.2
0x594c  br       loc_59D7
0x5951  ldloc.2
0x5952  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5957  castclass [System.Xml]System.Xml.XmlNode
0x595c  dup
0x595d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5962  stloc.3
0x5963  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5968  stloc.s  4
0x596a  ldloc.3
0x596b  brfalse.s loc_59D7
0x596d  ldloc.s  4
0x596f  brfalse.s loc_59D7
0x5971  ldloc.3
0x5972  callvirt instance string [mscorlib]System.String::Trim()
0x5977  ldsfld   string [mscorlib]System.String::Empty
0x597c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5981  brfalse.s loc_59D7
0x5983  ldloc.3
0x5984  callvirt instance string [mscorlib]System.String::Trim()
0x5989  stloc.3
0x598a  ldloc.3
0x598b  ldstr    aFielddelimiter// "FieldDelimiter"
0x5990  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5995  brfalse.s loc_59AD
0x5997  ldloc.3
0x5998  ldstr    aRecorddelimite// "RecordDelimiter"
0x599d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x59a2  brfalse.s loc_59AD
0x59a4  ldloc.s  4
0x59a6  callvirt instance string [mscorlib]System.String::Trim()
0x59ab  stloc.s  4
0x59ad  ldloc.s  4
0x59af  ldsfld   string [mscorlib]System.String::Empty
0x59b4  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x59b9  brfalse.s loc_59D7
0x59bb  ldarg.2
0x59bc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Diagnostics.RenderingExtension::get_DeviceInfo()
0x59c1  ldloc.3
0x59c2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x59c7  brtrue.s loc_59D7
0x59c9  ldarg.2
0x59ca  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Diagnostics.RenderingExtension::get_DeviceInfo()
0x59cf  ldloc.3
0x59d0  ldloc.s  4
0x59d2  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x59d7  ldloc.2
0x59d8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x59dd  brtrue   loc_5951
0x59e2  leave.s  loc_59F8
0x59e4  ldloc.2
0x59e5  isinst   [mscorlib]System.IDisposable
0x59ea  stloc.s  5
0x59ec  ldloc.s  5
0x59ee  brfalse.s loc_59F7
0x59f0  ldloc.s  5
0x59f2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x59f7  endfinally
0x59f8  ret
```
