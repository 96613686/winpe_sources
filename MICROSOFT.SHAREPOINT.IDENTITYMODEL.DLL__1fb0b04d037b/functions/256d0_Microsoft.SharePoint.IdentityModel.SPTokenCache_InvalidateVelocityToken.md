# Microsoft.SharePoint.IdentityModel.SPTokenCache::InvalidateVelocityToken

- ea: `0x256d0`
- end: `0x2577f`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::InvalidateVelocityToken`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x25690`

## callees

- `0x256d0`
- `0x26030`
- `0x26050`
- `0x26300`

## string_xrefs

- `0x256ee`: `cacheKey`
- `0x256e4`: `InvalidateVelocityToken: Invalid cacheKey.`
- `0x25713`: `InvalidateVelocityToken: Distributed cache is not available.`
- `0x2575b`: `Invalidating velocity cache for entry. Key: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x256d0  ldarg.1
0x256d1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x256d6  brfalse.s loc_256F9
0x256d8  ldc.i4   0x89470C
0x256dd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x256e2  ldc.i4.s 0xA
0x256e4  ldstr    aInvalidatevelo_0// "InvalidateVelocityToken: Invalid cacheK"...
0x256e9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x256ee  ldstr    aCachekey_0// "cacheKey"
0x256f3  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x256f8  throw
0x256f9  call     bool Microsoft.SharePoint.IdentityModel.SPTokenCache::get_UseDistributedCache()
0x256fe  brfalse.s loc_25707
0x25700  ldsfld   bool Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCacheInitializer::IsInitialized
0x25705  brtrue.s loc_2571E
0x25707  ldc.i4   0x89470D
0x2570c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25711  ldc.i4.s 0x32
0x25713  ldstr    aInvalidatevelo_1// "InvalidateVelocityToken: Distributed ca"...
0x25718  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2571d  ret
0x2571e  ldarg.0
0x2571f  call     instance class Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_DistributedTokenCache()
0x25724  ldarg.1
0x25725  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::GetObject(string key)
0x2572a  brtrue.s loc_2574F
0x2572c  ldc.i4   0x89470E
0x25731  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25736  ldc.i4.s 0x32
0x25738  ldstr    aDidNotFindAnEn// "Did not find an entry in velocity with "...
0x2573d  ldc.i4.1
0x2573e  newarr   [mscorlib]System.Object
0x25743  stloc.0
0x25744  ldloc.0
0x25745  ldc.i4.0
0x25746  ldarg.1
0x25747  stelem.ref
0x25748  ldloc.0
0x25749  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2574e  ret
0x2574f  ldc.i4   0x89470F
0x25754  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25759  ldc.i4.s 0x14
0x2575b  ldstr    aInvalidatingVe// "Invalidating velocity cache for entry. "...
0x25760  ldc.i4.1
0x25761  newarr   [mscorlib]System.Object
0x25766  stloc.1
0x25767  ldloc.1
0x25768  ldc.i4.0
0x25769  ldarg.1
0x2576a  stelem.ref
0x2576b  ldloc.1
0x2576c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25771  ldarg.0
0x25772  call     instance class Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_DistributedTokenCache()
0x25777  ldarg.1
0x25778  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.DistributedCaching.SPDistributedCache::Remove(string)
0x2577d  pop
0x2577e  ret
```
