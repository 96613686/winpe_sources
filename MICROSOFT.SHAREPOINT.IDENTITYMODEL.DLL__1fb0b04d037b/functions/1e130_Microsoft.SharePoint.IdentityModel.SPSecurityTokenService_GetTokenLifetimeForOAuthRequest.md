# Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::GetTokenLifetimeForOAuthRequest

- ea: `0x1e130`
- end: `0x1e2f9`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::GetTokenLifetimeForOAuthRequest`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1df00`

## callees

- `0x1e130`

## string_xrefs

- `0x1e146`: `GetTokenLifetime: Principal property is null.`
- `0x1e166`: `GetTokenLifetime: Request property is null.`
- `0x1e186`: `GetTokenLifetime: Scope property is null.`
- `0x1e1da`: `GetTokenLifetime: Couldn't find SPClaimTypes.UserIdentifier claim.`
- `0x1e28d`: `GetTokenLifetime: Unrecognized original issuer type '{0}', original issuer '{1}'.`
- `0x1e2c7`: `GetTokenLifetime: Falling back to calculating token life time based on OnBehalfOf token lifetime.`

## pseudocode

```c

```

## disassembly

```asm
0x1e130  ldc.i4.0
0x1e131  stloc.0
0x1e132  ldarg.0
0x1e133  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.SecurityTokenService::get_Principal()
0x1e138  brtrue.s loc_1E152
0x1e13a  ldc.i4   0x35D0D7
0x1e13f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e144  ldc.i4.s 0xA
0x1e146  ldstr    aGettokenlifeti_0// "GetTokenLifetime: Principal property is"...
0x1e14b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1e150  ldc.i4.1
0x1e151  stloc.0
0x1e152  ldarg.0
0x1e153  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.SecurityTokenService::get_Request()
0x1e158  brtrue.s loc_1E172
0x1e15a  ldc.i4   0x35D0D8
0x1e15f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e164  ldc.i4.s 0xA
0x1e166  ldstr    aGettokenlifeti_1// "GetTokenLifetime: Request property is n"...
0x1e16b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1e170  ldc.i4.1
0x1e171  stloc.0
0x1e172  ldarg.0
0x1e173  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.Scope [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.SecurityTokenService::get_Scope()
0x1e178  brtrue.s loc_1E192
0x1e17a  ldc.i4   0x35D0D9
0x1e17f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e184  ldc.i4.s 0xA
0x1e186  ldstr    aGettokenlifeti_2// "GetTokenLifetime: Scope property is nul"...
0x1e18b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1e190  ldc.i4.1
0x1e191  stloc.0
0x1e192  ldnull
0x1e193  stloc.1
0x1e194  ldloc.0
0x1e195  brtrue   loc_1E2B8
0x1e19a  ldarg.0
0x1e19b  ldarg.0
0x1e19c  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.SecurityTokenService::get_Principal()
0x1e1a1  ldarg.0
0x1e1a2  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.SecurityTokenService::get_Request()
0x1e1a7  ldarg.0
0x1e1a8  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.Scope [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.SecurityTokenService::get_Scope()
0x1e1ad  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.SecurityTokenService::GetOutputClaimsIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken, class [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.Scope)
0x1e1b2  stloc.2
0x1e1b3  ldloc.2
0x1e1b4  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x1e1b9  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_UserIdentifier()
0x1e1be  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x1e1c3  stloc.3
0x1e1c4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalOrThrow()
0x1e1c9  stloc.s  4
0x1e1cb  ldloc.3
0x1e1cc  brtrue.s loc_1E1EB
0x1e1ce  ldc.i4   0x35D0DA
0x1e1d3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e1d8  ldc.i4.s 0xA
0x1e1da  ldstr    aGettokenlifeti_3// "GetTokenLifetime: Couldn't find SPClaim"...
0x1e1df  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1e1e4  ldc.i4.1
0x1e1e5  stloc.0
0x1e1e6  br       loc_1E2B8
0x1e1eb  ldloc.3
0x1e1ec  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x1e1f1  ldloc.3
0x1e1f2  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x1e1f7  ldloc.3
0x1e1f8  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ValueType()
0x1e1fd  ldloc.3
0x1e1fe  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_OriginalIssuer()
0x1e203  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager::DecodeUserIdentifierClaim(string, string, string, string)
0x1e208  stloc.s  5
0x1e20a  ldloc.s  5
0x1e20c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_OriginalIssuer()
0x1e211  stloc.s  6
0x1e213  ldloc.s  6
0x1e215  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuers::GetIssuerType(string)
0x1e21a  stloc.s  7
0x1e21c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1e221  stloc.s  8
0x1e223  ldloc.s  7
0x1e225  stloc.s  0xA
0x1e227  ldloc.s  0xA
0x1e229  ldc.i4.s 0x66
0x1e22b  beq.s    loc_1E251
0x1e22d  ldloc.s  0xA
0x1e22f  ldc.i4.s 0x74
0x1e231  beq.s    loc_1E269
0x1e233  ldloc.s  0xA
0x1e235  ldc.i4.s 0x77
0x1e237  bne.un.s loc_1E281
0x1e239  ldloc.s  8
0x1e23b  ldloc.s  8
0x1e23d  ldloc.s  4
0x1e23f  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_WindowsTokenLifetime()
0x1e244  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x1e249  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.Lifetime::.ctor(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1e24e  stloc.1
0x1e24f  br.s     loc_1E2B8
0x1e251  ldloc.s  8
0x1e253  ldloc.s  8
0x1e255  ldloc.s  4
0x1e257  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_FormsTokenLifetime()
0x1e25c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x1e261  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.Lifetime::.ctor(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1e266  stloc.1
0x1e267  br.s     loc_1E2B8
0x1e269  ldloc.s  8
0x1e26b  ldloc.s  8
0x1e26d  ldloc.s  4
0x1e26f  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_TrustedTokenLifetime()
0x1e274  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x1e279  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.Lifetime::.ctor(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1e27e  stloc.1
0x1e27f  br.s     loc_1E2B8
0x1e281  ldc.i4   0x35D0DB
0x1e286  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e28b  ldc.i4.s 0xA
0x1e28d  ldstr    aGettokenlifeti_4// "GetTokenLifetime: Unrecognized original"...
0x1e292  ldc.i4.2
0x1e293  newarr   [mscorlib]System.Object
0x1e298  stloc.s  0xB
0x1e29a  ldloc.s  0xB
0x1e29c  ldc.i4.0
0x1e29d  ldloc.s  7
0x1e29f  box      [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType
0x1e2a4  stelem.ref
0x1e2a5  ldloc.s  0xB
0x1e2a7  ldc.i4.1
0x1e2a8  ldloc.s  6
0x1e2aa  stelem.ref
0x1e2ab  ldloc.s  0xB
0x1e2ad  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1e2b2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x1e2b7  throw
0x1e2b8  ldloc.0
0x1e2b9  brfalse.s loc_1E2F7
0x1e2bb  ldc.i4   0x35D0DC
0x1e2c0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e2c5  ldc.i4.s 0xA
0x1e2c7  ldstr    aGettokenlifeti_5// "GetTokenLifetime: Falling back to calcu"...
0x1e2cc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1e2d1  ldarg.0
0x1e2d2  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.SecurityTokenService::get_Request()
0x1e2d7  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_OnBehalfOf()
0x1e2dc  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement::GetSecurityToken()
0x1e2e1  stloc.s  9
0x1e2e3  ldloc.s  9
0x1e2e5  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0x1e2ea  ldloc.s  9
0x1e2ec  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0x1e2f1  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.Lifetime::.ctor(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1e2f6  stloc.1
0x1e2f7  ldloc.1
0x1e2f8  ret
```
