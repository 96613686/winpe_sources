# Microsoft.SharePoint.IdentityModel.SPTokenCache::AddCachedTokenV1

- ea: `0x25ab0`
- end: `0x25bba`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::AddCachedTokenV1`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x25a90`

## callees

- `0x25ab0`
- `0x26030`
- `0x26040`
- `0x26050`
- `0x26700`

## string_xrefs

- `0x25ad5`: `Token Cache: Added token to distributed cache.`
- `0x25ae9`: `Token Cache: Failed to add token from distributed cache. Key: '{0}'.(This is expected during the process warm up or if data cache Initialization is getting done by some other thread).`
- `0x25b0b`: `Token Cache: Reverting to local cache to Add the token. Key: '{0}'.`
- `0x25b6c`: `Token Cache: Reverting to local cache to Add the token. Key: '{0}'.`
- `0x25b3d`: `Token Cache: Failed to add token from distributed cache. Key: '{0}', Exception: '{1}'.`
- `0x25ba1`: `Token Cache: Added token to local cache.`

## pseudocode

```c

```

## disassembly

```asm
0x25ab0  ldsfld   string [mscorlib]System.String::Empty
0x25ab5  stloc.0
0x25ab6  call     bool Microsoft.SharePoint.IdentityModel.SPTokenCache::get_UseDistributedCache()
0x25abb  brfalse  loc_25B94
0x25ac0  ldsfld   bool Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCacheInitializer::IsInitialized
0x25ac5  brfalse.s loc_25ADD
0x25ac7  ldarg.0
0x25ac8  call     instance class Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_DistributedTokenCache()
0x25acd  ldarg.1
0x25ace  ldarg.2
0x25acf  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.DistributedCaching.SPDataCacheItemVersion [Microsoft.SharePoint]Microsoft.SharePoint.DistributedCaching.SPDistributedCache::Put(string, object)
0x25ad4  pop
0x25ad5  ldstr    aTokenCacheAdde// "Token Cache: Added token to distributed"...
0x25ada  stloc.0
0x25adb  br.s     loc_25B2E
0x25add  ldc.i4   0x211760
0x25ae2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x25ae7  ldc.i4.s 0xF
0x25ae9  ldstr    aTokenCacheFail_9// "Token Cache: Failed to add token from d"...
0x25aee  ldc.i4.1
0x25aef  newarr   [mscorlib]System.Object
0x25af4  stloc.2
0x25af5  ldloc.2
0x25af6  ldc.i4.0
0x25af7  ldarg.1
0x25af8  stelem.ref
0x25af9  ldloc.2
0x25afa  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25aff  ldc.i4   0x211761
0x25b04  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x25b09  ldc.i4.s 0xF
0x25b0b  ldstr    aTokenCacheReve// "Token Cache: Reverting to local cache t"...
0x25b10  ldc.i4.1
0x25b11  newarr   [mscorlib]System.Object
0x25b16  stloc.3
0x25b17  ldloc.3
0x25b18  ldc.i4.0
0x25b19  ldarg.1
0x25b1a  stelem.ref
0x25b1b  ldloc.3
0x25b1c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25b21  ldarg.0
0x25b22  call     instance class Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_WFETokenCache()
0x25b27  ldarg.1
0x25b28  ldarg.2
0x25b29  callvirt instance void Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache::Add(string key, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry token)
0x25b2e  leave.s  loc_25BA7
0x25b30  stloc.1
0x25b31  ldc.i4   0x211762
0x25b36  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x25b3b  ldc.i4.s 0x32
0x25b3d  ldstr    aTokenCacheFail_10// "Token Cache: Failed to add token from d"...
0x25b42  ldc.i4.2
0x25b43  newarr   [mscorlib]System.Object
0x25b48  stloc.s  4
0x25b4a  ldloc.s  4
0x25b4c  ldc.i4.0
0x25b4d  ldarg.1
0x25b4e  stelem.ref
0x25b4f  ldloc.s  4
0x25b51  ldc.i4.1
0x25b52  ldloc.1
0x25b53  callvirt instance string [mscorlib]System.Object::ToString()
0x25b58  stelem.ref
0x25b59  ldloc.s  4
0x25b5b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25b60  ldc.i4   0x211763
0x25b65  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x25b6a  ldc.i4.s 0x32
0x25b6c  ldstr    aTokenCacheReve// "Token Cache: Reverting to local cache t"...
0x25b71  ldc.i4.1
0x25b72  newarr   [mscorlib]System.Object
0x25b77  stloc.s  5
0x25b79  ldloc.s  5
0x25b7b  ldc.i4.0
0x25b7c  ldarg.1
0x25b7d  stelem.ref
0x25b7e  ldloc.s  5
0x25b80  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25b85  ldarg.0
0x25b86  call     instance class Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_WFETokenCache()
0x25b8b  ldarg.1
0x25b8c  ldarg.2
0x25b8d  callvirt instance void Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache::Add(string key, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry token)
0x25b92  leave.s  loc_25BA7
0x25b94  ldarg.0
0x25b95  call     instance class Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_WFETokenCache()
0x25b9a  ldarg.1
0x25b9b  ldarg.2
0x25b9c  callvirt instance void Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache::Add(string key, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry token)
0x25ba1  ldstr    aTokenCacheAdde_0// "Token Cache: Added token to local cache"...
0x25ba6  stloc.0
0x25ba7  ldc.i4   0x15D68A
0x25bac  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25bb1  ldc.i4.s 0x64
0x25bb3  ldloc.0
0x25bb4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x25bb9  ret
```
