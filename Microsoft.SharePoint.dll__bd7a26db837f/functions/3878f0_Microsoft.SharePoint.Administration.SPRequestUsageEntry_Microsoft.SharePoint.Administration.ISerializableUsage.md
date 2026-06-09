# Microsoft.SharePoint.Administration.SPRequestUsageEntry::Microsoft.SharePoint.Administration.ISerializableUsageEntry.GetObjectData

- ea: `0x3878f0`
- end: `0x3881ca`
- name: `Microsoft.SharePoint.Administration.SPRequestUsageEntry::Microsoft.SharePoint.Administration.ISerializableUsageEntry.GetObjectData`
- size: `2266`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x1a18c0`
- `0x1a18e0`
- `0x2061f0`
- `0x3878f0`
- `0x6c9890`
- `0x7ae700`

## string_xrefs

- `0x387a10`: `UserAgent`
- `0x387a74`: `ServiceCallCount`
- `0x387a8a`: `ServiceCallDurationSum`
- `0x38796d`: `DocumentPath`
- `0x387aee`: `SqlLogicalReads`
- `0x387b30`: `DistributedCacheReads`
- `0x387b46`: `DistributedCacheReadsDuration`
- `0x387b88`: `DistributedCacheReadsSize`
- `0x387b5c`: `DistributedCacheWrites`
- `0x387b72`: `DistributedCacheWritesDuration`
- `0x387b9e`: `DistributedCacheWritesSize`
- `0x387bb4`: `DistributedCacheMisses`
- `0x387bca`: `DistributedCacheHits`
- `0x387be0`: `DistributedCacheFailures`
- `0x387bf6`: `DistributedCachedObjectsRequested`
- `0x387ed2`: `VirtualDocumentPath`
- `0x3880f7`: `DocumentPathOriginalCasing`

## pseudocode

```c

