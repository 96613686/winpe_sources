# Microsoft.SharePoint.Library.SPRequest::GetSubwebsFiltered

- ea: `0x4bad0`
- end: `0x4bec6`
- name: `Microsoft.SharePoint.Library.SPRequest::GetSubwebsFiltered`
- size: `1014`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5d4400`

## callees

- `0x30b0`
- `0x4bad0`
- `0x4727e0`
- `0x472800`
- `0x4729d0`
- `0x472c90`
- `0x472d60`
- `0x7b4dd0`
- `0x7c78d0`
- `0x7c89b0`
- `0x957470`

## string_xrefs

- `0x4bb89`: `nWebTemplate`
- `0x4bc2d`: `nWebTemplate`
- `0x4bcd2`: `nWebTemplate`
- `0x4bd8e`: `nWebTemplate`
- `0x4be3f`: `nWebTemplate`
- `0x4bb92`: `nProvisionConfig`
- `0x4bc36`: `nProvisionConfig`
- `0x4bcdb`: `nProvisionConfig`
- `0x4bd97`: `nProvisionConfig`
- `0x4be48`: `nProvisionConfig`
- `0x4bb9b`: `lToLinkRecurringMeeting`
- `0x4bc3f`: `lToLinkRecurringMeeting`
- `0x4bce4`: `lToLinkRecurringMeeting`
- `0x4bda0`: `lToLinkRecurringMeeting`
- `0x4be51`: `lToLinkRecurringMeeting`

## pseudocode

```c

