# Microsoft.SharePoint.Administration.SPRequestUsageDefinition::get_Columns

- ea: `0x384ad0`
- end: `0x38536c`
- name: `Microsoft.SharePoint.Administration.SPRequestUsageDefinition::get_Columns`
- size: `2204`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x1a18c0`
- `0x1a18e0`
- `0x378200`
- `0x378210`
- `0x384ad0`
- `0x6c9890`

## string_xrefs

- `0x384c1e`: `UserAgent`
- `0x384c7e`: `ServiceCallCount`
- `0x384c90`: `ServiceCallDurationSum`
- `0x384b5d`: `DocumentPath`
- `0x384cee`: `SqlLogicalReads`
- `0x384d21`: `DistributedCacheReads`
- `0x384d32`: `DistributedCacheReadsDuration`
- `0x384d43`: `DistributedCacheReadsSize`
- `0x384d54`: `DistributedCacheWrites`
- `0x384d65`: `DistributedCacheWritesDuration`
- `0x384d76`: `DistributedCacheWritesSize`
- `0x384d87`: `DistributedCacheMisses`
- `0x384d98`: `DistributedCacheHits`
- `0x384da9`: `DistributedCacheFailures`
- `0x384dba`: `DistributedCachedObjectsRequested`
- `0x38505d`: `VirtualDocumentPath`
- `0x385261`: `DocumentPathOriginalCasing`

## pseudocode

```c

