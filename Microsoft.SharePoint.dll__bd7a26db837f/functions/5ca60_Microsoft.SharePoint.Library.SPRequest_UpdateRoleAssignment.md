# Microsoft.SharePoint.Library.SPRequest::UpdateRoleAssignment

- ea: `0x5ca60`
- end: `0x5ce91`
- name: `Microsoft.SharePoint.Library.SPRequest::UpdateRoleAssignment`
- size: `1073`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x583060`

## callees

- `0x30b0`
- `0x5ca60`
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

- `0x5ca6c`: `SPRequest.UpdateRoleAssignment`
- `0x5cad2`: `UpdateRoleAssignment`
- `0x5cb85`: `UpdateRoleAssignment`
- `0x5cc39`: `UpdateRoleAssignment`
- `0x5cd04`: `UpdateRoleAssignment`
- `0x5cdc4`: `UpdateRoleAssignment`
- `0x5cb1b`: `bAllowAddToLimitedAccess`
- `0x5cbce`: `bAllowAddToLimitedAccess`
- `0x5cc82`: `bAllowAddToLimitedAccess`
- `0x5cd4d`: `bAllowAddToLimitedAccess`
- `0x5ce0d`: `bAllowAddToLimitedAccess`
- `0x5cb24`: `bPropagateAcl`
- `0x5cbd7`: `bPropagateAcl`
- `0x5cc8b`: `bPropagateAcl`
- `0x5cd56`: `bPropagateAcl`
- `0x5ce16`: `bPropagateAcl`

## pseudocode

```c

