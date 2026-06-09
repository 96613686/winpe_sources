# Microsoft.SharePoint.Library.SPRequest::ResetSecurityScope

- ea: `0x2ce90`
- end: `0x2d393`
- name: `Microsoft.SharePoint.Library.SPRequest::ResetSecurityScope`
- size: `1283`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x476cd0`
- `0x614f90`

## callees

- `0x30b0`
- `0x2ce90`
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

- `0x2ce9c`: `SPRequest.ResetSecurityScope`
- `0x2cf02`: `ResetSecurityScope`
- `0x2cfdf`: `ResetSecurityScope`
- `0x2d0bd`: `ResetSecurityScope`
- `0x2d1b2`: `ResetSecurityScope`
- `0x2d29c`: `ResetSecurityScope`
- `0x2cf4c`: `bCopyRoleAssignments`
- `0x2d029`: `bCopyRoleAssignments`
- `0x2d107`: `bCopyRoleAssignments`
- `0x2d1fc`: `bCopyRoleAssignments`
- `0x2d2e6`: `bCopyRoleAssignments`
- `0x2cf5e`: `bDontCopyLimitedPerms`
- `0x2d03b`: `bDontCopyLimitedPerms`
- `0x2d119`: `bDontCopyLimitedPerms`
- `0x2d20e`: `bDontCopyLimitedPerms`
- `0x2d2f8`: `bDontCopyLimitedPerms`
- `0x2cf67`: `bDontCopyLimitedPermsV2`
- `0x2d044`: `bDontCopyLimitedPermsV2`
- `0x2d122`: `bDontCopyLimitedPermsV2`
- `0x2d217`: `bDontCopyLimitedPermsV2`
- `0x2d301`: `bDontCopyLimitedPermsV2`

## pseudocode

```c

