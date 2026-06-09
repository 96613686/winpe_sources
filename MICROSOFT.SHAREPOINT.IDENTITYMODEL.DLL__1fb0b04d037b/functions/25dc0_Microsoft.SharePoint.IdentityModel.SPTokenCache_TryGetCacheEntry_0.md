# Microsoft.SharePoint.IdentityModel.SPTokenCache::TryGetCacheEntry_0

- ea: `0x25dc0`
- end: `0x25f77`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::TryGetCacheEntry_0`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x258c0`

## callees

- `0x25dc0`
- `0x26030`
- `0x26040`
- `0x26050`
- `0x26300`
- `0x26690`

## string_xrefs

- `0x25e07`: `Token Cache: Failed to get token from distributed cache. Key: '{0}'.(This is expected during the process warm up or if data cache Initialization is getting done by some other thread).`
- `0x25e2c`: `Token Cache: Reverting to local cache to get the token. Key: '{0}'.`
- `0x25ede`: `Token Cache: Reverting to local cache to get the token. Key: '{0}'.`
- `0x25e6e`: `Token Cache: Failed to get token from distributed cache. Key: '{0}'. (This is expected during the process warm up or if data cache Initialization is getting done by some other thread). If this occurs upwards of 1000 times in 60 seconds engage the Distributed Cache team to reset the cache cluster. Exception: '{1}'.`
- `0x25eaf`: `Token Cache: Failed to get token from distributed cache. Key: '{0}'.(This is expected during the process warm up or if data cache Initialization is getting done by some other thread). Exception: '{1}'.`
- `0x25f2f`: `Token Cache: Got token from cache. CacheType: '{0}'.`
- `0x25f59`: `Token Cache: Failed to get token from cache. CacheType: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x25dc0  ldnull
0x25dc1  stloc.0
0x25dc2  ldsfld   string [mscorlib]System.String::Empty
0x25dc7  stloc.1
0x25dc8  call     bool Microsoft.SharePoint.IdentityModel.SPTokenCache::get_UseDistributedCache()
0x25dcd  brfalse  loc_25F08
0x25dd2  ldstr    aDistributed// "distributed"
0x25dd7  stloc.1
0x25dd8  ldsfld   bool Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCacheInitializer::IsInitialized
0x25ddd  brfalse.s loc_25DFB
0x25ddf  ldarg.0
0x25de0  call     instance class Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_DistributedTokenCache()
0x25de5  ldarg.1
0x25de6  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::GetObject(string key)
0x25deb  stloc.2
0x25dec  ldloc.2
0x25ded  brtrue.s loc_25DF7
0x25def  ldnull
0x25df0  stloc.s  5
0x25df2  leave    loc_25F74
0x25df7  ldloc.2
0x25df8  stloc.0
0x25df9  br.s     loc_25E54
0x25dfb  ldc.i4   0x211780
0x25e00  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x25e05  ldc.i4.s 0xF
0x25e07  ldstr    aTokenCacheFail_11// "Token Cache: Failed to get token from d"...
0x25e0c  ldc.i4.1
0x25e0d  newarr   [mscorlib]System.Object
0x25e12  stloc.s  6
0x25e14  ldloc.s  6
0x25e16  ldc.i4.0
0x25e17  ldarg.1
0x25e18  stelem.ref
0x25e19  ldloc.s  6
0x25e1b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25e20  ldc.i4   0x211781
0x25e25  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x25e2a  ldc.i4.s 0xF
0x25e2c  ldstr    aTokenCacheReve_0// "Token Cache: Reverting to local cache t"...
0x25e31  ldc.i4.1
0x25e32  newarr   [mscorlib]System.Object
0x25e37  stloc.s  7
0x25e39  ldloc.s  7
0x25e3b  ldc.i4.0
0x25e3c  ldarg.1
0x25e3d  stelem.ref
0x25e3e  ldloc.s  7
0x25e40  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25e45  ldarg.0
0x25e46  call     instance class Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_WFETokenCache()
0x25e4b  ldarg.1
0x25e4c  ldloca.s 0
0x25e4e  callvirt instance object Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache::TryGetValue(string key, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry& result)
0x25e53  pop
0x25e54  leave    loc_25F1D
0x25e59  stloc.3
0x25e5a  ldc.i4   0x3767
0x25e5f  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x25e64  brfalse.s loc_25EA3
0x25e66  ldc.i4.1
0x25e67  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPGlobal::GetIsSPO(bool)
0x25e6c  brfalse.s loc_25EA3
0x25e6e  ldstr    aTokenCacheFail_12// "Token Cache: Failed to get token from d"...
0x25e73  stloc.s  4
0x25e75  ldc.i4   0x1359820
0x25e7a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x25e7f  ldc.i4.s 0xF
0x25e81  ldloc.s  4
0x25e83  ldc.i4.2
0x25e84  newarr   [mscorlib]System.Object
0x25e89  stloc.s  8
0x25e8b  ldloc.s  8
0x25e8d  ldc.i4.0
0x25e8e  ldarg.1
0x25e8f  stelem.ref
0x25e90  ldloc.s  8
0x25e92  ldc.i4.1
0x25e93  ldloc.3
0x25e94  callvirt instance string [mscorlib]System.Object::ToString()
0x25e99  stelem.ref
0x25e9a  ldloc.s  8
0x25e9c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25ea1  br.s     loc_25ED2
0x25ea3  ldc.i4   0x211782
0x25ea8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x25ead  ldc.i4.s 0x32
0x25eaf  ldstr    aTokenCacheFail_13// "Token Cache: Failed to get token from d"...
0x25eb4  ldc.i4.2
0x25eb5  newarr   [mscorlib]System.Object
0x25eba  stloc.s  9
0x25ebc  ldloc.s  9
0x25ebe  ldc.i4.0
0x25ebf  ldarg.1
0x25ec0  stelem.ref
0x25ec1  ldloc.s  9
0x25ec3  ldc.i4.1
0x25ec4  ldloc.3
0x25ec5  callvirt instance string [mscorlib]System.Object::ToString()
0x25eca  stelem.ref
0x25ecb  ldloc.s  9
0x25ecd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25ed2  ldc.i4   0x211783
0x25ed7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x25edc  ldc.i4.s 0x32
0x25ede  ldstr    aTokenCacheReve_0// "Token Cache: Reverting to local cache t"...
0x25ee3  ldc.i4.1
0x25ee4  newarr   [mscorlib]System.Object
0x25ee9  stloc.s  0xA
0x25eeb  ldloc.s  0xA
0x25eed  ldc.i4.0
0x25eee  ldarg.1
0x25eef  stelem.ref
0x25ef0  ldloc.s  0xA
0x25ef2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25ef7  ldarg.0
0x25ef8  call     instance class Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_WFETokenCache()
0x25efd  ldarg.1
0x25efe  ldloca.s 0
0x25f00  callvirt instance object Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache::TryGetValue(string key, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry& result)
0x25f05  pop
0x25f06  leave.s  loc_25F1D
0x25f08  ldstr    aLocal// "local"
0x25f0d  stloc.1
0x25f0e  ldarg.0
0x25f0f  call     instance class Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_WFETokenCache()
0x25f14  ldarg.1
0x25f15  ldloca.s 0
0x25f17  callvirt instance object Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache::TryGetValue(string key, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry& result)
0x25f1c  pop
0x25f1d  ldloc.0
0x25f1e  brfalse.s loc_25F4A
0x25f20  ldc.i4   0x15D68B
0x25f25  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25f2a  ldc.i4   0xC8
0x25f2f  ldstr    aTokenCacheGotT// "Token Cache: Got token from cache. Cach"...
0x25f34  ldc.i4.1
0x25f35  newarr   [mscorlib]System.Object
0x25f3a  stloc.s  0xB
0x25f3c  ldloc.s  0xB
0x25f3e  ldc.i4.0
0x25f3f  ldloc.1
0x25f40  stelem.ref
0x25f41  ldloc.s  0xB
0x25f43  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25f48  br.s     loc_25F72
0x25f4a  ldc.i4   0x15D68C
0x25f4f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25f54  ldc.i4   0xC8
0x25f59  ldstr    aTokenCacheFail_14// "Token Cache: Failed to get token from c"...
0x25f5e  ldc.i4.1
0x25f5f  newarr   [mscorlib]System.Object
0x25f64  stloc.s  0xC
0x25f66  ldloc.s  0xC
0x25f68  ldc.i4.0
0x25f69  ldloc.1
0x25f6a  stelem.ref
0x25f6b  ldloc.s  0xC
0x25f6d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25f72  ldloc.0
0x25f73  ret
0x25f74  ldloc.s  5
0x25f76  ret
```
