# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseAuthentication

- ea: `0x8ac0`
- end: `0x8c46`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseAuthentication`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7390`

## callees

- `0x1700`
- `0x8ac0`
- `0x8c50`
- `0x8fd0`
- `0x100d0`

## pseudocode

```c

```

## disassembly

```asm
0x8ac0  ldarg.1
0x8ac1  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x8ac6  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x8acb  stloc.0
0x8acc  br       loc_8C24
0x8ad1  ldloc.0
0x8ad2  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8ad7  castclass [System.Xml]System.Xml.XmlNode
0x8adc  stloc.1
0x8add  ldloc.1
0x8ade  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8ae3  stloc.2
0x8ae4  ldloc.1
0x8ae5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8aea  stloc.3
0x8aeb  ldloc.3
0x8aec  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x8af1  stloc.s  4
0x8af3  ldloc.s  4
0x8af5  ldc.i4   0x94354A1A
0x8afa  bgt.un.s loc_8B1F
0x8afc  ldloc.s  4
0x8afe  ldc.i4   0x6AC704CF
0x8b03  beq.s    loc_8B78
0x8b05  ldloc.s  4
0x8b07  ldc.i4   0x897A4493
0x8b0c  beq.s    loc_8B8A
0x8b0e  ldloc.s  4
0x8b10  ldc.i4   0x94354A1A
0x8b15  beq      loc_8BB7
0x8b1a  br       loc_8C10
0x8b1f  ldloc.s  4
0x8b21  ldc.i4   0xBDE03FE3
0x8b26  bgt.un.s loc_8B3F
0x8b28  ldloc.s  4
0x8b2a  ldc.i4   0xB40044FD
0x8b2f  beq.s    loc_8B66
0x8b31  ldloc.s  4
0x8b33  ldc.i4   0xBDE03FE3
0x8b38  beq.s    loc_8B99
0x8b3a  br       loc_8C10
0x8b3f  ldloc.s  4
0x8b41  ldc.i4   0xD8286192
0x8b46  beq.s    loc_8BA8
0x8b48  ldloc.s  4
0x8b4a  ldc.i4   0xDC8C9F6E
0x8b4f  bne.un   loc_8C10
0x8b54  ldloc.3
0x8b55  ldstr    aAuthentication// "AuthenticationTypes"
0x8b5a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8b5f  brtrue.s loc_8BC6
0x8b61  br       loc_8C10
0x8b66  ldloc.3
0x8b67  ldstr    aRswindowsexten// "RSWindowsExtendedProtectionLevel"
0x8b6c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8b71  brtrue.s loc_8BD0
0x8b73  br       loc_8C10
0x8b78  ldloc.3
0x8b79  ldstr    aRswindowsexten_0// "RSWindowsExtendedProtectionScenario"
0x8b7e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8b83  brtrue.s loc_8BDB
0x8b85  br       loc_8C10
0x8b8a  ldloc.3
0x8b8b  ldstr    aEnableauthpers// "EnableAuthPersistence"
0x8b90  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8b95  brtrue.s loc_8BE6
0x8b97  br.s     loc_8C10
0x8b99  ldloc.3
0x8b9a  ldstr    aMaxunauthentic// "MaxUnauthenticatedRequests"
0x8b9f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8ba4  brtrue.s loc_8BF0
0x8ba6  br.s     loc_8C10
0x8ba8  ldloc.3
0x8ba9  ldstr    aUnauthenticate// "UnauthenticatedRequestWindow"
0x8bae  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8bb3  brtrue.s loc_8BFA
0x8bb5  br.s     loc_8C10
0x8bb7  ldloc.3
0x8bb8  ldstr    aUnauthenticate_0// "UnauthenticatedRequestLockoutTime"
0x8bbd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8bc2  brtrue.s loc_8C05
0x8bc4  br.s     loc_8C10
0x8bc6  ldarg.0
0x8bc7  ldloc.1
0x8bc8  ldarg.2
0x8bc9  call     instance void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseAuthenticationTypes(class [System.Xml]System.Xml.XmlNode node, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties)
0x8bce  br.s     loc_8C24
0x8bd0  ldarg.2
0x8bd1  ldc.i4.s 0x6A
0x8bd3  ldloc.2
0x8bd4  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value)
0x8bd9  br.s     loc_8C24
0x8bdb  ldarg.2
0x8bdc  ldc.i4.s 0x6B
0x8bde  ldloc.2
0x8bdf  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value)
0x8be4  br.s     loc_8C24
0x8be6  ldarg.2
0x8be7  ldc.i4.7
0x8be8  ldloc.2
0x8be9  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value)
0x8bee  br.s     loc_8C24
0x8bf0  ldarg.2
0x8bf1  ldc.i4.8
0x8bf2  ldloc.2
0x8bf3  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value)
0x8bf8  br.s     loc_8C24
0x8bfa  ldarg.2
0x8bfb  ldc.i4.s 9
0x8bfd  ldloc.2
0x8bfe  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value)
0x8c03  br.s     loc_8C24
0x8c05  ldarg.2
0x8c06  ldc.i4.s 0xA
0x8c08  ldloc.2
0x8c09  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value)
0x8c0e  br.s     loc_8C24
0x8c10  ldloc.1
0x8c11  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x8c16  ldc.i4.8
0x8c17  beq.s    loc_8C24
0x8c19  ldloc.1
0x8c1a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8c1f  call     void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ThrowInvalidFormat(string element)
0x8c24  ldloc.0
0x8c25  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8c2a  brtrue   loc_8AD1
0x8c2f  leave.s  loc_8C45
0x8c31  ldloc.0
0x8c32  isinst   [mscorlib]System.IDisposable
0x8c37  stloc.s  5
0x8c39  ldloc.s  5
0x8c3b  brfalse.s loc_8C44
0x8c3d  ldloc.s  5
0x8c3f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8c44  endfinally
0x8c45  ret
```