```

## disassembly

```asm
0x2ce90  ldc.i4   0x66366C37
0x2ce95  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x2ce9a  ldc.i4.s 0x64
0x2ce9c  ldstr    aSprequestReset// "SPRequest.ResetSecurityScope"
0x2cea1  ldc.i4.1
0x2cea2  ldc.i4.2
0x2cea3  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x2cea8  stloc.s  5
0x2ceaa  ldloc.s  5
0x2ceac  ldc.i4.0
0x2cead  ldc.i4   0x96
0x2ceb2  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x2ceb7  stelem.ref
0x2ceb8  ldloc.s  5
0x2ceba  ldc.i4.1
0x2cebb  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x2cec0  stelem.ref
0x2cec1  ldloc.s  5
0x2cec3  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x2cec8  stloc.s  6
0x2ceca  ldarg.0
0x2cecb  dup
0x2cecc  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x2ced1  ldc.i4.1
0x2ced2  add
0x2ced3  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x2ced8  ldarg.0
0x2ced9  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x2cede  ldarg.0
0x2cedf  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x2cee4  ldarg.1
0x2cee5  ldarg.2
0x2cee6  ldarg.3
0x2cee7  ldarg.s  4
0x2cee9  ldarg.s  5
0x2ceeb  ldarg.s  6
0x2ceed  ldarg.s  7
0x2ceef  ldarg.s  8
0x2cef1  ldarg.s  9
0x2cef3  ldarg.s  0xA
0x2cef5  ldarg.s  0xB
0x2cef7  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::ResetSecurityScope(string, unsigned int32, string, valuetype [mscorlib]System.Guid, bool, bool, bool, valuetype [mscorlib]System.Guid&, int32&, bool, bool)
0x2cefc  leave    loc_2D373
0x2cf01  stloc.0
0x2cf02  ldstr    aResetsecuritys// "ResetSecurityScope"
0x2cf07  ldarg.0
0x2cf08  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x2cf0d  ldarg.0
0x2cf0e  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x2cf13  ldc.i4.s 9
0x2cf15  newarr   [mscorlib]System.String
0x2cf1a  stloc.s  7
0x2cf1c  ldloc.s  7
0x2cf1e  ldc.i4.0
0x2cf1f  ldstr    aBstrurl// "bstrUrl"
0x2cf24  stelem.ref
0x2cf25  ldloc.s  7
0x2cf27  ldc.i4.1
0x2cf28  ldstr    aDwobjecttype// "dwObjectType"
0x2cf2d  stelem.ref
0x2cf2e  ldloc.s  7
0x2cf30  ldc.i4.2
0x2cf31  ldstr    aBstrobjurl// "bstrObjUrl"
0x2cf36  stelem.ref
0x2cf37  ldloc.s  7
0x2cf39  ldc.i4.3
0x2cf3a  ldstr    aGuiddoc// "guidDoc"
0x2cf3f  stelem.ref
0x2cf40  ldloc.s  7
0x2cf42  ldc.i4.4
0x2cf43  ldstr    aBunique// "bUnique"
0x2cf48  stelem.ref
0x2cf49  ldloc.s  7
0x2cf4b  ldc.i4.5
0x2cf4c  ldstr    aBcopyroleassig// "bCopyRoleAssignments"
0x2cf51  stelem.ref
0x2cf52  ldloc.s  7
0x2cf54  ldc.i4.6
0x2cf55  ldstr    aBclearsubscope// "bClearSubScopes"
0x2cf5a  stelem.ref
0x2cf5b  ldloc.s  7
0x2cf5d  ldc.i4.7
0x2cf5e  ldstr    aBdontcopylimit// "bDontCopyLimitedPerms"
0x2cf63  stelem.ref
0x2cf64  ldloc.s  7
0x2cf66  ldc.i4.8
0x2cf67  ldstr    aBdontcopylimit_0// "bDontCopyLimitedPermsV2"
0x2cf6c  stelem.ref
0x2cf6d  ldloc.s  7
0x2cf6f  ldc.i4.s 9
0x2cf71  newarr   [mscorlib]System.Object
0x2cf76  stloc.s  8
0x2cf78  ldloc.s  8
0x2cf7a  ldc.i4.0
0x2cf7b  ldarg.1
0x2cf7c  stelem.ref
0x2cf7d  ldloc.s  8
0x2cf7f  ldc.i4.1
0x2cf80  ldarg.2
0x2cf81  box      [mscorlib]System.UInt32
0x2cf86  stelem.ref
0x2cf87  ldloc.s  8
0x2cf89  ldc.i4.2
0x2cf8a  ldarg.3
0x2cf8b  stelem.ref
0x2cf8c  ldloc.s  8
0x2cf8e  ldc.i4.3
0x2cf8f  ldarg.s  4
0x2cf91  box      [mscorlib]System.Guid
0x2cf96  stelem.ref
0x2cf97  ldloc.s  8
0x2cf99  ldc.i4.4
0x2cf9a  ldarg.s  5
0x2cf9c  box      [mscorlib]System.Boolean
0x2cfa1  stelem.ref
0x2cfa2  ldloc.s  8
0x2cfa4  ldc.i4.5
0x2cfa5  ldarg.s  6
0x2cfa7  box      [mscorlib]System.Boolean
0x2cfac  stelem.ref
0x2cfad  ldloc.s  8
0x2cfaf  ldc.i4.6
0x2cfb0  ldarg.s  7
0x2cfb2  box      [mscorlib]System.Boolean
0x2cfb7  stelem.ref
0x2cfb8  ldloc.s  8
0x2cfba  ldc.i4.7
0x2cfbb  ldarg.s  0xA
0x2cfbd  box      [mscorlib]System.Boolean
0x2cfc2  stelem.ref
0x2cfc3  ldloc.s  8
0x2cfc5  ldc.i4.8
0x2cfc6  ldarg.s  0xB
0x2cfc8  box      [mscorlib]System.Boolean
0x2cfcd  stelem.ref
0x2cfce  ldloc.s  8
0x2cfd0  ldloc.0
0x2cfd1  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x2cfd6  ldloc.0
0x2cfd7  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x2cfdc  rethrow
0x2cfde  stloc.1
0x2cfdf  ldstr    aResetsecuritys// "ResetSecurityScope"
0x2cfe4  ldarg.0
0x2cfe5  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x2cfea  ldarg.0
0x2cfeb  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x2cff0  ldc.i4.s 9
0x2cff2  newarr   [mscorlib]System.String
0x2cff7  stloc.s  9
0x2cff9  ldloc.s  9
0x2cffb  ldc.i4.0
0x2cffc  ldstr    aBstrurl// "bstrUrl"
0x2d001  stelem.ref
0x2d002  ldloc.s  9
0x2d004  ldc.i4.1
0x2d005  ldstr    aDwobjecttype// "dwObjectType"
0x2d00a  stelem.ref
0x2d00b  ldloc.s  9
0x2d00d  ldc.i4.2
0x2d00e  ldstr    aBstrobjurl// "bstrObjUrl"
0x2d013  stelem.ref
0x2d014  ldloc.s  9
0x2d016  ldc.i4.3
0x2d017  ldstr    aGuiddoc// "guidDoc"
0x2d01c  stelem.ref
0x2d01d  ldloc.s  9
0x2d01f  ldc.i4.4
0x2d020  ldstr    aBunique// "bUnique"
0x2d025  stelem.ref
0x2d026  ldloc.s  9
0x2d028  ldc.i4.5
0x2d029  ldstr    aBcopyroleassig// "bCopyRoleAssignments"
0x2d02e  stelem.ref
0x2d02f  ldloc.s  9
0x2d031  ldc.i4.6
0x2d032  ldstr    aBclearsubscope// "bClearSubScopes"
0x2d037  stelem.ref
0x2d038  ldloc.s  9
0x2d03a  ldc.i4.7
0x2d03b  ldstr    aBdontcopylimit// "bDontCopyLimitedPerms"
0x2d040  stelem.ref
0x2d041  ldloc.s  9
0x2d043  ldc.i4.8
0x2d044  ldstr    aBdontcopylimit_0// "bDontCopyLimitedPermsV2"
0x2d049  stelem.ref
0x2d04a  ldloc.s  9
0x2d04c  ldc.i4.s 9
0x2d04e  newarr   [mscorlib]System.Object
0x2d053  stloc.s  0xA
0x2d055  ldloc.s  0xA
0x2d057  ldc.i4.0
0x2d058  ldarg.1
0x2d059  stelem.ref
0x2d05a  ldloc.s  0xA
0x2d05c  ldc.i4.1
0x2d05d  ldarg.2
0x2d05e  box      [mscorlib]System.UInt32
0x2d063  stelem.ref
0x2d064  ldloc.s  0xA
0x2d066  ldc.i4.2
0x2d067  ldarg.3
0x2d068  stelem.ref
0x2d069  ldloc.s  0xA
0x2d06b  ldc.i4.3
0x2d06c  ldarg.s  4
0x2d06e  box      [mscorlib]System.Guid
0x2d073  stelem.ref
0x2d074  ldloc.s  0xA
0x2d076  ldc.i4.4
0x2d077  ldarg.s  5
0x2d079  box      [mscorlib]System.Boolean
0x2d07e  stelem.ref
0x2d07f  ldloc.s  0xA
0x2d081  ldc.i4.5
0x2d082  ldarg.s  6
0x2d084  box      [mscorlib]System.Boolean
0x2d089  stelem.ref
0x2d08a  ldloc.s  0xA
0x2d08c  ldc.i4.6
0x2d08d  ldarg.s  7
0x2d08f  box      [mscorlib]System.Boolean
0x2d094  stelem.ref
0x2d095  ldloc.s  0xA
0x2d097  ldc.i4.7
0x2d098  ldarg.s  0xA
0x2d09a  box      [mscorlib]System.Boolean
0x2d09f  stelem.ref
0x2d0a0  ldloc.s  0xA
0x2d0a2  ldc.i4.8
0x2d0a3  ldarg.s  0xB
0x2d0a5  box      [mscorlib]System.Boolean
0x2d0aa  stelem.ref
0x2d0ab  ldloc.s  0xA
0x2d0ad  ldloc.1
0x2d0ae  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x2d0b3  ldloc.1
0x2d0b4  ldc.i4.0
0x2d0b5  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x2d0ba  rethrow
0x2d0bc  stloc.2
0x2d0bd  ldstr    aResetsecuritys// "ResetSecurityScope"
0x2d0c2  ldarg.0
0x2d0c3  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x2d0c8  ldarg.0
0x2d0c9  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x2d0ce  ldc.i4.s 9
0x2d0d0  newarr   [mscorlib]System.String
0x2d0d5  stloc.s  0xB
0x2d0d7  ldloc.s  0xB
0x2d0d9  ldc.i4.0
0x2d0da  ldstr    aBstrurl// "bstrUrl"
0x2d0df  stelem.ref
0x2d0e0  ldloc.s  0xB
0x2d0e2  ldc.i4.1
0x2d0e3  ldstr    aDwobjecttype// "dwObjectType"
0x2d0e8  stelem.ref
0x2d0e9  ldloc.s  0xB
0x2d0eb  ldc.i4.2
0x2d0ec  ldstr    aBstrobjurl// "bstrObjUrl"
0x2d0f1  stelem.ref
0x2d0f2  ldloc.s  0xB
0x2d0f4  ldc.i4.3
0x2d0f5  ldstr    aGuiddoc// "guidDoc"
0x2d0fa  stelem.ref
0x2d0fb  ldloc.s  0xB
0x2d0fd  ldc.i4.4
0x2d0fe  ldstr    aBunique// "bUnique"
0x2d103  stelem.ref
0x2d104  ldloc.s  0xB
0x2d106  ldc.i4.5
0x2d107  ldstr    aBcopyroleassig// "bCopyRoleAssignments"
0x2d10c  stelem.ref
0x2d10d  ldloc.s  0xB
0x2d10f  ldc.i4.6
0x2d110  ldstr    aBclearsubscope// "bClearSubScopes"
0x2d115  stelem.ref
0x2d116  ldloc.s  0xB
0x2d118  ldc.i4.7
0x2d119  ldstr    aBdontcopylimit// "bDontCopyLimitedPerms"
0x2d11e  stelem.ref
0x2d11f  ldloc.s  0xB
0x2d121  ldc.i4.8
0x2d122  ldstr    aBdontcopylimit_0// "bDontCopyLimitedPermsV2"
0x2d127  stelem.ref
0x2d128  ldloc.s  0xB
0x2d12a  ldc.i4.s 9
0x2d12c  newarr   [mscorlib]System.Object
0x2d131  stloc.s  0xC
0x2d133  ldloc.s  0xC
0x2d135  ldc.i4.0
0x2d136  ldarg.1
0x2d137  stelem.ref
0x2d138  ldloc.s  0xC
0x2d13a  ldc.i4.1
0x2d13b  ldarg.2
0x2d13c  box      [mscorlib]System.UInt32
0x2d141  stelem.ref
0x2d142  ldloc.s  0xC
0x2d144  ldc.i4.2
  ... truncated ...
```
