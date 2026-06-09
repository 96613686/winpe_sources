# Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::GetObject

- ea: `0x26300`
- end: `0x26420`
- name: `Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::GetObject`
- size: `288`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x256d0`
- `0x25dc0`

## callees

- `0x26070`
- `0x26300`
- `0x265d0`
- `0x26690`
- `0x26700`

## string_xrefs

- `0x26318`: `Weak Reference Cache is enabled....`
- `0x2633f`: `Weak Reference Cache is disabled. Requests will always go to Distributed Cache....`
- `0x2639f`: `SPDistributedSecurityTokenCache.GetObject: Deserialized token was null. Returning null.`

## pseudocode

```c

```

## disassembly

```asm
0x26300  ldnull
0x26301  stloc.0
0x26302  ldc.i4.0
0x26303  stloc.1
0x26304  ldarg.0
0x26305  call     instance bool Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::get_UseWeakRefCache()
0x2630a  brfalse.s loc_26333
0x2630c  ldc.i4   0xDE21C
0x26311  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x26316  ldc.i4.s 0x64
0x26318  ldstr    aWeakReferenceC// "Weak Reference Cache is enabled...."
0x2631d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x26322  ldarg.0
0x26323  ldfld    class Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::_weakReferenceCache
0x26328  ldarg.1
0x26329  ldloca.s 0
0x2632b  callvirt instance object Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache::TryGetValue(string key, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry& result)
0x26330  pop
0x26331  br.s     loc_26349
0x26333  ldc.i4   0xDE21D
0x26338  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x2633d  ldc.i4.s 0x64
0x2633f  ldstr    aWeakReferenceC_0// "Weak Reference Cache is disabled. Reque"...
0x26344  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x26349  ldloc.0
0x2634a  brtrue   loc_2641B
0x2634f  ldarg.0
0x26350  ldarg.1
0x26351  call     T0x2B000020
0x26356  stloc.2
0x26357  ldloc.2
0x26358  brtrue.s loc_26363
0x2635a  ldloc.1
0x2635b  ldc.i4.4
0x2635c  or
0x2635d  stloc.1
0x2635e  br       loc_26415
0x26363  ldloc.1
0x26364  ldc.i4.5
0x26365  or
0x26366  stloc.1
0x26367  ldloc.2
0x26368  stloc.0
0x26369  ldloc.0
0x2636a  brtrue.s loc_263C2
0x2636c  ldloc.2
0x2636d  callvirt instance string [mscorlib]System.Object::ToString()
0x26372  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x26377  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x2637c  stloc.3
0x2637d  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.ServiceConfiguration [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.FederatedAuthentication::get_ServiceConfiguration()
0x26382  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.ServiceConfiguration::get_SecurityTokenHandlers()
0x26387  ldloc.3
0x26388  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollection::ReadToken(class [System.Xml]System.Xml.XmlReader)
0x2638d  stloc.s  4
0x2638f  ldloc.s  4
0x26391  brtrue.s loc_263AE
0x26393  ldc.i4   0x5D48A3
0x26398  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x2639d  ldc.i4.s 0xF
0x2639f  ldstr    aSpdistributeds// "SPDistributedSecurityTokenCache.GetObje"...
0x263a4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x263a9  ldnull
0x263aa  stloc.s  5
0x263ac  leave.s  loc_2641D
0x263ae  ldloc.s  4
0x263b0  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0x263b5  stloc.0
0x263b6  leave.s  loc_263C2
0x263b8  ldloc.3
0x263b9  brfalse.s loc_263C1
0x263bb  ldloc.3
0x263bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x263c1  endfinally
0x263c2  ldloc.0
0x263c3  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::get_Token()
0x263c8  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0x263cd  stloc.s  6
0x263cf  ldloca.s 6
0x263d1  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x263d6  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x263db  stloc.s  7
0x263dd  ldloca.s 7
0x263df  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x263e4  sub
0x263e5  ldarg.0
0x263e6  ldfld    int64 Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::_minimumTokenExpirationWindow
0x263eb  bge.s    loc_263F5
0x263ed  ldloc.1
0x263ee  ldc.i4.6
0x263ef  or
0x263f0  stloc.1
0x263f1  ldnull
0x263f2  stloc.0
0x263f3  br.s     loc_26415
0x263f5  ldarg.0
0x263f6  call     instance bool Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::get_UseWeakRefCache()
0x263fb  brfalse.s loc_26415
0x263fd  ldarg.0
0x263fe  ldfld    class Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::_weakReferenceCache
0x26403  ldarg.1
0x26404  ldarg.0
0x26405  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.DistributedCaching.SPDistributedCache::get_AdditionalMarker()
0x2640a  call     string [mscorlib]System.String::Concat(string, string)
0x2640f  ldloc.0
0x26410  callvirt instance void Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache::Add(string key, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry token)
0x26415  ldloc.1
0x26416  call     void Microsoft.SharePoint.IdentityModel.SPTokenCache::RecordCacheEvent(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPClaimsAuthenticationTimeCategory eventCategory)
0x2641b  ldloc.0
0x2641c  ret
0x2641d  ldloc.s  5
0x2641f  ret
```
