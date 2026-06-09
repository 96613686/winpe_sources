# Microsoft.SharePoint.IdentityModel.SPTokenCache::AddCachedToken

- ea: `0x25990`
- end: `0x25a84`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::AddCachedToken`
- size: `244`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x244f0`
- `0x25d40`
- `0x25f80`

## callees

- `0x25820`
- `0x25990`
- `0x25a90`

## string_xrefs

- `0x259ac`: `SPTokenCache.AddCachedToken: The identity is null. Stack: '{0}'.`
- `0x259ec`: `SPTokenCache.AddCachedToken: The value is null. Stack: '{0}'.`
- `0x25a2c`: `Token Cache: Successfully added token to cache. Identity: '{0}', SubscriptionId: '{1}'.`
- `0x25a59`: `Token Cache: Failed to add token to cache. Identity: '{0}', SubscriptionId: '{1}', Exception: '{2}'.`

## pseudocode

```c

```

## disassembly

```asm
0x25990  ldarg.2
0x25991  brtrue.s loc_259D0
0x25993  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25998  ldc.i4.s 0xA
0x2599a  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0x2599f  stloc.0
0x259a0  ldc.i4   0x20F889
0x259a5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x259aa  ldc.i4.s 0xA
0x259ac  ldstr    aSptokencacheAd// "SPTokenCache.AddCachedToken: The identi"...
0x259b1  ldc.i4.1
0x259b2  newarr   [mscorlib]System.Object
0x259b7  stloc.s  4
0x259b9  ldloc.s  4
0x259bb  ldc.i4.0
0x259bc  ldloc.0
0x259bd  stelem.ref
0x259be  ldloc.s  4
0x259c0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x259c5  ldstr    aIdentity// "identity"
0x259ca  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x259cf  throw
0x259d0  ldarg.3
0x259d1  brtrue.s loc_25A10
0x259d3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x259d8  ldc.i4.s 0xA
0x259da  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0x259df  stloc.1
0x259e0  ldc.i4   0x20F88A
0x259e5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x259ea  ldc.i4.s 0xA
0x259ec  ldstr    aSptokencacheAd_0// "SPTokenCache.AddCachedToken: The value "...
0x259f1  ldc.i4.1
0x259f2  newarr   [mscorlib]System.Object
0x259f7  stloc.s  5
0x259f9  ldloc.s  5
0x259fb  ldc.i4.0
0x259fc  ldloc.1
0x259fd  stelem.ref
0x259fe  ldloc.s  5
0x25a00  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25a05  ldstr    aValue// "value"
0x25a0a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x25a0f  throw
0x25a10  ldarg.1
0x25a11  ldarg.2
0x25a12  call     string Microsoft.SharePoint.IdentityModel.SPTokenCache::GetCacheKey(string subscriptionId, string userKeyClaimValue)
0x25a17  stloc.2
0x25a18  ldarg.0
0x25a19  ldloc.2
0x25a1a  ldarg.3
0x25a1b  call     instance void Microsoft.SharePoint.IdentityModel.SPTokenCache::AddCachedToken(string cachekey, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry value)
0x25a20  ldc.i4   0x15D662
0x25a25  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25a2a  ldc.i4.s 0x64
0x25a2c  ldstr    aTokenCacheSucc_2// "Token Cache: Successfully added token t"...
0x25a31  ldc.i4.2
0x25a32  newarr   [mscorlib]System.Object
0x25a37  stloc.s  6
0x25a39  ldloc.s  6
0x25a3b  ldc.i4.0
0x25a3c  ldarg.2
0x25a3d  stelem.ref
0x25a3e  ldloc.s  6
0x25a40  ldc.i4.1
0x25a41  ldarg.1
0x25a42  stelem.ref
0x25a43  ldloc.s  6
0x25a45  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25a4a  leave.s  loc_25A83
0x25a4c  stloc.3
0x25a4d  ldc.i4   0x21649A
0x25a52  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25a57  ldc.i4.s 0xF
0x25a59  ldstr    aTokenCacheFail_8// "Token Cache: Failed to add token to cac"...
0x25a5e  ldc.i4.3
0x25a5f  newarr   [mscorlib]System.Object
0x25a64  stloc.s  7
0x25a66  ldloc.s  7
0x25a68  ldc.i4.0
0x25a69  ldarg.2
0x25a6a  stelem.ref
0x25a6b  ldloc.s  7
0x25a6d  ldc.i4.1
0x25a6e  ldarg.1
0x25a6f  stelem.ref
0x25a70  ldloc.s  7
0x25a72  ldc.i4.2
0x25a73  ldloc.3
0x25a74  callvirt instance string [mscorlib]System.Object::ToString()
0x25a79  stelem.ref
0x25a7a  ldloc.s  7
0x25a7c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25a81  leave.s  loc_25A83
0x25a83  ret
```
