# Microsoft.ReportingServices.Library.ServerConfigInfo::XmlToList

- ea: `0x5c0`
- end: `0x694`
- name: `Microsoft.ReportingServices.Library.ServerConfigInfo::XmlToList`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5c0`
- `0x6a0`
- `0x6c0`

## string_xrefs

- `0x5e0`: `ServerConfigInfo`
- `0x64a`: `ServiceAccountName`

## pseudocode

```c

```

## disassembly

```asm
0x5c0  ldarg.0
0x5c1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5c6  brfalse.s loc_5CA
0x5c8  ldnull
0x5c9  ret
0x5ca  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x5cf  dup
0x5d0  ldarg.0
0x5d1  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeOpenXmlDocumentString(class [System.Xml]System.Xml.XmlDocument, string)
0x5d6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5db  ldstr    a01// "/{0}/{1}"
0x5e0  ldstr    aServerconfigin// "ServerConfigInfo"
0x5e5  ldstr    aServer// "Server"
0x5ea  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x5ef  stloc.0
0x5f0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ServerConfigInfo>::.ctor()
0x5f5  stloc.1
0x5f6  ldloc.0
0x5f7  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x5fc  stloc.2
0x5fd  ldloc.2
0x5fe  brfalse  loc_692
0x603  ldloc.2
0x604  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x609  stloc.3
0x60a  br.s     loc_674
0x60c  ldloc.3
0x60d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x612  castclass [System.Xml]System.Xml.XmlNode
0x617  stloc.s  4
0x619  newobj   instance void Microsoft.ReportingServices.Library.ServerConfigInfo::.ctor()
0x61e  stloc.s  5
0x620  ldloc.s  5
0x622  ldloc.s  4
0x624  ldstr    aMachinename// "MachineName"
0x629  call     string Microsoft.ReportingServices.Library.ServerConfigInfo::GetServerNodeValue(class [System.Xml]System.Xml.XmlNode serverNode, string requestedElement)
0x62e  stfld    string Microsoft.ReportingServices.Library.ServerConfigInfo::MachineName
0x633  ldloc.s  5
0x635  ldloc.s  4
0x637  ldstr    aInstancename// "InstanceName"
0x63c  call     string Microsoft.ReportingServices.Library.ServerConfigInfo::GetServerNodeValue(class [System.Xml]System.Xml.XmlNode serverNode, string requestedElement)
0x641  stfld    string Microsoft.ReportingServices.Library.ServerConfigInfo::InstanceName
0x646  ldloc.s  5
0x648  ldloc.s  4
0x64a  ldstr    aServiceaccount// "ServiceAccountName"
0x64f  call     string Microsoft.ReportingServices.Library.ServerConfigInfo::GetServerNodeValue(class [System.Xml]System.Xml.XmlNode serverNode, string requestedElement)
0x654  stfld    string Microsoft.ReportingServices.Library.ServerConfigInfo::ServiceAccountName
0x659  ldloc.s  5
0x65b  ldloc.s  4
0x65d  ldstr    aReportserverur// "ReportServerUrlItem"
0x662  call     string Microsoft.ReportingServices.Library.ServerConfigInfo::GetServerNodeValue(class [System.Xml]System.Xml.XmlNode serverNode, string requestedElement)
0x667  stfld    string Microsoft.ReportingServices.Library.ServerConfigInfo::ReportServerUrlItem
0x66c  ldloc.1
0x66d  ldloc.s  5
0x66f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ServerConfigInfo>::Add(var<u1>)
0x674  ldloc.3
0x675  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x67a  brtrue.s loc_60C
0x67c  leave.s  loc_692
0x67e  ldloc.3
0x67f  isinst   [mscorlib]System.IDisposable
0x684  stloc.s  6
0x686  ldloc.s  6
0x688  brfalse.s loc_691
0x68a  ldloc.s  6
0x68c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x691  endfinally
0x692  ldloc.1
0x693  ret
```
