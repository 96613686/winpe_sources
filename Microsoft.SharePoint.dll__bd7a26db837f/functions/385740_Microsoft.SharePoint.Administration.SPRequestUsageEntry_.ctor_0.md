# Microsoft.SharePoint.Administration.SPRequestUsageEntry::.ctor_0

- ea: `0x385740`
- end: `0x385f4d`
- name: `Microsoft.SharePoint.Administration.SPRequestUsageEntry::.ctor_0`
- size: `2061`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x385f50`

## callees

- `0x1a18c0`
- `0x1a18e0`
- `0x2060c0`
- `0x385740`
- `0x4cc890`
- `0x6c9890`

## string_xrefs

- `0x385869`: `UserAgent`
- `0x3858c3`: `ServiceCallCount`
- `0x3858e7`: `ServiceCallDurationSum`
- `0x3857b4`: `DocumentPath`
- `0x38592f`: `SqlLogicalReads`
- `0x385965`: `DistributedCacheReads`
- `0x385977`: `DistributedCacheReadsDuration`
- `0x385989`: `DistributedCacheReadsSize`
- `0x38599b`: `DistributedCacheWrites`
- `0x3859ad`: `DistributedCacheWritesDuration`
- `0x3859bf`: `DistributedCacheWritesSize`
- `0x3859d1`: `DistributedCacheMisses`
- `0x3859e3`: `DistributedCacheHits`
- `0x3859f5`: `DistributedCacheFailures`
- `0x385a07`: `DistributedCachedObjectsRequested`
- `0x385c8f`: `VirtualDocumentPath`
- `0x385e75`: `DocumentPathOriginalCasing`

## pseudocode

```c

