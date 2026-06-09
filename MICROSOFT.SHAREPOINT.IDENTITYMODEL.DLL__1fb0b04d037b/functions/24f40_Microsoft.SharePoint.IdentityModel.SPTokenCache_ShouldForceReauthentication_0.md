# Microsoft.SharePoint.IdentityModel.SPTokenCache::ShouldForceReauthentication_0

- ea: `0x24f40`
- end: `0x25122`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::ShouldForceReauthentication_0`
- size: `482`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x244f0`
- `0x24c50`

## callees

- `0x20660`
- `0x206a0`
- `0x21b70`
- `0x22690`
- `0x24f40`

## string_xrefs

- `0x24f51`: `Token Cache: The RequestData is null.`
- `0x24f6f`: `Token Cache: The tokenKind is None.`
- `0x24f93`: `Token Cache: The CacheEntry is null.`
- `0x24fb6`: `Token Cache: The CookieValue is null.`
- `0x24fe7`: `Token Cache: Token has never received a revocation signal. Requestor does not need to reauthenticate.`
- `0x25017`: `Token Cache: Cookie valid-from time is absent. Requestor must reauthenticate. Username: <name>'{0}'</name>.`
- `0x25086`: `Token Cache: Cookie valid-from time is older than token valid-from time. Requestor must reauthenticate. Username: <name>'{0}'</name>, Cookie (UTC): '{1}', ValidFrom (UTC): '{2}'.`

## pseudocode

```c

```

## disassembly

```asm
0x24f40  ldc.i4.0
0x24f41  stloc.0
0x24f42  ldarg.1
0x24f43  brtrue.s loc_24F60
0x24f45  ldc.i4   0x5E34CB
0x24f4a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24f4f  ldc.i4.s 0xA
0x24f51  ldstr    aTokenCacheTheR_0// "Token Cache: The RequestData is null."
0x24f56  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24f5b  br       loc_25120
0x24f60  ldarg.2
0x24f61  brtrue.s loc_24F7E
0x24f63  ldc.i4   0x6D31DA
0x24f68  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24f6d  ldc.i4.s 0xA
0x24f6f  ldstr    aTokenCacheTheT_3// "Token Cache: The tokenKind is None."
0x24f74  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24f79  br       loc_25120
0x24f7e  ldarg.1
0x24f7f  ldarg.2
0x24f80  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::GetCacheEntry(valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind kind)
0x24f85  brtrue.s loc_24FA2
0x24f87  ldc.i4   0x5E34CC
0x24f8c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24f91  ldc.i4.s 0xA
0x24f93  ldstr    aTokenCacheTheC_4// "Token Cache: The CacheEntry is null."
0x24f98  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24f9d  br       loc_25120
0x24fa2  ldarg.1
0x24fa3  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24fa8  brtrue.s loc_24FC5
0x24faa  ldc.i4   0x5E34CD
0x24faf  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24fb4  ldc.i4.s 0xA
0x24fb6  ldstr    aTokenCacheTheC_5// "Token Cache: The CookieValue is null."
0x24fbb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24fc0  br       loc_25120
0x24fc5  ldarg.1
0x24fc6  ldarg.2
0x24fc7  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::GetCacheEntry(valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind kind)
0x24fcc  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::get_AuthenticationValidFromUtc()
0x24fd1  stloc.1
0x24fd2  ldloca.s 1
0x24fd4  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x24fd9  brtrue.s loc_24FF6
0x24fdb  ldc.i4   0x5E34CE
0x24fe0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24fe5  ldc.i4.s 0x64
0x24fe7  ldstr    aTokenCacheToke_6// "Token Cache: Token has never received a"...
0x24fec  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24ff1  br       loc_25120
0x24ff6  ldarg.1
0x24ff7  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24ffc  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_AuthenticationValidFromUtc()
0x25001  stloc.2
0x25002  ldloca.s 2
0x25004  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x25009  brtrue.s loc_25047
0x2500b  ldc.i4   0x5E34CF
0x25010  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25015  ldc.i4.s 0x32
0x25017  ldstr    aTokenCacheCook_12// "Token Cache: Cookie valid-from time is "...
0x2501c  ldc.i4.1
0x2501d  newarr   [mscorlib]System.Object
0x25022  stloc.3
0x25023  ldloc.3
0x25024  ldc.i4.0
0x25025  ldarg.1
0x25026  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2502b  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x25030  dup
0x25031  brtrue.s loc_25039
0x25033  pop
0x25034  ldsfld   string [mscorlib]System.String::Empty
0x25039  stelem.ref
0x2503a  ldloc.3
0x2503b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25040  ldc.i4.1
0x25041  stloc.0
0x25042  br       loc_25120
0x25047  ldarg.1
0x25048  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2504d  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_AuthenticationValidFromUtc()
0x25052  stloc.s  4
0x25054  ldloca.s 4
0x25056  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x2505b  ldarg.1
0x2505c  ldarg.2
0x2505d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::GetCacheEntry(valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind kind)
0x25062  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::get_AuthenticationValidFromUtc()
0x25067  stloc.s  5
0x25069  ldloca.s 5
0x2506b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x25070  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x25075  brfalse  loc_25120
0x2507a  ldc.i4   0x5E34D0
0x2507f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25084  ldc.i4.s 0xF
0x25086  ldstr    aTokenCacheCook_13// "Token Cache: Cookie valid-from time is "...
0x2508b  ldc.i4.3
0x2508c  newarr   [mscorlib]System.Object
0x25091  stloc.s  6
0x25093  ldloc.s  6
0x25095  ldc.i4.0
0x25096  ldarg.1
0x25097  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x2509c  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x250a1  dup
0x250a2  brtrue.s loc_250AA
0x250a4  pop
0x250a5  ldsfld   string [mscorlib]System.String::Empty
0x250aa  stelem.ref
0x250ab  ldloc.s  6
0x250ad  ldc.i4.1
0x250ae  ldarg.1
0x250af  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x250b4  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_AuthenticationValidFromUtc()
0x250b9  stloc.s  7
0x250bb  ldloca.s 7
0x250bd  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x250c2  brtrue.s loc_250CB
0x250c4  ldstr    aNoValue// "No value"
0x250c9  br.s     loc_250EE
0x250cb  ldarg.1
0x250cc  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x250d1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_AuthenticationValidFromUtc()
0x250d6  stloc.s  8
0x250d8  ldloca.s 8
0x250da  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x250df  stloc.s  9
0x250e1  ldloca.s 9
0x250e3  constrained. [mscorlib]System.DateTime
0x250e9  callvirt instance string [mscorlib]System.Object::ToString()
0x250ee  stelem.ref
0x250ef  ldloc.s  6
0x250f1  ldc.i4.2
0x250f2  ldarg.1
0x250f3  ldarg.2
0x250f4  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::GetCacheEntry(valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind kind)
0x250f9  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::get_AuthenticationValidFromUtc()
0x250fe  stloc.s  0xA
0x25100  ldloca.s 0xA
0x25102  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x25107  stloc.s  0xB
0x25109  ldloca.s 0xB
0x2510b  constrained. [mscorlib]System.DateTime
0x25111  callvirt instance string [mscorlib]System.Object::ToString()
0x25116  stelem.ref
0x25117  ldloc.s  6
0x25119  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2511e  ldc.i4.1
0x2511f  stloc.0
0x25120  ldloc.0
0x25121  ret
```
