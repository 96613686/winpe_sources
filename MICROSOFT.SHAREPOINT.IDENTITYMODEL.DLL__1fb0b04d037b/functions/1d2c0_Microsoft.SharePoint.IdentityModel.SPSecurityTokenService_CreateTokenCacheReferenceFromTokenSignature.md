# Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::CreateTokenCacheReferenceFromTokenSignature

- ea: `0x1d2c0`
- end: `0x1d380`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::CreateTokenCacheReferenceFromTokenSignature`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d910`

## callees

- `0x17bc0`
- `0x1b880`
- `0x1d250`
- `0x1d2c0`
- `0x2c520`

## string_xrefs

- `0x1d30a`: `NullBootstrapToken`
- `0x1d350`: `NullBootstrapToken`
- `0x1d2f6`: `Identity does not have a bootstraptoken`
- `0x1d33c`: `Bootstrap token isn't of a supported type.`

## pseudocode

```c

```

## disassembly

```asm
0x1d2c0  ldc.i4   0x1299216
0x1d2c5  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x1d2ca  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1d2cf  ldstr    aIdentity// "identity"
0x1d2d4  ldarg.2
0x1d2d5  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x1d2da  ldarg.2
0x1d2db  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_BootstrapToken()
0x1d2e0  stloc.0
0x1d2e1  ldloc.0
0x1d2e2  brtrue.s loc_1D320
0x1d2e4  ldc.i4   0xCB303
0x1d2e9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1d2ee  ldc.i4.s 0xA
0x1d2f0  ldarg.1
0x1d2f1  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1d2f6  ldstr    aIdentityDoesNo// "Identity does not have a bootstraptoken"
0x1d2fb  call     string [mscorlib]System.String::Concat(string, string)
0x1d300  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1d305  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d30a  ldstr    aNullbootstrapt// "NullBootstrapToken"
0x1d30f  ldc.i4.0
0x1d310  newarr   [mscorlib]System.Object
0x1d315  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x1d31a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1d31f  throw
0x1d320  ldloc.0
0x1d321  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x1d326  stloc.1
0x1d327  ldloc.1
0x1d328  brtrue.s loc_1D366
0x1d32a  ldc.i4   0x1C565C
0x1d32f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1d334  ldc.i4.s 0xA
0x1d336  ldarg.1
0x1d337  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1d33c  ldstr    aBootstrapToken// "Bootstrap token isn't of a supported ty"...
0x1d341  call     string [mscorlib]System.String::Concat(string, string)
0x1d346  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1d34b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d350  ldstr    aNullbootstrapt// "NullBootstrapToken"
0x1d355  ldc.i4.0
0x1d356  newarr   [mscorlib]System.Object
0x1d35b  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x1d360  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1d365  throw
0x1d366  ldarg.2
0x1d367  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x1d36c  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager::GetProviderUserKey(string)
0x1d371  stloc.2
0x1d372  ldarg.2
0x1d373  ldloc.2
0x1d374  call     void Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::AugmentNameIdClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity, string userKey)
0x1d379  ldloc.1
0x1d37a  call     string Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::GetTokenSignature(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken jwtToken)
0x1d37f  ret
```
