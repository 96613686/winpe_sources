# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ReadCustomAuthenticationUI

- ea: `0x8530`
- end: `0x85f0`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ReadCustomAuthenticationUI`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8440`

## callees

- `0x1710`
- `0x8530`
- `0x85f0`
- `0x8fd0`

## pseudocode

```c

```

## disassembly

```asm
0x8530  ldarg.0
0x8531  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x8536  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x853b  stloc.0
0x853c  br       loc_85D1
0x8541  ldloc.0
0x8542  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8547  castclass [System.Xml]System.Xml.XmlNode
0x854c  stloc.1
0x854d  ldloc.1
0x854e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8553  pop
0x8554  ldloc.1
0x8555  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x855a  ldstr    aLoginurl// "loginUrl"
0x855f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8564  brfalse.s loc_857B
0x8566  ldarg.1
0x8567  ldc.i4.s 0xB
0x8569  ldloc.1
0x856a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x856f  ldstr    aLoginurl// "loginUrl"
0x8574  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value, string name)
0x8579  br.s     loc_85D1
0x857b  ldloc.1
0x857c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8581  ldstr    aUsessl// "UseSSL"
0x8586  call     bool [mscorlib]System.String::op_Equality(string, string)
0x858b  brfalse.s loc_85A2
0x858d  ldarg.1
0x858e  ldc.i4.s 0xC
0x8590  ldloc.1
0x8591  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8596  ldstr    aUsessl// "UseSSL"
0x859b  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value, string name)
0x85a0  br.s     loc_85D1
0x85a2  ldloc.1
0x85a3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x85a8  ldstr    aPassthroughcoo// "PassThroughCookies"
0x85ad  call     bool [mscorlib]System.String::op_Equality(string, string)
0x85b2  brfalse.s loc_85BD
0x85b4  ldloc.1
0x85b5  ldarg.1
0x85b6  call     void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ReadPassThroughCookies(class [System.Xml]System.Xml.XmlNode node, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties)
0x85bb  br.s     loc_85D1
0x85bd  ldloc.1
0x85be  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x85c3  ldc.i4.8
0x85c4  beq.s    loc_85D1
0x85c6  ldloc.1
0x85c7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x85cc  call     void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ThrowInvalidFormat(string element)
0x85d1  ldloc.0
0x85d2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x85d7  brtrue   loc_8541
0x85dc  leave.s  loc_85EF
0x85de  ldloc.0
0x85df  isinst   [mscorlib]System.IDisposable
0x85e4  stloc.2
0x85e5  ldloc.2
0x85e6  brfalse.s loc_85EE
0x85e8  ldloc.2
0x85e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x85ee  endfinally
0x85ef  ret
```
