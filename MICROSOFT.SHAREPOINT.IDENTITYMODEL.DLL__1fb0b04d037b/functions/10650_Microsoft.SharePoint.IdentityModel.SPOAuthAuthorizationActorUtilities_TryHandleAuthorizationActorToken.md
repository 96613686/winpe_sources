# Microsoft.SharePoint.IdentityModel.SPOAuthAuthorizationActorUtilities::TryHandleAuthorizationActorToken

- ea: `0x10650`
- end: `0x108af`
- name: `Microsoft.SharePoint.IdentityModel.SPOAuthAuthorizationActorUtilities::TryHandleAuthorizationActorToken`
- size: `607`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x5b90`

## callees

- `0x10650`
- `0x108b0`
- `0x10900`
- `0x10ab0`
- `0x181f0`
- `0x2c520`

## string_xrefs

- `0x10693`: `tokenContext`
- `0x106e7`: `OAuth Token: {0}`
- `0x10679`: `tokenHandler`
- `0x1071c`: `Could not read Json Web Security Token.`
- `0x10734`: `Successfully read Json Web Security Token.`
- `0x10751`: `Authorization Actor Token Issuer validation succeed.`
- `0x10770`: `Successfully set authentication actor app id in token context.`
- `0x1078a`: `Failed to set authentication actor app id in token context.`
- `0x10794`: `Failed to set authentication actor app id in token context.`
- `0x107b2`: `Authorization Actor Token audience validation failed. Exception: '{0}'`
- `0x107e4`: `Authorization Actor Token life time validation failed. Exception: '{0}'`
- `0x10816`: `Authorization Actor Token issuer validation failed. Exception: '{0}'`
- `0x10845`: `Authorization Actor Token context set failed, '{0}'.`
- `0x10874`: `Authorization Actor Token validation failed. Exception: '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x10650  ldc.i4   0x2315791
0x10655  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x1065a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1065f  ldstr    aRequest// "request"
0x10664  ldarg.0
0x10665  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x1066a  ldc.i4   0x2315792
0x1066f  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x10674  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x10679  ldstr    aTokenhandler// "tokenHandler"
0x1067e  ldarg.1
0x1067f  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x10684  ldc.i4   0x2315793
0x10689  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x1068e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x10693  ldstr    aTokencontext// "tokenContext"
0x10698  ldarg.2
0x10699  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x1069e  ldc.i4.0
0x1069f  stloc.0
0x106a0  ldnull
0x106a1  stloc.1
0x106a2  ldnull
0x106a3  stloc.2
0x106a4  ldarg.0
0x106a5  ldloca.s 1
0x106a7  call     bool Microsoft.SharePoint.IdentityModel.SPOAuthAuthorizationActorUtilities::TryParseAuthorizationActorToken(class [System.Web]System.Web.HttpRequest request, [out] string& authActortToken)
0x106ac  brfalse  loc_10895
0x106b1  ldloc.1
0x106b2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x106b7  brfalse.s loc_106D4
0x106b9  ldc.i4   0x2315794
0x106be  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x106c3  ldc.i4.s 0x64
0x106c5  ldstr    aSpapplicationa_107// "SPApplicationAuthenticationModule: Auth"...
0x106ca  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x106cf  br       loc_108AD
0x106d4  ldloc.1
0x106d5  call     string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOAuth2SecurityTokenManager::GetReadableTokenString(string)
0x106da  stloc.3
0x106db  ldc.i4   0x2315795
0x106e0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x106e5  ldc.i4.s 0x32
0x106e7  ldstr    aOauthToken0// "OAuth Token: {0}"
0x106ec  ldc.i4.1
0x106ed  newarr   [mscorlib]System.Object
0x106f2  stloc.s  9
0x106f4  ldloc.s  9
0x106f6  ldc.i4.0
0x106f7  ldloc.3
0x106f8  stelem.ref
0x106f9  ldloc.s  9
0x106fb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x10700  ldarg.1
0x10701  ldloc.1
0x10702  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityTokenHandler::ReadToken(string)
0x10707  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x1070c  stloc.2
0x1070d  ldloc.2
0x1070e  brtrue.s loc_10728
0x10710  ldc.i4   0x2315796
0x10715  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1071a  ldc.i4.s 0x14
0x1071c  ldstr    aCouldNotReadJs// "Could not read Json Web Security Token."
0x10721  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x10726  br.s     loc_1079F
0x10728  ldc.i4   0x2315797
0x1072d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x10732  ldc.i4.s 0x32
0x10734  ldstr    aSuccessfullyRe// "Successfully read Json Web Security Tok"...
0x10739  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1073e  ldarg.1
0x1073f  ldloc.2
0x10740  callvirt instance void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateAuthorizationActorToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x10745  ldc.i4   0x2315798
0x1074a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1074f  ldc.i4.s 0x32
0x10751  ldstr    aAuthorizationA_0// "Authorization Actor Token Issuer valida"...
0x10756  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1075b  ldloc.2
0x1075c  ldarg.2
0x1075d  call     bool Microsoft.SharePoint.IdentityModel.SPOAuthAuthorizationActorUtilities::TrySetAuthorizationActorAppIdToTokenContext(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken jsonWebSecurityToken, class Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext tokenContext)
0x10762  brfalse.s loc_1077E
0x10764  ldc.i4   0x2315799
0x10769  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1076e  ldc.i4.s 0x32
0x10770  ldstr    aSuccessfullySe// "Successfully set authentication actor a"...
0x10775  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1077a  ldc.i4.1
0x1077b  stloc.0
0x1077c  br.s     loc_1079F
0x1077e  ldc.i4   0x231579A
0x10783  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x10788  ldc.i4.s 0xA
0x1078a  ldstr    aFailedToSetAut// "Failed to set authentication actor app "...
0x1078f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x10794  ldstr    aFailedToSetAut// "Failed to set authentication actor app "...
0x10799  newobj   instance void Microsoft.SharePoint.IdentityModel.AuthorizationActorTokenContextException::.ctor(string errorMessage)
0x1079e  throw
0x1079f  leave    loc_108AD
0x107a4  stloc.s  4
0x107a6  ldc.i4   0x231579B
0x107ab  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x107b0  ldc.i4.s 0xA
0x107b2  ldstr    aAuthorizationA_1// "Authorization Actor Token audience vali"...
0x107b7  ldc.i4.1
0x107b8  newarr   [mscorlib]System.Object
0x107bd  stloc.s  0xA
0x107bf  ldloc.s  0xA
0x107c1  ldc.i4.0
0x107c2  ldloc.s  4
0x107c4  callvirt instance string [mscorlib]System.Object::ToString()
0x107c9  stelem.ref
0x107ca  ldloc.s  0xA
0x107cc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x107d1  leave    loc_108AD
0x107d6  stloc.s  5
0x107d8  ldc.i4   0x231579C
0x107dd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x107e2  ldc.i4.s 0xA
0x107e4  ldstr    aAuthorizationA_2// "Authorization Actor Token life time val"...
0x107e9  ldc.i4.1
0x107ea  newarr   [mscorlib]System.Object
0x107ef  stloc.s  0xB
0x107f1  ldloc.s  0xB
0x107f3  ldc.i4.0
0x107f4  ldloc.s  5
0x107f6  callvirt instance string [mscorlib]System.Object::ToString()
0x107fb  stelem.ref
0x107fc  ldloc.s  0xB
0x107fe  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x10803  leave    loc_108AD
0x10808  stloc.s  6
0x1080a  ldc.i4   0x231579D
0x1080f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x10814  ldc.i4.s 0xA
0x10816  ldstr    aAuthorizationA_3// "Authorization Actor Token issuer valida"...
0x1081b  ldc.i4.1
0x1081c  newarr   [mscorlib]System.Object
0x10821  stloc.s  0xC
0x10823  ldloc.s  0xC
0x10825  ldc.i4.0
0x10826  ldloc.s  6
0x10828  callvirt instance string [mscorlib]System.Object::ToString()
0x1082d  stelem.ref
0x1082e  ldloc.s  0xC
0x10830  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x10835  leave.s  loc_108AD
0x10837  stloc.s  7
0x10839  ldc.i4   0x231579E
0x1083e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x10843  ldc.i4.s 0xA
0x10845  ldstr    aAuthorizationA_4// "Authorization Actor Token context set f"...
0x1084a  ldc.i4.1
0x1084b  newarr   [mscorlib]System.Object
0x10850  stloc.s  0xD
0x10852  ldloc.s  0xD
0x10854  ldc.i4.0
0x10855  ldloc.s  7
0x10857  callvirt instance string [mscorlib]System.Object::ToString()
0x1085c  stelem.ref
0x1085d  ldloc.s  0xD
0x1085f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x10864  leave.s  loc_108AD
0x10866  stloc.s  8
0x10868  ldc.i4   0x231579F
0x1086d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x10872  ldc.i4.s 0xA
0x10874  ldstr    aAuthorizationA_5// "Authorization Actor Token validation fa"...
0x10879  ldc.i4.1
0x1087a  newarr   [mscorlib]System.Object
0x1087f  stloc.s  0xE
0x10881  ldloc.s  0xE
0x10883  ldc.i4.0
0x10884  ldloc.s  8
0x10886  callvirt instance string [mscorlib]System.Object::ToString()
0x1088b  stelem.ref
0x1088c  ldloc.s  0xE
0x1088e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x10893  leave.s  loc_108AD
0x10895  ldc.i4   0x23157A0
0x1089a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1089f  ldc.i4.s 0x32
0x108a1  ldstr    aSpapplicationa_108// "SPApplicationAuthenticationModule: Auth"...
0x108a6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x108ab  ldc.i4.1
0x108ac  stloc.0
0x108ad  ldloc.0
0x108ae  ret
```