```

## disassembly

```asm
0x5ca60  ldc.i4   0x66366C37
0x5ca65  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5ca6a  ldc.i4.s 0x64
0x5ca6c  ldstr    aSprequestUpdat_21// "SPRequest.UpdateRoleAssignment"
0x5ca71  ldc.i4.1
0x5ca72  ldc.i4.2
0x5ca73  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x5ca78  stloc.s  5
0x5ca7a  ldloc.s  5
0x5ca7c  ldc.i4.0
0x5ca7d  ldc.i4   0x96
0x5ca82  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x5ca87  stelem.ref
0x5ca88  ldloc.s  5
0x5ca8a  ldc.i4.1
0x5ca8b  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x5ca90  stelem.ref
0x5ca91  ldloc.s  5
0x5ca93  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x5ca98  stloc.s  6
0x5ca9a  ldarg.0
0x5ca9b  dup
0x5ca9c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x5caa1  ldc.i4.1
0x5caa2  add
0x5caa3  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x5caa8  ldarg.0
0x5caa9  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x5caae  ldarg.0
0x5caaf  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x5cab4  ldarg.1
0x5cab5  ldarg.2
0x5cab6  ldarg.3
0x5cab7  ldarg.s  4
0x5cab9  ldarg.s  5
0x5cabb  ldarg.s  6
0x5cabd  ldarg.s  7
0x5cabf  ldarg.s  8
0x5cac1  ldarg.s  9
0x5cac3  ldarg.s  0xA
0x5cac5  ldarg.s  0xB
0x5cac7  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::UpdateRoleAssignment(string, unsigned int32, string, valuetype [mscorlib]System.Guid&, int32, bool, bool, bool, object&, object&, object&)
0x5cacc  leave    loc_5CE71
0x5cad1  stloc.0
0x5cad2  ldstr    aUpdateroleassi// "UpdateRoleAssignment"
0x5cad7  ldarg.0
0x5cad8  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x5cadd  ldarg.0
0x5cade  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x5cae3  ldc.i4.7
0x5cae4  newarr   [mscorlib]System.String
0x5cae9  stloc.s  7
0x5caeb  ldloc.s  7
0x5caed  ldc.i4.0
0x5caee  ldstr    aBstrurl// "bstrUrl"
0x5caf3  stelem.ref
0x5caf4  ldloc.s  7
0x5caf6  ldc.i4.1
0x5caf7  ldstr    aDwobjecttype// "dwObjectType"
0x5cafc  stelem.ref
0x5cafd  ldloc.s  7
0x5caff  ldc.i4.2
0x5cb00  ldstr    aBstrobjid// "bstrObjId"
0x5cb05  stelem.ref
0x5cb06  ldloc.s  7
0x5cb08  ldc.i4.3
0x5cb09  ldstr    aLprincipalid// "lPrincipalID"
0x5cb0e  stelem.ref
0x5cb0f  ldloc.s  7
0x5cb11  ldc.i4.4
0x5cb12  ldstr    aBaddtocurrents// "bAddToCurrentScopeOnly"
0x5cb17  stelem.ref
0x5cb18  ldloc.s  7
0x5cb1a  ldc.i4.5
0x5cb1b  ldstr    aBallowaddtolim// "bAllowAddToLimitedAccess"
0x5cb20  stelem.ref
0x5cb21  ldloc.s  7
0x5cb23  ldc.i4.6
0x5cb24  ldstr    aBpropagateacl// "bPropagateAcl"
0x5cb29  stelem.ref
0x5cb2a  ldloc.s  7
0x5cb2c  ldc.i4.7
0x5cb2d  newarr   [mscorlib]System.Object
0x5cb32  stloc.s  8
0x5cb34  ldloc.s  8
0x5cb36  ldc.i4.0
0x5cb37  ldarg.1
0x5cb38  stelem.ref
0x5cb39  ldloc.s  8
0x5cb3b  ldc.i4.1
0x5cb3c  ldarg.2
0x5cb3d  box      [mscorlib]System.UInt32
0x5cb42  stelem.ref
0x5cb43  ldloc.s  8
0x5cb45  ldc.i4.2
0x5cb46  ldarg.3
0x5cb47  stelem.ref
0x5cb48  ldloc.s  8
0x5cb4a  ldc.i4.3
0x5cb4b  ldarg.s  5
0x5cb4d  box      [mscorlib]System.Int32
0x5cb52  stelem.ref
0x5cb53  ldloc.s  8
0x5cb55  ldc.i4.4
0x5cb56  ldarg.s  6
0x5cb58  box      [mscorlib]System.Boolean
0x5cb5d  stelem.ref
0x5cb5e  ldloc.s  8
0x5cb60  ldc.i4.5
0x5cb61  ldarg.s  7
0x5cb63  box      [mscorlib]System.Boolean
0x5cb68  stelem.ref
0x5cb69  ldloc.s  8
0x5cb6b  ldc.i4.6
0x5cb6c  ldarg.s  8
0x5cb6e  box      [mscorlib]System.Boolean
0x5cb73  stelem.ref
0x5cb74  ldloc.s  8
0x5cb76  ldloc.0
0x5cb77  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x5cb7c  ldloc.0
0x5cb7d  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x5cb82  rethrow
0x5cb84  stloc.1
0x5cb85  ldstr    aUpdateroleassi// "UpdateRoleAssignment"
0x5cb8a  ldarg.0
0x5cb8b  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x5cb90  ldarg.0
0x5cb91  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x5cb96  ldc.i4.7
0x5cb97  newarr   [mscorlib]System.String
0x5cb9c  stloc.s  9
0x5cb9e  ldloc.s  9
0x5cba0  ldc.i4.0
0x5cba1  ldstr    aBstrurl// "bstrUrl"
0x5cba6  stelem.ref
0x5cba7  ldloc.s  9
0x5cba9  ldc.i4.1
0x5cbaa  ldstr    aDwobjecttype// "dwObjectType"
0x5cbaf  stelem.ref
0x5cbb0  ldloc.s  9
0x5cbb2  ldc.i4.2
0x5cbb3  ldstr    aBstrobjid// "bstrObjId"
0x5cbb8  stelem.ref
0x5cbb9  ldloc.s  9
0x5cbbb  ldc.i4.3
0x5cbbc  ldstr    aLprincipalid// "lPrincipalID"
0x5cbc1  stelem.ref
0x5cbc2  ldloc.s  9
0x5cbc4  ldc.i4.4
0x5cbc5  ldstr    aBaddtocurrents// "bAddToCurrentScopeOnly"
0x5cbca  stelem.ref
0x5cbcb  ldloc.s  9
0x5cbcd  ldc.i4.5
0x5cbce  ldstr    aBallowaddtolim// "bAllowAddToLimitedAccess"
0x5cbd3  stelem.ref
0x5cbd4  ldloc.s  9
0x5cbd6  ldc.i4.6
0x5cbd7  ldstr    aBpropagateacl// "bPropagateAcl"
0x5cbdc  stelem.ref
0x5cbdd  ldloc.s  9
0x5cbdf  ldc.i4.7
0x5cbe0  newarr   [mscorlib]System.Object
0x5cbe5  stloc.s  0xA
0x5cbe7  ldloc.s  0xA
0x5cbe9  ldc.i4.0
0x5cbea  ldarg.1
0x5cbeb  stelem.ref
0x5cbec  ldloc.s  0xA
0x5cbee  ldc.i4.1
0x5cbef  ldarg.2
0x5cbf0  box      [mscorlib]System.UInt32
0x5cbf5  stelem.ref
0x5cbf6  ldloc.s  0xA
0x5cbf8  ldc.i4.2
0x5cbf9  ldarg.3
0x5cbfa  stelem.ref
0x5cbfb  ldloc.s  0xA
0x5cbfd  ldc.i4.3
0x5cbfe  ldarg.s  5
0x5cc00  box      [mscorlib]System.Int32
0x5cc05  stelem.ref
0x5cc06  ldloc.s  0xA
0x5cc08  ldc.i4.4
0x5cc09  ldarg.s  6
0x5cc0b  box      [mscorlib]System.Boolean
0x5cc10  stelem.ref
0x5cc11  ldloc.s  0xA
0x5cc13  ldc.i4.5
0x5cc14  ldarg.s  7
0x5cc16  box      [mscorlib]System.Boolean
0x5cc1b  stelem.ref
0x5cc1c  ldloc.s  0xA
0x5cc1e  ldc.i4.6
0x5cc1f  ldarg.s  8
0x5cc21  box      [mscorlib]System.Boolean
0x5cc26  stelem.ref
0x5cc27  ldloc.s  0xA
0x5cc29  ldloc.1
0x5cc2a  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x5cc2f  ldloc.1
0x5cc30  ldc.i4.0
0x5cc31  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x5cc36  rethrow
0x5cc38  stloc.2
0x5cc39  ldstr    aUpdateroleassi// "UpdateRoleAssignment"
0x5cc3e  ldarg.0
0x5cc3f  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x5cc44  ldarg.0
0x5cc45  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x5cc4a  ldc.i4.7
0x5cc4b  newarr   [mscorlib]System.String
0x5cc50  stloc.s  0xB
0x5cc52  ldloc.s  0xB
0x5cc54  ldc.i4.0
0x5cc55  ldstr    aBstrurl// "bstrUrl"
0x5cc5a  stelem.ref
0x5cc5b  ldloc.s  0xB
0x5cc5d  ldc.i4.1
0x5cc5e  ldstr    aDwobjecttype// "dwObjectType"
0x5cc63  stelem.ref
0x5cc64  ldloc.s  0xB
0x5cc66  ldc.i4.2
0x5cc67  ldstr    aBstrobjid// "bstrObjId"
0x5cc6c  stelem.ref
0x5cc6d  ldloc.s  0xB
0x5cc6f  ldc.i4.3
0x5cc70  ldstr    aLprincipalid// "lPrincipalID"
0x5cc75  stelem.ref
0x5cc76  ldloc.s  0xB
0x5cc78  ldc.i4.4
0x5cc79  ldstr    aBaddtocurrents// "bAddToCurrentScopeOnly"
0x5cc7e  stelem.ref
0x5cc7f  ldloc.s  0xB
0x5cc81  ldc.i4.5
0x5cc82  ldstr    aBallowaddtolim// "bAllowAddToLimitedAccess"
0x5cc87  stelem.ref
0x5cc88  ldloc.s  0xB
0x5cc8a  ldc.i4.6
0x5cc8b  ldstr    aBpropagateacl// "bPropagateAcl"
0x5cc90  stelem.ref
0x5cc91  ldloc.s  0xB
0x5cc93  ldc.i4.7
0x5cc94  newarr   [mscorlib]System.Object
0x5cc99  stloc.s  0xC
0x5cc9b  ldloc.s  0xC
0x5cc9d  ldc.i4.0
0x5cc9e  ldarg.1
0x5cc9f  stelem.ref
0x5cca0  ldloc.s  0xC
0x5cca2  ldc.i4.1
0x5cca3  ldarg.2
0x5cca4  box      [mscorlib]System.UInt32
0x5cca9  stelem.ref
0x5ccaa  ldloc.s  0xC
0x5ccac  ldc.i4.2
0x5ccad  ldarg.3
0x5ccae  stelem.ref
0x5ccaf  ldloc.s  0xC
0x5ccb1  ldc.i4.3
0x5ccb2  ldarg.s  5
0x5ccb4  box      [mscorlib]System.Int32
0x5ccb9  stelem.ref
0x5ccba  ldloc.s  0xC
0x5ccbc  ldc.i4.4
0x5ccbd  ldarg.s  6
0x5ccbf  box      [mscorlib]System.Boolean
0x5ccc4  stelem.ref
0x5ccc5  ldloc.s  0xC
0x5ccc7  ldc.i4.5
0x5ccc8  ldarg.s  7
0x5ccca  box      [mscorlib]System.Boolean
0x5cccf  stelem.ref
0x5ccd0  ldloc.s  0xC
0x5ccd2  ldc.i4.6
0x5ccd3  ldarg.s  8
0x5ccd5  box      [mscorlib]System.Boolean
0x5ccda  stelem.ref
0x5ccdb  ldloc.s  0xC
0x5ccdd  ldloc.2
0x5ccde  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x5cce3  ldloc.2
0x5cce4  ldarg.0
0x5cce5  ldfld    valuetype [mscorlib]System.Threading.ApartmentState Microsoft.SharePoint.Library.SPRequest::m_ApartmentState
0x5ccea  ldarg.0
0x5cceb  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_ManagedThreadId
0x5ccf0  ldarg.0
0x5ccf1  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedThreadId
0x5ccf6  ldarg.0
0x5ccf7  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_StackTrace
0x5ccfc  call     void Microsoft.SharePoint.SPGlobal::HandleSPRequestInvalidCastException(class [mscorlib]System.InvalidCastException castEx, valuetype [mscorlib]System.Threading.ApartmentState apartmentState, int32 managedThreadId, int32 unmanagedThreadId, string constructorStackTrace)
0x5cd01  rethrow
0x5cd03  stloc.3
0x5cd04  ldstr    aUpdateroleassi// "UpdateRoleAssignment"
0x5cd09  ldarg.0
0x5cd0a  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x5cd0f  ldarg.0
0x5cd10  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x5cd15  ldc.i4.7
0x5cd16  newarr   [mscorlib]System.String
  ... truncated ...
```
