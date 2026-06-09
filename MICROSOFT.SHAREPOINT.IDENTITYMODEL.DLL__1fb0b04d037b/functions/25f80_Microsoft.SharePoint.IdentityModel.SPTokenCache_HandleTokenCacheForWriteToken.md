# Microsoft.SharePoint.IdentityModel.SPTokenCache::HandleTokenCacheForWriteToken

- ea: `0x25f80`
- end: `0x26023`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::HandleTokenCacheForWriteToken`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x23170`

## callees

- `0x22b00`
- `0x22c40`
- `0x25990`
- `0x25f80`
- `0x2c520`

## string_xrefs

- `0x25f8f`: `sessionToken`
- `0x25f9f`: `SPTokenCacheDontCacheToken`
- `0x25fc5`: `SPTokenCacheDontCacheToken`
- `0x25fb7`: `Token Cache: Not adding token to cache because key value is not null. Key: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x25f80  ldc.i4   0x13C5412
0x25f85  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x25f8a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25f8f  ldstr    aSessiontoken// "sessionToken"
0x25f94  ldarg.2
0x25f95  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x25f9a  call     class [mscorlib]System.Collections.IDictionary [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPThreadContext::get_Items()
0x25f9f  ldstr    aSptokencachedo// "SPTokenCacheDontCacheToken"
0x25fa4  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x25fa9  brfalse.s loc_25FD2
0x25fab  ldc.i4   0x25E680
0x25fb0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25fb5  ldc.i4.s 0x64
0x25fb7  ldstr    aTokenCacheNotA// "Token Cache: Not adding token to cache "...
0x25fbc  ldc.i4.1
0x25fbd  newarr   [mscorlib]System.Object
0x25fc2  stloc.1
0x25fc3  ldloc.1
0x25fc4  ldc.i4.0
0x25fc5  ldstr    aSptokencachedo// "SPTokenCacheDontCacheToken"
0x25fca  stelem.ref
0x25fcb  ldloc.1
0x25fcc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25fd1  ret
0x25fd2  ldarg.1
0x25fd3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25fd8  brtrue.s loc_26022
0x25fda  ldarg.2
0x25fdb  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0x25fe0  stloc.0
0x25fe1  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPTokenCache::SiteLoadKillSwitch
0x25fe6  ldstr    a7242017// "7/24/2017"
0x25feb  ldstr    aUseTheOldWayOf// "Use the old way of doing this."
0x25ff0  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x25ff5  brfalse.s loc_2600F
0x25ff7  ldarg.0
0x25ff8  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x25ffd  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x26002  call     string Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSubscriptionIdFromContext(string context)
0x26007  ldarg.1
0x26008  ldloc.0
0x26009  call     instance void Microsoft.SharePoint.IdentityModel.SPTokenCache::AddCachedToken(string subscriptionId, string identity, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry value)
0x2600e  ret
0x2600f  ldarg.0
0x26010  ldarg.0
0x26011  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x26016  callvirt instance string Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSiteSubscriptionIdFromUri(class [System]System.Uri context)
0x2601b  ldarg.1
0x2601c  ldloc.0
0x2601d  call     instance void Microsoft.SharePoint.IdentityModel.SPTokenCache::AddCachedToken(string subscriptionId, string identity, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry value)
0x26022  ret
```
