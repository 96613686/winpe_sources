# Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSiteSubscriptionIdFromUri

- ea: `0x22c40`
- end: `0x22d68`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSiteSubscriptionIdFromUri`
- size: `296`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x4500`
- `0x21fd0`
- `0x24e00`
- `0x25f80`
- `0x26e80`
- `0x28d60`

## callees

- `0x22b00`
- `0x22c40`
- `0x2c520`

## string_xrefs

- `0x22cb7`: `Token Cache: Found side subscription. Value: '{0}', SPSite: '{1}', Uri: '{2}'.`
- `0x22cf5`: `Token Cache: No site subscription. SPSite: '{0}', Uri: '{1}'.`
- `0x22d46`: `Token Cache: Could not find SPSite. Uri: '{0}', Stack: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x22c40  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPTokenCache::SiteLoadKillSwitch
0x22c45  ldstr    a7242017// "7/24/2017"
0x22c4a  ldstr    aUseTheOldWayOf// "Use the old way of doing this."
0x22c4f  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x22c54  brfalse.s loc_22C62
0x22c56  ldarg.1
0x22c57  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x22c5c  call     string Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSubscriptionIdFromContext(string context)
0x22c61  ret
0x22c62  ldc.i4   0x1709509
0x22c67  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x22c6c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22c71  ldstr    aContext_0// "context"
0x22c76  ldarg.1
0x22c77  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x22c7c  ldnull
0x22c7d  stloc.0
0x22c7e  ldarg.1
0x22c7f  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x22c84  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserToken [Microsoft.SharePoint]Microsoft.SharePoint.SPUserToken::get_SystemAccount()
0x22c89  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::.ctor(string, class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserToken)
0x22c8e  stloc.1
0x22c8f  ldloc.1
0x22c90  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x22c95  brfalse.s loc_22CE6
0x22c97  ldloc.1
0x22c98  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x22c9d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscriptionIdentifier [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription::get_Id()
0x22ca2  callvirt instance string [mscorlib]System.Object::ToString()
0x22ca7  stloc.0
0x22ca8  ldc.i4   0x170950A
0x22cad  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22cb2  ldc.i4   0xC8
0x22cb7  ldstr    aTokenCacheFoun// "Token Cache: Found side subscription. V"...
0x22cbc  ldc.i4.3
0x22cbd  newarr   [mscorlib]System.Object
0x22cc2  stloc.s  4
0x22cc4  ldloc.s  4
0x22cc6  ldc.i4.0
0x22cc7  ldloc.0
0x22cc8  stelem.ref
0x22cc9  ldloc.s  4
0x22ccb  ldc.i4.1
0x22ccc  ldloc.1
0x22ccd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x22cd2  box      [mscorlib]System.Guid
0x22cd7  stelem.ref
0x22cd8  ldloc.s  4
0x22cda  ldc.i4.2
0x22cdb  ldarg.1
0x22cdc  stelem.ref
0x22cdd  ldloc.s  4
0x22cdf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x22ce4  br.s     loc_22D1D
0x22ce6  ldc.i4   0x170950B
0x22ceb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22cf0  ldc.i4   0xC8
0x22cf5  ldstr    aTokenCacheNoSi_0// "Token Cache: No site subscription. SPSi"...
0x22cfa  ldc.i4.2
0x22cfb  newarr   [mscorlib]System.Object
0x22d00  stloc.s  5
0x22d02  ldloc.s  5
0x22d04  ldc.i4.0
0x22d05  ldloc.1
0x22d06  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x22d0b  box      [mscorlib]System.Guid
0x22d10  stelem.ref
0x22d11  ldloc.s  5
0x22d13  ldc.i4.1
0x22d14  ldarg.1
0x22d15  stelem.ref
0x22d16  ldloc.s  5
0x22d18  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x22d1d  leave.s  loc_22D29
0x22d1f  ldloc.1
0x22d20  brfalse.s loc_22D28
0x22d22  ldloc.1
0x22d23  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22d28  endfinally
0x22d29  leave.s  loc_22D66
0x22d2b  stloc.2
0x22d2c  ldloc.2
0x22d2d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22d32  ldc.i4.s 0xA
0x22d34  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::ExceptionTraceString(class [mscorlib]System.Exception, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0x22d39  stloc.3
0x22d3a  ldc.i4   0x170950C
0x22d3f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22d44  ldc.i4.s 0x32
0x22d46  ldstr    aTokenCacheCoul_0// "Token Cache: Could not find SPSite. Uri"...
0x22d4b  ldc.i4.2
0x22d4c  newarr   [mscorlib]System.Object
0x22d51  stloc.s  6
0x22d53  ldloc.s  6
0x22d55  ldc.i4.0
0x22d56  ldarg.1
0x22d57  stelem.ref
0x22d58  ldloc.s  6
0x22d5a  ldc.i4.1
0x22d5b  ldloc.3
0x22d5c  stelem.ref
0x22d5d  ldloc.s  6
0x22d5f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x22d64  leave.s  loc_22D66
0x22d66  ldloc.0
0x22d67  ret
```
