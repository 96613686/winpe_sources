# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseAuthenticationTypes

- ea: `0x8c50`
- end: `0x8eee`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseAuthenticationTypes`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8ac0`

## callees

- `0x1700`
- `0x1710`
- `0x8c50`
- `0x8fd0`
- `0x100d0`

## string_xrefs

- `0x8dc5`: `AuthTokenCacheMaxSize`
- `0x8dd5`: `AuthTokenCacheMaintenanceInterval`
- `0x8de5`: `AuthTokenCacheLogonTimeout`
- `0x8df5`: `AuthTokenCacheEntryTimeout`

## pseudocode

```c

```

## disassembly

```asm
0x8c50  ldc.i4.0
0x8c51  stloc.0
0x8c52  ldarg.1
0x8c53  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x8c58  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x8c5d  stloc.1
0x8c5e  br       loc_8EB6
0x8c63  ldloc.1
0x8c64  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8c69  castclass [System.Xml]System.Xml.XmlNode
0x8c6e  stloc.2
0x8c6f  ldc.i4.0
0x8c70  stloc.3
0x8c71  ldloc.2
0x8c72  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8c77  stloc.s  4
0x8c79  ldloc.s  4
0x8c7b  ldstr    aRswindowskerbe// "RSWindowsKerberos"
0x8c80  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8c85  brtrue.s loc_8CDB
0x8c87  ldloc.s  4
0x8c89  ldstr    aRswindowsntlm// "RSWindowsNTLM"
0x8c8e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8c93  brtrue.s loc_8CE4
0x8c95  ldloc.s  4
0x8c97  ldstr    aRswindowsbasic// "RSWindowsBasic"
0x8c9c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8ca1  brtrue.s loc_8CED
0x8ca3  ldloc.s  4
0x8ca5  ldstr    aRswindowsnegot// "RSWindowsNegotiate"
0x8caa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8caf  brtrue   loc_8E78
0x8cb4  ldloc.s  4
0x8cb6  ldstr    aCustom// "Custom"
0x8cbb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8cc0  brtrue   loc_8E7E
0x8cc5  ldloc.s  4
0x8cc7  ldstr    aOauth// "OAuth"
0x8ccc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8cd1  brtrue   loc_8E85
0x8cd6  br       loc_8E8C
0x8cdb  ldloc.0
0x8cdc  ldc.i4.2
0x8cdd  or
0x8cde  stloc.0
0x8cdf  br       loc_8EA0
0x8ce4  ldloc.0
0x8ce5  ldc.i4.4
0x8ce6  or
0x8ce7  stloc.0
0x8ce8  br       loc_8EA0
0x8ced  ldloc.0
0x8cee  ldc.i4.8
0x8cef  or
0x8cf0  stloc.0
0x8cf1  ldloc.2
0x8cf2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x8cf7  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x8cfc  stloc.s  5
0x8cfe  br       loc_8E55
0x8d03  ldloc.s  5
0x8d05  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8d0a  castclass [System.Xml]System.Xml.XmlNode
0x8d0f  stloc.s  6
0x8d11  ldc.i4.0
0x8d12  stloc.s  7
0x8d14  ldloc.s  6
0x8d16  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8d1b  stloc.s  8
0x8d1d  ldloc.s  6
0x8d1f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8d24  stloc.s  4
0x8d26  ldloc.s  4
0x8d28  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x8d2d  stloc.s  9
0x8d2f  ldloc.s  9
0x8d31  ldc.i4   0x543A8071
0x8d36  bgt.un.s loc_8D5B
0x8d38  ldloc.s  9
0x8d3a  ldc.i4   0x17DDCD30
0x8d3f  beq.s    loc_8DA3
0x8d41  ldloc.s  9
0x8d43  ldc.i4   0x2132F311
0x8d48  beq.s    loc_8DC3
0x8d4a  ldloc.s  9
0x8d4c  ldc.i4   0x543A8071
0x8d51  beq      loc_8DF3
0x8d56  br       loc_8E2A
0x8d5b  ldloc.s  9
0x8d5d  ldc.i4   0xAE5ADEA2
0x8d62  bgt.un.s loc_8D7B
0x8d64  ldloc.s  9
0x8d66  ldc.i4   0xAD3F4340
0x8d6b  beq.s    loc_8DE3
0x8d6d  ldloc.s  9
0x8d6f  ldc.i4   0xAE5ADEA2
0x8d74  beq.s    loc_8DB3
0x8d76  br       loc_8E2A
0x8d7b  ldloc.s  9
0x8d7d  ldc.i4   0xE8F5246C
0x8d82  beq.s    loc_8DD3
0x8d84  ldloc.s  9
0x8d86  ldc.i4   0xF1F78955
0x8d8b  bne.un   loc_8E2A
0x8d90  ldloc.s  4
0x8d92  ldstr    aLogonmethod// "LogonMethod"
0x8d97  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8d9c  brtrue.s loc_8E03
0x8d9e  br       loc_8E2A
0x8da3  ldloc.s  4
0x8da5  ldstr    aRealm// "Realm"
0x8daa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8daf  brtrue.s loc_8E08
0x8db1  br.s     loc_8E2A
0x8db3  ldloc.s  4
0x8db5  ldstr    aDefaultdomain// "DefaultDomain"
0x8dba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8dbf  brtrue.s loc_8E0D
0x8dc1  br.s     loc_8E2A
0x8dc3  ldloc.s  4
0x8dc5  ldstr    aAuthtokencache// "AuthTokenCacheMaxSize"
0x8dca  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8dcf  brtrue.s loc_8E12
0x8dd1  br.s     loc_8E2A
0x8dd3  ldloc.s  4
0x8dd5  ldstr    aAuthtokencache_0// "AuthTokenCacheMaintenanceInterval"
0x8dda  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8ddf  brtrue.s loc_8E18
0x8de1  br.s     loc_8E2A
0x8de3  ldloc.s  4
0x8de5  ldstr    aAuthtokencache_1// "AuthTokenCacheLogonTimeout"
0x8dea  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8def  brtrue.s loc_8E1E
0x8df1  br.s     loc_8E2A
0x8df3  ldloc.s  4
0x8df5  ldstr    aAuthtokencache_2// "AuthTokenCacheEntryTimeout"
0x8dfa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8dff  brtrue.s loc_8E24
0x8e01  br.s     loc_8E2A
0x8e03  ldc.i4.4
0x8e04  stloc.s  7
0x8e06  br.s     loc_8E40
0x8e08  ldc.i4.5
0x8e09  stloc.s  7
0x8e0b  br.s     loc_8E40
0x8e0d  ldc.i4.6
0x8e0e  stloc.s  7
0x8e10  br.s     loc_8E40
0x8e12  ldc.i4.s 0xE
0x8e14  stloc.s  7
0x8e16  br.s     loc_8E40
0x8e18  ldc.i4.s 0xF
0x8e1a  stloc.s  7
0x8e1c  br.s     loc_8E40
0x8e1e  ldc.i4.s 0x10
0x8e20  stloc.s  7
0x8e22  br.s     loc_8E40
0x8e24  ldc.i4.s 0x11
0x8e26  stloc.s  7
0x8e28  br.s     loc_8E40
0x8e2a  ldloc.s  6
0x8e2c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x8e31  ldc.i4.8
0x8e32  beq.s    loc_8E40
0x8e34  ldloc.s  6
0x8e36  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8e3b  call     void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ThrowInvalidFormat(string element)
0x8e40  ldloc.s  7
0x8e42  brfalse.s loc_8E55
0x8e44  ldarg.2
0x8e45  ldloc.s  7
0x8e47  ldloc.s  8
0x8e49  ldloc.s  6
0x8e4b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8e50  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value, string name)
0x8e55  ldloc.s  5
0x8e57  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8e5c  brtrue   loc_8D03
0x8e61  leave.s  loc_8EA0
0x8e63  ldloc.s  5
0x8e65  isinst   [mscorlib]System.IDisposable
0x8e6a  stloc.s  0xA
0x8e6c  ldloc.s  0xA
0x8e6e  brfalse.s loc_8E77
0x8e70  ldloc.s  0xA
0x8e72  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8e77  endfinally
0x8e78  ldloc.0
0x8e79  ldc.i4.1
0x8e7a  or
0x8e7b  stloc.0
0x8e7c  br.s     loc_8EA0
0x8e7e  ldloc.0
0x8e7f  ldc.i4.s 0x10
0x8e81  or
0x8e82  stloc.0
0x8e83  br.s     loc_8EA0
0x8e85  ldloc.0
0x8e86  ldc.i4.s 0x40
0x8e88  or
0x8e89  stloc.0
0x8e8a  br.s     loc_8EA0
0x8e8c  ldloc.2
0x8e8d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x8e92  ldc.i4.8
0x8e93  beq.s    loc_8EA0
0x8e95  ldloc.2
0x8e96  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8e9b  call     void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ThrowInvalidFormat(string element)
0x8ea0  ldloc.3
0x8ea1  brfalse.s loc_8EB6
0x8ea3  ldarg.2
0x8ea4  ldloc.3
0x8ea5  ldloc.2
0x8ea6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8eab  ldloc.2
0x8eac  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8eb1  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value, string name)
0x8eb6  ldloc.1
0x8eb7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8ebc  brtrue   loc_8C63
0x8ec1  leave.s  loc_8ED7
0x8ec3  ldloc.1
0x8ec4  isinst   [mscorlib]System.IDisposable
0x8ec9  stloc.s  0xA
0x8ecb  ldloc.s  0xA
0x8ecd  brfalse.s loc_8ED6
0x8ecf  ldloc.s  0xA
0x8ed1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ed6  endfinally
0x8ed7  ldarg.2
0x8ed8  ldc.i4.3
0x8ed9  ldloc.0
0x8eda  stloc.s  0xB
0x8edc  ldloca.s 0xB
0x8ede  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8ee3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8ee8  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value)
0x8eed  ret
```
