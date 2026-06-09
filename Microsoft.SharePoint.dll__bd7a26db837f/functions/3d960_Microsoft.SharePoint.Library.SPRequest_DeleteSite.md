# Microsoft.SharePoint.Library.SPRequest::DeleteSite

- ea: `0x3d960`
- end: `0x3dd3c`
- name: `Microsoft.SharePoint.Library.SPRequest::DeleteSite`
- size: `988`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x26f2a0`

## callees

- `0x30b0`
- `0x3d960`
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

- `0x3d96c`: `SPRequest.DeleteSite`
- `0x3d9c8`: `DeleteSite`
- `0x3da6c`: `DeleteSite`
- `0x3db11`: `DeleteSite`
- `0x3dbcd`: `DeleteSite`
- `0x3dc7e`: `DeleteSite`
- `0x3d9ed`: `bDeleteADAccounts`
- `0x3da91`: `bDeleteADAccounts`
- `0x3db36`: `bDeleteADAccounts`
- `0x3dbf2`: `bDeleteADAccounts`
- `0x3dca3`: `bDeleteADAccounts`
- `0x3d9f6`: `bGradualDelete`
- `0x3da9a`: `bGradualDelete`
- `0x3db3f`: `bGradualDelete`
- `0x3dbfb`: `bGradualDelete`
- `0x3dcac`: `bGradualDelete`
- `0x3da08`: `bDeleteIsForMigration`
- `0x3daac`: `bDeleteIsForMigration`
- `0x3db51`: `bDeleteIsForMigration`
- `0x3dc0d`: `bDeleteIsForMigration`
- `0x3dcbe`: `bDeleteIsForMigration`
- `0x3da11`: `bCheckComplianceFlags`
- `0x3dab5`: `bCheckComplianceFlags`
- `0x3db5a`: `bCheckComplianceFlags`
- `0x3dc16`: `bCheckComplianceFlags`
- `0x3dcc7`: `bCheckComplianceFlags`

## pseudocode

```c

