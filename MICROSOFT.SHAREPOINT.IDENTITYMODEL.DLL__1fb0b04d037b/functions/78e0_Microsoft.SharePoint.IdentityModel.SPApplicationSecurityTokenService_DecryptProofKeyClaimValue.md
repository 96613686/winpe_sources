# Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::DecryptProofKeyClaimValue

- ea: `0x78e0`
- end: `0x799d`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::DecryptProofKeyClaimValue`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x78e0`
- `0x1f850`

## string_xrefs

- `0x7908`: `Security handlers don't exist.`
- `0x7912`: `Security handlers don't exist.`
- `0x7955`: `Proof token handler does not exist.`
- `0x795f`: `Proof token handler does not exist.`
- `0x7980`: `Unable to cast to SPIdentityProofTokenHandler.`
- `0x798a`: `Unable to cast to SPIdentityProofTokenHandler.`

## pseudocode

```c

```

## disassembly

```asm
0x78e0  ldarg.1
0x78e1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x78e6  brfalse.s loc_78F3
0x78e8  ldstr    aProofkey// "proofKey"
0x78ed  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x78f2  throw
0x78f3  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler> Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceConfiguration::GetSecurityTokenHandlers()
0x78f8  stloc.0
0x78f9  ldloc.0
0x78fa  brtrue.s loc_791D
0x78fc  ldc.i4   0x119E28A
0x7901  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x7906  ldc.i4.s 0xA
0x7908  ldstr    aSecurityHandle// "Security handlers don't exist."
0x790d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x7912  ldstr    aSecurityHandle// "Security handlers don't exist."
0x7917  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x791c  throw
0x791d  ldloc.0
0x791e  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler, bool> Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::CS$<>9__CachedAnonymousMethodDelegate1
0x7923  brtrue.s loc_7936
0x7925  ldnull
0x7926  ldftn    bool Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::<DecryptProofKeyClaimValue>b__0(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler h)
0x792c  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler, bool>::.ctor(object, native int)
0x7931  stsfld   class [mscorlib]System.Func`2<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler, bool> Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::CS$<>9__CachedAnonymousMethodDelegate1
0x7936  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler, bool> Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::CS$<>9__CachedAnonymousMethodDelegate1
0x793b  call     T0x2B000011
0x7940  call     T0x2B000012
0x7945  stloc.1
0x7946  ldloc.1
0x7947  brtrue.s loc_796A
0x7949  ldc.i4   0x119E28B
0x794e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x7953  ldc.i4.s 0xA
0x7955  ldstr    aProofTokenHand// "Proof token handler does not exist."
0x795a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x795f  ldstr    aProofTokenHand// "Proof token handler does not exist."
0x7964  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7969  throw
0x796a  ldloc.1
0x796b  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenHandler
0x7970  stloc.2
0x7971  ldloc.2
0x7972  brtrue.s loc_7995
0x7974  ldc.i4   0x119E28C
0x7979  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x797e  ldc.i4.s 0xA
0x7980  ldstr    aUnableToCastTo// "Unable to cast to SPIdentityProofTokenH"...
0x7985  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x798a  ldstr    aUnableToCastTo// "Unable to cast to SPIdentityProofTokenH"...
0x798f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7994  throw
0x7995  ldloc.2
0x7996  ldarg.1
0x7997  callvirt instance unsigned int8[] [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenHandler::DecryptProofKeyClaimValue(string)
0x799c  ret
```
