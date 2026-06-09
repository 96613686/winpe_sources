# Microsoft.ReportingServices.Library.KeyStorage::GetPowerBIInformation

- ea: `0x2990`
- end: `0x2b95`
- name: `Microsoft.ReportingServices.Library.KeyStorage::GetPowerBIInformation`
- size: `517`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x2990`
- `0x6c60`
- `0x7120`
- `0x8e90`

## string_xrefs

- `0x2990`: `SELECT Name, Value FROM ConfigurationInfo\n                                where [NAME] IN ('ClientId', \n                                                'AppObjectId', \n                                                'TenantName', \n                                                'TenantId', \n                                                'ClientSecret', \n                                                'ResourceUrl', \n                                                'AuthorizationUrl`
- `0x2afd`: `TokenUrl`
- `0x2b89`: `Invalid PBI Configuration`

## pseudocode

```c

```

## disassembly

```asm
0x2990  ldstr    aSelectNameValu// "SELECT Name, Value FROM ConfigurationIn"...
0x2995  stloc.0
0x2996  ldarg.0
0x2997  ldloc.0
0x2998  call     instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommandQuery(string query)
0x299d  ldarg.1
0x299e  ldnull
0x299f  stind.ref
0x29a0  ldarg.2
0x29a1  ldnull
0x29a2  stind.ref
0x29a3  ldarg.3
0x29a4  ldnull
0x29a5  stind.ref
0x29a6  ldarg.s  4
0x29a8  ldnull
0x29a9  stind.ref
0x29aa  ldarg.s  5
0x29ac  ldnull
0x29ad  stind.ref
0x29ae  ldarg.s  6
0x29b0  ldnull
0x29b1  stind.ref
0x29b2  ldarg.s  7
0x29b4  ldnull
0x29b5  stind.ref
0x29b6  ldarg.s  8
0x29b8  ldnull
0x29b9  stind.ref
0x29ba  ldnull
0x29bb  stloc.1
0x29bc  callvirt instance class [System.Data]System.Data.IDataReader Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x29c1  stloc.2
0x29c2  br       loc_2B4A
0x29c7  ldloc.2
0x29c8  ldstr    aValue// "Value"
0x29cd  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x29d2  isinst   [mscorlib]System.String
0x29d7  stloc.3
0x29d8  ldloc.2
0x29d9  ldstr    aName_0// "Name"
0x29de  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x29e3  isinst   [mscorlib]System.String
0x29e8  stloc.s  4
0x29ea  ldloc.s  4
0x29ec  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x29f1  stloc.s  5
0x29f3  ldloc.s  5
0x29f5  ldc.i4   0x382DA9A3
0x29fa  bgt.un.s loc_2A3C
0x29fc  ldloc.s  5
0x29fe  ldc.i4   0x1B058C3B
0x2a03  bgt.un.s loc_2A22
0x2a05  ldloc.s  5
0x2a07  ldc.i4   0x98F6896
0x2a0c  beq      loc_2A95
0x2a11  ldloc.s  5
0x2a13  ldc.i4   0x1B058C3B
0x2a18  beq      loc_2AFB
0x2a1d  br       loc_2B4A
0x2a22  ldloc.s  5
0x2a24  ldc.i4   0x2A54EE06
0x2a29  beq.s    loc_2AA8
0x2a2b  ldloc.s  5
0x2a2d  ldc.i4   0x382DA9A3
0x2a32  beq      loc_2B0B
0x2a37  br       loc_2B4A
0x2a3c  ldloc.s  5
0x2a3e  ldc.i4   0x7AC1B423
0x2a43  bgt.un.s loc_2A5F
0x2a45  ldloc.s  5
0x2a47  ldc.i4   0x70B21C2F
0x2a4c  beq      loc_2AEB
0x2a51  ldloc.s  5
0x2a53  ldc.i4   0x7AC1B423
0x2a58  beq.s    loc_2A7F
0x2a5a  br       loc_2B4A
0x2a5f  ldloc.s  5
0x2a61  ldc.i4   0x7DD89AF6
0x2a66  beq.s    loc_2ACB
0x2a68  ldloc.s  5
0x2a6a  ldc.i4   0x8C9BFC00
0x2a6f  beq.s    loc_2ABB
0x2a71  ldloc.s  5
0x2a73  ldc.i4   0xF561A1AE
0x2a78  beq.s    loc_2ADB
0x2a7a  br       loc_2B4A
0x2a7f  ldloc.s  4
0x2a81  ldstr    aClientid// "ClientId"
0x2a86  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2a8b  brtrue   loc_2B1B
0x2a90  br       loc_2B4A
0x2a95  ldloc.s  4
0x2a97  ldstr    aAppobjectid// "AppObjectId"
0x2a9c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2aa1  brtrue.s loc_2B20
0x2aa3  br       loc_2B4A
0x2aa8  ldloc.s  4
0x2aaa  ldstr    aTenantname// "TenantName"
0x2aaf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ab4  brtrue.s loc_2B25
0x2ab6  br       loc_2B4A
0x2abb  ldloc.s  4
0x2abd  ldstr    aTenantid// "TenantId"
0x2ac2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ac7  brtrue.s loc_2B2A
0x2ac9  br.s     loc_2B4A
0x2acb  ldloc.s  4
0x2acd  ldstr    aClientsecret// "ClientSecret"
0x2ad2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ad7  brtrue.s loc_2B30
0x2ad9  br.s     loc_2B4A
0x2adb  ldloc.s  4
0x2add  ldstr    aResourceurl// "ResourceUrl"
0x2ae2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ae7  brtrue.s loc_2B34
0x2ae9  br.s     loc_2B4A
0x2aeb  ldloc.s  4
0x2aed  ldstr    aAuthorizationu// "AuthorizationUrl"
0x2af2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2af7  brtrue.s loc_2B3A
0x2af9  br.s     loc_2B4A
0x2afb  ldloc.s  4
0x2afd  ldstr    aTokenurl// "TokenUrl"
0x2b02  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2b07  brtrue.s loc_2B40
0x2b09  br.s     loc_2B4A
0x2b0b  ldloc.s  4
0x2b0d  ldstr    aRedirecturls// "RedirectUrls"
0x2b12  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2b17  brtrue.s loc_2B46
0x2b19  br.s     loc_2B4A
0x2b1b  ldarg.1
0x2b1c  ldloc.3
0x2b1d  stind.ref
0x2b1e  br.s     loc_2B4A
0x2b20  ldarg.2
0x2b21  ldloc.3
0x2b22  stind.ref
0x2b23  br.s     loc_2B4A
0x2b25  ldarg.3
0x2b26  ldloc.3
0x2b27  stind.ref
0x2b28  br.s     loc_2B4A
0x2b2a  ldarg.s  4
0x2b2c  ldloc.3
0x2b2d  stind.ref
0x2b2e  br.s     loc_2B4A
0x2b30  ldloc.3
0x2b31  stloc.1
0x2b32  br.s     loc_2B4A
0x2b34  ldarg.s  5
0x2b36  ldloc.3
0x2b37  stind.ref
0x2b38  br.s     loc_2B4A
0x2b3a  ldarg.s  6
0x2b3c  ldloc.3
0x2b3d  stind.ref
0x2b3e  br.s     loc_2B4A
0x2b40  ldarg.s  7
0x2b42  ldloc.3
0x2b43  stind.ref
0x2b44  br.s     loc_2B4A
0x2b46  ldarg.s  8
0x2b48  ldloc.3
0x2b49  stind.ref
0x2b4a  ldloc.2
0x2b4b  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x2b50  brtrue   loc_29C7
0x2b55  leave.s  loc_2B61
0x2b57  ldloc.2
0x2b58  brfalse.s loc_2B60
0x2b5a  ldloc.2
0x2b5b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b60  endfinally
0x2b61  ldarg.1
0x2b62  ldind.ref
0x2b63  brfalse.s loc_2B89
0x2b65  ldarg.2
0x2b66  ldind.ref
0x2b67  brfalse.s loc_2B89
0x2b69  ldarg.3
0x2b6a  ldind.ref
0x2b6b  brfalse.s loc_2B89
0x2b6d  ldarg.s  4
0x2b6f  ldind.ref
0x2b70  brfalse.s loc_2B89
0x2b72  ldarg.s  5
0x2b74  ldind.ref
0x2b75  brfalse.s loc_2B89
0x2b77  ldarg.s  6
0x2b79  ldind.ref
0x2b7a  brfalse.s loc_2B89
0x2b7c  ldarg.s  7
0x2b7e  ldind.ref
0x2b7f  brfalse.s loc_2B89
0x2b81  ldarg.s  8
0x2b83  ldind.ref
0x2b84  brfalse.s loc_2B89
0x2b86  ldloc.1
0x2b87  brtrue.s loc_2B94
0x2b89  ldstr    aInvalidPbiConf// "Invalid PBI Configuration"
0x2b8e  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x2b93  throw
0x2b94  ret
```
