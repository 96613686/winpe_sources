# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseServiceConfiguration

- ea: `0x7d20`
- end: `0x82db`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseServiceConfiguration`
- size: `1467`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x7390`

## callees

- `0x1710`
- `0x7d20`
- `0x82e0`
- `0x8390`
- `0x8fd0`
- `0x100d0`

## string_xrefs

- `0x7f48`: `IsSchedulingService`
- `0x7f74`: `IsAlertingService`
- `0x7f8a`: `WindowsServiceUseFileShareStorage`
- `0x7fa0`: `IsNotificationService`
- `0x7fcc`: `IsEventService`
- `0x8092`: `MaxQueueThreads`
- `0x812c`: `IsWebServiceEnabled`
- `0x8158`: `IsReportBuilderAnonymousAccessEnabled`
- `0x80d4`: `UpdatePoliciesSeconds`
- `0x80ea`: `UpdatePoliciesChunkSize`
- `0x7f5e`: `IsDataModelRefreshService`
- `0x8116`: `WebServiceAccount`

## pseudocode

```c

```

## disassembly

```asm
0x7d20  ldarg.0
0x7d21  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x7d26  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x7d2b  stloc.0
0x7d2c  br       loc_82B9
0x7d31  ldloc.0
0x7d32  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7d37  castclass [System.Xml]System.Xml.XmlNode
0x7d3c  stloc.1
0x7d3d  ldc.i4.0
0x7d3e  stloc.2
0x7d3f  ldloc.1
0x7d40  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x7d45  stloc.3
0x7d46  ldloc.1
0x7d47  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x7d4c  stloc.s  4
0x7d4e  ldloc.s  4
0x7d50  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x7d55  stloc.s  5
0x7d57  ldloc.s  5
0x7d59  ldc.i4   0x66F6A78C
0x7d5e  bgt.un   loc_7E56
0x7d63  ldloc.s  5
0x7d65  ldc.i4   0x30EF02E4
0x7d6a  bgt.un.s loc_7DE1
0x7d6c  ldloc.s  5
0x7d6e  ldc.i4   0x178FCC4E
0x7d73  bgt.un.s loc_7D9E
0x7d75  ldloc.s  5
0x7d77  ldc.i4   0xEC8B8AD
0x7d7c  beq      loc_7F9E
0x7d81  ldloc.s  5
0x7d83  ldc.i4   0x14ED52CD
0x7d88  beq      loc_8090
0x7d8d  ldloc.s  5
0x7d8f  ldc.i4   0x178FCC4E
0x7d94  beq      loc_8156
0x7d99  br       loc_8294
0x7d9e  ldloc.s  5
0x7da0  ldc.i4   0x1F3C7EA7
0x7da5  bgt.un.s loc_7DC4
0x7da7  ldloc.s  5
0x7da9  ldc.i4   0x184F7306
0x7dae  beq      loc_8198
0x7db3  ldloc.s  5
0x7db5  ldc.i4   0x1F3C7EA7
0x7dba  beq      loc_8064
0x7dbf  br       loc_8294
0x7dc4  ldloc.s  5
0x7dc6  ldc.i4   0x28C7DE52
0x7dcb  beq      loc_7FCA
0x7dd0  ldloc.s  5
0x7dd2  ldc.i4   0x30EF02E4
0x7dd7  beq      loc_804E
0x7ddc  br       loc_8294
0x7de1  ldloc.s  5
0x7de3  ldc.i4   0x4263C94A
0x7de8  bgt.un.s loc_7E13
0x7dea  ldloc.s  5
0x7dec  ldc.i4   0x350FC0EF
0x7df1  beq      loc_7FF6
0x7df6  ldloc.s  5
0x7df8  ldc.i4   0x3C0DED96
0x7dfd  beq      loc_7F88
0x7e02  ldloc.s  5
0x7e04  ldc.i4   0x4263C94A
0x7e09  beq      loc_7FB4
0x7e0e  br       loc_8294
0x7e13  ldloc.s  5
0x7e15  ldc.i4   0x6153F3BF
0x7e1a  bgt.un.s loc_7E39
0x7e1c  ldloc.s  5
0x7e1e  ldc.i4   0x48EEA66E
0x7e23  beq      loc_807A
0x7e28  ldloc.s  5
0x7e2a  ldc.i4   0x6153F3BF
0x7e2f  beq      loc_8114
0x7e34  br       loc_8294
0x7e39  ldloc.s  5
0x7e3b  ldc.i4   0x65F77659
0x7e40  beq      loc_8022
0x7e45  ldloc.s  5
0x7e47  ldc.i4   0x66F6A78C
0x7e4c  beq      loc_816C
0x7e51  br       loc_8294
0x7e56  ldloc.s  5
0x7e58  ldc.i4   0xB2027452
0x7e5d  bgt.un.s loc_7ED4
0x7e5f  ldloc.s  5
0x7e61  ldc.i4   0x89BD6F78
0x7e66  bgt.un.s loc_7E91
0x7e68  ldloc.s  5
0x7e6a  ldc.i4   0x6E291752
0x7e6f  beq      loc_7F46
0x7e74  ldloc.s  5
0x7e76  ldc.i4   0x77328A3A
0x7e7b  beq      loc_7F72
0x7e80  ldloc.s  5
0x7e82  ldc.i4   0x89BD6F78
0x7e87  beq      loc_80FE
0x7e8c  br       loc_8294
0x7e91  ldloc.s  5
0x7e93  ldc.i4   0xA806EA7F
0x7e98  bgt.un.s loc_7EB7
0x7e9a  ldloc.s  5
0x7e9c  ldc.i4   0x8A5137B1
0x7ea1  beq      loc_812A
0x7ea6  ldloc.s  5
0x7ea8  ldc.i4   0xA806EA7F
0x7ead  beq      loc_80BC
0x7eb2  br       loc_8294
0x7eb7  ldloc.s  5
0x7eb9  ldc.i4   0xA9EE8C36
0x7ebe  beq      loc_8038
0x7ec3  ldloc.s  5
0x7ec5  ldc.i4   0xB2027452
0x7eca  beq      loc_800C
0x7ecf  br       loc_8294
0x7ed4  ldloc.s  5
0x7ed6  ldc.i4   0xC1747C5A
0x7edb  bgt.un.s loc_7F06
0x7edd  ldloc.s  5
0x7edf  ldc.i4   0xB820B9B4
0x7ee4  beq      loc_8182
0x7ee9  ldloc.s  5
0x7eeb  ldc.i4   0xBAC153E9
0x7ef0  beq      loc_7FE0
0x7ef5  ldloc.s  5
0x7ef7  ldc.i4   0xC1747C5A
0x7efc  beq      loc_80A6
0x7f01  br       loc_8294
0x7f06  ldloc.s  5
0x7f08  ldc.i4   0xDEE8E983
0x7f0d  bgt.un.s loc_7F2C
0x7f0f  ldloc.s  5
0x7f11  ldc.i4   0xD53F5157
0x7f16  beq      loc_8140
0x7f1b  ldloc.s  5
0x7f1d  ldc.i4   0xDEE8E983
0x7f22  beq      loc_80D2
0x7f27  br       loc_8294
0x7f2c  ldloc.s  5
0x7f2e  ldc.i4   0xE3316E62
0x7f33  beq      loc_80E8
0x7f38  ldloc.s  5
0x7f3a  ldc.i4   0xFBD56EF0
0x7f3f  beq.s    loc_7F5C
0x7f41  br       loc_8294
0x7f46  ldloc.s  4
0x7f48  ldstr    aIsschedulingse// "IsSchedulingService"
0x7f4d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f52  brtrue   loc_81AE
0x7f57  br       loc_8294
0x7f5c  ldloc.s  4
0x7f5e  ldstr    aIsdatamodelref// "IsDataModelRefreshService"
0x7f63  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f68  brtrue   loc_82A8
0x7f6d  br       loc_8294
0x7f72  ldloc.s  4
0x7f74  ldstr    aIsalertingserv// "IsAlertingService"
0x7f79  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f7e  brtrue   loc_81B6
0x7f83  br       loc_8294
0x7f88  ldloc.s  4
0x7f8a  ldstr    aWindowsservice// "WindowsServiceUseFileShareStorage"
0x7f8f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f94  brtrue   loc_81BE
0x7f99  br       loc_8294
0x7f9e  ldloc.s  4
0x7fa0  ldstr    aIsnotification// "IsNotificationService"
0x7fa5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7faa  brtrue   loc_81C6
0x7faf  br       loc_8294
0x7fb4  ldloc.s  4
0x7fb6  ldstr    aUrlroot// "UrlRoot"
0x7fbb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7fc0  brtrue   loc_81CE
0x7fc5  br       loc_8294
0x7fca  ldloc.s  4
0x7fcc  ldstr    aIseventservice// "IsEventService"
0x7fd1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7fd6  brtrue   loc_81D6
0x7fdb  br       loc_8294
0x7fe0  ldloc.s  4
0x7fe2  ldstr    aPollinginterva// "PollingInterval"
0x7fe7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7fec  brtrue   loc_81DE
0x7ff1  br       loc_8294
0x7ff6  ldloc.s  4
0x7ff8  ldstr    aMaxcatalogconn// "MaxCatalogConnectionPoolSizePerProcess"
0x7ffd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8002  brtrue   loc_81E6
0x8007  br       loc_8294
0x800c  ldloc.s  4
0x800e  ldstr    aMemorysafetyma// "MemorySafetyMargin"
0x8013  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8018  brtrue   loc_81EE
0x801d  br       loc_8294
0x8022  ldloc.s  4
0x8024  ldstr    aMemorythreshol// "MemoryThreshold"
0x8029  call     bool [mscorlib]System.String::op_Equality(string, string)
0x802e  brtrue   loc_81F6
0x8033  br       loc_8294
0x8038  ldloc.s  4
0x803a  ldstr    aWorkingsetmaxi// "WorkingSetMaximum"
0x803f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8044  brtrue   loc_81FE
0x8049  br       loc_8294
0x804e  ldloc.s  4
0x8050  ldstr    aWorkingsetmini// "WorkingSetMinimum"
0x8055  call     bool [mscorlib]System.String::op_Equality(string, string)
0x805a  brtrue   loc_8206
0x805f  br       loc_8294
0x8064  ldloc.s  4
0x8066  ldstr    aRecycletime// "RecycleTime"
0x806b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8070  brtrue   loc_820E
0x8075  br       loc_8294
0x807a  ldloc.s  4
0x807c  ldstr    aMaxappdomainun// "MaxAppDomainUnloadTime"
0x8081  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8086  brtrue   loc_8216
0x808b  br       loc_8294
0x8090  ldloc.s  4
0x8092  ldstr    aMaxqueuethread// "MaxQueueThreads"
0x8097  call     bool [mscorlib]System.String::op_Equality(string, string)
0x809c  brtrue   loc_821E
0x80a1  br       loc_8294
0x80a6  ldloc.s  4
0x80a8  ldstr    aUnattendedexec_2// "UnattendedExecutionAccount"
0x80ad  call     bool [mscorlib]System.String::op_Equality(string, string)
0x80b2  brtrue   loc_8226
0x80b7  br       loc_8294
0x80bc  ldloc.s  4
0x80be  ldstr    aPolicylevel// "PolicyLevel"
0x80c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x80c8  brtrue   loc_8231
0x80cd  br       loc_8294
0x80d2  ldloc.s  4
0x80d4  ldstr    aUpdatepolicies// "UpdatePoliciesSeconds"
0x80d9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x80de  brtrue   loc_8236
0x80e3  br       loc_8294
0x80e8  ldloc.s  4
0x80ea  ldstr    aUpdatepolicies_0// "UpdatePoliciesChunkSize"
0x80ef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x80f4  brtrue   loc_823B
0x80f9  br       loc_8294
0x80fe  ldloc.s  4
0x8100  ldstr    aFilesharestora// "FileShareStorageLocation"
0x8105  call     bool [mscorlib]System.String::op_Equality(string, string)
0x810a  brtrue   loc_8240
0x810f  br       loc_8294
0x8114  ldloc.s  4
0x8116  ldstr    aWebserviceacco// "WebServiceAccount"
0x811b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8120  brtrue   loc_82A8
0x8125  br       loc_8294
0x812a  ldloc.s  4
0x812c  ldstr    aIswebserviceen// "IsWebServiceEnabled"
0x8131  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8136  brtrue   loc_8271
0x813b  br       loc_8294
0x8140  ldloc.s  4
0x8142  ldstr    aIsreportmanage// "IsReportManagerEnabled"
0x8147  call     bool [mscorlib]System.String::op_Equality(string, string)
0x814c  brtrue   loc_8276
0x8151  br       loc_8294
0x8156  ldloc.s  4
0x8158  ldstr    aIsreportbuilde// "IsReportBuilderAnonymousAccessEnabled"
0x815d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8162  brtrue   loc_827A
0x8167  br       loc_8294
0x816c  ldloc.s  4
0x816e  ldstr    aHostname// "Hostname"
0x8173  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8178  brtrue   loc_827F
0x817d  br       loc_8294
0x8182  ldloc.s  4
0x8184  ldstr    aIsrdceenabled// "IsRdceEnabled"
0x8189  call     bool [mscorlib]System.String::op_Equality(string, string)
0x818e  brtrue   loc_8284
0x8193  br       loc_8294
0x8198  ldloc.s  4
0x819a  ldstr    aDefaultfilesha// "DefaultFileShareAccount"
0x819f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x81a4  brtrue   loc_8289
0x81a9  br       loc_8294
0x81ae  ldc.i4.s 0x55
0x81b0  stloc.2
0x81b1  br       loc_82A8
0x81b6  ldc.i4.s 0x6C
0x81b8  stloc.2
0x81b9  br       loc_82A8
0x81be  ldc.i4.s 0x50
0x81c0  stloc.2
0x81c1  br       loc_82A8
0x81c6  ldc.i4.s 0x56
0x81c8  stloc.2
  ... truncated ...
```