```

## disassembly

```asm
0x3d960  ldc.i4   0x66366C37
0x3d965  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x3d96a  ldc.i4.s 0x64
0x3d96c  ldstr    aSprequestDelet_10// "SPRequest.DeleteSite"
0x3d971  ldc.i4.1
0x3d972  ldc.i4.2
0x3d973  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x3d978  stloc.s  5
0x3d97a  ldloc.s  5
0x3d97c  ldc.i4.0
0x3d97d  ldc.i4   0x96
0x3d982  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x3d987  stelem.ref
0x3d988  ldloc.s  5
0x3d98a  ldc.i4.1
0x3d98b  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x3d990  stelem.ref
0x3d991  ldloc.s  5
0x3d993  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x3d998  stloc.s  6
0x3d99a  ldarg.0
0x3d99b  dup
0x3d99c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x3d9a1  ldc.i4.1
0x3d9a2  add
0x3d9a3  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x3d9a8  ldarg.0
0x3d9a9  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x3d9ae  ldarg.0
0x3d9af  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x3d9b4  ldarg.1
0x3d9b5  ldarg.2
0x3d9b6  ldarg.3
0x3d9b7  ldarg.s  4
0x3d9b9  ldarg.s  5
0x3d9bb  ldarg.s  6
0x3d9bd  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::DeleteSite(string, bool, bool, bool, bool, bool)
0x3d9c2  leave    loc_3DD1C
0x3d9c7  stloc.0
0x3d9c8  ldstr    aDeletesite// "DeleteSite"
0x3d9cd  ldarg.0
0x3d9ce  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x3d9d3  ldarg.0
0x3d9d4  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x3d9d9  ldc.i4.6
0x3d9da  newarr   [mscorlib]System.String
0x3d9df  stloc.s  7
0x3d9e1  ldloc.s  7
0x3d9e3  ldc.i4.0
0x3d9e4  ldstr    aBstrurl// "bstrUrl"
0x3d9e9  stelem.ref
0x3d9ea  ldloc.s  7
0x3d9ec  ldc.i4.1
0x3d9ed  ldstr    aBdeleteadaccou// "bDeleteADAccounts"
0x3d9f2  stelem.ref
0x3d9f3  ldloc.s  7
0x3d9f5  ldc.i4.2
0x3d9f6  ldstr    aBgradualdelete// "bGradualDelete"
0x3d9fb  stelem.ref
0x3d9fc  ldloc.s  7
0x3d9fe  ldc.i4.3
0x3d9ff  ldstr    aBsiterecyclebi// "bSiteRecycleBinEnabled"
0x3da04  stelem.ref
0x3da05  ldloc.s  7
0x3da07  ldc.i4.4
0x3da08  ldstr    aBdeleteisformi// "bDeleteIsForMigration"
0x3da0d  stelem.ref
0x3da0e  ldloc.s  7
0x3da10  ldc.i4.5
0x3da11  ldstr    aBcheckcomplian// "bCheckComplianceFlags"
0x3da16  stelem.ref
0x3da17  ldloc.s  7
0x3da19  ldc.i4.6
0x3da1a  newarr   [mscorlib]System.Object
0x3da1f  stloc.s  8
0x3da21  ldloc.s  8
0x3da23  ldc.i4.0
0x3da24  ldarg.1
0x3da25  stelem.ref
0x3da26  ldloc.s  8
0x3da28  ldc.i4.1
0x3da29  ldarg.2
0x3da2a  box      [mscorlib]System.Boolean
0x3da2f  stelem.ref
0x3da30  ldloc.s  8
0x3da32  ldc.i4.2
0x3da33  ldarg.3
0x3da34  box      [mscorlib]System.Boolean
0x3da39  stelem.ref
0x3da3a  ldloc.s  8
0x3da3c  ldc.i4.3
0x3da3d  ldarg.s  4
0x3da3f  box      [mscorlib]System.Boolean
0x3da44  stelem.ref
0x3da45  ldloc.s  8
0x3da47  ldc.i4.4
0x3da48  ldarg.s  5
0x3da4a  box      [mscorlib]System.Boolean
0x3da4f  stelem.ref
0x3da50  ldloc.s  8
0x3da52  ldc.i4.5
0x3da53  ldarg.s  6
0x3da55  box      [mscorlib]System.Boolean
0x3da5a  stelem.ref
0x3da5b  ldloc.s  8
0x3da5d  ldloc.0
0x3da5e  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x3da63  ldloc.0
0x3da64  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x3da69  rethrow
0x3da6b  stloc.1
0x3da6c  ldstr    aDeletesite// "DeleteSite"
0x3da71  ldarg.0
0x3da72  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x3da77  ldarg.0
0x3da78  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x3da7d  ldc.i4.6
0x3da7e  newarr   [mscorlib]System.String
0x3da83  stloc.s  9
0x3da85  ldloc.s  9
0x3da87  ldc.i4.0
0x3da88  ldstr    aBstrurl// "bstrUrl"
0x3da8d  stelem.ref
0x3da8e  ldloc.s  9
0x3da90  ldc.i4.1
0x3da91  ldstr    aBdeleteadaccou// "bDeleteADAccounts"
0x3da96  stelem.ref
0x3da97  ldloc.s  9
0x3da99  ldc.i4.2
0x3da9a  ldstr    aBgradualdelete// "bGradualDelete"
0x3da9f  stelem.ref
0x3daa0  ldloc.s  9
0x3daa2  ldc.i4.3
0x3daa3  ldstr    aBsiterecyclebi// "bSiteRecycleBinEnabled"
0x3daa8  stelem.ref
0x3daa9  ldloc.s  9
0x3daab  ldc.i4.4
0x3daac  ldstr    aBdeleteisformi// "bDeleteIsForMigration"
0x3dab1  stelem.ref
0x3dab2  ldloc.s  9
0x3dab4  ldc.i4.5
0x3dab5  ldstr    aBcheckcomplian// "bCheckComplianceFlags"
0x3daba  stelem.ref
0x3dabb  ldloc.s  9
0x3dabd  ldc.i4.6
0x3dabe  newarr   [mscorlib]System.Object
0x3dac3  stloc.s  0xA
0x3dac5  ldloc.s  0xA
0x3dac7  ldc.i4.0
0x3dac8  ldarg.1
0x3dac9  stelem.ref
0x3daca  ldloc.s  0xA
0x3dacc  ldc.i4.1
0x3dacd  ldarg.2
0x3dace  box      [mscorlib]System.Boolean
0x3dad3  stelem.ref
0x3dad4  ldloc.s  0xA
0x3dad6  ldc.i4.2
0x3dad7  ldarg.3
0x3dad8  box      [mscorlib]System.Boolean
0x3dadd  stelem.ref
0x3dade  ldloc.s  0xA
0x3dae0  ldc.i4.3
0x3dae1  ldarg.s  4
0x3dae3  box      [mscorlib]System.Boolean
0x3dae8  stelem.ref
0x3dae9  ldloc.s  0xA
0x3daeb  ldc.i4.4
0x3daec  ldarg.s  5
0x3daee  box      [mscorlib]System.Boolean
0x3daf3  stelem.ref
0x3daf4  ldloc.s  0xA
0x3daf6  ldc.i4.5
0x3daf7  ldarg.s  6
0x3daf9  box      [mscorlib]System.Boolean
0x3dafe  stelem.ref
0x3daff  ldloc.s  0xA
0x3db01  ldloc.1
0x3db02  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x3db07  ldloc.1
0x3db08  ldc.i4.0
0x3db09  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x3db0e  rethrow
0x3db10  stloc.2
0x3db11  ldstr    aDeletesite// "DeleteSite"
0x3db16  ldarg.0
0x3db17  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x3db1c  ldarg.0
0x3db1d  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x3db22  ldc.i4.6
0x3db23  newarr   [mscorlib]System.String
0x3db28  stloc.s  0xB
0x3db2a  ldloc.s  0xB
0x3db2c  ldc.i4.0
0x3db2d  ldstr    aBstrurl// "bstrUrl"
0x3db32  stelem.ref
0x3db33  ldloc.s  0xB
0x3db35  ldc.i4.1
0x3db36  ldstr    aBdeleteadaccou// "bDeleteADAccounts"
0x3db3b  stelem.ref
0x3db3c  ldloc.s  0xB
0x3db3e  ldc.i4.2
0x3db3f  ldstr    aBgradualdelete// "bGradualDelete"
0x3db44  stelem.ref
0x3db45  ldloc.s  0xB
0x3db47  ldc.i4.3
0x3db48  ldstr    aBsiterecyclebi// "bSiteRecycleBinEnabled"
0x3db4d  stelem.ref
0x3db4e  ldloc.s  0xB
0x3db50  ldc.i4.4
0x3db51  ldstr    aBdeleteisformi// "bDeleteIsForMigration"
0x3db56  stelem.ref
0x3db57  ldloc.s  0xB
0x3db59  ldc.i4.5
0x3db5a  ldstr    aBcheckcomplian// "bCheckComplianceFlags"
0x3db5f  stelem.ref
0x3db60  ldloc.s  0xB
0x3db62  ldc.i4.6
0x3db63  newarr   [mscorlib]System.Object
0x3db68  stloc.s  0xC
0x3db6a  ldloc.s  0xC
0x3db6c  ldc.i4.0
0x3db6d  ldarg.1
0x3db6e  stelem.ref
0x3db6f  ldloc.s  0xC
0x3db71  ldc.i4.1
0x3db72  ldarg.2
0x3db73  box      [mscorlib]System.Boolean
0x3db78  stelem.ref
0x3db79  ldloc.s  0xC
0x3db7b  ldc.i4.2
0x3db7c  ldarg.3
0x3db7d  box      [mscorlib]System.Boolean
0x3db82  stelem.ref
0x3db83  ldloc.s  0xC
0x3db85  ldc.i4.3
0x3db86  ldarg.s  4
0x3db88  box      [mscorlib]System.Boolean
0x3db8d  stelem.ref
0x3db8e  ldloc.s  0xC
0x3db90  ldc.i4.4
0x3db91  ldarg.s  5
0x3db93  box      [mscorlib]System.Boolean
0x3db98  stelem.ref
0x3db99  ldloc.s  0xC
0x3db9b  ldc.i4.5
0x3db9c  ldarg.s  6
0x3db9e  box      [mscorlib]System.Boolean
0x3dba3  stelem.ref
0x3dba4  ldloc.s  0xC
0x3dba6  ldloc.2
0x3dba7  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x3dbac  ldloc.2
0x3dbad  ldarg.0
0x3dbae  ldfld    valuetype [mscorlib]System.Threading.ApartmentState Microsoft.SharePoint.Library.SPRequest::m_ApartmentState
0x3dbb3  ldarg.0
0x3dbb4  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_ManagedThreadId
0x3dbb9  ldarg.0
0x3dbba  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedThreadId
0x3dbbf  ldarg.0
0x3dbc0  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x3dbc5  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestInvalidCastException(class [mscorlib]System.InvalidCastException castEx, valuetype [mscorlib]System.Threading.ApartmentState apartmentState, int32 managedThreadId, int32 unmanagedThreadId, string constructorStackTrace)
0x3dbca  rethrow
0x3dbcc  stloc.3
0x3dbcd  ldstr    aDeletesite// "DeleteSite"
0x3dbd2  ldarg.0
0x3dbd3  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x3dbd8  ldarg.0
0x3dbd9  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x3dbde  ldc.i4.6
0x3dbdf  newarr   [mscorlib]System.String
0x3dbe4  stloc.s  0xD
0x3dbe6  ldloc.s  0xD
0x3dbe8  ldc.i4.0
0x3dbe9  ldstr    aBstrurl// "bstrUrl"
0x3dbee  stelem.ref
0x3dbef  ldloc.s  0xD
0x3dbf1  ldc.i4.1
0x3dbf2  ldstr    aBdeleteadaccou// "bDeleteADAccounts"
0x3dbf7  stelem.ref
0x3dbf8  ldloc.s  0xD
0x3dbfa  ldc.i4.2
0x3dbfb  ldstr    aBgradualdelete// "bGradualDelete"
0x3dc00  stelem.ref
0x3dc01  ldloc.s  0xD
0x3dc03  ldc.i4.3
0x3dc04  ldstr    aBsiterecyclebi// "bSiteRecycleBinEnabled"
0x3dc09  stelem.ref
0x3dc0a  ldloc.s  0xD
0x3dc0c  ldc.i4.4
0x3dc0d  ldstr    aBdeleteisformi// "bDeleteIsForMigration"
0x3dc12  stelem.ref
0x3dc13  ldloc.s  0xD
0x3dc15  ldc.i4.5
0x3dc16  ldstr    aBcheckcomplian// "bCheckComplianceFlags"
0x3dc1b  stelem.ref
0x3dc1c  ldloc.s  0xD
0x3dc1e  ldc.i4.6
0x3dc1f  newarr   [mscorlib]System.Object
0x3dc24  stloc.s  0xE
  ... truncated ...
```
