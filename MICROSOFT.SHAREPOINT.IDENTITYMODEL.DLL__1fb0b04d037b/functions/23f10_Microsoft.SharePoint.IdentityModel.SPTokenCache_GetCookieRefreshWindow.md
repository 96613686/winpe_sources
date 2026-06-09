# Microsoft.SharePoint.IdentityModel.SPTokenCache::GetCookieRefreshWindow

- ea: `0x23f10`
- end: `0x24076`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::GetCookieRefreshWindow`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x23de0`

## callees

- `0x20800`
- `0x21b70`
- `0x21c00`
- `0x21c20`
- `0x23f10`

## string_xrefs

- `0x23f7e`: `Token Request Data: SubscriptionId is null or empty.`
- `0x23fe5`: `Token Cache: CookieValue is persistent so using CookieLifetimeRefreshWindow.`
- `0x23ffd`: `Token Cache: CookieValue is session so using SessionCookieLifetimeRefreshWindow.`

## pseudocode

```c

```

## disassembly

```asm
0x23f10  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_Local()
0x23f15  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_CookieLifetimeRefreshWindow()
0x23f1a  stloc.3
0x23f1b  ldloca.s 3
0x23f1d  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x23f22  stloc.0
0x23f23  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPTokenCache::SessionCookieLifetimeKillSwitch
0x23f28  ldstr    a10132017// "10/13/2017"
0x23f2d  ldstr    aAuthzenSession// "AuthZen_SessionCookieLifetime"
0x23f32  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x23f37  brfalse.s loc_23F54
0x23f39  ldc.i4   0x1803797
0x23f3e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x23f43  ldc.i4.s 0xA
0x23f45  ldstr    aKillswitchAuth// "Killswitch AuthZen_SessionCookieLifetim"...
0x23f4a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23f4f  br       loc_2404A
0x23f54  ldarg.1
0x23f55  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_SubscriptionIdAsGuid()
0x23f5a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x23f5f  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x23f64  brfalse.s loc_23F8D
0x23f66  ldc.i4.s 0x64
0x23f68  stloc.1
0x23f69  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPGlobal::get_IsSPO()
0x23f6e  brfalse.s loc_23F73
0x23f70  ldc.i4.s 0xA
0x23f72  stloc.1
0x23f73  ldc.i4   0x1803798
0x23f78  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23f7d  ldloc.1
0x23f7e  ldstr    aTokenRequestDa_0// "Token Request Data: SubscriptionId is n"...
0x23f83  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23f88  br       loc_2401B
0x23f8d  ldc.i4   0x37A8
0x23f92  ldarg.1
0x23f93  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_SubscriptionIdAsGuid()
0x23f98  ldc.i4.0
0x23f99  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.FederatedDirectory.Flighting::IsExpFeatureEnabledForSubscriptionId(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId, valuetype [mscorlib]System.Guid, bool)
0x23f9e  brtrue.s loc_23FCC
0x23fa0  ldc.i4   0x1803799
0x23fa5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23faa  ldc.i4.s 0x64
0x23fac  ldstr    aTheAuthzensess// "The AuthZenSessionCookieLifetime flight"...
0x23fb1  ldc.i4.1
0x23fb2  newarr   [mscorlib]System.Object
0x23fb7  stloc.s  4
0x23fb9  ldloc.s  4
0x23fbb  ldc.i4.0
0x23fbc  ldarg.1
0x23fbd  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_SubscriptionId()
0x23fc2  stelem.ref
0x23fc3  ldloc.s  4
0x23fc5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x23fca  br.s     loc_2401B
0x23fcc  ldarg.1
0x23fcd  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x23fd2  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IsPersistent()
0x23fd7  brfalse.s loc_23FF1
0x23fd9  ldc.i4   0x180379A
0x23fde  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23fe3  ldc.i4.s 0x64
0x23fe5  ldstr    aTokenCacheCook_9// "Token Cache: CookieValue is persistent "...
0x23fea  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23fef  br.s     loc_2401B
0x23ff1  ldc.i4   0x180379D
0x23ff6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23ffb  ldc.i4.s 0x64
0x23ffd  ldstr    aTokenCacheCook_10// "Token Cache: CookieValue is session so "...
0x24002  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24007  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_Local()
0x2400c  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_SessionCookieLifetimeRefreshWindow()
0x24011  stloc.s  5
0x24013  ldloca.s 5
0x24015  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x2401a  stloc.0
0x2401b  leave.s  loc_2404A
0x2401d  stloc.2
0x2401e  ldc.i4   0x180379E
0x24023  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24028  ldc.i4.s 0xA
0x2402a  ldstr    aProblemCheckin// "Problem checking session cookie lifetim"...
0x2402f  ldc.i4.1
0x24030  newarr   [mscorlib]System.Object
0x24035  stloc.s  6
0x24037  ldloc.s  6
0x24039  ldc.i4.0
0x2403a  ldloc.2
0x2403b  callvirt instance string [mscorlib]System.Object::ToString()
0x24040  stelem.ref
0x24041  ldloc.s  6
0x24043  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x24048  leave.s  loc_2404A
0x2404a  ldc.i4   0x180379F
0x2404f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24054  ldc.i4.s 0x32
0x24056  ldstr    aCookieLifetime// "Cookie lifetime refresh window value: '"...
0x2405b  ldc.i4.1
0x2405c  newarr   [mscorlib]System.Object
0x24061  stloc.s  7
0x24063  ldloc.s  7
0x24065  ldc.i4.0
0x24066  ldloc.0
0x24067  box      [mscorlib]System.Int64
0x2406c  stelem.ref
0x2406d  ldloc.s  7
0x2406f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x24074  ldloc.0
0x24075  ret
```
