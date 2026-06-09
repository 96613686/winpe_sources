# Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::AugmentTokenCacheReferenceClaimIfNeeded

- ea: `0x1d910`
- end: `0x1da58`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::AugmentTokenCacheReferenceClaimIfNeeded`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1dae0`

## callees

- `0x198c0`
- `0x1b880`
- `0x1cef0`
- `0x1d2c0`
- `0x1d910`
- `0x2c520`

## string_xrefs

- `0x1d9d9`: `Missing token reference value.`
- `0x1da00`: `Adding a token reference claim with type '{0}', value '{1}', value type '{2}', issuer '{3}' and original issuer '{4}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1d910  ldc.i4   0x12113DC
0x1d915  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x1d91a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1d91f  ldstr    aContext_0// "context"
0x1d924  ldarg.1
0x1d925  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x1d92a  ldc.i4   0x12113DD
0x1d92f  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x1d934  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1d939  ldstr    aIdentity// "identity"
0x1d93e  ldarg.2
0x1d93f  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x1d944  ldstr    asc_336C0// ""
0x1d949  stloc.0
0x1d94a  ldarg.1
0x1d94b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_SPRequest()
0x1d950  stloc.1
0x1d951  ldloc.1
0x1d952  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.IdentityModel]Microsoft.IdentityModel.OpenObject::get_Properties()
0x1d957  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::.ctor(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x1d95c  stloc.2
0x1d95d  ldnull
0x1d95e  stloc.3
0x1d95f  ldloc.2
0x1d960  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_CanStoreTokenReference()
0x1d965  stloc.s  4
0x1d967  ldloca.s 4
0x1d969  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1d96e  brfalse.s loc_1D99D
0x1d970  ldloc.2
0x1d971  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_CanStoreTokenReference()
0x1d976  stloc.s  5
0x1d978  ldloca.s 5
0x1d97a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1d97f  brtrue.s loc_1D99D
0x1d981  ldarg.0
0x1d982  ldarg.1
0x1d983  ldarg.2
0x1d984  call     instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::CreateTokenCacheReferenceFromTokenSignature(class Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext requestInfo, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity)
0x1d989  stloc.0
0x1d98a  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_ApplicationTokenCacheKey()
0x1d98f  ldloc.0
0x1d990  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimValueTypes::get_String()
0x1d995  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string, string)
0x1d99a  stloc.3
0x1d99b  br.s     loc_1D9B7
0x1d99d  ldarg.0
0x1d99e  ldarg.1
0x1d99f  ldarg.2
0x1d9a0  call     instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::CreateTokenCacheReferenceFromUserId(class Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext requestInfo, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity)
0x1d9a5  stloc.0
0x1d9a6  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_TokenReference()
0x1d9ab  ldloc.0
0x1d9ac  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimValueTypes::get_String()
0x1d9b1  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string, string)
0x1d9b6  stloc.3
0x1d9b7  ldloc.0
0x1d9b8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d9bd  brtrue.s loc_1D9C7
0x1d9bf  ldloc.0
0x1d9c0  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1d9c5  brfalse.s loc_1D9E8
0x1d9c7  ldc.i4   0x15D61F
0x1d9cc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1d9d1  ldc.i4.s 0xA
0x1d9d3  ldarg.1
0x1d9d4  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1d9d9  ldstr    aMissingTokenRe// "Missing token reference value."
0x1d9de  call     string [mscorlib]System.String::Concat(string, string)
0x1d9e3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1d9e8  ldloc.3
0x1d9e9  brfalse.s loc_1DA57
0x1d9eb  ldc.i4   0x15D620
0x1d9f0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1d9f5  ldc.i4   0xC8
0x1d9fa  ldarg.1
0x1d9fb  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1da00  ldstr    aAddingATokenRe// "Adding a token reference claim with typ"...
0x1da05  call     string [mscorlib]System.String::Concat(string, string)
0x1da0a  ldc.i4.5
0x1da0b  newarr   [mscorlib]System.Object
0x1da10  stloc.s  6
0x1da12  ldloc.s  6
0x1da14  ldc.i4.0
0x1da15  ldloc.3
0x1da16  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x1da1b  stelem.ref
0x1da1c  ldloc.s  6
0x1da1e  ldc.i4.1
0x1da1f  ldloc.3
0x1da20  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x1da25  stelem.ref
0x1da26  ldloc.s  6
0x1da28  ldc.i4.2
0x1da29  ldloc.3
0x1da2a  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ValueType()
0x1da2f  stelem.ref
0x1da30  ldloc.s  6
0x1da32  ldc.i4.3
0x1da33  ldloc.3
0x1da34  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Issuer()
0x1da39  stelem.ref
0x1da3a  ldloc.s  6
0x1da3c  ldc.i4.4
0x1da3d  ldloc.3
0x1da3e  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_OriginalIssuer()
0x1da43  stelem.ref
0x1da44  ldloc.s  6
0x1da46  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1da4b  ldarg.2
0x1da4c  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x1da51  ldloc.3
0x1da52  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::Add(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x1da57  ret
```
