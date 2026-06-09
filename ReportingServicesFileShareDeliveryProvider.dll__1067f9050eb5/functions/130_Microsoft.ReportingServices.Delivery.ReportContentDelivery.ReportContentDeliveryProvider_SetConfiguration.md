# Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::SetConfiguration

- ea: `0x130`
- end: `0x290`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::SetConfiguration`
- size: `352`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x130`
- `0x750`

## string_xrefs

- `0x1d9`: `RenderingExtension`
- `0x260`: `Error reading configuration information: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x130  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x135  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentCulture()
0x13a  stloc.0
0x13b  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x140  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x145  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0x14a  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x14f  stloc.1
0x150  ldloc.1
0x151  ldarg.1
0x152  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeOpenXmlDocumentString(class [System.Xml]System.Xml.XmlDocument, string)
0x157  ldloc.1
0x158  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x15d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x162  ldarg.0
0x163  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::get_ConfigurationTopElement()
0x168  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16d  brfalse  loc_23F
0x172  ldloc.1
0x173  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x178  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x17d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x182  stloc.2
0x183  br       loc_21E
0x188  ldloc.2
0x189  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x18e  castclass [System.Xml]System.Xml.XmlNode
0x193  stloc.3
0x194  ldloc.3
0x195  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x19a  stloc.s  4
0x19c  ldloc.s  4
0x19e  ldstr    aExcludedrender// "ExcludedRenderFormats"
0x1a3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1a8  brfalse.s loc_21E
0x1aa  ldarg.0
0x1ab  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_excludedRenderFormats
0x1b0  callvirt instance void [mscorlib]System.Collections.Hashtable::Clear()
0x1b5  ldloc.3
0x1b6  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x1bb  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1c0  stloc.s  5
0x1c2  br.s     loc_1FE
0x1c4  ldloc.s  5
0x1c6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1cb  castclass [System.Xml]System.Xml.XmlNode
0x1d0  stloc.s  6
0x1d2  ldloc.s  6
0x1d4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x1d9  ldstr    aRenderingexten// "RenderingExtension"
0x1de  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e3  brfalse.s loc_1FE
0x1e5  ldarg.0
0x1e6  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_excludedRenderFormats
0x1eb  ldloc.s  6
0x1ed  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1f2  ldloc.s  6
0x1f4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1f9  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x1fe  ldloc.s  5
0x200  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x205  brtrue.s loc_1C4
0x207  leave.s  loc_21E
0x209  ldloc.s  5
0x20b  isinst   [mscorlib]System.IDisposable
0x210  stloc.s  7
0x212  ldloc.s  7
0x214  brfalse.s loc_21D
0x216  ldloc.s  7
0x218  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21d  endfinally
0x21e  ldloc.2
0x21f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x224  brtrue   loc_188
0x229  leave.s  loc_23F
0x22b  ldloc.2
0x22c  isinst   [mscorlib]System.IDisposable
0x231  stloc.s  7
0x233  ldloc.s  7
0x235  brfalse.s loc_23E
0x237  ldloc.s  7
0x239  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23e  endfinally
0x23f  leave.s  loc_28F
0x241  stloc.s  8
0x243  ldloc.s  8
0x245  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x24a  brfalse.s loc_24E
0x24c  rethrow
0x24e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_tracer
0x253  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x258  brfalse.s loc_27A
0x25a  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_tracer
0x25f  ldc.i4.1
0x260  ldstr    aErrorReadingCo// "Error reading configuration information"...
0x265  ldc.i4.1
0x266  newarr   [mscorlib]System.Object
0x26b  dup
0x26c  ldc.i4.0
0x26d  ldloc.s  8
0x26f  callvirt instance string [mscorlib]System.Object::ToString()
0x274  stelem.ref
0x275  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x27a  ldloc.s  8
0x27c  ldnull
0x27d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(class [mscorlib]System.Exception, string)
0x282  throw
0x283  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x288  ldloc.0
0x289  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0x28e  endfinally
0x28f  ret
```
