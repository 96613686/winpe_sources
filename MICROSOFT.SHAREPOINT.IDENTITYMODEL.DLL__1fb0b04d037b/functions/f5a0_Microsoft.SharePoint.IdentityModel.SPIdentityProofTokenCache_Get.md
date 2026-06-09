# Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache::Get

- ea: `0xf5a0`
- end: `0xf648`
- name: `Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache::Get`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf510`

## callees

- `0xf5a0`
- `0xf900`

## string_xrefs

- `0xf5c1`: `cacheKey == localIssuerCacheKey`
- `0xf5a9`: `cacheKey`
- `0xf5e7`: `SPIdentityProofTokenCache: Couldn't find a cached item with cachekey '{0}'.`
- `0xf622`: `SPIdentityProofTokenCache: Successfully retrieved a cached item with cachekey '{0}'. Cached item: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xf5a0  ldnull
0xf5a1  ldarg.1
0xf5a2  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity, class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity)
0xf5a7  brfalse.s loc_F5B4
0xf5a9  ldstr    aCachekey_0// "cacheKey"
0xf5ae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf5b3  throw
0xf5b4  ldarg.1
0xf5b5  ldsfld   class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache::s_LocalIssuerCacheKey
0xf5ba  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity, class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity)
0xf5bf  brfalse.s loc_F5CC
0xf5c1  ldstr    aCachekeyLocali// "cacheKey == localIssuerCacheKey"
0xf5c6  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xf5cb  throw
0xf5cc  ldsfld   class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWeakReferenceMruCache`2<class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity, class Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem> Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache::s_Cache
0xf5d1  ldarg.1
0xf5d2  ldloca.s 0
0xf5d4  callvirt instance bool class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWeakReferenceMruCache`2<class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity, class Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem>::TryGetValue(var<u1>, !!T0)
0xf5d9  brtrue.s loc_F608
0xf5db  ldc.i4   0x45615D
0xf5e0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0xf5e5  ldc.i4.s 0x64
0xf5e7  ldstr    aSpidentityproo_0// "SPIdentityProofTokenCache: Couldn't fin"...
0xf5ec  ldc.i4.1
0xf5ed  newarr   [mscorlib]System.Object
0xf5f2  stloc.1
0xf5f3  ldloc.1
0xf5f4  ldc.i4.0
0xf5f5  ldarg.1
0xf5f6  callvirt instance string [mscorlib]System.Object::ToString()
0xf5fb  stelem.ref
0xf5fc  ldloc.1
0xf5fd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xf602  newobj   instance void Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItemNotFoundException::.ctor()
0xf607  throw
0xf608  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0xf60d  ldc.i4.s 0x64
0xf60f  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::ShouldTrace(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xf614  brfalse.s loc_F646
0xf616  ldc.i4   0x45615E
0xf61b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0xf620  ldc.i4.s 0x64
0xf622  ldstr    aSpidentityproo_1// "SPIdentityProofTokenCache: Successfully"...
0xf627  ldc.i4.2
0xf628  newarr   [mscorlib]System.Object
0xf62d  stloc.2
0xf62e  ldloc.2
0xf62f  ldc.i4.0
0xf630  ldarg.1
0xf631  callvirt instance string [mscorlib]System.Object::ToString()
0xf636  stelem.ref
0xf637  ldloc.2
0xf638  ldc.i4.1
0xf639  ldloc.0
0xf63a  callvirt instance string [mscorlib]System.Object::ToString()
0xf63f  stelem.ref
0xf640  ldloc.2
0xf641  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xf646  ldloc.0
0xf647  ret
```
