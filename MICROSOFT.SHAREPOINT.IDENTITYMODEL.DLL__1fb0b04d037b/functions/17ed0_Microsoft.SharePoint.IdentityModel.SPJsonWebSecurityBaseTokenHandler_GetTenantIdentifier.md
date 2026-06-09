# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::GetTenantIdentifier

- ea: `0x17ed0`
- end: `0x17f7d`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::GetTenantIdentifier`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x169c0`
- `0x17ed0`
- `0x1bf90`

## string_xrefs

- `0x17ee9`: `token`
- `0x17f12`: `token`
- `0x17edf`: `The token is null.`
- `0x17f08`: `The token's Claims property is null.`

## pseudocode

```c

```

## disassembly

```asm
0x17ed0  ldarg.0
0x17ed1  brtrue.s loc_17EF4
0x17ed3  ldc.i4   0x809355
0x17ed8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17edd  ldc.i4.s 0xA
0x17edf  ldstr    aTheTokenIsNull// "The token is null."
0x17ee4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17ee9  ldstr    aToken// "token"
0x17eee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x17ef3  throw
0x17ef4  ldarg.0
0x17ef5  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x17efa  brtrue.s loc_17F1D
0x17efc  ldc.i4   0x809356
0x17f01  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17f06  ldc.i4.s 0xA
0x17f08  ldstr    aTheTokenSClaim// "The token's Claims property is null."
0x17f0d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17f12  ldstr    aToken// "token"
0x17f17  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x17f1c  throw
0x17f1d  ldnull
0x17f1e  stloc.0
0x17f1f  ldarg.0
0x17f20  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x17f25  ldstr    aTid// "tid"
0x17f2a  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::GetSingleClaim(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> self, string claimType)
0x17f2f  stloc.1
0x17f30  ldloc.1
0x17f31  brtrue.s loc_17F4D
0x17f33  ldc.i4   0x809357
0x17f38  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17f3d  ldc.i4.s 0x32
0x17f3f  ldstr    aNoTenantIdClai// "No tenant id claim."
0x17f44  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17f49  ldnull
0x17f4a  stloc.0
0x17f4b  br.s     loc_17F7B
0x17f4d  ldloc.1
0x17f4e  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x17f53  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17f58  brfalse.s loc_17F74
0x17f5a  ldc.i4   0x809358
0x17f5f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17f64  ldc.i4.s 0x32
0x17f66  ldstr    aTheTenantIdCla// "The tenant id claim value is null or em"...
0x17f6b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17f70  ldnull
0x17f71  stloc.0
0x17f72  br.s     loc_17F7B
0x17f74  ldloc.1
0x17f75  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x17f7a  stloc.0
0x17f7b  ldloc.0
0x17f7c  ret
```
