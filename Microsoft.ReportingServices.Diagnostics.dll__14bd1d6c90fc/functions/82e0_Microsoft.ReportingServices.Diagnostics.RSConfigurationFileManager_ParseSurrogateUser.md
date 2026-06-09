# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseSurrogateUser

- ea: `0x82e0`
- end: `0x8381`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseSurrogateUser`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7d20`

## callees

- `0x1710`
- `0x82e0`

## pseudocode

```c

```

## disassembly

```asm
0x82e0  ldarg.0
0x82e1  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x82e6  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x82eb  stloc.0
0x82ec  br.s     loc_8365
0x82ee  ldloc.0
0x82ef  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x82f4  castclass [System.Xml]System.Xml.XmlNode
0x82f9  stloc.1
0x82fa  ldloc.1
0x82fb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8300  stloc.2
0x8301  ldloc.1
0x8302  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8307  ldstr    aUsername// "UserName"
0x830c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8311  brfalse.s loc_8323
0x8313  ldarg.1
0x8314  ldc.i4.s 0x5B
0x8316  ldloc.2
0x8317  ldstr    aUsername// "UserName"
0x831c  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value, string name)
0x8321  br.s     loc_8365
0x8323  ldloc.1
0x8324  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8329  ldstr    aPassword// "Password"
0x832e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8333  brfalse.s loc_8345
0x8335  ldarg.1
0x8336  ldc.i4.s 0x5C
0x8338  ldloc.2
0x8339  ldstr    aPassword// "Password"
0x833e  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value, string name)
0x8343  br.s     loc_8365
0x8345  ldloc.1
0x8346  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x834b  ldstr    aDomain// "Domain"
0x8350  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8355  brfalse.s loc_8365
0x8357  ldarg.1
0x8358  ldc.i4.s 0x5A
0x835a  ldloc.2
0x835b  ldstr    aDomain// "Domain"
0x8360  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value, string name)
0x8365  ldloc.0
0x8366  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x836b  brtrue.s loc_82EE
0x836d  leave.s  loc_8380
0x836f  ldloc.0
0x8370  isinst   [mscorlib]System.IDisposable
0x8375  stloc.3
0x8376  ldloc.3
0x8377  brfalse.s loc_837F
0x8379  ldloc.3
0x837a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x837f  endfinally
0x8380  ret
```
