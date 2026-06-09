# Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::Put

- ea: `0x26420`
- end: `0x264e2`
- name: `Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::Put`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x26420`
- `0x265d0`
- `0x26700`

## string_xrefs

- `0x2649b`: `Weak Reference Cache is enabled....`
- `0x264c3`: `Weak Reference Cache is disabled. Requests will always go to Distributed Cache....`
- `0x2642f`: `SPDistributedSecurityTokenCache.Put: Supplied value was not an SPTokenCacheEntry. Value: '{0}', Type: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x26420  ldarg.2
0x26421  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry
0x26426  stloc.0
0x26427  ldloc.0
0x26428  brtrue.s loc_26484
0x2642a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2642f  ldstr    aSpdistributeds_0// "SPDistributedSecurityTokenCache.Put: Su"...
0x26434  ldc.i4.2
0x26435  newarr   [mscorlib]System.Object
0x2643a  stloc.2
0x2643b  ldloc.2
0x2643c  ldc.i4.0
0x2643d  ldarg.2
0x2643e  brfalse.s loc_26448
0x26440  ldarg.2
0x26441  callvirt instance string [mscorlib]System.Object::ToString()
0x26446  br.s     loc_2644D
0x26448  ldstr    aNull_0// "Null"
0x2644d  stelem.ref
0x2644e  ldloc.2
0x2644f  ldc.i4.1
0x26450  ldarg.2
0x26451  brfalse.s loc_26460
0x26453  ldarg.2
0x26454  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x26459  callvirt instance string [mscorlib]System.Object::ToString()
0x2645e  br.s     loc_26465
0x26460  ldstr    aNull_0// "Null"
0x26465  stelem.ref
0x26466  ldloc.2
0x26467  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2646c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x26471  stloc.1
0x26472  ldc.i4   0x5D48C0
0x26477  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x2647c  ldloc.1
0x2647d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, class [mscorlib]System.Exception)
0x26482  ldloc.1
0x26483  throw
0x26484  ldarg.0
0x26485  call     instance bool Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::get_UseWeakRefCache()
0x2648a  brfalse.s loc_264B4
0x2648c  ldc.i4   0xDE21E
0x26491  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x26496  ldc.i4   0xC8
0x2649b  ldstr    aWeakReferenceC// "Weak Reference Cache is enabled...."
0x264a0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x264a5  ldarg.0
0x264a6  ldfld    class Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::_weakReferenceCache
0x264ab  ldarg.1
0x264ac  ldloc.0
0x264ad  callvirt instance void Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache::Add(string key, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry token)
0x264b2  br.s     loc_264CD
0x264b4  ldc.i4   0xDE21F
0x264b9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x264be  ldc.i4   0xC8
0x264c3  ldstr    aWeakReferenceC_0// "Weak Reference Cache is disabled. Reque"...
0x264c8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x264cd  ldloc.0
0x264ce  ldarg.0
0x264cf  ldfld    class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenSerializer Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::_serializer
0x264d4  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::SerializeToken(class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenSerializer)
0x264d9  ldarg.0
0x264da  ldarg.1
0x264db  ldloc.0
0x264dc  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.DistributedCaching.SPDataCacheItemVersion [Microsoft.SharePoint]Microsoft.SharePoint.DistributedCaching.SPDistributedCache::Put(string, object)
0x264e1  ret
```
