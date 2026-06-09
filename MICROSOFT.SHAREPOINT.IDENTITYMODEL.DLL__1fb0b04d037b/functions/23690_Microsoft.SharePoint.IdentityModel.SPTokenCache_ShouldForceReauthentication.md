# Microsoft.SharePoint.IdentityModel.SPTokenCache::ShouldForceReauthentication

- ea: `0x23690`
- end: `0x2383e`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::ShouldForceReauthentication`
- size: `430`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x206a0`
- `0x23690`

## string_xrefs

- `0x236a1`: `incomingCookie`
- `0x236b8`: `ShouldForceReauthentication: Performing session revocation check. Username: <name>'{0}'</name>, Cookie (UTC): '{1}', Token (UTC): '{2}'.`
- `0x23766`: `NeedToForceReauthentication: Token has never received a revocation signal. Requestor does not need to reauthenticate.`
- `0x237bc`: `ShouldForceReauthentication: Cookie valid-from time is absent or older than token valid-from time. Requestor must reauthenticate. Username: <name>'{0}'</name> Cookie (UTC): '{1}', ValidFrom (UTC): '{2}'.`

## pseudocode

```c

```

## disassembly

```asm
0x23690  ldarg.1
0x23691  brtrue.s loc_2369E
0x23693  ldstr    aEntry// "entry"
0x23698  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2369d  throw
0x2369e  ldarg.2
0x2369f  brtrue.s loc_236AC
0x236a1  ldstr    aIncomingcookie// "incomingCookie"
0x236a6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x236ab  throw
0x236ac  ldc.i4   0x5D489F
0x236b1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x236b6  ldc.i4.s 0x32
0x236b8  ldstr    aShouldforcerea// "ShouldForceReauthentication: Performing"...
0x236bd  ldc.i4.3
0x236be  newarr   [mscorlib]System.Object
0x236c3  stloc.1
0x236c4  ldloc.1
0x236c5  ldc.i4.0
0x236c6  ldarg.3
0x236c7  dup
0x236c8  brtrue.s loc_236D0
0x236ca  pop
0x236cb  ldsfld   string [mscorlib]System.String::Empty
0x236d0  stelem.ref
0x236d1  ldloc.1
0x236d2  ldc.i4.1
0x236d3  ldarg.2
0x236d4  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_AuthenticationValidFromUtc()
0x236d9  stloc.2
0x236da  ldloca.s 2
0x236dc  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x236e1  brtrue.s loc_236EA
0x236e3  ldstr    aNoValue// "No value"
0x236e8  br.s     loc_23707
0x236ea  ldarg.2
0x236eb  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_AuthenticationValidFromUtc()
0x236f0  stloc.3
0x236f1  ldloca.s 3
0x236f3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x236f8  stloc.s  4
0x236fa  ldloca.s 4
0x236fc  constrained. [mscorlib]System.DateTime
0x23702  callvirt instance string [mscorlib]System.Object::ToString()
0x23707  stelem.ref
0x23708  ldloc.1
0x23709  ldc.i4.2
0x2370a  ldarg.1
0x2370b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::get_AuthenticationValidFromUtc()
0x23710  stloc.s  5
0x23712  ldloca.s 5
0x23714  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x23719  brtrue.s loc_23722
0x2371b  ldstr    aNoValue// "No value"
0x23720  br.s     loc_23740
0x23722  ldarg.1
0x23723  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::get_AuthenticationValidFromUtc()
0x23728  stloc.s  6
0x2372a  ldloca.s 6
0x2372c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x23731  stloc.s  7
0x23733  ldloca.s 7
0x23735  constrained. [mscorlib]System.DateTime
0x2373b  callvirt instance string [mscorlib]System.Object::ToString()
0x23740  stelem.ref
0x23741  ldloc.1
0x23742  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x23747  ldc.i4.0
0x23748  stloc.0
0x23749  ldarg.1
0x2374a  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::get_AuthenticationValidFromUtc()
0x2374f  stloc.s  8
0x23751  ldloca.s 8
0x23753  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x23758  brtrue.s loc_23777
0x2375a  ldc.i4   0x5D48A0
0x2375f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23764  ldc.i4.s 0x64
0x23766  ldstr    aNeedtoforcerea// "NeedToForceReauthentication: Token has "...
0x2376b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23770  ldc.i4.0
0x23771  stloc.0
0x23772  br       loc_2383C
0x23777  ldarg.2
0x23778  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_AuthenticationValidFromUtc()
0x2377d  stloc.s  9
0x2377f  ldloca.s 9
0x23781  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x23786  brfalse.s loc_237B0
0x23788  ldarg.2
0x23789  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_AuthenticationValidFromUtc()
0x2378e  stloc.s  0xA
0x23790  ldloca.s 0xA
0x23792  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x23797  ldarg.1
0x23798  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::get_AuthenticationValidFromUtc()
0x2379d  stloc.s  0xB
0x2379f  ldloca.s 0xB
0x237a1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x237a6  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x237ab  brfalse  loc_2383C
0x237b0  ldc.i4   0x5D48A1
0x237b5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x237ba  ldc.i4.s 0xF
0x237bc  ldstr    aShouldforcerea_0// "ShouldForceReauthentication: Cookie val"...
0x237c1  ldc.i4.3
0x237c2  newarr   [mscorlib]System.Object
0x237c7  stloc.s  0xC
0x237c9  ldloc.s  0xC
0x237cb  ldc.i4.0
0x237cc  ldarg.3
0x237cd  dup
0x237ce  brtrue.s loc_237D6
0x237d0  pop
0x237d1  ldsfld   string [mscorlib]System.String::Empty
0x237d6  stelem.ref
0x237d7  ldloc.s  0xC
0x237d9  ldc.i4.1
0x237da  ldarg.2
0x237db  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_AuthenticationValidFromUtc()
0x237e0  stloc.s  0xD
0x237e2  ldloca.s 0xD
0x237e4  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x237e9  brtrue.s loc_237F2
0x237eb  ldstr    aNoValue// "No value"
0x237f0  br.s     loc_23810
0x237f2  ldarg.2
0x237f3  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_AuthenticationValidFromUtc()
0x237f8  stloc.s  0xE
0x237fa  ldloca.s 0xE
0x237fc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x23801  stloc.s  0xF
0x23803  ldloca.s 0xF
0x23805  constrained. [mscorlib]System.DateTime
0x2380b  callvirt instance string [mscorlib]System.Object::ToString()
0x23810  stelem.ref
0x23811  ldloc.s  0xC
0x23813  ldc.i4.2
0x23814  ldarg.1
0x23815  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::get_AuthenticationValidFromUtc()
0x2381a  stloc.s  0x10
0x2381c  ldloca.s 0x10
0x2381e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x23823  stloc.s  0x11
0x23825  ldloca.s 0x11
0x23827  constrained. [mscorlib]System.DateTime
0x2382d  callvirt instance string [mscorlib]System.Object::ToString()
0x23832  stelem.ref
0x23833  ldloc.s  0xC
0x23835  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2383a  ldc.i4.1
0x2383b  stloc.0
0x2383c  ldloc.0
0x2383d  ret
```
