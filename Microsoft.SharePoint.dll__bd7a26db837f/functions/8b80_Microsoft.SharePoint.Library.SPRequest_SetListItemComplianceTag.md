# Microsoft.SharePoint.Library.SPRequest::SetListItemComplianceTag

- ea: `0x8b80`
- end: `0x919d`
- name: `Microsoft.SharePoint.Library.SPRequest::SetListItemComplianceTag`
- size: `1565`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x35b840`
- `0x53c770`

## callees

- `0x30b0`
- `0x8b80`
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

- `0x8b8c`: `SPRequest.SetListItemComplianceTag`
- `0x8bf4`: `SetListItemComplianceTag`
- `0x8d09`: `SetListItemComplianceTag`
- `0x8e1f`: `SetListItemComplianceTag`
- `0x8f4c`: `SetListItemComplianceTag`
- `0x906e`: `SetListItemComplianceTag`
- `0x8c2c`: `bstrComplianceTag`
- `0x8d41`: `bstrComplianceTag`
- `0x8e57`: `bstrComplianceTag`
- `0x8f84`: `bstrComplianceTag`
- `0x90a6`: `bstrComplianceTag`
- `0x8c35`: `iComplianceFlags`
- `0x8d4a`: `iComplianceFlags`
- `0x8e60`: `iComplianceFlags`
- `0x8f8d`: `iComplianceFlags`
- `0x90af`: `iComplianceFlags`
- `0x8c3e`: `iComplianceTagUserid`
- `0x8d53`: `iComplianceTagUserid`
- `0x8e69`: `iComplianceTagUserid`
- `0x8f96`: `iComplianceTagUserid`
- `0x90b8`: `iComplianceTagUserid`
- `0x8c47`: `varComplianceTagWrittenTime`
- `0x8d5c`: `varComplianceTagWrittenTime`
- `0x8e72`: `varComplianceTagWrittenTime`
- `0x8f9f`: `varComplianceTagWrittenTime`
- `0x90c1`: `varComplianceTagWrittenTime`
- `0x8c50`: `iComplianceFlagsToReset`
- `0x8d65`: `iComplianceFlagsToReset`
- `0x8e7b`: `iComplianceFlagsToReset`
- `0x8fa8`: `iComplianceFlagsToReset`
- `0x90ca`: `iComplianceFlagsToReset`
- `0x8c59`: `bKeepOldComplianceTag`
- `0x8d6e`: `bKeepOldComplianceTag`
- `0x8e84`: `bKeepOldComplianceTag`
- `0x8fb1`: `bKeepOldComplianceTag`
- `0x90d3`: `bKeepOldComplianceTag`

## pseudocode

```c

