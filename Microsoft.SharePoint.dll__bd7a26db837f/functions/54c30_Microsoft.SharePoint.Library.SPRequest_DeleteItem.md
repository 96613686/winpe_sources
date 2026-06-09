# Microsoft.SharePoint.Library.SPRequest::DeleteItem

- ea: `0x54c30`
- end: `0x54ff5`
- name: `Microsoft.SharePoint.Library.SPRequest::DeleteItem`
- size: `965`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x542530`

## callees

- `0x30b0`
- `0x54c30`
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

- `0x54cd1`: `dwDeleteOp`
- `0x54d70`: `dwDeleteOp`
- `0x54e10`: `dwDeleteOp`
- `0x54ec7`: `dwDeleteOp`
- `0x54f73`: `dwDeleteOp`
- `0x54cda`: `bUnRestrictedUpdateInProgress`
- `0x54d79`: `bUnRestrictedUpdateInProgress`
- `0x54e19`: `bUnRestrictedUpdateInProgress`
- `0x54ed0`: `bUnRestrictedUpdateInProgress`
- `0x54f7c`: `bUnRestrictedUpdateInProgress`
- `0x54c3c`: `SPRequest.DeleteItem`
- `0x54c9a`: `DeleteItem`
- `0x54d39`: `DeleteItem`
- `0x54dd9`: `DeleteItem`
- `0x54e90`: `DeleteItem`
- `0x54f3c`: `DeleteItem`
- `0x54ce3`: `bIgnoreCompliancePolicy`
- `0x54d82`: `bIgnoreCompliancePolicy`
- `0x54e22`: `bIgnoreCompliancePolicy`
- `0x54ed9`: `bIgnoreCompliancePolicy`
- `0x54f85`: `bIgnoreCompliancePolicy`

## pseudocode

```c

