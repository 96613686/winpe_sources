# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::GetIssuerNameFromIssuerToken

- ea: `0x17d40`
- end: `0x17e59`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::GetIssuerNameFromIssuerToken`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x17580`

## callees

- `0x169c0`
- `0x17d40`

## string_xrefs

- `0x17d59`: `token`
- `0x17d4f`: `The token is null.`
- `0x17d95`: `Could not find a match for the json token issuer in the issuer registry. IssuerRegistryType: '{0}', TokenIssuerName: '{1}'.`
- `0x17de3`: `Found a match for the json token issuer which is the local farm. IssuerRegistryType: '{0}', TokenIssuerName: '{1}'.`
- `0x17e25`: `Found a match for the json token issuer. IssuerRegistryType: '{0}', TokenIssuerName: '{1}', IssuerName: '{2}'.`

## pseudocode

```c

```

## disassembly

```asm
0x17d40  ldarg.1
0x17d41  brtrue.s loc_17D64
0x17d43  ldc.i4   0x65040A
0x17d48  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17d4d  ldc.i4.s 0xA
0x17d4f  ldstr    aTheTokenIsNull// "The token is null."
0x17d54  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17d59  ldstr    aToken// "token"
0x17d5e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x17d63  throw
0x17d64  ldarg.0
0x17d65  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerConfiguration [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler::get_Configuration()
0x17d6a  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.IssuerNameRegistry [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerConfiguration::get_IssuerNameRegistry()
0x17d6f  ldarg.1
0x17d70  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_IssuerToken()
0x17d75  ldarg.1
0x17d76  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x17d7b  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.IssuerNameRegistry::GetIssuerName(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken, string)
0x17d80  stloc.0
0x17d81  ldloc.0
0x17d82  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17d87  brfalse.s loc_17DC9
0x17d89  ldc.i4   0x20B1E3
0x17d8e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17d93  ldc.i4.s 0x14
0x17d95  ldstr    aCouldNotFindAM// "Could not find a match for the json tok"...
0x17d9a  ldc.i4.2
0x17d9b  newarr   [mscorlib]System.Object
0x17da0  stloc.1
0x17da1  ldloc.1
0x17da2  ldc.i4.0
0x17da3  ldarg.0
0x17da4  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerConfiguration [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler::get_Configuration()
0x17da9  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.IssuerNameRegistry [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerConfiguration::get_IssuerNameRegistry()
0x17dae  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x17db3  stelem.ref
0x17db4  ldloc.1
0x17db5  ldc.i4.1
0x17db6  ldarg.1
0x17db7  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x17dbc  stelem.ref
0x17dbd  ldloc.1
0x17dbe  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x17dc3  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIssuerNameAndNameIdMismatchException::.ctor()
0x17dc8  throw
0x17dc9  ldstr    aSharepoint// "SharePoint"
0x17dce  ldloc.0
0x17dcf  ldc.i4.5
0x17dd0  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x17dd5  brfalse.s loc_17E19
0x17dd7  ldc.i4   0x20B200
0x17ddc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17de1  ldc.i4.s 0x64
0x17de3  ldstr    aFoundAMatchFor// "Found a match for the json token issuer"...
0x17de8  ldc.i4.2
0x17de9  newarr   [mscorlib]System.Object
0x17dee  stloc.2
0x17def  ldloc.2
0x17df0  ldc.i4.0
0x17df1  ldarg.0
0x17df2  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerConfiguration [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler::get_Configuration()
0x17df7  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.IssuerNameRegistry [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerConfiguration::get_IssuerNameRegistry()
0x17dfc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x17e01  stelem.ref
0x17e02  ldloc.2
0x17e03  ldc.i4.1
0x17e04  ldarg.1
0x17e05  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x17e0a  stelem.ref
0x17e0b  ldloc.2
0x17e0c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x17e11  call     string [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationPrincipalName::get_SharePointApplicationName()
0x17e16  stloc.0
0x17e17  br.s     loc_17E57
0x17e19  ldc.i4   0x7CC18D
0x17e1e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17e23  ldc.i4.s 0x64
0x17e25  ldstr    aFoundAMatchFor_0// "Found a match for the json token issuer"...
0x17e2a  ldc.i4.3
0x17e2b  newarr   [mscorlib]System.Object
0x17e30  stloc.3
0x17e31  ldloc.3
0x17e32  ldc.i4.0
0x17e33  ldarg.0
0x17e34  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerConfiguration [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler::get_Configuration()
0x17e39  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.IssuerNameRegistry [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerConfiguration::get_IssuerNameRegistry()
0x17e3e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x17e43  stelem.ref
0x17e44  ldloc.3
0x17e45  ldc.i4.1
0x17e46  ldarg.1
0x17e47  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x17e4c  stelem.ref
0x17e4d  ldloc.3
0x17e4e  ldc.i4.2
0x17e4f  ldloc.0
0x17e50  stelem.ref
0x17e51  ldloc.3
0x17e52  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x17e57  ldloc.0
0x17e58  ret
```