```

## disassembly

```asm
0x385740  ldarg.0
0x385741  ldarg.1
0x385742  call     instance void Microsoft.SharePoint.Administration.SPUsageEntry::.ctor(class Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo info)
0x385747  ldarg.1
0x385748  ldstr    aWebapplication_5// "WebApplicationId"
0x38574d  ldarg.0
0x38574e  ldflda   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_WebApplicationId
0x385753  callvirt T0x2B0000FC
0x385758  pop
0x385759  ldarg.1
0x38575a  ldstr    aServerurl// "ServerUrl"
0x38575f  ldarg.0
0x385760  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ServerUrl
0x385765  callvirt T0x2B0000FD
0x38576a  pop
0x38576b  ldarg.1
0x38576c  ldstr    aSiteid_0// "SiteId"
0x385771  ldarg.0
0x385772  ldflda   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_SiteId
0x385777  callvirt T0x2B0000FC
0x38577c  pop
0x38577d  ldarg.1
0x38577e  ldstr    aSiteurl// "SiteUrl"
0x385783  ldarg.0
0x385784  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_SiteUrl
0x385789  callvirt T0x2B0000FD
0x38578e  pop
0x38578f  ldarg.1
0x385790  ldstr    aWebid// "WebId"
0x385795  ldarg.0
0x385796  ldflda   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_WebId
0x38579b  callvirt T0x2B0000FC
0x3857a0  pop
0x3857a1  ldarg.1
0x3857a2  ldstr    aWeburl_1// "WebUrl"
0x3857a7  ldarg.0
0x3857a8  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_WebUrl
0x3857ad  callvirt T0x2B0000FD
0x3857b2  pop
0x3857b3  ldarg.1
0x3857b4  ldstr    aDocumentpath// "DocumentPath"
0x3857b9  ldarg.0
0x3857ba  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_DocNameAndPath
0x3857bf  callvirt T0x2B0000FD
0x3857c4  pop
0x3857c5  ldarg.1
0x3857c6  ldstr    aContenttypeid_2// "ContentTypeId"
0x3857cb  ldarg.0
0x3857cc  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ContentTypeId
0x3857d1  call     valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentTypeId::get_Empty()
0x3857d6  stloc.0
0x3857d7  ldloca.s 0
0x3857d9  constrained. Microsoft.SharePoint.SPContentTypeId
0x3857df  callvirt instance string [mscorlib]System.Object::ToString()
0x3857e4  callvirt T0x2B000294
0x3857e9  pop
0x3857ea  ldarg.1
0x3857eb  ldstr    aQuerystring// "QueryString"
0x3857f0  ldarg.0
0x3857f1  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_QueryString
0x3857f6  callvirt T0x2B0000FD
0x3857fb  pop
0x3857fc  ldarg.1
0x3857fd  ldstr    aBytesconsumed// "BytesConsumed"
0x385802  ldarg.0
0x385803  ldflda   int32 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_BytesSent
0x385808  callvirt T0x2B00012C
0x38580d  pop
0x38580e  ldarg.1
0x38580f  ldstr    aHttpstatus// "HttpStatus"
0x385814  ldarg.0
0x385815  ldflda   int16 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_HttpStatus
0x38581a  callvirt T0x2B000295
0x38581f  pop
0x385820  ldarg.1
0x385821  ldstr    aSessionid// "SessionId"
0x385826  ldarg.0
0x385827  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_SessionId
0x38582c  callvirt T0x2B0000FD
0x385831  pop
0x385832  ldarg.1
0x385833  ldstr    aReferrerurl_0// "ReferrerUrl"
0x385838  ldarg.0
0x385839  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ReferrerUrl
0x38583e  callvirt T0x2B0000FD
0x385843  pop
0x385844  ldarg.1
0x385845  ldstr    aReferrerquerys// "ReferrerQueryString"
0x38584a  ldarg.0
0x38584b  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ReferrerQueryString
0x385850  callvirt T0x2B0000FD
0x385855  pop
0x385856  ldarg.1
0x385857  ldstr    aBrowser// "Browser"
0x38585c  ldarg.0
0x38585d  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_Browser
0x385862  callvirt T0x2B0000FD
0x385867  pop
0x385868  ldarg.1
0x385869  ldstr    aUseragent// "UserAgent"
0x38586e  ldarg.0
0x38586f  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_UserAgent
0x385874  callvirt T0x2B0000FD
0x385879  pop
0x38587a  ldarg.1
0x38587b  ldstr    aUseraddress// "UserAddress"
0x385880  ldarg.0
0x385881  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_UserAddress
0x385886  callvirt T0x2B0000FD
0x38588b  pop
0x38588c  ldarg.1
0x38588d  ldstr    aRequestcount// "RequestCount"
0x385892  ldarg.0
0x385893  ldflda   int16 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_Requests
0x385898  callvirt T0x2B000295
0x38589d  pop
0x38589e  ldarg.1
0x38589f  ldstr    aQuerycount// "QueryCount"
0x3858a4  ldarg.0
0x3858a5  ldflda   int16 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_Queries
0x3858aa  callvirt T0x2B000295
0x3858af  pop
0x3858b0  ldarg.1
0x3858b1  ldstr    aQuerydurations// "QueryDurationSum"
0x3858b6  ldarg.0
0x3858b7  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_QueryDurationSum
0x3858bc  callvirt T0x2B000271
0x3858c1  pop
0x3858c2  ldarg.1
0x3858c3  ldstr    aServicecallcou// "ServiceCallCount"
0x3858c8  ldarg.0
0x3858c9  ldflda   int16 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ServiceCalls
0x3858ce  callvirt T0x2B000295
0x3858d3  pop
0x3858d4  ldarg.1
0x3858d5  ldstr    aOperationcount// "OperationCount"
0x3858da  ldarg.0
0x3858db  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_Operations
0x3858e0  callvirt T0x2B000271
0x3858e5  pop
0x3858e6  ldarg.1
0x3858e7  ldstr    aServicecalldur// "ServiceCallDurationSum"
0x3858ec  ldarg.0
0x3858ed  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ServiceCallDurationSum
0x3858f2  callvirt T0x2B000271
0x3858f7  pop
0x3858f8  ldarg.1
0x3858f9  ldstr    aDuration// "Duration"
0x3858fe  ldarg.0
0x3858ff  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_Duration
0x385904  callvirt T0x2B000271
0x385909  pop
0x38590a  ldarg.1
0x38590b  ldstr    aRequesttype// "RequestType"
0x385910  ldarg.0
0x385911  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_RequestType
0x385916  callvirt T0x2B0000FD
0x38591b  pop
0x38591c  ldarg.1
0x38591d  ldstr    aTitle_0// "Title"
0x385922  ldarg.0
0x385923  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_Title
0x385928  callvirt T0x2B0000FD
0x38592d  pop
0x38592e  ldarg.1
0x38592f  ldstr    aSqllogicalread// "SqlLogicalReads"
0x385934  ldarg.0
0x385935  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_SqlLogicalReads
0x38593a  callvirt T0x2B000271
0x38593f  pop
0x385940  ldarg.1
0x385941  ldstr    aCpumcycles// "CPUMCycles"
0x385946  ldarg.0
0x385947  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_CPUMCycles
0x38594c  callvirt T0x2B000271
0x385951  pop
0x385952  ldarg.1
0x385953  ldstr    aCpuduration_0// "CPUDuration"
0x385958  ldarg.0
0x385959  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_CPUDuration
0x38595e  callvirt T0x2B000271
0x385963  pop
0x385964  ldarg.1
0x385965  ldstr    aDistributedcac_0// "DistributedCacheReads"
0x38596a  ldarg.0
0x38596b  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheReads
0x385970  callvirt T0x2B000271
0x385975  pop
0x385976  ldarg.1
0x385977  ldstr    aDistributedcac_1// "DistributedCacheReadsDuration"
0x38597c  ldarg.0
0x38597d  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheReadsDuration
0x385982  callvirt T0x2B000271
0x385987  pop
0x385988  ldarg.1
0x385989  ldstr    aDistributedcac_2// "DistributedCacheReadsSize"
0x38598e  ldarg.0
0x38598f  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheReadsSize
0x385994  callvirt T0x2B000271
0x385999  pop
0x38599a  ldarg.1
0x38599b  ldstr    aDistributedcac_3// "DistributedCacheWrites"
0x3859a0  ldarg.0
0x3859a1  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheWrites
0x3859a6  callvirt T0x2B000271
0x3859ab  pop
0x3859ac  ldarg.1
0x3859ad  ldstr    aDistributedcac_4// "DistributedCacheWritesDuration"
0x3859b2  ldarg.0
0x3859b3  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheWritesDuration
0x3859b8  callvirt T0x2B000271
0x3859bd  pop
0x3859be  ldarg.1
0x3859bf  ldstr    aDistributedcac_5// "DistributedCacheWritesSize"
0x3859c4  ldarg.0
0x3859c5  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheWritesSize
0x3859ca  callvirt T0x2B000271
0x3859cf  pop
0x3859d0  ldarg.1
0x3859d1  ldstr    aDistributedcac_6// "DistributedCacheMisses"
0x3859d6  ldarg.0
0x3859d7  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheMisses
0x3859dc  callvirt T0x2B000271
0x3859e1  pop
0x3859e2  ldarg.1
0x3859e3  ldstr    aDistributedcac_7// "DistributedCacheHits"
0x3859e8  ldarg.0
0x3859e9  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheHits
0x3859ee  callvirt T0x2B000271
0x3859f3  pop
0x3859f4  ldarg.1
0x3859f5  ldstr    aDistributedcac_8// "DistributedCacheFailures"
0x3859fa  ldarg.0
0x3859fb  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheFailures
0x385a00  callvirt T0x2B000271
0x385a05  pop
0x385a06  ldarg.1
0x385a07  ldstr    aDistributedcac_9// "DistributedCachedObjectsRequested"
0x385a0c  ldarg.0
0x385a0d  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCachedObjectsRequested
0x385a12  callvirt T0x2B000271
0x385a17  pop
0x385a18  ldarg.1
0x385a19  ldstr    aManagedmemoryb// "ManagedMemoryBytes"
0x385a1e  ldarg.0
0x385a1f  ldflda   valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ManagedMemoryBytes
0x385a24  callvirt T0x2B000131
0x385a29  pop
0x385a2a  ldarg.1
0x385a2b  ldstr    aManagedmemoryb_0// "ManagedMemoryBytesLOH"
0x385a30  ldarg.0
0x385a31  ldflda   valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ManagedMemoryBytesLOH
0x385a36  callvirt T0x2B000131
0x385a3b  pop
0x385a3c  ldarg.1
0x385a3d  ldstr    aIislatency_0// "IisLatency"
0x385a42  ldarg.0
0x385a43  ldflda   valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_IisLatency
0x385a48  callvirt T0x2B000131
0x385a4d  pop
0x385a4e  ldarg.1
0x385a4f  ldstr    aRequestmanagem_9// "RequestManagementRoutedServerUrl"
0x385a54  ldarg.0
0x385a55  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_RequestManagementRoutedServerUrl
0x385a5a  callvirt T0x2B0000FD
0x385a5f  pop
0x385a60  ldarg.1
0x385a61  ldstr    aRequestmanagem_10// "RequestManagementThrottled"
0x385a66  ldarg.0
0x385a67  ldflda   bool Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_RequestManagementThrottled
0x385a6c  callvirt T0x2B000272
0x385a71  pop
0x385a72  ldarg.1
0x385a73  ldstr    aRequestmanagem_11// "RequestManagementUploadDuration"
0x385a78  ldarg.0
0x385a79  ldflda   valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_RequestManagementUploadDuration
0x385a7e  callvirt T0x2B000131
0x385a83  pop
0x385a84  ldarg.1
0x385a85  ldstr    aRequestmanagem_12// "RequestManagementResponseDuration"
0x385a8a  ldarg.0
0x385a8b  ldflda   valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_RequestManagementResponseDuration
0x385a90  callvirt T0x2B000131
0x385a95  pop
0x385a96  ldarg.1
0x385a97  ldstr    aRequestmanagem_13// "RequestManagementDownloadDuration"
0x385a9c  ldarg.0
0x385a9d  ldflda   valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_RequestManagementDownloadDuration
0x385aa2  callvirt T0x2B000131
0x385aa7  pop
0x385aa8  ldarg.1
0x385aa9  ldstr    aHeadersforward// "HeadersForwarded"
0x385aae  ldarg.0
0x385aaf  ldflda   string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_HeadersForwarded
0x385ab4  callvirt T0x2B0000FD
0x385ab9  pop
0x385aba  ldarg.1
0x385abb  ldstr    aClaimsauthenti// "ClaimsAuthenticationTime"
0x385ac0  ldarg.0
0x385ac1  ldflda   int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ClaimsAuthenticationTime
  ... truncated ...
```
