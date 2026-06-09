# Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryGetUserKeyFromIdentityToken

- ea: `0x1b670`
- end: `0x1b799`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryGetUserKeyFromIdentityToken`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1b340`

## callees

- `0x1a4c0`
- `0x1a5b0`
- `0x1b670`
- `0x1b7a0`

## string_xrefs

- `0x1b6e3`: `cachekey`
- `0x1b6c2`: `TryGetUserKeyFromIdentityToken: Got user key from puid claim. Result: '{0}'.`
- `0x1b71e`: `TryGetUserKeyFromIdentityToken: Got user key from cachekey claim. Result: '{0}'.`
- `0x1b748`: `TryGetUserKeyFromIdentityToken: Could not decode userKey. Encoded value: '{0}'.`
- `0x1b777`: `TryGetCacheKeyClaimFromIdentityToken. Exception encountered. Exception: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1b670  ldc.i4.0
0x1b671  stloc.0
0x1b672  ldarg.1
0x1b673  ldnull
0x1b674  stind.ref
0x1b675  ldnull
0x1b676  stloc.1
0x1b677  ldarg.0
0x1b678  ldarg.0
0x1b679  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Request
0x1b67e  ldloca.s 1
0x1b680  call     instance bool Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryGetJwtIdentityToken(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken request, [out] class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken& jwtToken)
0x1b685  brfalse  loc_1B766
0x1b68a  ldnull
0x1b68b  stloc.2
0x1b68c  ldarg.0
0x1b68d  ldloc.1
0x1b68e  ldstr    aPuid// "puid"
0x1b693  ldloca.s 2
0x1b695  call     instance bool Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryGetClaimFromJwtToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken jwtToken, string claimType, [out] class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim& claimValue)
0x1b69a  brfalse.s loc_1B6E1
0x1b69c  ldloc.2
0x1b69d  brfalse.s loc_1B6E1
0x1b69f  ldloc.2
0x1b6a0  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x1b6a5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b6aa  brtrue.s loc_1B6E1
0x1b6ac  ldc.i4.1
0x1b6ad  stloc.0
0x1b6ae  ldarg.1
0x1b6af  ldloc.2
0x1b6b0  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x1b6b5  stind.ref
0x1b6b6  ldc.i4   0x1512762
0x1b6bb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1b6c0  ldc.i4.s 0x32
0x1b6c2  ldstr    aTrygetuserkeyf// "TryGetUserKeyFromIdentityToken: Got use"...
0x1b6c7  ldc.i4.1
0x1b6c8  newarr   [mscorlib]System.Object
0x1b6cd  stloc.s  4
0x1b6cf  ldloc.s  4
0x1b6d1  ldc.i4.0
0x1b6d2  ldarg.1
0x1b6d3  ldind.ref
0x1b6d4  stelem.ref
0x1b6d5  ldloc.s  4
0x1b6d7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1b6dc  br       loc_1B766
0x1b6e1  ldarg.0
0x1b6e2  ldloc.1
0x1b6e3  ldstr    aCachekey// "cachekey"
0x1b6e8  ldloca.s 2
0x1b6ea  call     instance bool Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryGetClaimFromJwtToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken jwtToken, string claimType, [out] class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim& claimValue)
0x1b6ef  brfalse.s loc_1B766
0x1b6f1  ldloc.2
0x1b6f2  brfalse.s loc_1B766
0x1b6f4  ldloc.2
0x1b6f5  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x1b6fa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b6ff  brtrue.s loc_1B766
0x1b701  ldarg.0
0x1b702  ldloc.2
0x1b703  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x1b708  ldarg.1
0x1b709  call     instance bool Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryDecodeUserKey(string encodedUserKey, [out] string& decodedUserKey)
0x1b70e  brfalse.s loc_1B73A
0x1b710  ldc.i4.1
0x1b711  stloc.0
0x1b712  ldc.i4   0x1512763
0x1b717  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1b71c  ldc.i4.s 0x32
0x1b71e  ldstr    aTrygetuserkeyf_0// "TryGetUserKeyFromIdentityToken: Got use"...
0x1b723  ldc.i4.1
0x1b724  newarr   [mscorlib]System.Object
0x1b729  stloc.s  5
0x1b72b  ldloc.s  5
0x1b72d  ldc.i4.0
0x1b72e  ldarg.1
0x1b72f  ldind.ref
0x1b730  stelem.ref
0x1b731  ldloc.s  5
0x1b733  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1b738  br.s     loc_1B766
0x1b73a  ldc.i4.0
0x1b73b  stloc.0
0x1b73c  ldc.i4   0x1512780
0x1b741  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1b746  ldc.i4.s 0xA
0x1b748  ldstr    aTrygetuserkeyf_1// "TryGetUserKeyFromIdentityToken: Could n"...
0x1b74d  ldc.i4.1
0x1b74e  newarr   [mscorlib]System.Object
0x1b753  stloc.s  6
0x1b755  ldloc.s  6
0x1b757  ldc.i4.0
0x1b758  ldloc.2
0x1b759  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x1b75e  stelem.ref
0x1b75f  ldloc.s  6
0x1b761  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1b766  leave.s  loc_1B797
0x1b768  stloc.3
0x1b769  ldc.i4.0
0x1b76a  stloc.0
0x1b76b  ldc.i4   0x1512781
0x1b770  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1b775  ldc.i4.s 0x32
0x1b777  ldstr    aTrygetcachekey// "TryGetCacheKeyClaimFromIdentityToken. E"...
0x1b77c  ldc.i4.1
0x1b77d  newarr   [mscorlib]System.Object
0x1b782  stloc.s  7
0x1b784  ldloc.s  7
0x1b786  ldc.i4.0
0x1b787  ldloc.3
0x1b788  callvirt instance string [mscorlib]System.Object::ToString()
0x1b78d  stelem.ref
0x1b78e  ldloc.s  7
0x1b790  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1b795  leave.s  loc_1B797
0x1b797  ldloc.0
0x1b798  ret
```
