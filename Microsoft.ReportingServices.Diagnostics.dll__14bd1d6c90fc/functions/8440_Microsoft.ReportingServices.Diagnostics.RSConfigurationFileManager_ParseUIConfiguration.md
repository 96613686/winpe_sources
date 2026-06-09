# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseUIConfiguration

- ea: `0x8440`
- end: `0x852d`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseUIConfiguration`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7390`

## callees

- `0x1710`
- `0x8440`
- `0x8530`
- `0x8fd0`

## pseudocode

```c

```

## disassembly

```asm
0x8440  ldarg.0
0x8441  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x8446  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x844b  stloc.0
0x844c  br       loc_850B
0x8451  ldloc.0
0x8452  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8457  castclass [System.Xml]System.Xml.XmlNode
0x845c  stloc.1
0x845d  ldc.i4.0
0x845e  stloc.2
0x845f  ldloc.1
0x8460  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8465  stloc.3
0x8466  ldloc.1
0x8467  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x846c  stloc.s  4
0x846e  ldloc.s  4
0x8470  ldstr    aReportserverur// "ReportServerUrl"
0x8475  call     bool [mscorlib]System.String::op_Equality(string, string)
0x847a  brtrue.s loc_84C4
0x847c  ldloc.s  4
0x847e  ldstr    aEnablereportde// "EnableReportDesignClientButton"
0x8483  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8488  brtrue.s loc_84C9
0x848a  ldloc.s  4
0x848c  ldstr    aReportserverex// "ReportServerExternalUrl"
0x8491  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8496  brtrue.s loc_84CE
0x8498  ldloc.s  4
0x849a  ldstr    aCustomauthenti// "CustomAuthenticationUI"
0x849f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x84a4  brtrue.s loc_84D3
0x84a6  ldloc.s  4
0x84a8  ldstr    aPagecountmode// "PageCountMode"
0x84ad  call     bool [mscorlib]System.String::op_Equality(string, string)
0x84b2  brtrue.s loc_84DC
0x84b4  ldloc.s  4
0x84b6  ldstr    aPostbacktimeou// "PostbackTimeout"
0x84bb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x84c0  brtrue.s loc_84E1
0x84c2  br.s     loc_84E6
0x84c4  ldc.i4.s 0x15
0x84c6  stloc.2
0x84c7  br.s     loc_84FA
0x84c9  ldc.i4.s 0x4B
0x84cb  stloc.2
0x84cc  br.s     loc_84FA
0x84ce  ldc.i4.s 0x16
0x84d0  stloc.2
0x84d1  br.s     loc_84FA
0x84d3  ldloc.1
0x84d4  ldarg.1
0x84d5  call     void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ReadCustomAuthenticationUI(class [System.Xml]System.Xml.XmlNode node, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties)
0x84da  br.s     loc_84FA
0x84dc  ldc.i4.s 0x4D
0x84de  stloc.2
0x84df  br.s     loc_84FA
0x84e1  ldc.i4.s 0x4E
0x84e3  stloc.2
0x84e4  br.s     loc_84FA
0x84e6  ldloc.1
0x84e7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x84ec  ldc.i4.8
0x84ed  beq.s    loc_84FA
0x84ef  ldloc.1
0x84f0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x84f5  call     void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ThrowInvalidFormat(string element)
0x84fa  ldloc.2
0x84fb  brfalse.s loc_850B
0x84fd  ldarg.1
0x84fe  ldloc.2
0x84ff  ldloc.3
0x8500  ldloc.1
0x8501  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8506  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value, string name)
0x850b  ldloc.0
0x850c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8511  brtrue   loc_8451
0x8516  leave.s  loc_852C
0x8518  ldloc.0
0x8519  isinst   [mscorlib]System.IDisposable
0x851e  stloc.s  5
0x8520  ldloc.s  5
0x8522  brfalse.s loc_852B
0x8524  ldloc.s  5
0x8526  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x852b  endfinally
0x852c  ret
```
