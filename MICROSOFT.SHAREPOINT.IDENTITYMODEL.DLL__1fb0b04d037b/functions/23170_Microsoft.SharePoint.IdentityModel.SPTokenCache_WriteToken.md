# Microsoft.SharePoint.IdentityModel.SPTokenCache::WriteToken

- ea: `0x23170`
- end: `0x23319`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::WriteToken`
- size: `425`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x20640`
- `0x20b10`
- `0x217c0`
- `0x22d70`
- `0x22f20`
- `0x23170`
- `0x25f80`
- `0x28160`

## string_xrefs

- `0x23275`: `Token Cache: Could not get cookie value handler.`
- `0x2320f`: `Token Cache: Could not find token refence claim in sessionToken to be written. Trying ApplicationTokenCacheKey`
- `0x23235`: `Token Cache: Could not find token refence claim in sessionToken to be written.`
- `0x23297`: `Token Cache: The token refence claim value is empty.`
- `0x232c4`: `Token Cache: Writing token out as cookie. '{0}'.`
- `0x232fe`: `Token Cache: New cookie value is empty. Throwing.`

## pseudocode

```c

```

## disassembly

```asm
0x23170  ldarg.1
0x23171  brtrue.s loc_2317A
0x23173  ldc.i4.0
0x23174  newarr   [mscorlib]System.Byte
0x23179  ret
0x2317a  ldarg.1
0x2317b  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x23180  brtrue.s loc_23189
0x23182  ldc.i4.0
0x23183  newarr   [mscorlib]System.Byte
0x23188  ret
0x23189  ldarg.1
0x2318a  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x2318f  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x23194  brfalse.s loc_231A8
0x23196  ldarg.1
0x23197  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x2319c  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x231a1  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x231a6  brtrue.s loc_231AF
0x231a8  ldc.i4.0
0x231a9  newarr   [mscorlib]System.Byte
0x231ae  ret
0x231af  ldarg.1
0x231b0  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x231b5  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x231ba  ldc.i4.0
0x231bb  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x231c0  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x231c5  brfalse.s loc_231E4
0x231c7  ldarg.1
0x231c8  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x231cd  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x231d2  ldc.i4.0
0x231d3  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x231d8  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x231dd  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::get_Count()
0x231e2  brtrue.s loc_231EB
0x231e4  ldc.i4.0
0x231e5  newarr   [mscorlib]System.Byte
0x231ea  ret
0x231eb  ldarg.0
0x231ec  ldarg.1
0x231ed  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_TokenReference()
0x231f2  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSingleClaimFromToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken sessionToken, string claimType)
0x231f7  stloc.0
0x231f8  ldnull
0x231f9  stloc.1
0x231fa  ldstr    asc_336C0// ""
0x231ff  stloc.2
0x23200  ldloc.0
0x23201  brtrue.s loc_23257
0x23203  ldc.i4   0x1C565D
0x23208  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2320d  ldc.i4.s 0x64
0x2320f  ldstr    aTokenCacheCoul_5// "Token Cache: Could not find token refen"...
0x23214  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23219  ldarg.0
0x2321a  ldarg.1
0x2321b  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_ApplicationTokenCacheKey()
0x23220  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSingleClaimFromToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken sessionToken, string claimType)
0x23225  stloc.0
0x23226  ldloc.0
0x23227  brtrue.s loc_23244
0x23229  ldc.i4   0x15D683
0x2322e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23233  ldc.i4.s 0xA
0x23235  ldstr    aTokenCacheCoul_6// "Token Cache: Could not find token refen"...
0x2323a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2323f  br       loc_232E2
0x23244  ldloc.0
0x23245  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x2324a  stloc.2
0x2324b  ldloc.0
0x2324c  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x23251  stloc.1
0x23252  br       loc_232E2
0x23257  ldloc.0
0x23258  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x2325d  stloc.2
0x2325e  call     class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetCookieValueHandler()
0x23263  stloc.3
0x23264  ldloc.3
0x23265  brtrue.s loc_23281
0x23267  ldnull
0x23268  stloc.1
0x23269  ldc.i4   0x19178E
0x2326e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23273  ldc.i4.s 0xA
0x23275  ldstr    aTokenCacheCoul_1// "Token Cache: Could not get cookie value"...
0x2327a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2327f  br.s     loc_232E2
0x23281  ldloc.2
0x23282  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23287  brfalse.s loc_232A3
0x23289  ldnull
0x2328a  stloc.1
0x2328b  ldc.i4   0x19178F
0x23290  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23295  ldc.i4.s 0xA
0x23297  ldstr    aTokenCacheTheT_2// "Token Cache: The token refence claim va"...
0x2329c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x232a1  br.s     loc_232E2
0x232a3  ldloc.3
0x232a4  ldloc.2
0x232a5  ldc.i4.1
0x232a6  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::Initialize(string cookieValue, valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValueOption options)
0x232ab  brtrue.s loc_232B1
0x232ad  ldnull
0x232ae  stloc.1
0x232af  br.s     loc_232E2
0x232b1  ldloc.3
0x232b2  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserKey()
0x232b7  stloc.1
0x232b8  ldc.i4   0x555741
0x232bd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x232c2  ldc.i4.s 0x32
0x232c4  ldstr    aTokenCacheWrit// "Token Cache: Writing token out as cooki"...
0x232c9  ldc.i4.1
0x232ca  newarr   [mscorlib]System.Object
0x232cf  stloc.s  5
0x232d1  ldloc.s  5
0x232d3  ldc.i4.0
0x232d4  ldloc.3
0x232d5  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::LogString()
0x232da  stelem.ref
0x232db  ldloc.s  5
0x232dd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x232e2  ldarg.0
0x232e3  ldloc.1
0x232e4  ldarg.1
0x232e5  call     instance void Microsoft.SharePoint.IdentityModel.SPTokenCache::HandleTokenCacheForWriteToken(string userkey, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken sessionToken)
0x232ea  ldloc.2
0x232eb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x232f0  brfalse.s loc_2330E
0x232f2  ldc.i4   0x1280592
0x232f7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x232fc  ldc.i4.s 0xA
0x232fe  ldstr    aTokenCacheNewC// "Token Cache: New cookie value is empty."...
0x23303  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23308  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x2330d  throw
0x2330e  ldloc.2
0x2330f  call     unsigned int8[] Microsoft.SharePoint.IdentityModel.SPTokenCache::WriteTokenXml(string tokenValue)
0x23314  stloc.s  4
0x23316  ldloc.s  4
0x23318  ret
```
