# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseFileShareUser

- ea: `0x8390`
- end: `0x8431`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseFileShareUser`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7d20`

## callees

- `0x1710`
- `0x8390`

## pseudocode

```c

```

## disassembly

```asm
0x8390  ldarg.0
0x8391  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x8396  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x839b  stloc.0
0x839c  br.s     loc_8415
0x839e  ldloc.0
0x839f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x83a4  castclass [System.Xml]System.Xml.XmlNode
0x83a9  stloc.1
0x83aa  ldloc.1
0x83ab  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x83b0  stloc.2
0x83b1  ldloc.1
0x83b2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x83b7  ldstr    aUsername// "UserName"
0x83bc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x83c1  brfalse.s loc_83D3
0x83c3  ldarg.1
0x83c4  ldc.i4.s 0x6F
0x83c6  ldloc.2
0x83c7  ldstr    aUsername// "UserName"
0x83cc  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value, string name)
0x83d1  br.s     loc_8415
0x83d3  ldloc.1
0x83d4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x83d9  ldstr    aPassword// "Password"
0x83de  call     bool [mscorlib]System.String::op_Equality(string, string)
0x83e3  brfalse.s loc_83F5
0x83e5  ldarg.1
0x83e6  ldc.i4.s 0x70
0x83e8  ldloc.2
0x83e9  ldstr    aPassword// "Password"
0x83ee  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value, string name)
0x83f3  br.s     loc_8415
0x83f5  ldloc.1
0x83f6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x83fb  ldstr    aDomain// "Domain"
0x8400  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8405  brfalse.s loc_8415
0x8407  ldarg.1
0x8408  ldc.i4.s 0x6E
0x840a  ldloc.2
0x840b  ldstr    aDomain// "Domain"
0x8410  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value, string name)
0x8415  ldloc.0
0x8416  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x841b  brtrue.s loc_839E
0x841d  leave.s  loc_8430
0x841f  ldloc.0
0x8420  isinst   [mscorlib]System.IDisposable
0x8425  stloc.3
0x8426  ldloc.3
0x8427  brfalse.s loc_842F
0x8429  ldloc.3
0x842a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x842f  endfinally
0x8430  ret
```
