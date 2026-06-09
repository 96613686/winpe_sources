# Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::GetOutputClaimsIdentityForCookieRenewalOrUpdate

- ea: `0x1e530`
- end: `0x1e6f6`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::GetOutputClaimsIdentityForCookieRenewalOrUpdate`
- size: `454`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x198f0`
- `0x1b880`
- `0x1ce30`
- `0x1e530`
- `0x20880`
- `0x2c520`

## string_xrefs

- `0x1e629`: `Missing token reference value.`
- `0x1e65d`: `Missing token reference value.`
- `0x1e6a9`: `Adding a token reference claim with type '{0}', value '{1}', value type '{2}', issuer '{3}' and original issuer '{4}'.`
- `0x1e5a9`: `STS Call: CanStoreTokenReference is false. Shouldn't call GetOutputClaimsIdentityForCookieRenew.`
- `0x1e5f1`: `STS Call: ShouldGenerateCookie is false. Shouldn't call GetOutputClaimsIdentityForCookieRenew.`

## pseudocode

```c

```

## disassembly

```asm
0x1e530  ldc.i4   0x121B356
0x1e535  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x1e53a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e53f  ldstr    aRequest// "request"
0x1e544  ldarg.1
0x1e545  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x1e54a  ldc.i4   0x121B357
0x1e54f  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x1e554  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e559  ldstr    aContext_0// "context"
0x1e55e  ldarg.2
0x1e55f  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x1e564  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentity::.ctor()
0x1e569  stloc.0
0x1e56a  ldarg.1
0x1e56b  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken
0x1e570  stloc.1
0x1e571  ldloc.1
0x1e572  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1e577  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_CanStoreTokenReference()
0x1e57c  stloc.s  4
0x1e57e  ldloca.s 4
0x1e580  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1e585  brfalse.s loc_1E5B9
0x1e587  ldloc.1
0x1e588  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1e58d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_CanStoreTokenReference()
0x1e592  stloc.s  5
0x1e594  ldloca.s 5
0x1e596  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1e59b  brtrue.s loc_1E5B9
0x1e59d  ldc.i4   0x1192347
0x1e5a2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e5a7  ldc.i4.s 0xA
0x1e5a9  ldstr    aStsCallCanstor// "STS Call: CanStoreTokenReference is fal"...
0x1e5ae  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1e5b3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x1e5b8  throw
0x1e5b9  ldloc.1
0x1e5ba  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1e5bf  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_ShouldGenerateCookie()
0x1e5c4  stloc.s  6
0x1e5c6  ldloca.s 6
0x1e5c8  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1e5cd  brfalse.s loc_1E606
0x1e5cf  ldloc.1
0x1e5d0  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1e5d5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_ShouldGenerateCookie()
0x1e5da  stloc.s  7
0x1e5dc  ldloca.s 7
0x1e5de  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1e5e3  brtrue.s loc_1E606
0x1e5e5  ldc.i4   0x12113DF
0x1e5ea  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e5ef  ldc.i4.s 0xA
0x1e5f1  ldstr    aStsCallShouldg// "STS Call: ShouldGenerateCookie is false"...
0x1e5f6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1e5fb  ldstr    aShouldgenerate// "ShouldGenerateCookie is false."
0x1e600  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1e605  throw
0x1e606  ldarg.0
0x1e607  ldarg.2
0x1e608  ldarg.2
0x1e609  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_Identity()
0x1e60e  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::CreateCookieValueFromIdentity(class Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext context, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity)
0x1e613  stloc.2
0x1e614  ldloc.2
0x1e615  brtrue.s loc_1E63E
0x1e617  ldc.i4   0x1192348
0x1e61c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e621  ldc.i4.s 0xA
0x1e623  ldarg.2
0x1e624  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1e629  ldstr    aMissingTokenRe// "Missing token reference value."
0x1e62e  call     string [mscorlib]System.String::Concat(string, string)
0x1e633  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1e638  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x1e63d  throw
0x1e63e  ldloc.2
0x1e63f  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_Value()
0x1e644  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1e649  brfalse.s loc_1E672
0x1e64b  ldc.i4   0x1192349
0x1e650  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e655  ldc.i4.s 0xA
0x1e657  ldarg.2
0x1e658  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1e65d  ldstr    aMissingTokenRe// "Missing token reference value."
0x1e662  call     string [mscorlib]System.String::Concat(string, string)
0x1e667  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1e66c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x1e671  throw
0x1e672  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_TokenReference()
0x1e677  ldloc.2
0x1e678  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_Value()
0x1e67d  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimValueTypes::get_String()
0x1e682  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string, string)
0x1e687  stloc.3
0x1e688  ldloc.0
0x1e689  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x1e68e  ldloc.3
0x1e68f  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::Add(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x1e694  ldc.i4   0x119234A
0x1e699  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e69e  ldc.i4   0xC8
0x1e6a3  ldarg.2
0x1e6a4  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1e6a9  ldstr    aAddingATokenRe// "Adding a token reference claim with typ"...
0x1e6ae  call     string [mscorlib]System.String::Concat(string, string)
0x1e6b3  ldc.i4.5
0x1e6b4  newarr   [mscorlib]System.Object
0x1e6b9  stloc.s  8
0x1e6bb  ldloc.s  8
0x1e6bd  ldc.i4.0
0x1e6be  ldloc.3
0x1e6bf  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x1e6c4  stelem.ref
0x1e6c5  ldloc.s  8
0x1e6c7  ldc.i4.1
0x1e6c8  ldloc.3
0x1e6c9  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x1e6ce  stelem.ref
0x1e6cf  ldloc.s  8
0x1e6d1  ldc.i4.2
0x1e6d2  ldloc.3
0x1e6d3  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ValueType()
0x1e6d8  stelem.ref
0x1e6d9  ldloc.s  8
0x1e6db  ldc.i4.3
0x1e6dc  ldloc.3
0x1e6dd  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Issuer()
0x1e6e2  stelem.ref
0x1e6e3  ldloc.s  8
0x1e6e5  ldc.i4.4
0x1e6e6  ldloc.3
0x1e6e7  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_OriginalIssuer()
0x1e6ec  stelem.ref
0x1e6ed  ldloc.s  8
0x1e6ef  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1e6f4  ldloc.0
0x1e6f5  ret
```