```

## disassembly

```asm
0x4bad0  ldc.i4   0x66366C37
0x4bad5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x4bada  ldc.i4.s 0x64
0x4badc  ldstr    aSprequestGetsu_2// "SPRequest.GetSubwebsFiltered"
0x4bae1  ldc.i4.1
0x4bae2  ldc.i4.2
0x4bae3  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x4bae8  stloc.s  5
0x4baea  ldloc.s  5
0x4baec  ldc.i4.0
0x4baed  ldc.i4   0x96
0x4baf2  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x4baf7  stelem.ref
0x4baf8  ldloc.s  5
0x4bafa  ldc.i4.1
0x4bafb  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x4bb00  stelem.ref
0x4bb01  ldloc.s  5
0x4bb03  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x4bb08  stloc.s  6
0x4bb0a  ldarg.0
0x4bb0b  dup
0x4bb0c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x4bb11  ldc.i4.1
0x4bb12  add
0x4bb13  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x4bb18  ldarg.0
0x4bb19  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x4bb1e  ldarg.0
0x4bb1f  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x4bb24  ldarg.1
0x4bb25  ldarg.2
0x4bb26  ldarg.3
0x4bb27  ldarg.s  4
0x4bb29  ldarg.s  5
0x4bb2b  ldarg.s  6
0x4bb2d  ldarg.s  7
0x4bb2f  ldarg.s  8
0x4bb31  ldarg.s  9
0x4bb33  ldarg.s  0xA
0x4bb35  ldarg.s  0xB
0x4bb37  ldarg.s  0xC
0x4bb39  ldarg.s  0xD
0x4bb3b  ldarg.s  0xE
0x4bb3d  ldarg.s  0xF
0x4bb3f  ldarg.s  0x10
0x4bb41  ldarg.s  0x11
0x4bb43  ldarg.s  0x12
0x4bb45  ldarg.s  0x13
0x4bb47  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::GetSubwebsFiltered(string, unsigned int64, unsigned int64, int32, int16, int32, object&, object&, object&, object&, object&, object&, object&, object&, object&, object&, object&, object&, object&)
0x4bb4c  leave    loc_4BEA6
0x4bb51  stloc.0
0x4bb52  ldstr    aGetsubwebsfilt// "GetSubwebsFiltered"
0x4bb57  ldarg.0
0x4bb58  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4bb5d  ldarg.0
0x4bb5e  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x4bb63  ldc.i4.6
0x4bb64  newarr   [mscorlib]System.String
0x4bb69  stloc.s  7
0x4bb6b  ldloc.s  7
0x4bb6d  ldc.i4.0
0x4bb6e  ldstr    aBstrparentwebu// "bstrParentWebUrl"
0x4bb73  stelem.ref
0x4bb74  ldloc.s  7
0x4bb76  ldc.i4.1
0x4bb77  ldstr    aIpermmaskforun// "iPermMaskForUnique"
0x4bb7c  stelem.ref
0x4bb7d  ldloc.s  7
0x4bb7f  ldc.i4.2
0x4bb80  ldstr    aIpermmaskforin// "iPermMaskForInherited"
0x4bb85  stelem.ref
0x4bb86  ldloc.s  7
0x4bb88  ldc.i4.3
0x4bb89  ldstr    aNwebtemplate// "nWebTemplate"
0x4bb8e  stelem.ref
0x4bb8f  ldloc.s  7
0x4bb91  ldc.i4.4
0x4bb92  ldstr    aNprovisionconf// "nProvisionConfig"
0x4bb97  stelem.ref
0x4bb98  ldloc.s  7
0x4bb9a  ldc.i4.5
0x4bb9b  ldstr    aLtolinkrecurri// "lToLinkRecurringMeeting"
0x4bba0  stelem.ref
0x4bba1  ldloc.s  7
0x4bba3  ldc.i4.6
0x4bba4  newarr   [mscorlib]System.Object
0x4bba9  stloc.s  8
0x4bbab  ldloc.s  8
0x4bbad  ldc.i4.0
0x4bbae  ldarg.1
0x4bbaf  stelem.ref
0x4bbb0  ldloc.s  8
0x4bbb2  ldc.i4.1
0x4bbb3  ldarg.2
0x4bbb4  box      [mscorlib]System.UInt64
0x4bbb9  stelem.ref
0x4bbba  ldloc.s  8
0x4bbbc  ldc.i4.2
0x4bbbd  ldarg.3
0x4bbbe  box      [mscorlib]System.UInt64
0x4bbc3  stelem.ref
0x4bbc4  ldloc.s  8
0x4bbc6  ldc.i4.3
0x4bbc7  ldarg.s  4
0x4bbc9  box      [mscorlib]System.Int32
0x4bbce  stelem.ref
0x4bbcf  ldloc.s  8
0x4bbd1  ldc.i4.4
0x4bbd2  ldarg.s  5
0x4bbd4  box      [mscorlib]System.Int16
0x4bbd9  stelem.ref
0x4bbda  ldloc.s  8
0x4bbdc  ldc.i4.5
0x4bbdd  ldarg.s  6
0x4bbdf  box      [mscorlib]System.Int32
0x4bbe4  stelem.ref
0x4bbe5  ldloc.s  8
0x4bbe7  ldloc.0
0x4bbe8  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x4bbed  ldloc.0
0x4bbee  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x4bbf3  rethrow
0x4bbf5  stloc.1
0x4bbf6  ldstr    aGetsubwebsfilt// "GetSubwebsFiltered"
0x4bbfb  ldarg.0
0x4bbfc  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4bc01  ldarg.0
0x4bc02  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x4bc07  ldc.i4.6
0x4bc08  newarr   [mscorlib]System.String
0x4bc0d  stloc.s  9
0x4bc0f  ldloc.s  9
0x4bc11  ldc.i4.0
0x4bc12  ldstr    aBstrparentwebu// "bstrParentWebUrl"
0x4bc17  stelem.ref
0x4bc18  ldloc.s  9
0x4bc1a  ldc.i4.1
0x4bc1b  ldstr    aIpermmaskforun// "iPermMaskForUnique"
0x4bc20  stelem.ref
0x4bc21  ldloc.s  9
0x4bc23  ldc.i4.2
0x4bc24  ldstr    aIpermmaskforin// "iPermMaskForInherited"
0x4bc29  stelem.ref
0x4bc2a  ldloc.s  9
0x4bc2c  ldc.i4.3
0x4bc2d  ldstr    aNwebtemplate// "nWebTemplate"
0x4bc32  stelem.ref
0x4bc33  ldloc.s  9
0x4bc35  ldc.i4.4
0x4bc36  ldstr    aNprovisionconf// "nProvisionConfig"
0x4bc3b  stelem.ref
0x4bc3c  ldloc.s  9
0x4bc3e  ldc.i4.5
0x4bc3f  ldstr    aLtolinkrecurri// "lToLinkRecurringMeeting"
0x4bc44  stelem.ref
0x4bc45  ldloc.s  9
0x4bc47  ldc.i4.6
0x4bc48  newarr   [mscorlib]System.Object
0x4bc4d  stloc.s  0xA
0x4bc4f  ldloc.s  0xA
0x4bc51  ldc.i4.0
0x4bc52  ldarg.1
0x4bc53  stelem.ref
0x4bc54  ldloc.s  0xA
0x4bc56  ldc.i4.1
0x4bc57  ldarg.2
0x4bc58  box      [mscorlib]System.UInt64
0x4bc5d  stelem.ref
0x4bc5e  ldloc.s  0xA
0x4bc60  ldc.i4.2
0x4bc61  ldarg.3
0x4bc62  box      [mscorlib]System.UInt64
0x4bc67  stelem.ref
0x4bc68  ldloc.s  0xA
0x4bc6a  ldc.i4.3
0x4bc6b  ldarg.s  4
0x4bc6d  box      [mscorlib]System.Int32
0x4bc72  stelem.ref
0x4bc73  ldloc.s  0xA
0x4bc75  ldc.i4.4
0x4bc76  ldarg.s  5
0x4bc78  box      [mscorlib]System.Int16
0x4bc7d  stelem.ref
0x4bc7e  ldloc.s  0xA
0x4bc80  ldc.i4.5
0x4bc81  ldarg.s  6
0x4bc83  box      [mscorlib]System.Int32
0x4bc88  stelem.ref
0x4bc89  ldloc.s  0xA
0x4bc8b  ldloc.1
0x4bc8c  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x4bc91  ldloc.1
0x4bc92  ldc.i4.0
0x4bc93  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x4bc98  rethrow
0x4bc9a  stloc.2
0x4bc9b  ldstr    aGetsubwebsfilt// "GetSubwebsFiltered"
0x4bca0  ldarg.0
0x4bca1  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4bca6  ldarg.0
0x4bca7  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x4bcac  ldc.i4.6
0x4bcad  newarr   [mscorlib]System.String
0x4bcb2  stloc.s  0xB
0x4bcb4  ldloc.s  0xB
0x4bcb6  ldc.i4.0
0x4bcb7  ldstr    aBstrparentwebu// "bstrParentWebUrl"
0x4bcbc  stelem.ref
0x4bcbd  ldloc.s  0xB
0x4bcbf  ldc.i4.1
0x4bcc0  ldstr    aIpermmaskforun// "iPermMaskForUnique"
0x4bcc5  stelem.ref
0x4bcc6  ldloc.s  0xB
0x4bcc8  ldc.i4.2
0x4bcc9  ldstr    aIpermmaskforin// "iPermMaskForInherited"
0x4bcce  stelem.ref
0x4bccf  ldloc.s  0xB
0x4bcd1  ldc.i4.3
0x4bcd2  ldstr    aNwebtemplate// "nWebTemplate"
0x4bcd7  stelem.ref
0x4bcd8  ldloc.s  0xB
0x4bcda  ldc.i4.4
0x4bcdb  ldstr    aNprovisionconf// "nProvisionConfig"
0x4bce0  stelem.ref
0x4bce1  ldloc.s  0xB
0x4bce3  ldc.i4.5
0x4bce4  ldstr    aLtolinkrecurri// "lToLinkRecurringMeeting"
0x4bce9  stelem.ref
0x4bcea  ldloc.s  0xB
0x4bcec  ldc.i4.6
0x4bced  newarr   [mscorlib]System.Object
0x4bcf2  stloc.s  0xC
0x4bcf4  ldloc.s  0xC
0x4bcf6  ldc.i4.0
0x4bcf7  ldarg.1
0x4bcf8  stelem.ref
0x4bcf9  ldloc.s  0xC
0x4bcfb  ldc.i4.1
0x4bcfc  ldarg.2
0x4bcfd  box      [mscorlib]System.UInt64
0x4bd02  stelem.ref
0x4bd03  ldloc.s  0xC
0x4bd05  ldc.i4.2
0x4bd06  ldarg.3
0x4bd07  box      [mscorlib]System.UInt64
0x4bd0c  stelem.ref
0x4bd0d  ldloc.s  0xC
0x4bd0f  ldc.i4.3
0x4bd10  ldarg.s  4
0x4bd12  box      [mscorlib]System.Int32
0x4bd17  stelem.ref
0x4bd18  ldloc.s  0xC
0x4bd1a  ldc.i4.4
0x4bd1b  ldarg.s  5
0x4bd1d  box      [mscorlib]System.Int16
0x4bd22  stelem.ref
0x4bd23  ldloc.s  0xC
0x4bd25  ldc.i4.5
0x4bd26  ldarg.s  6
0x4bd28  box      [mscorlib]System.Int32
0x4bd2d  stelem.ref
0x4bd2e  ldloc.s  0xC
0x4bd30  ldloc.2
0x4bd31  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x4bd36  ldloc.2
0x4bd37  ldarg.0
0x4bd38  ldfld    valuetype [mscorlib]System.Threading.ApartmentState Microsoft.SharePoint.Library.SPRequest::m_ApartmentState
0x4bd3d  ldarg.0
0x4bd3e  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_ManagedThreadId
0x4bd43  ldarg.0
0x4bd44  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedThreadId
0x4bd49  ldarg.0
0x4bd4a  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x4bd4f  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestInvalidCastException(class [mscorlib]System.InvalidCastException castEx, valuetype [mscorlib]System.Threading.ApartmentState apartmentState, int32 managedThreadId, int32 unmanagedThreadId, string constructorStackTrace)
0x4bd54  rethrow
0x4bd56  stloc.3
0x4bd57  ldstr    aGetsubwebsfilt// "GetSubwebsFiltered"
0x4bd5c  ldarg.0
0x4bd5d  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4bd62  ldarg.0
0x4bd63  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x4bd68  ldc.i4.6
0x4bd69  newarr   [mscorlib]System.String
0x4bd6e  stloc.s  0xD
0x4bd70  ldloc.s  0xD
0x4bd72  ldc.i4.0
0x4bd73  ldstr    aBstrparentwebu// "bstrParentWebUrl"
0x4bd78  stelem.ref
0x4bd79  ldloc.s  0xD
0x4bd7b  ldc.i4.1
0x4bd7c  ldstr    aIpermmaskforun// "iPermMaskForUnique"
0x4bd81  stelem.ref
0x4bd82  ldloc.s  0xD
0x4bd84  ldc.i4.2
0x4bd85  ldstr    aIpermmaskforin// "iPermMaskForInherited"
0x4bd8a  stelem.ref
0x4bd8b  ldloc.s  0xD
0x4bd8d  ldc.i4.3
0x4bd8e  ldstr    aNwebtemplate// "nWebTemplate"
  ... truncated ...
```
