# Microsoft.SharePoint.IdentityModel.SPTokenCache::TryGetCacheEntry

- ea: `0x258c0`
- end: `0x2598d`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::TryGetCacheEntry`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x22230`
- `0x258a0`

## callees

- `0x25820`
- `0x258c0`
- `0x25dc0`

## string_xrefs

- `0x258dc`: `SPTokenCache.TryGetCachedToken: The identity is null. Stack: '{0}'.`
- `0x25921`: `Token Cache: {0} a token from cache. Identity: '{1}', SiteSubscription: '{2}'.`
- `0x25961`: `Token Cache: Failed to get token from cache. Identity: '{0}', SiteSubscription: '{1}', Exception: '{2}'.`

## pseudocode

```c

```

## disassembly

```asm
0x258c0  ldarg.2
0x258c1  brtrue.s loc_25900
0x258c3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x258c8  ldc.i4.s 0xA
0x258ca  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0x258cf  stloc.0
0x258d0  ldc.i4   0x20F888
0x258d5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x258da  ldc.i4.s 0xA
0x258dc  ldstr    aSptokencacheTr// "SPTokenCache.TryGetCachedToken: The ide"...
0x258e1  ldc.i4.1
0x258e2  newarr   [mscorlib]System.Object
0x258e7  stloc.s  4
0x258e9  ldloc.s  4
0x258eb  ldc.i4.0
0x258ec  ldloc.0
0x258ed  stelem.ref
0x258ee  ldloc.s  4
0x258f0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x258f5  ldstr    aIdentity// "identity"
0x258fa  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x258ff  throw
0x25900  ldnull
0x25901  stloc.1
0x25902  ldarg.1
0x25903  ldarg.2
0x25904  call     string Microsoft.SharePoint.IdentityModel.SPTokenCache::GetCacheKey(string subscriptionId, string userKeyClaimValue)
0x25909  stloc.2
0x2590a  ldarg.0
0x2590b  ldloc.2
0x2590c  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry Microsoft.SharePoint.IdentityModel.SPTokenCache::TryGetCacheEntry(string cacheKey)
0x25911  stloc.1
0x25912  ldc.i4   0x15D661
0x25917  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2591c  ldc.i4   0xC8
0x25921  ldstr    aTokenCache0ATo// "Token Cache: {0} a token from cache. Id"...
0x25926  ldc.i4.3
0x25927  newarr   [mscorlib]System.Object
0x2592c  stloc.s  5
0x2592e  ldloc.s  5
0x25930  ldc.i4.0
0x25931  ldloc.1
0x25932  brfalse.s loc_2593B
0x25934  ldstr    aGot// "Got"
0x25939  br.s     loc_25940
0x2593b  ldstr    aDidNotGet// "Did not get"
0x25940  stelem.ref
0x25941  ldloc.s  5
0x25943  ldc.i4.1
0x25944  ldarg.2
0x25945  stelem.ref
0x25946  ldloc.s  5
0x25948  ldc.i4.2
0x25949  ldarg.1
0x2594a  stelem.ref
0x2594b  ldloc.s  5
0x2594d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25952  leave.s  loc_2598B
0x25954  stloc.3
0x25955  ldc.i4   0x216499
0x2595a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2595f  ldc.i4.s 0xF
0x25961  ldstr    aTokenCacheFail_7// "Token Cache: Failed to get token from c"...
0x25966  ldc.i4.3
0x25967  newarr   [mscorlib]System.Object
0x2596c  stloc.s  6
0x2596e  ldloc.s  6
0x25970  ldc.i4.0
0x25971  ldarg.2
0x25972  stelem.ref
0x25973  ldloc.s  6
0x25975  ldc.i4.1
0x25976  ldarg.1
0x25977  stelem.ref
0x25978  ldloc.s  6
0x2597a  ldc.i4.2
0x2597b  ldloc.3
0x2597c  callvirt instance string [mscorlib]System.Object::ToString()
0x25981  stelem.ref
0x25982  ldloc.s  6
0x25984  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25989  leave.s  loc_2598B
0x2598b  ldloc.1
0x2598c  ret
```
