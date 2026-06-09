# Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::PutV2

- ea: `0x264f0`
- end: `0x265d0`
- name: `Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::PutV2`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x25bc0`

## callees

- `0x264f0`
- `0x265d0`
- `0x26700`

## string_xrefs

- `0x2656e`: `Weak Reference Cache is enabled....`
- `0x265b1`: `Weak Reference Cache is disabled. Requests will always go to Distributed Cache....`
- `0x264ff`: `SPDistributedSecurityTokenCache.Put: Supplied value was not an SPTokenCacheEntry. Value: '{0}', Type: '{1}'.`
- `0x26596`: `This user is a BOT, search crawler, etc. and we are not adding them to the WFE memory cache.`

## pseudocode

```c

```

## disassembly

```asm
0x264f0  ldarg.2
0x264f1  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry
0x264f6  stloc.0
0x264f7  ldloc.0
0x264f8  brtrue.s loc_26554
0x264fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x264ff  ldstr    aSpdistributeds_0// "SPDistributedSecurityTokenCache.Put: Su"...
0x26504  ldc.i4.2
0x26505  newarr   [mscorlib]System.Object
0x2650a  stloc.2
0x2650b  ldloc.2
0x2650c  ldc.i4.0
0x2650d  ldarg.2
0x2650e  brfalse.s loc_26518
0x26510  ldarg.2
0x26511  callvirt instance string [mscorlib]System.Object::ToString()
0x26516  br.s     loc_2651D
0x26518  ldstr    aNull_0// "Null"
0x2651d  stelem.ref
0x2651e  ldloc.2
0x2651f  ldc.i4.1
0x26520  ldarg.2
0x26521  brfalse.s loc_26530
0x26523  ldarg.2
0x26524  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x26529  callvirt instance string [mscorlib]System.Object::ToString()
0x2652e  br.s     loc_26535
0x26530  ldstr    aNull_0// "Null"
0x26535  stelem.ref
0x26536  ldloc.2
0x26537  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2653c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x26541  stloc.1
0x26542  ldc.i4   0x101785B
0x26547  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x2654c  ldloc.1
0x2654d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, class [mscorlib]System.Exception)
0x26552  ldloc.1
0x26553  throw
0x26554  ldarg.0
0x26555  call     instance bool Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::get_UseWeakRefCache()
0x2655a  brfalse.s loc_265A2
0x2655c  ldarg.3
0x2655d  brfalse.s loc_26587
0x2655f  ldc.i4   0x101785C
0x26564  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x26569  ldc.i4   0xC8
0x2656e  ldstr    aWeakReferenceC// "Weak Reference Cache is enabled...."
0x26573  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x26578  ldarg.0
0x26579  ldfld    class Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::_weakReferenceCache
0x2657e  ldarg.1
0x2657f  ldloc.0
0x26580  callvirt instance void Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache::Add(string key, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry token)
0x26585  br.s     loc_265BB
0x26587  ldc.i4   0x101785D
0x2658c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x26591  ldc.i4   0xC8
0x26596  ldstr    aThisUserIsABot// "This user is a BOT, search crawler, etc"...
0x2659b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x265a0  br.s     loc_265BB
0x265a2  ldc.i4   0x101785E
0x265a7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x265ac  ldc.i4   0xC8
0x265b1  ldstr    aWeakReferenceC_0// "Weak Reference Cache is disabled. Reque"...
0x265b6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x265bb  ldloc.0
0x265bc  ldarg.0
0x265bd  ldfld    class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenSerializer Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::_serializer
0x265c2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::SerializeToken(class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenSerializer)
0x265c7  ldarg.0
0x265c8  ldarg.1
0x265c9  ldloc.0
0x265ca  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.DistributedCaching.SPDataCacheItemVersion [Microsoft.SharePoint]Microsoft.SharePoint.DistributedCaching.SPDistributedCache::Put(string, object)
0x265cf  ret
```