```

## disassembly

```asm
0x54c30  ldc.i4   0x66366C37
0x54c35  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x54c3a  ldc.i4.s 0x64
0x54c3c  ldstr    aSprequestDelet_17// "SPRequest.DeleteItem"
0x54c41  ldc.i4.1
0x54c42  ldc.i4.2
0x54c43  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x54c48  stloc.s  5
0x54c4a  ldloc.s  5
0x54c4c  ldc.i4.0
0x54c4d  ldc.i4   0x96
0x54c52  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x54c57  stelem.ref
0x54c58  ldloc.s  5
0x54c5a  ldc.i4.1
0x54c5b  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x54c60  stelem.ref
0x54c61  ldloc.s  5
0x54c63  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x54c68  stloc.s  6
0x54c6a  ldarg.0
0x54c6b  dup
0x54c6c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x54c71  ldc.i4.1
0x54c72  add
0x54c73  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x54c78  ldarg.0
0x54c79  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x54c7e  ldarg.0
0x54c7f  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x54c84  ldarg.1
0x54c85  ldarg.2
0x54c86  ldarg.3
0x54c87  ldarg.s  4
0x54c89  ldarg.s  5
0x54c8b  ldarg.s  6
0x54c8d  ldarg.s  7
0x54c8f  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::DeleteItem(string, string, int32, unsigned int32, bool, bool, valuetype [mscorlib]System.Guid&)
0x54c94  leave    loc_54FD5
0x54c99  stloc.0
0x54c9a  ldstr    aDeleteitem// "DeleteItem"
0x54c9f  ldarg.0
0x54ca0  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x54ca5  ldarg.0
0x54ca6  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x54cab  ldc.i4.6
0x54cac  newarr   [mscorlib]System.String
0x54cb1  stloc.s  7
0x54cb3  ldloc.s  7
0x54cb5  ldc.i4.0
0x54cb6  ldstr    aBstrurl// "bstrUrl"
0x54cbb  stelem.ref
0x54cbc  ldloc.s  7
0x54cbe  ldc.i4.1
0x54cbf  ldstr    aBstrlistname// "bstrListName"
0x54cc4  stelem.ref
0x54cc5  ldloc.s  7
0x54cc7  ldc.i4.2
0x54cc8  ldstr    aLid// "lID"
0x54ccd  stelem.ref
0x54cce  ldloc.s  7
0x54cd0  ldc.i4.3
0x54cd1  ldstr    aDwdeleteop// "dwDeleteOp"
0x54cd6  stelem.ref
0x54cd7  ldloc.s  7
0x54cd9  ldc.i4.4
0x54cda  ldstr    aBunrestrictedu// "bUnRestrictedUpdateInProgress"
0x54cdf  stelem.ref
0x54ce0  ldloc.s  7
0x54ce2  ldc.i4.5
0x54ce3  ldstr    aBignorecomplia// "bIgnoreCompliancePolicy"
0x54ce8  stelem.ref
0x54ce9  ldloc.s  7
0x54ceb  ldc.i4.6
0x54cec  newarr   [mscorlib]System.Object
0x54cf1  stloc.s  8
0x54cf3  ldloc.s  8
0x54cf5  ldc.i4.0
0x54cf6  ldarg.1
0x54cf7  stelem.ref
0x54cf8  ldloc.s  8
0x54cfa  ldc.i4.1
0x54cfb  ldarg.2
0x54cfc  stelem.ref
0x54cfd  ldloc.s  8
0x54cff  ldc.i4.2
0x54d00  ldarg.3
0x54d01  box      [mscorlib]System.Int32
0x54d06  stelem.ref
0x54d07  ldloc.s  8
0x54d09  ldc.i4.3
0x54d0a  ldarg.s  4
0x54d0c  box      [mscorlib]System.UInt32
0x54d11  stelem.ref
0x54d12  ldloc.s  8
0x54d14  ldc.i4.4
0x54d15  ldarg.s  5
0x54d17  box      [mscorlib]System.Boolean
0x54d1c  stelem.ref
0x54d1d  ldloc.s  8
0x54d1f  ldc.i4.5
0x54d20  ldarg.s  6
0x54d22  box      [mscorlib]System.Boolean
0x54d27  stelem.ref
0x54d28  ldloc.s  8
0x54d2a  ldloc.0
0x54d2b  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x54d30  ldloc.0
0x54d31  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x54d36  rethrow
0x54d38  stloc.1
0x54d39  ldstr    aDeleteitem// "DeleteItem"
0x54d3e  ldarg.0
0x54d3f  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x54d44  ldarg.0
0x54d45  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x54d4a  ldc.i4.6
0x54d4b  newarr   [mscorlib]System.String
0x54d50  stloc.s  9
0x54d52  ldloc.s  9
0x54d54  ldc.i4.0
0x54d55  ldstr    aBstrurl// "bstrUrl"
0x54d5a  stelem.ref
0x54d5b  ldloc.s  9
0x54d5d  ldc.i4.1
0x54d5e  ldstr    aBstrlistname// "bstrListName"
0x54d63  stelem.ref
0x54d64  ldloc.s  9
0x54d66  ldc.i4.2
0x54d67  ldstr    aLid// "lID"
0x54d6c  stelem.ref
0x54d6d  ldloc.s  9
0x54d6f  ldc.i4.3
0x54d70  ldstr    aDwdeleteop// "dwDeleteOp"
0x54d75  stelem.ref
0x54d76  ldloc.s  9
0x54d78  ldc.i4.4
0x54d79  ldstr    aBunrestrictedu// "bUnRestrictedUpdateInProgress"
0x54d7e  stelem.ref
0x54d7f  ldloc.s  9
0x54d81  ldc.i4.5
0x54d82  ldstr    aBignorecomplia// "bIgnoreCompliancePolicy"
0x54d87  stelem.ref
0x54d88  ldloc.s  9
0x54d8a  ldc.i4.6
0x54d8b  newarr   [mscorlib]System.Object
0x54d90  stloc.s  0xA
0x54d92  ldloc.s  0xA
0x54d94  ldc.i4.0
0x54d95  ldarg.1
0x54d96  stelem.ref
0x54d97  ldloc.s  0xA
0x54d99  ldc.i4.1
0x54d9a  ldarg.2
0x54d9b  stelem.ref
0x54d9c  ldloc.s  0xA
0x54d9e  ldc.i4.2
0x54d9f  ldarg.3
0x54da0  box      [mscorlib]System.Int32
0x54da5  stelem.ref
0x54da6  ldloc.s  0xA
0x54da8  ldc.i4.3
0x54da9  ldarg.s  4
0x54dab  box      [mscorlib]System.UInt32
0x54db0  stelem.ref
0x54db1  ldloc.s  0xA
0x54db3  ldc.i4.4
0x54db4  ldarg.s  5
0x54db6  box      [mscorlib]System.Boolean
0x54dbb  stelem.ref
0x54dbc  ldloc.s  0xA
0x54dbe  ldc.i4.5
0x54dbf  ldarg.s  6
0x54dc1  box      [mscorlib]System.Boolean
0x54dc6  stelem.ref
0x54dc7  ldloc.s  0xA
0x54dc9  ldloc.1
0x54dca  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x54dcf  ldloc.1
0x54dd0  ldc.i4.0
0x54dd1  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x54dd6  rethrow
0x54dd8  stloc.2
0x54dd9  ldstr    aDeleteitem// "DeleteItem"
0x54dde  ldarg.0
0x54ddf  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x54de4  ldarg.0
0x54de5  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x54dea  ldc.i4.6
0x54deb  newarr   [mscorlib]System.String
0x54df0  stloc.s  0xB
0x54df2  ldloc.s  0xB
0x54df4  ldc.i4.0
0x54df5  ldstr    aBstrurl// "bstrUrl"
0x54dfa  stelem.ref
0x54dfb  ldloc.s  0xB
0x54dfd  ldc.i4.1
0x54dfe  ldstr    aBstrlistname// "bstrListName"
0x54e03  stelem.ref
0x54e04  ldloc.s  0xB
0x54e06  ldc.i4.2
0x54e07  ldstr    aLid// "lID"
0x54e0c  stelem.ref
0x54e0d  ldloc.s  0xB
0x54e0f  ldc.i4.3
0x54e10  ldstr    aDwdeleteop// "dwDeleteOp"
0x54e15  stelem.ref
0x54e16  ldloc.s  0xB
0x54e18  ldc.i4.4
0x54e19  ldstr    aBunrestrictedu// "bUnRestrictedUpdateInProgress"
0x54e1e  stelem.ref
0x54e1f  ldloc.s  0xB
0x54e21  ldc.i4.5
0x54e22  ldstr    aBignorecomplia// "bIgnoreCompliancePolicy"
0x54e27  stelem.ref
0x54e28  ldloc.s  0xB
0x54e2a  ldc.i4.6
0x54e2b  newarr   [mscorlib]System.Object
0x54e30  stloc.s  0xC
0x54e32  ldloc.s  0xC
0x54e34  ldc.i4.0
0x54e35  ldarg.1
0x54e36  stelem.ref
0x54e37  ldloc.s  0xC
0x54e39  ldc.i4.1
0x54e3a  ldarg.2
0x54e3b  stelem.ref
0x54e3c  ldloc.s  0xC
0x54e3e  ldc.i4.2
0x54e3f  ldarg.3
0x54e40  box      [mscorlib]System.Int32
0x54e45  stelem.ref
0x54e46  ldloc.s  0xC
0x54e48  ldc.i4.3
0x54e49  ldarg.s  4
0x54e4b  box      [mscorlib]System.UInt32
0x54e50  stelem.ref
0x54e51  ldloc.s  0xC
0x54e53  ldc.i4.4
0x54e54  ldarg.s  5
0x54e56  box      [mscorlib]System.Boolean
0x54e5b  stelem.ref
0x54e5c  ldloc.s  0xC
0x54e5e  ldc.i4.5
0x54e5f  ldarg.s  6
0x54e61  box      [mscorlib]System.Boolean
0x54e66  stelem.ref
0x54e67  ldloc.s  0xC
0x54e69  ldloc.2
0x54e6a  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x54e6f  ldloc.2
0x54e70  ldarg.0
0x54e71  ldfld    valuetype [mscorlib]System.Threading.ApartmentState Microsoft.SharePoint.Library.SPRequest::m_ApartmentState
0x54e76  ldarg.0
0x54e77  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_ManagedThreadId
0x54e7c  ldarg.0
0x54e7d  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedThreadId
0x54e82  ldarg.0
0x54e83  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x54e88  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestInvalidCastException(class [mscorlib]System.InvalidCastException castEx, valuetype [mscorlib]System.Threading.ApartmentState apartmentState, int32 managedThreadId, int32 unmanagedThreadId, string constructorStackTrace)
0x54e8d  rethrow
0x54e8f  stloc.3
0x54e90  ldstr    aDeleteitem// "DeleteItem"
0x54e95  ldarg.0
0x54e96  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x54e9b  ldarg.0
0x54e9c  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x54ea1  ldc.i4.6
0x54ea2  newarr   [mscorlib]System.String
0x54ea7  stloc.s  0xD
0x54ea9  ldloc.s  0xD
0x54eab  ldc.i4.0
0x54eac  ldstr    aBstrurl// "bstrUrl"
0x54eb1  stelem.ref
0x54eb2  ldloc.s  0xD
0x54eb4  ldc.i4.1
0x54eb5  ldstr    aBstrlistname// "bstrListName"
0x54eba  stelem.ref
0x54ebb  ldloc.s  0xD
0x54ebd  ldc.i4.2
0x54ebe  ldstr    aLid// "lID"
0x54ec3  stelem.ref
0x54ec4  ldloc.s  0xD
0x54ec6  ldc.i4.3
0x54ec7  ldstr    aDwdeleteop// "dwDeleteOp"
0x54ecc  stelem.ref
0x54ecd  ldloc.s  0xD
0x54ecf  ldc.i4.4
0x54ed0  ldstr    aBunrestrictedu// "bUnRestrictedUpdateInProgress"
0x54ed5  stelem.ref
0x54ed6  ldloc.s  0xD
0x54ed8  ldc.i4.5
0x54ed9  ldstr    aBignorecomplia// "bIgnoreCompliancePolicy"
0x54ede  stelem.ref
0x54edf  ldloc.s  0xD
0x54ee1  ldc.i4.6
0x54ee2  newarr   [mscorlib]System.Object
0x54ee7  stloc.s  0xE
0x54ee9  ldloc.s  0xE
0x54eeb  ldc.i4.0
  ... truncated ...
```