```

## disassembly

```asm
0x3878f0  ldarg.0
0x3878f1  ldarg.1
0x3878f2  call     instance void Microsoft.SharePoint.Administration.SPUsageEntry::GetBaseObjectData(class Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo info)
0x3878f7  ldarg.1
0x3878f8  ldstr    aWebapplication_5// "WebApplicationId"
0x3878fd  ldarg.0
0x3878fe  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_WebApplicationId
0x387903  box      [mscorlib]System.Guid
0x387908  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38790d  ldarg.1
0x38790e  ldstr    aServerurl// "ServerUrl"
0x387913  ldarg.0
0x387914  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ServerUrl
0x387919  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38791e  ldarg.1
0x38791f  ldstr    aSiteid_0// "SiteId"
0x387924  ldarg.0
0x387925  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_SiteId
0x38792a  box      [mscorlib]System.Guid
0x38792f  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387934  ldarg.1
0x387935  ldstr    aSiteurl// "SiteUrl"
0x38793a  ldarg.0
0x38793b  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_SiteUrl
0x387940  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387945  ldarg.1
0x387946  ldstr    aWebid// "WebId"
0x38794b  ldarg.0
0x38794c  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_WebId
0x387951  box      [mscorlib]System.Guid
0x387956  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38795b  ldarg.1
0x38795c  ldstr    aWeburl_1// "WebUrl"
0x387961  ldarg.0
0x387962  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_WebUrl
0x387967  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38796c  ldarg.1
0x38796d  ldstr    aDocumentpath// "DocumentPath"
0x387972  ldarg.0
0x387973  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_DocNameAndPath
0x387978  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38797d  ldarg.1
0x38797e  ldstr    aContenttypeid_2// "ContentTypeId"
0x387983  ldarg.0
0x387984  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ContentTypeId
0x387989  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38798e  ldarg.1
0x38798f  ldstr    aQuerystring// "QueryString"
0x387994  ldarg.0
0x387995  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_QueryString
0x38799a  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38799f  ldarg.1
0x3879a0  ldstr    aBytesconsumed// "BytesConsumed"
0x3879a5  ldarg.0
0x3879a6  ldfld    int32 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_BytesSent
0x3879ab  box      [mscorlib]System.Int32
0x3879b0  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x3879b5  ldarg.1
0x3879b6  ldstr    aHttpstatus// "HttpStatus"
0x3879bb  ldarg.0
0x3879bc  ldfld    int16 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_HttpStatus
0x3879c1  box      [mscorlib]System.Int16
0x3879c6  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x3879cb  ldarg.1
0x3879cc  ldstr    aSessionid// "SessionId"
0x3879d1  ldarg.0
0x3879d2  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_SessionId
0x3879d7  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x3879dc  ldarg.1
0x3879dd  ldstr    aReferrerurl_0// "ReferrerUrl"
0x3879e2  ldarg.0
0x3879e3  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ReferrerUrl
0x3879e8  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x3879ed  ldarg.1
0x3879ee  ldstr    aReferrerquerys// "ReferrerQueryString"
0x3879f3  ldarg.0
0x3879f4  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ReferrerQueryString
0x3879f9  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x3879fe  ldarg.1
0x3879ff  ldstr    aBrowser// "Browser"
0x387a04  ldarg.0
0x387a05  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_Browser
0x387a0a  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387a0f  ldarg.1
0x387a10  ldstr    aUseragent// "UserAgent"
0x387a15  ldarg.0
0x387a16  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_UserAgent
0x387a1b  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387a20  ldarg.1
0x387a21  ldstr    aUseraddress// "UserAddress"
0x387a26  ldarg.0
0x387a27  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_UserAddress
0x387a2c  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387a31  ldarg.1
0x387a32  ldstr    aRequestcount// "RequestCount"
0x387a37  ldarg.0
0x387a38  ldfld    int16 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_Requests
0x387a3d  box      [mscorlib]System.Int16
0x387a42  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387a47  ldarg.1
0x387a48  ldstr    aQuerycount// "QueryCount"
0x387a4d  ldarg.0
0x387a4e  ldfld    int16 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_Queries
0x387a53  box      [mscorlib]System.Int16
0x387a58  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387a5d  ldarg.1
0x387a5e  ldstr    aQuerydurations// "QueryDurationSum"
0x387a63  ldarg.0
0x387a64  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_QueryDurationSum
0x387a69  box      [mscorlib]System.Int64
0x387a6e  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387a73  ldarg.1
0x387a74  ldstr    aServicecallcou// "ServiceCallCount"
0x387a79  ldarg.0
0x387a7a  ldfld    int16 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ServiceCalls
0x387a7f  box      [mscorlib]System.Int16
0x387a84  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387a89  ldarg.1
0x387a8a  ldstr    aServicecalldur// "ServiceCallDurationSum"
0x387a8f  ldarg.0
0x387a90  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ServiceCallDurationSum
0x387a95  box      [mscorlib]System.Int64
0x387a9a  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387a9f  ldarg.1
0x387aa0  ldstr    aOperationcount// "OperationCount"
0x387aa5  ldarg.0
0x387aa6  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_Operations
0x387aab  box      [mscorlib]System.Int64
0x387ab0  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387ab5  ldarg.1
0x387ab6  ldstr    aDuration// "Duration"
0x387abb  ldarg.0
0x387abc  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_Duration
0x387ac1  box      [mscorlib]System.Int64
0x387ac6  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387acb  ldarg.1
0x387acc  ldstr    aRequesttype// "RequestType"
0x387ad1  ldarg.0
0x387ad2  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_RequestType
0x387ad7  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387adc  ldarg.1
0x387add  ldstr    aTitle_0// "Title"
0x387ae2  ldarg.0
0x387ae3  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_Title
0x387ae8  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387aed  ldarg.1
0x387aee  ldstr    aSqllogicalread// "SqlLogicalReads"
0x387af3  ldarg.0
0x387af4  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_SqlLogicalReads
0x387af9  box      [mscorlib]System.Int64
0x387afe  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387b03  ldarg.1
0x387b04  ldstr    aCpumcycles// "CPUMCycles"
0x387b09  ldarg.0
0x387b0a  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_CPUMCycles
0x387b0f  box      [mscorlib]System.Int64
0x387b14  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387b19  ldarg.1
0x387b1a  ldstr    aCpuduration_0// "CPUDuration"
0x387b1f  ldarg.0
0x387b20  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_CPUDuration
0x387b25  box      [mscorlib]System.Int64
0x387b2a  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387b2f  ldarg.1
0x387b30  ldstr    aDistributedcac_0// "DistributedCacheReads"
0x387b35  ldarg.0
0x387b36  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheReads
0x387b3b  box      [mscorlib]System.Int64
0x387b40  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387b45  ldarg.1
0x387b46  ldstr    aDistributedcac_1// "DistributedCacheReadsDuration"
0x387b4b  ldarg.0
0x387b4c  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheReadsDuration
0x387b51  box      [mscorlib]System.Int64
0x387b56  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387b5b  ldarg.1
0x387b5c  ldstr    aDistributedcac_3// "DistributedCacheWrites"
0x387b61  ldarg.0
0x387b62  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheWrites
0x387b67  box      [mscorlib]System.Int64
0x387b6c  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387b71  ldarg.1
0x387b72  ldstr    aDistributedcac_4// "DistributedCacheWritesDuration"
0x387b77  ldarg.0
0x387b78  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheWritesDuration
0x387b7d  box      [mscorlib]System.Int64
0x387b82  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387b87  ldarg.1
0x387b88  ldstr    aDistributedcac_2// "DistributedCacheReadsSize"
0x387b8d  ldarg.0
0x387b8e  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheReadsSize
0x387b93  box      [mscorlib]System.Int64
0x387b98  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387b9d  ldarg.1
0x387b9e  ldstr    aDistributedcac_5// "DistributedCacheWritesSize"
0x387ba3  ldarg.0
0x387ba4  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheWritesSize
0x387ba9  box      [mscorlib]System.Int64
0x387bae  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387bb3  ldarg.1
0x387bb4  ldstr    aDistributedcac_6// "DistributedCacheMisses"
0x387bb9  ldarg.0
0x387bba  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheMisses
0x387bbf  box      [mscorlib]System.Int64
0x387bc4  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387bc9  ldarg.1
0x387bca  ldstr    aDistributedcac_7// "DistributedCacheHits"
0x387bcf  ldarg.0
0x387bd0  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheHits
0x387bd5  box      [mscorlib]System.Int64
0x387bda  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387bdf  ldarg.1
0x387be0  ldstr    aDistributedcac_8// "DistributedCacheFailures"
0x387be5  ldarg.0
0x387be6  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCacheFailures
0x387beb  box      [mscorlib]System.Int64
0x387bf0  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387bf5  ldarg.1
0x387bf6  ldstr    aDistributedcac_9// "DistributedCachedObjectsRequested"
0x387bfb  ldarg.0
0x387bfc  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_distributedCachedObjectsRequested
0x387c01  box      [mscorlib]System.Int64
0x387c06  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387c0b  ldarg.1
0x387c0c  ldstr    aManagedmemoryb// "ManagedMemoryBytes"
0x387c11  ldarg.0
0x387c12  ldfld    valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ManagedMemoryBytes
0x387c17  box      valuetype [mscorlib]System.Nullable`1<int64>
0x387c1c  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387c21  ldarg.1
0x387c22  ldstr    aManagedmemoryb_0// "ManagedMemoryBytesLOH"
0x387c27  ldarg.0
0x387c28  ldfld    valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ManagedMemoryBytesLOH
0x387c2d  box      valuetype [mscorlib]System.Nullable`1<int64>
0x387c32  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387c37  ldarg.1
0x387c38  ldstr    aIislatency_0// "IisLatency"
0x387c3d  ldarg.0
0x387c3e  ldfld    valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_IisLatency
0x387c43  box      valuetype [mscorlib]System.Nullable`1<int64>
0x387c48  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387c4d  ldarg.1
0x387c4e  ldstr    aRequestmanagem_9// "RequestManagementRoutedServerUrl"
0x387c53  ldarg.0
0x387c54  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_RequestManagementRoutedServerUrl
0x387c59  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387c5e  ldarg.1
0x387c5f  ldstr    aRequestmanagem_10// "RequestManagementThrottled"
0x387c64  ldarg.0
0x387c65  ldfld    bool Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_RequestManagementThrottled
0x387c6a  box      [mscorlib]System.Boolean
0x387c6f  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387c74  ldarg.1
0x387c75  ldstr    aRequestmanagem_11// "RequestManagementUploadDuration"
0x387c7a  ldarg.0
0x387c7b  ldfld    valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_RequestManagementUploadDuration
0x387c80  box      valuetype [mscorlib]System.Nullable`1<int64>
0x387c85  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387c8a  ldarg.1
0x387c8b  ldstr    aRequestmanagem_12// "RequestManagementResponseDuration"
0x387c90  ldarg.0
0x387c91  ldfld    valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_RequestManagementResponseDuration
0x387c96  box      valuetype [mscorlib]System.Nullable`1<int64>
0x387c9b  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387ca0  ldarg.1
0x387ca1  ldstr    aRequestmanagem_13// "RequestManagementDownloadDuration"
0x387ca6  ldarg.0
0x387ca7  ldfld    valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_RequestManagementDownloadDuration
0x387cac  box      valuetype [mscorlib]System.Nullable`1<int64>
0x387cb1  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387cb6  ldarg.1
0x387cb7  ldstr    aHeadersforward// "HeadersForwarded"
0x387cbc  ldarg.0
0x387cbd  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_HeadersForwarded
0x387cc2  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387cc7  ldarg.1
0x387cc8  ldstr    aClaimsauthenti// "ClaimsAuthenticationTime"
0x387ccd  ldarg.0
0x387cce  ldfld    int64 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ClaimsAuthenticationTime
0x387cd3  box      [mscorlib]System.Int64
0x387cd8  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387cdd  ldarg.1
0x387cde  ldstr    aClaimsauthenti_0// "ClaimsAuthenticationTimeType"
0x387ce3  ldarg.0
0x387ce4  ldfld    string Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_ClaimsAuthenticationTimeType
0x387ce9  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387cee  ldarg.1
0x387cef  ldstr    aMuienabled// "MUIEnabled"
0x387cf4  ldarg.0
0x387cf5  ldfld    bool Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_MUIEnabled
0x387cfa  box      [mscorlib]System.Boolean
0x387cff  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387d04  ldarg.1
0x387d05  ldstr    aWebculture// "WebCulture"
0x387d0a  ldarg.0
0x387d0b  ldfld    int32 Microsoft.SharePoint.Administration.SPRequestUsageEntry::m_WebCulture
0x387d10  box      [mscorlib]System.Int32
0x387d15  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x387d1a  ldarg.1
0x387d1b  ldstr    aUiculture// "UICulture"
  ... truncated ...
```
