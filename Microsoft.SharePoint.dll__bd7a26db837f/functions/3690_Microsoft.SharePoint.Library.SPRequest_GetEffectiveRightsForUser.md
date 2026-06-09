# Microsoft.SharePoint.Library.SPRequest::GetEffectiveRightsForUser

- ea: `0x3690`
- end: `0x3cba`
- name: `Microsoft.SharePoint.Library.SPRequest::GetEffectiveRightsForUser`
- size: `1578`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1994b0`

## callees

- `0x30b0`
- `0x3690`
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

- `0x376a`: `dtExtTokenLastUpdated`
- `0x3880`: `dtExtTokenLastUpdated`
- `0x3997`: `dtExtTokenLastUpdated`
- `0x3ac5`: `dtExtTokenLastUpdated`
- `0x3be8`: `dtExtTokenLastUpdated`
- `0x377d`: `dtDynamicClaimsLastUpdated`
- `0x3893`: `dtDynamicClaimsLastUpdated`
- `0x39aa`: `dtDynamicClaimsLastUpdated`
- `0x3ad8`: `dtDynamicClaimsLastUpdated`
- `0x3bfb`: `dtDynamicClaimsLastUpdated`
- `0x3787`: `llClaimMapVersionAtLastUpdate`
- `0x389d`: `llClaimMapVersionAtLastUpdate`
- `0x39b4`: `llClaimMapVersionAtLastUpdate`
- `0x3ae2`: `llClaimMapVersionAtLastUpdate`
- `0x3c05`: `llClaimMapVersionAtLastUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x3690  ldc.i4   0x66366C37
0x3695  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x369a  ldc.i4.s 0x64
0x369c  ldstr    aSprequestGetef_0// "SPRequest.GetEffectiveRightsForUser"
0x36a1  ldc.i4.1
0x36a2  ldc.i4.2
0x36a3  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x36a8  stloc.s  6
0x36aa  ldloc.s  6
0x36ac  ldc.i4.0
0x36ad  ldc.i4   0x96
0x36b2  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x36b7  stelem.ref
0x36b8  ldloc.s  6
0x36ba  ldc.i4.1
0x36bb  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x36c0  stelem.ref
0x36c1  ldloc.s  6
0x36c3  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x36c8  stloc.s  7
0x36ca  ldarg.0
0x36cb  dup
0x36cc  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x36d1  ldc.i4.1
0x36d2  add
0x36d3  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x36d8  ldarg.0
0x36d9  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x36de  ldarg.0
0x36df  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x36e4  ldarg.1
0x36e5  ldarg.2
0x36e6  ldarg.3
0x36e7  ldarg.s  4
0x36e9  ldarg.s  5
0x36eb  ldarg.s  6
0x36ed  ldarg.s  7
0x36ef  ldarg.s  8
0x36f1  ldarg.s  9
0x36f3  ldarg.s  0xA
0x36f5  ldarg.s  0xB
0x36f7  ldarg.s  0xC
0x36f9  ldarg.s  0xD
0x36fb  ldarg.s  0xE
0x36fd  ldarg.s  0xF
0x36ff  ldarg.s  0x10
0x3701  callvirt instance unsigned int64 [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::GetEffectiveRightsForUser(string, unsigned int8[]&, unsigned int64, int32, bool, string, string, string, unsigned int8[]&, valuetype [mscorlib]System.DateTime, unsigned int8[]&, int32, unsigned int8[]&, valuetype [mscorlib]System.DateTime, int64, bool)
0x3706  stloc.s  5
0x3708  leave    loc_3CB7
0x370d  stloc.0
0x370e  ldstr    aGeteffectiveri_0// "GetEffectiveRightsForUser"
0x3713  ldarg.0
0x3714  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x3719  ldarg.0
0x371a  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x371f  ldc.i4.s 0xC
0x3721  newarr   [mscorlib]System.String
0x3726  stloc.s  8
0x3728  ldloc.s  8
0x372a  ldc.i4.0
0x372b  ldstr    aBstrweburl// "bstrWebUrl"
0x3730  stelem.ref
0x3731  ldloc.s  8
0x3733  ldc.i4.1
0x3734  ldstr    aLanonymousmask// "lAnonymousMask"
0x3739  stelem.ref
0x373a  ldloc.s  8
0x373c  ldc.i4.2
0x373d  ldstr    aId// "id"
0x3742  stelem.ref
0x3743  ldloc.s  8
0x3745  ldc.i4.3
0x3746  ldstr    aBsiteadmin// "bSiteAdmin"
0x374b  stelem.ref
0x374c  ldloc.s  8
0x374e  ldc.i4.4
0x374f  ldstr    aBstrlogin// "bstrLogin"
0x3754  stelem.ref
0x3755  ldloc.s  8
0x3757  ldc.i4.5
0x3758  ldstr    aBstremail// "bstrEmail"
0x375d  stelem.ref
0x375e  ldloc.s  8
0x3760  ldc.i4.6
0x3761  ldstr    aBstrtitle// "bstrTitle"
0x3766  stelem.ref
0x3767  ldloc.s  8
0x3769  ldc.i4.7
0x376a  ldstr    aDtexttokenlast// "dtExtTokenLastUpdated"
0x376f  stelem.ref
0x3770  ldloc.s  8
0x3772  ldc.i4.8
0x3773  ldstr    aFlags// "flags"
0x3778  stelem.ref
0x3779  ldloc.s  8
0x377b  ldc.i4.s 9
0x377d  ldstr    aDtdynamicclaim// "dtDynamicClaimsLastUpdated"
0x3782  stelem.ref
0x3783  ldloc.s  8
0x3785  ldc.i4.s 0xA
0x3787  ldstr    aLlclaimmapvers// "llClaimMapVersionAtLastUpdate"
0x378c  stelem.ref
0x378d  ldloc.s  8
0x378f  ldc.i4.s 0xB
0x3791  ldstr    aBallowdynamicc// "bAllowDynamicClaimsRefresh"
0x3796  stelem.ref
0x3797  ldloc.s  8
0x3799  ldc.i4.s 0xC
0x379b  newarr   [mscorlib]System.Object
0x37a0  stloc.s  9
0x37a2  ldloc.s  9
0x37a4  ldc.i4.0
0x37a5  ldarg.1
0x37a6  stelem.ref
0x37a7  ldloc.s  9
0x37a9  ldc.i4.1
0x37aa  ldarg.3
0x37ab  box      [mscorlib]System.UInt64
0x37b0  stelem.ref
0x37b1  ldloc.s  9
0x37b3  ldc.i4.2
0x37b4  ldarg.s  4
0x37b6  box      [mscorlib]System.Int32
0x37bb  stelem.ref
0x37bc  ldloc.s  9
0x37be  ldc.i4.3
0x37bf  ldarg.s  5
0x37c1  box      [mscorlib]System.Boolean
0x37c6  stelem.ref
0x37c7  ldloc.s  9
0x37c9  ldc.i4.4
0x37ca  ldarg.s  6
0x37cc  stelem.ref
0x37cd  ldloc.s  9
0x37cf  ldc.i4.5
0x37d0  ldarg.s  7
0x37d2  stelem.ref
0x37d3  ldloc.s  9
0x37d5  ldc.i4.6
0x37d6  ldarg.s  8
0x37d8  stelem.ref
0x37d9  ldloc.s  9
0x37db  ldc.i4.7
0x37dc  ldarg.s  0xA
0x37de  box      [mscorlib]System.DateTime
0x37e3  stelem.ref
0x37e4  ldloc.s  9
0x37e6  ldc.i4.8
0x37e7  ldarg.s  0xC
0x37e9  box      [mscorlib]System.Int32
0x37ee  stelem.ref
0x37ef  ldloc.s  9
0x37f1  ldc.i4.s 9
0x37f3  ldarg.s  0xE
0x37f5  box      [mscorlib]System.DateTime
0x37fa  stelem.ref
0x37fb  ldloc.s  9
0x37fd  ldc.i4.s 0xA
0x37ff  ldarg.s  0xF
0x3801  box      [mscorlib]System.Int64
0x3806  stelem.ref
0x3807  ldloc.s  9
0x3809  ldc.i4.s 0xB
0x380b  ldarg.s  0x10
0x380d  box      [mscorlib]System.Boolean
0x3812  stelem.ref
0x3813  ldloc.s  9
0x3815  ldloc.0
0x3816  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x381b  ldloc.0
0x381c  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x3821  rethrow
0x3823  stloc.1
0x3824  ldstr    aGeteffectiveri_0// "GetEffectiveRightsForUser"
0x3829  ldarg.0
0x382a  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x382f  ldarg.0
0x3830  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x3835  ldc.i4.s 0xC
0x3837  newarr   [mscorlib]System.String
0x383c  stloc.s  0xA
0x383e  ldloc.s  0xA
0x3840  ldc.i4.0
0x3841  ldstr    aBstrweburl// "bstrWebUrl"
0x3846  stelem.ref
0x3847  ldloc.s  0xA
0x3849  ldc.i4.1
0x384a  ldstr    aLanonymousmask// "lAnonymousMask"
0x384f  stelem.ref
0x3850  ldloc.s  0xA
0x3852  ldc.i4.2
0x3853  ldstr    aId// "id"
0x3858  stelem.ref
0x3859  ldloc.s  0xA
0x385b  ldc.i4.3
0x385c  ldstr    aBsiteadmin// "bSiteAdmin"
0x3861  stelem.ref
0x3862  ldloc.s  0xA
0x3864  ldc.i4.4
0x3865  ldstr    aBstrlogin// "bstrLogin"
0x386a  stelem.ref
0x386b  ldloc.s  0xA
0x386d  ldc.i4.5
0x386e  ldstr    aBstremail// "bstrEmail"
0x3873  stelem.ref
0x3874  ldloc.s  0xA
0x3876  ldc.i4.6
0x3877  ldstr    aBstrtitle// "bstrTitle"
0x387c  stelem.ref
0x387d  ldloc.s  0xA
0x387f  ldc.i4.7
0x3880  ldstr    aDtexttokenlast// "dtExtTokenLastUpdated"
0x3885  stelem.ref
0x3886  ldloc.s  0xA
0x3888  ldc.i4.8
0x3889  ldstr    aFlags// "flags"
0x388e  stelem.ref
0x388f  ldloc.s  0xA
0x3891  ldc.i4.s 9
0x3893  ldstr    aDtdynamicclaim// "dtDynamicClaimsLastUpdated"
0x3898  stelem.ref
0x3899  ldloc.s  0xA
0x389b  ldc.i4.s 0xA
0x389d  ldstr    aLlclaimmapvers// "llClaimMapVersionAtLastUpdate"
0x38a2  stelem.ref
0x38a3  ldloc.s  0xA
0x38a5  ldc.i4.s 0xB
0x38a7  ldstr    aBallowdynamicc// "bAllowDynamicClaimsRefresh"
0x38ac  stelem.ref
0x38ad  ldloc.s  0xA
0x38af  ldc.i4.s 0xC
0x38b1  newarr   [mscorlib]System.Object
0x38b6  stloc.s  0xB
0x38b8  ldloc.s  0xB
0x38ba  ldc.i4.0
0x38bb  ldarg.1
0x38bc  stelem.ref
0x38bd  ldloc.s  0xB
0x38bf  ldc.i4.1
0x38c0  ldarg.3
0x38c1  box      [mscorlib]System.UInt64
0x38c6  stelem.ref
0x38c7  ldloc.s  0xB
0x38c9  ldc.i4.2
0x38ca  ldarg.s  4
0x38cc  box      [mscorlib]System.Int32
0x38d1  stelem.ref
0x38d2  ldloc.s  0xB
0x38d4  ldc.i4.3
0x38d5  ldarg.s  5
0x38d7  box      [mscorlib]System.Boolean
0x38dc  stelem.ref
0x38dd  ldloc.s  0xB
0x38df  ldc.i4.4
0x38e0  ldarg.s  6
0x38e2  stelem.ref
0x38e3  ldloc.s  0xB
0x38e5  ldc.i4.5
0x38e6  ldarg.s  7
0x38e8  stelem.ref
0x38e9  ldloc.s  0xB
0x38eb  ldc.i4.6
0x38ec  ldarg.s  8
0x38ee  stelem.ref
0x38ef  ldloc.s  0xB
0x38f1  ldc.i4.7
0x38f2  ldarg.s  0xA
0x38f4  box      [mscorlib]System.DateTime
0x38f9  stelem.ref
0x38fa  ldloc.s  0xB
0x38fc  ldc.i4.8
0x38fd  ldarg.s  0xC
0x38ff  box      [mscorlib]System.Int32
0x3904  stelem.ref
0x3905  ldloc.s  0xB
0x3907  ldc.i4.s 9
0x3909  ldarg.s  0xE
0x390b  box      [mscorlib]System.DateTime
0x3910  stelem.ref
0x3911  ldloc.s  0xB
0x3913  ldc.i4.s 0xA
0x3915  ldarg.s  0xF
0x3917  box      [mscorlib]System.Int64
0x391c  stelem.ref
0x391d  ldloc.s  0xB
0x391f  ldc.i4.s 0xB
0x3921  ldarg.s  0x10
0x3923  box      [mscorlib]System.Boolean
0x3928  stelem.ref
0x3929  ldloc.s  0xB
0x392b  ldloc.1
0x392c  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x3931  ldloc.1
0x3932  ldc.i4.0
0x3933  call     void Microsoft.SharePoint.SPGlobal::HandleUnauthorizedAccessException(class [mscorlib]System.UnauthorizedAccessException ex, [opt] bool allowCompleteRequest)
0x3938  rethrow
0x393a  stloc.2
0x393b  ldstr    aGeteffectiveri_0// "GetEffectiveRightsForUser"
0x3940  ldarg.0
0x3941  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
  ... truncated ...
```