```

## disassembly

```asm
0x8b80  ldc.i4   0x66366C37
0x8b85  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x8b8a  ldc.i4.s 0x64
0x8b8c  ldstr    aSprequestSetli_0// "SPRequest.SetListItemComplianceTag"
0x8b91  ldc.i4.1
0x8b92  ldc.i4.2
0x8b93  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x8b98  stloc.s  5
0x8b9a  ldloc.s  5
0x8b9c  ldc.i4.0
0x8b9d  ldc.i4   0x96
0x8ba2  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x8ba7  stelem.ref
0x8ba8  ldloc.s  5
0x8baa  ldc.i4.1
0x8bab  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x8bb0  stelem.ref
0x8bb1  ldloc.s  5
0x8bb3  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x8bb8  stloc.s  6
0x8bba  ldarg.0
0x8bbb  dup
0x8bbc  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x8bc1  ldc.i4.1
0x8bc2  add
0x8bc3  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x8bc8  ldarg.0
0x8bc9  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x8bce  ldarg.0
0x8bcf  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x8bd4  ldarg.1
0x8bd5  ldarg.2
0x8bd6  ldarg.3
0x8bd7  ldarg.s  4
0x8bd9  ldarg.s  5
0x8bdb  ldarg.s  6
0x8bdd  ldarg.s  7
0x8bdf  ldarg.s  8
0x8be1  ldarg.s  9
0x8be3  ldarg.s  0xA
0x8be5  ldarg.s  0xB
0x8be7  ldarg.s  0xC
0x8be9  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::SetListItemComplianceTag(string, string, int32, string, int32, int32, object, int32, bool, bool, bool, bool)
0x8bee  leave    loc_917D
0x8bf3  stloc.0
0x8bf4  ldstr    aSetlistitemcom// "SetListItemComplianceTag"
0x8bf9  ldarg.0
0x8bfa  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x8bff  ldarg.0
0x8c00  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x8c05  ldc.i4.s 0xC
0x8c07  newarr   [mscorlib]System.String
0x8c0c  stloc.s  7
0x8c0e  ldloc.s  7
0x8c10  ldc.i4.0
0x8c11  ldstr    aBstrurl// "bstrUrl"
0x8c16  stelem.ref
0x8c17  ldloc.s  7
0x8c19  ldc.i4.1
0x8c1a  ldstr    aBstrlistname// "bstrListName"
0x8c1f  stelem.ref
0x8c20  ldloc.s  7
0x8c22  ldc.i4.2
0x8c23  ldstr    aLid// "lID"
0x8c28  stelem.ref
0x8c29  ldloc.s  7
0x8c2b  ldc.i4.3
0x8c2c  ldstr    aBstrcompliance// "bstrComplianceTag"
0x8c31  stelem.ref
0x8c32  ldloc.s  7
0x8c34  ldc.i4.4
0x8c35  ldstr    aIcompliancefla// "iComplianceFlags"
0x8c3a  stelem.ref
0x8c3b  ldloc.s  7
0x8c3d  ldc.i4.5
0x8c3e  ldstr    aIcompliancetag// "iComplianceTagUserid"
0x8c43  stelem.ref
0x8c44  ldloc.s  7
0x8c46  ldc.i4.6
0x8c47  ldstr    aVarcompliancet// "varComplianceTagWrittenTime"
0x8c4c  stelem.ref
0x8c4d  ldloc.s  7
0x8c4f  ldc.i4.7
0x8c50  ldstr    aIcompliancefla_0// "iComplianceFlagsToReset"
0x8c55  stelem.ref
0x8c56  ldloc.s  7
0x8c58  ldc.i4.8
0x8c59  ldstr    aBkeepoldcompli// "bKeepOldComplianceTag"
0x8c5e  stelem.ref
0x8c5f  ldloc.s  7
0x8c61  ldc.i4.s 9
0x8c63  ldstr    aBsynctochildre// "bSynctoChildren"
0x8c68  stelem.ref
0x8c69  ldloc.s  7
0x8c6b  ldc.i4.s 0xA
0x8c6d  ldstr    aBallowtogglere// "bAllowToggleRecordLabel"
0x8c72  stelem.ref
0x8c73  ldloc.s  7
0x8c75  ldc.i4.s 0xB
0x8c77  ldstr    aBtogglerecordp// "bToggleRecordPermissionChecked"
0x8c7c  stelem.ref
0x8c7d  ldloc.s  7
0x8c7f  ldc.i4.s 0xC
0x8c81  newarr   [mscorlib]System.Object
0x8c86  stloc.s  8
0x8c88  ldloc.s  8
0x8c8a  ldc.i4.0
0x8c8b  ldarg.1
0x8c8c  stelem.ref
0x8c8d  ldloc.s  8
0x8c8f  ldc.i4.1
0x8c90  ldarg.2
0x8c91  stelem.ref
0x8c92  ldloc.s  8
0x8c94  ldc.i4.2
0x8c95  ldarg.3
0x8c96  box      [mscorlib]System.Int32
0x8c9b  stelem.ref
0x8c9c  ldloc.s  8
0x8c9e  ldc.i4.3
0x8c9f  ldarg.s  4
0x8ca1  stelem.ref
0x8ca2  ldloc.s  8
0x8ca4  ldc.i4.4
0x8ca5  ldarg.s  5
0x8ca7  box      [mscorlib]System.Int32
0x8cac  stelem.ref
0x8cad  ldloc.s  8
0x8caf  ldc.i4.5
0x8cb0  ldarg.s  6
0x8cb2  box      [mscorlib]System.Int32
0x8cb7  stelem.ref
0x8cb8  ldloc.s  8
0x8cba  ldc.i4.6
0x8cbb  ldarg.s  7
0x8cbd  stelem.ref
0x8cbe  ldloc.s  8
0x8cc0  ldc.i4.7
0x8cc1  ldarg.s  8
0x8cc3  box      [mscorlib]System.Int32
0x8cc8  stelem.ref
0x8cc9  ldloc.s  8
0x8ccb  ldc.i4.8
0x8ccc  ldarg.s  9
0x8cce  box      [mscorlib]System.Boolean
0x8cd3  stelem.ref
0x8cd4  ldloc.s  8
0x8cd6  ldc.i4.s 9
0x8cd8  ldarg.s  0xA
0x8cda  box      [mscorlib]System.Boolean
0x8cdf  stelem.ref
0x8ce0  ldloc.s  8
0x8ce2  ldc.i4.s 0xA
0x8ce4  ldarg.s  0xB
0x8ce6  box      [mscorlib]System.Boolean
0x8ceb  stelem.ref
0x8cec  ldloc.s  8
0x8cee  ldc.i4.s 0xB
0x8cf0  ldarg.s  0xC
0x8cf2  box      [mscorlib]System.Boolean
0x8cf7  stelem.ref
0x8cf8  ldloc.s  8
0x8cfa  ldloc.0
0x8cfb  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x8d00  ldloc.0
0x8d01  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x8d06  rethrow
0x8d08  stloc.1
0x8d09  ldstr    aSetlistitemcom// "SetListItemComplianceTag"
0x8d0e  ldarg.0
0x8d0f  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x8d14  ldarg.0
0x8d15  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x8d1a  ldc.i4.s 0xC
0x8d1c  newarr   [mscorlib]System.String
0x8d21  stloc.s  9
0x8d23  ldloc.s  9
0x8d25  ldc.i4.0
0x8d26  ldstr    aBstrurl// "bstrUrl"
0x8d2b  stelem.ref
0x8d2c  ldloc.s  9
0x8d2e  ldc.i4.1
0x8d2f  ldstr    aBstrlistname// "bstrListName"
0x8d34  stelem.ref
0x8d35  ldloc.s  9
0x8d37  ldc.i4.2
0x8d38  ldstr    aLid// "lID"
0x8d3d  stelem.ref
0x8d3e  ldloc.s  9
0x8d40  ldc.i4.3
0x8d41  ldstr    aBstrcompliance// "bstrComplianceTag"
0x8d46  stelem.ref
0x8d47  ldloc.s  9
0x8d49  ldc.i4.4
0x8d4a  ldstr    aIcompliancefla// "iComplianceFlags"
0x8d4f  stelem.ref
0x8d50  ldloc.s  9
0x8d52  ldc.i4.5
0x8d53  ldstr    aIcompliancetag// "iComplianceTagUserid"
0x8d58  stelem.ref
0x8d59  ldloc.s  9
0x8d5b  ldc.i4.6
0x8d5c  ldstr    aVarcompliancet// "varComplianceTagWrittenTime"
0x8d61  stelem.ref
0x8d62  ldloc.s  9
0x8d64  ldc.i4.7
0x8d65  ldstr    aIcompliancefla_0// "iComplianceFlagsToReset"
0x8d6a  stelem.ref
0x8d6b  ldloc.s  9
0x8d6d  ldc.i4.8
0x8d6e  ldstr    aBkeepoldcompli// "bKeepOldComplianceTag"
0x8d73  stelem.ref
0x8d74  ldloc.s  9
0x8d76  ldc.i4.s 9
0x8d78  ldstr    aBsynctochildre// "bSynctoChildren"
0x8d7d  stelem.ref
0x8d7e  ldloc.s  9
0x8d80  ldc.i4.s 0xA
0x8d82  ldstr    aBallowtogglere// "bAllowToggleRecordLabel"
0x8d87  stelem.ref
0x8d88  ldloc.s  9
0x8d8a  ldc.i4.s 0xB
0x8d8c  ldstr    aBtogglerecordp// "bToggleRecordPermissionChecked"
0x8d91  stelem.ref
0x8d92  ldloc.s  9
0x8d94  ldc.i4.s 0xC
0x8d96  newarr   [mscorlib]System.Object
0x8d9b  stloc.s  0xA
0x8d9d  ldloc.s  0xA
0x8d9f  ldc.i4.0
0x8da0  ldarg.1
0x8da1  stelem.ref
0x8da2  ldloc.s  0xA
0x8da4  ldc.i4.1
0x8da5  ldarg.2
0x8da6  stelem.ref
0x8da7  ldloc.s  0xA
0x8da9  ldc.i4.2
0x8daa  ldarg.3
0x8dab  box      [mscorlib]System.Int32
0x8db0  stelem.ref
0x8db1  ldloc.s  0xA
0x8db3  ldc.i4.3
0x8db4  ldarg.s  4
0x8db6  stelem.ref
0x8db7  ldloc.s  0xA
0x8db9  ldc.i4.4
0x8dba  ldarg.s  5
0x8dbc  box      [mscorlib]System.Int32
0x8dc1  stelem.ref
0x8dc2  ldloc.s  0xA
0x8dc4  ldc.i4.5
0x8dc5  ldarg.s  6
0x8dc7  box      [mscorlib]System.Int32
0x8dcc  stelem.ref
0x8dcd  ldloc.s  0xA
0x8dcf  ldc.i4.6
0x8dd0  ldarg.s  7
0x8dd2  stelem.ref
0x8dd3  ldloc.s  0xA
0x8dd5  ldc.i4.7
0x8dd6  ldarg.s  8
0x8dd8  box      [mscorlib]System.Int32
0x8ddd  stelem.ref
0x8dde  ldloc.s  0xA
0x8de0  ldc.i4.8
0x8de1  ldarg.s  9
0x8de3  box      [mscorlib]System.Boolean
0x8de8  stelem.ref
0x8de9  ldloc.s  0xA
0x8deb  ldc.i4.s 9
0x8ded  ldarg.s  0xA
0x8def  box      [mscorlib]System.Boolean
0x8df4  stelem.ref
0x8df5  ldloc.s  0xA
0x8df7  ldc.i4.s 0xA
0x8df9  ldarg.s  0xB
0x8dfb  box      [mscorlib]System.Boolean
0x8e00  stelem.ref
0x8e01  ldloc.s  0xA
0x8e03  ldc.i4.s 0xB
0x8e05  ldarg.s  0xC
0x8e07  box      [mscorlib]System.Boolean
0x8e0c  stelem.ref
0x8e0d  ldloc.s  0xA
0x8e0f  ldloc.1
0x8e10  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x8e15  ldloc.1
0x8e16  ldc.i4.0
0x8e17  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x8e1c  rethrow
0x8e1e  stloc.2
0x8e1f  ldstr    aSetlistitemcom// "SetListItemComplianceTag"
0x8e24  ldarg.0
0x8e25  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x8e2a  ldarg.0
0x8e2b  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x8e30  ldc.i4.s 0xC
0x8e32  newarr   [mscorlib]System.String
0x8e37  stloc.s  0xB
  ... truncated ...
```