```

## disassembly

```asm
0x384ad0  ldarg.0
0x384ad1  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition> Microsoft.SharePoint.Administration.SPRequestUsageDefinition::m_Columns
0x384ad6  brtrue   loc_385365
0x384adb  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::.ctor()
0x384ae0  stloc.0
0x384ae1  ldloc.0
0x384ae2  ldstr    aWebapplication_5// "WebApplicationId"
0x384ae7  ldc.i4.s 0xE
0x384ae9  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384aee  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384af3  ldloc.0
0x384af4  ldstr    aServerurl// "ServerUrl"
0x384af9  ldc.i4.s 0xC
0x384afb  ldc.i4   0x100
0x384b00  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384b05  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384b0a  ldloc.0
0x384b0b  ldstr    aSiteid_0// "SiteId"
0x384b10  ldc.i4.s 0xE
0x384b12  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384b17  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384b1c  ldloc.0
0x384b1d  ldstr    aSiteurl// "SiteUrl"
0x384b22  ldc.i4.s 0xC
0x384b24  ldc.i4   0x100
0x384b29  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384b2e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384b33  ldloc.0
0x384b34  ldstr    aWebid// "WebId"
0x384b39  ldc.i4.s 0xE
0x384b3b  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384b40  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384b45  ldloc.0
0x384b46  ldstr    aWeburl_1// "WebUrl"
0x384b4b  ldc.i4.s 0xC
0x384b4d  ldc.i4   0x100
0x384b52  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384b57  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384b5c  ldloc.0
0x384b5d  ldstr    aDocumentpath// "DocumentPath"
0x384b62  ldc.i4.s 0xC
0x384b64  ldc.i4   0x100
0x384b69  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384b6e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384b73  ldloc.0
0x384b74  ldstr    aContenttypeid_2// "ContentTypeId"
0x384b79  ldc.i4.s 0xC
0x384b7b  ldc.i4   0x400
0x384b80  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384b85  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384b8a  ldloc.0
0x384b8b  ldstr    aQuerystring// "QueryString"
0x384b90  ldc.i4.s 0xC
0x384b92  ldc.i4   0x200
0x384b97  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384b9c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384ba1  ldloc.0
0x384ba2  ldstr    aBytesconsumed// "BytesConsumed"
0x384ba7  ldc.i4.8
0x384ba8  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384bad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384bb2  ldloc.0
0x384bb3  ldstr    aHttpstatus// "HttpStatus"
0x384bb8  ldc.i4.s 0x10
0x384bba  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384bbf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384bc4  ldloc.0
0x384bc5  ldstr    aSessionid// "SessionId"
0x384bca  ldc.i4.s 0xC
0x384bcc  ldc.i4.s 0x40
0x384bce  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384bd3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384bd8  ldloc.0
0x384bd9  ldstr    aReferrerurl_0// "ReferrerUrl"
0x384bde  ldc.i4.s 0xC
0x384be0  ldc.i4   0x104
0x384be5  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384bea  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384bef  ldloc.0
0x384bf0  ldstr    aReferrerquerys// "ReferrerQueryString"
0x384bf5  ldc.i4.s 0xC
0x384bf7  ldc.i4   0x200
0x384bfc  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384c01  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384c06  ldloc.0
0x384c07  ldstr    aBrowser// "Browser"
0x384c0c  ldc.i4.s 0xC
0x384c0e  ldc.i4   0x80
0x384c13  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384c18  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384c1d  ldloc.0
0x384c1e  ldstr    aUseragent// "UserAgent"
0x384c23  ldc.i4.s 0xC
0x384c25  ldc.i4   0x200
0x384c2a  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384c2f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384c34  ldloc.0
0x384c35  ldstr    aUseraddress// "UserAddress"
0x384c3a  ldc.i4.s 0xC
0x384c3c  ldc.i4.s 0x2E
0x384c3e  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384c43  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384c48  ldloc.0
0x384c49  ldstr    aRequestcount// "RequestCount"
0x384c4e  ldc.i4.s 0x10
0x384c50  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384c55  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384c5a  ldloc.0
0x384c5b  ldstr    aQuerycount// "QueryCount"
0x384c60  ldc.i4.s 0x10
0x384c62  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384c67  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384c6c  ldloc.0
0x384c6d  ldstr    aQuerydurations// "QueryDurationSum"
0x384c72  ldc.i4.0
0x384c73  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384c78  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384c7d  ldloc.0
0x384c7e  ldstr    aServicecallcou// "ServiceCallCount"
0x384c83  ldc.i4.s 0x10
0x384c85  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384c8a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384c8f  ldloc.0
0x384c90  ldstr    aServicecalldur// "ServiceCallDurationSum"
0x384c95  ldc.i4.0
0x384c96  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384c9b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384ca0  ldloc.0
0x384ca1  ldstr    aOperationcount// "OperationCount"
0x384ca6  ldc.i4.0
0x384ca7  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384cac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384cb1  ldloc.0
0x384cb2  ldstr    aDuration// "Duration"
0x384cb7  ldc.i4.0
0x384cb8  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384cbd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384cc2  ldloc.0
0x384cc3  ldstr    aRequesttype// "RequestType"
0x384cc8  ldc.i4.s 0xC
0x384cca  ldc.i4.s 0x10
0x384ccc  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384cd1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384cd6  ldloc.0
0x384cd7  ldstr    aTitle_0// "Title"
0x384cdc  ldc.i4.s 0xC
0x384cde  ldc.i4   0x80
0x384ce3  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384ce8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384ced  ldloc.0
0x384cee  ldstr    aSqllogicalread// "SqlLogicalReads"
0x384cf3  ldc.i4.0
0x384cf4  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384cf9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384cfe  ldloc.0
0x384cff  ldstr    aCpumcycles// "CPUMCycles"
0x384d04  ldc.i4.0
0x384d05  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384d0a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384d0f  ldloc.0
0x384d10  ldstr    aCpuduration_0// "CPUDuration"
0x384d15  ldc.i4.0
0x384d16  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384d1b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384d20  ldloc.0
0x384d21  ldstr    aDistributedcac_0// "DistributedCacheReads"
0x384d26  ldc.i4.0
0x384d27  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384d2c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384d31  ldloc.0
0x384d32  ldstr    aDistributedcac_1// "DistributedCacheReadsDuration"
0x384d37  ldc.i4.0
0x384d38  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384d3d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384d42  ldloc.0
0x384d43  ldstr    aDistributedcac_2// "DistributedCacheReadsSize"
0x384d48  ldc.i4.0
0x384d49  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384d4e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384d53  ldloc.0
0x384d54  ldstr    aDistributedcac_3// "DistributedCacheWrites"
0x384d59  ldc.i4.0
0x384d5a  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384d5f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384d64  ldloc.0
0x384d65  ldstr    aDistributedcac_4// "DistributedCacheWritesDuration"
0x384d6a  ldc.i4.0
0x384d6b  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384d70  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384d75  ldloc.0
0x384d76  ldstr    aDistributedcac_5// "DistributedCacheWritesSize"
0x384d7b  ldc.i4.0
0x384d7c  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384d81  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384d86  ldloc.0
0x384d87  ldstr    aDistributedcac_6// "DistributedCacheMisses"
0x384d8c  ldc.i4.0
0x384d8d  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384d92  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384d97  ldloc.0
0x384d98  ldstr    aDistributedcac_7// "DistributedCacheHits"
0x384d9d  ldc.i4.0
0x384d9e  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384da3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384da8  ldloc.0
0x384da9  ldstr    aDistributedcac_8// "DistributedCacheFailures"
0x384dae  ldc.i4.0
0x384daf  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384db4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384db9  ldloc.0
0x384dba  ldstr    aDistributedcac_9// "DistributedCachedObjectsRequested"
0x384dbf  ldc.i4.0
0x384dc0  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384dc5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384dca  ldloc.0
0x384dcb  ldstr    aManagedmemoryb// "ManagedMemoryBytes"
0x384dd0  ldc.i4.0
0x384dd1  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384dd6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384ddb  ldloc.0
0x384ddc  ldstr    aManagedmemoryb_0// "ManagedMemoryBytesLOH"
0x384de1  ldc.i4.0
0x384de2  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384de7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384dec  ldloc.0
0x384ded  ldstr    aIislatency_0// "IisLatency"
0x384df2  ldc.i4.0
0x384df3  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384df8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384dfd  ldloc.0
0x384dfe  ldstr    aRequestmanagem_9// "RequestManagementRoutedServerUrl"
0x384e03  ldc.i4.s 0xC
0x384e05  ldc.i4   0x100
0x384e0a  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384e0f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384e14  ldloc.0
0x384e15  ldstr    aRequestmanagem_10// "RequestManagementThrottled"
0x384e1a  ldc.i4.2
0x384e1b  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384e20  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384e25  ldloc.0
0x384e26  ldstr    aRequestmanagem_11// "RequestManagementUploadDuration"
0x384e2b  ldc.i4.0
0x384e2c  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384e31  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384e36  ldloc.0
0x384e37  ldstr    aRequestmanagem_12// "RequestManagementResponseDuration"
0x384e3c  ldc.i4.0
0x384e3d  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384e42  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384e47  ldloc.0
0x384e48  ldstr    aRequestmanagem_13// "RequestManagementDownloadDuration"
0x384e4d  ldc.i4.0
0x384e4e  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384e53  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384e58  ldloc.0
0x384e59  ldstr    aHeadersforward// "HeadersForwarded"
0x384e5e  ldc.i4.s 0xC
0x384e60  ldc.i4   0x100
0x384e65  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384e6a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384e6f  ldloc.0
0x384e70  ldstr    aClaimsauthenti// "ClaimsAuthenticationTime"
0x384e75  ldc.i4.0
0x384e76  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384e7b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384e80  ldloc.0
0x384e81  ldstr    aClaimsauthenti_0// "ClaimsAuthenticationTimeType"
0x384e86  ldc.i4.s 0xC
0x384e88  ldc.i4.s 0x3C
0x384e8a  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384e8f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384e94  ldloc.0
0x384e95  ldstr    aMuienabled// "MUIEnabled"
0x384e9a  ldc.i4.2
0x384e9b  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384ea0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384ea5  ldloc.0
0x384ea6  ldstr    aWebculture// "WebCulture"
0x384eab  ldc.i4.8
0x384eac  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384eb1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384eb6  ldloc.0
0x384eb7  ldstr    aUiculture// "UICulture"
0x384ebc  ldc.i4.8
0x384ebd  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x384ec2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384ec7  ldloc.0
0x384ec8  ldstr    aLargegapstartt// "LargeGapStartTag"
0x384ecd  ldc.i4.s 0xC
0x384ecf  ldc.i4.s 0x10
0x384ed1  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384ed6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384edb  ldloc.0
0x384edc  ldstr    aLargegapendtag// "LargeGapEndTag"
0x384ee1  ldc.i4.s 0xC
0x384ee3  ldc.i4.s 0x10
0x384ee5  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x384eea  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x384eef  ldloc.0
  ... truncated ...
```
