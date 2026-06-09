# Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseEventExtensions

- ea: `0x56c0`
- end: `0x57c2`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseEventExtensions`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x5bd0`

## callees

- `0x4ea0`
- `0x4ed0`
- `0x4ef0`
- `0x4f10`
- `0x4fa0`
- `0x5030`
- `0x56c0`
- `0x5cf0`
- `0x5d40`

## pseudocode

```c

```

## disassembly

```asm
0x56c0  ldarg.1
0x56c1  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x56c6  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x56cb  stloc.0
0x56cc  br       loc_57A0
0x56d1  ldloc.0
0x56d2  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x56d7  castclass [System.Xml]System.Xml.XmlNode
0x56dc  stloc.1
0x56dd  ldloc.1
0x56de  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x56e3  ldc.i4.8
0x56e4  beq      loc_57A0
0x56e9  newobj   instance void Microsoft.ReportingServices.Diagnostics.EventExtension::.ctor()
0x56ee  stloc.2
0x56ef  ldloc.2
0x56f0  ldarg.1
0x56f1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x56f6  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Type(string value)
0x56fb  ldloc.2
0x56fc  stloc.3
0x56fd  ldarg.0
0x56fe  ldloc.1
0x56ff  ldloca.s 3
0x5701  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensionElement(class [System.Xml]System.Xml.XmlNode child, class Microsoft.ReportingServices.Diagnostics.Extension& extension)
0x5706  ldloc.1
0x5707  ldstr    aMaxretries// "MaxRetries"
0x570c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5711  stloc.s  4
0x5713  ldloc.s  4
0x5715  brfalse.s loc_572E
0x5717  ldloc.2
0x5718  ldloc.s  4
0x571a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x571f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5724  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x5729  callvirt instance void Microsoft.ReportingServices.Diagnostics.EventExtension::set_MaxRetries(int32 value)
0x572e  ldloc.1
0x572f  ldstr    aSecondsbeforer// "SecondsBeforeRetry"
0x5734  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5739  stloc.s  4
0x573b  ldloc.s  4
0x573d  brfalse.s loc_5756
0x573f  ldloc.2
0x5740  ldloc.s  4
0x5742  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5747  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x574c  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x5751  callvirt instance void Microsoft.ReportingServices.Diagnostics.EventExtension::set_SecondsBeforeRetry(int32 value)
0x5756  ldloc.1
0x5757  ldstr    aEvent// "Event"
0x575c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5761  stloc.s  5
0x5763  ldloc.s  5
0x5765  brfalse.s loc_577A
0x5767  ldloc.s  5
0x5769  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x576e  ldstr    asc_19000// ""
0x5773  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5778  brfalse.s loc_578B
0x577a  ldloc.3
0x577b  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x5780  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStringsWrapper::NoEventForEventProcessor(string)
0x5785  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x578a  throw
0x578b  ldloc.2
0x578c  ldloc.s  5
0x578e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5793  callvirt instance void Microsoft.ReportingServices.Diagnostics.EventExtension::set_EventType(string value)
0x5798  ldarg.0
0x5799  ldloc.2
0x579a  ldarg.2
0x579b  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::AddExtensionToArray(class Microsoft.ReportingServices.Diagnostics.Extension extension, class ExtensionArray array)
0x57a0  ldloc.0
0x57a1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x57a6  brtrue   loc_56D1
0x57ab  leave.s  loc_57C1
0x57ad  ldloc.0
0x57ae  isinst   [mscorlib]System.IDisposable
0x57b3  stloc.s  6
0x57b5  ldloc.s  6
0x57b7  brfalse.s loc_57C0
0x57b9  ldloc.s  6
0x57bb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x57c0  endfinally
0x57c1  ret
```
