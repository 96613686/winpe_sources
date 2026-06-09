# Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::ValidateToken

- ea: `0xe1c0`
- end: `0xe34c`
- name: `Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::ValidateToken`
- size: `396`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xd240`
- `0xd270`
- `0xd310`
- `0xd400`
- `0xd760`
- `0xda00`
- `0xdb40`
- `0xdff0`
- `0xe060`
- `0xe170`
- `0xe1c0`
- `0x2c520`

## string_xrefs

- `0xe1cf`: `token`
- `0xe1fa`: `SecurityTokenIsInvalidType`
- `0xe219`: `UserNameSecurityToken`
- `0xe1f0`: `The token is not a UserNameSecurityToken object.`
- `0xe29e`: `Token Handler: Unkown operation type '{0}' found.`

## pseudocode

```c

```

## disassembly

```asm
0xe1c0  ldc.i4   0x12991DC
0xe1c5  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xe1ca  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe1cf  ldstr    aToken// "token"
0xe1d4  ldarg.1
0xe1d5  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0xe1da  ldarg.1
0xe1db  isinst   [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken
0xe1e0  stloc.0
0xe1e1  ldloc.0
0xe1e2  brtrue.s loc_E22C
0xe1e4  ldc.i4   0x12991DD
0xe1e9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe1ee  ldc.i4.s 0xA
0xe1f0  ldstr    aTheTokenIsNotA_2// "The token is not a UserNameSecurityToke"...
0xe1f5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xe1fa  ldstr    aSecuritytokeni// "SecurityTokenIsInvalidType"
0xe1ff  ldc.i4.2
0xe200  newarr   [mscorlib]System.Object
0xe205  stloc.s  0xA
0xe207  ldloc.s  0xA
0xe209  ldc.i4.0
0xe20a  ldarg.1
0xe20b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xe210  callvirt instance string [mscorlib]System.Object::ToString()
0xe215  stelem.ref
0xe216  ldloc.s  0xA
0xe218  ldc.i4.1
0xe219  ldstr    aUsernamesecuri// "UserNameSecurityToken"
0xe21e  stelem.ref
0xe21f  ldloc.s  0xA
0xe221  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(string, object[])
0xe226  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe22b  throw
0xe22c  ldnull
0xe22d  stloc.1
0xe22e  ldnull
0xe22f  stloc.2
0xe230  ldnull
0xe231  stloc.3
0xe232  ldloca.s 5
0xe234  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0xe23a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim>::.ctor()
0xe23f  stloc.s  6
0xe241  ldarg.0
0xe242  ldloc.0
0xe243  call     instance class [System.Web.ApplicationServices]System.Web.Security.MembershipProvider Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::GetMembershipProvider(class [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken userToken)
0xe248  stloc.s  7
0xe24a  ldarg.0
0xe24b  ldloc.0
0xe24c  ldloc.s  7
0xe24e  ldloca.s 1
0xe250  ldloca.s 2
0xe252  ldloca.s 3
0xe254  ldloca.s 4
0xe256  ldloca.s 5
0xe258  call     instance void Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::SetupUserValidationType(class [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken userToken, class [System.Web.ApplicationServices]System.Web.Security.MembershipProvider membershipProvider, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim& userNameClaim, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim& userKeyClaim, [out] string& userNameSuffix, [out] valuetype Microsoft.SharePoint.IdentityModel.SPFormOperation& operationType, [out] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>& incomingValidFromTimeUtc)
0xe25d  ldloc.s  4
0xe25f  brtrue.s loc_E27B
0xe261  ldarg.0
0xe262  ldloc.s  4
0xe264  ldloc.s  7
0xe266  ldloc.1
0xe267  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_Value()
0xe26c  ldloc.0
0xe26d  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken::get_Password()
0xe272  ldloc.s  6
0xe274  call     instance void Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::ValidateUsernamePassword(valuetype Microsoft.SharePoint.IdentityModel.SPFormOperation operationType, class [System.Web.ApplicationServices]System.Web.Security.MembershipProvider provider, string userName, string password, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim> claims)
0xe279  br.s     loc_E2C4
0xe27b  ldc.i4.1
0xe27c  ldloc.s  4
0xe27e  bne.un.s loc_E292
0xe280  ldarg.0
0xe281  ldloc.s  4
0xe283  ldloc.s  7
0xe285  ldloc.1
0xe286  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_Value()
0xe28b  call     instance void Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::ValidateUserStatus(valuetype Microsoft.SharePoint.IdentityModel.SPFormOperation operationType, class [System.Web.ApplicationServices]System.Web.Security.MembershipProvider provider, string userName)
0xe290  br.s     loc_E2C4
0xe292  ldc.i4   0x15D611
0xe297  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe29c  ldc.i4.s 0xA
0xe29e  ldstr    aTokenHandlerUn_0// "Token Handler: Unkown operation type '{"...
0xe2a3  ldc.i4.1
0xe2a4  newarr   [mscorlib]System.Object
0xe2a9  stloc.s  0xB
0xe2ab  ldloc.s  0xB
0xe2ad  ldc.i4.0
0xe2ae  ldloc.s  4
0xe2b0  box      Microsoft.SharePoint.IdentityModel.SPFormOperation
0xe2b5  stelem.ref
0xe2b6  ldloc.s  0xB
0xe2b8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xe2bd  ldarg.0
0xe2be  call     instance class [mscorlib]System.Exception Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::CreateFailureException()
0xe2c3  throw
0xe2c4  ldnull
0xe2c5  stloc.s  8
0xe2c7  ldarg.0
0xe2c8  ldloc.s  4
0xe2ca  ldloc.0
0xe2cb  ldloc.1
0xe2cc  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_Value()
0xe2d1  ldloc.s  6
0xe2d3  call     instance void Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::AddClaimsForRolesIfNeeded(valuetype Microsoft.SharePoint.IdentityModel.SPFormOperation operationType, class [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken userToken, string userName, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim> claims)
0xe2d8  ldarg.0
0xe2d9  ldloc.s  4
0xe2db  ldloc.s  6
0xe2dd  call     instance void Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::AddFormOperationClaim(valuetype Microsoft.SharePoint.IdentityModel.SPFormOperation operationType, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim> claims)
0xe2e2  ldarg.0
0xe2e3  ldloc.s  4
0xe2e5  ldloc.s  5
0xe2e7  ldloc.s  6
0xe2e9  call     instance void Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::AddIncomingValidFromTimeClaim(valuetype Microsoft.SharePoint.IdentityModel.SPFormOperation operationType, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> incomingValidFromTimeUtc, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim> claims)
0xe2ee  ldarg.0
0xe2ef  ldloc.s  4
0xe2f1  ldloc.1
0xe2f2  ldloc.3
0xe2f3  ldloc.s  6
0xe2f5  call     instance void Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::AddNameClaims(valuetype Microsoft.SharePoint.IdentityModel.SPFormOperation operationType, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim userLogonNameClaim, string userNameSuffix, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim> claims)
0xe2fa  ldloc.2
0xe2fb  brtrue.s loc_E304
0xe2fd  ldloc.1
0xe2fe  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager::GetProviderUserKeyClaim(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim)
0xe303  stloc.2
0xe304  ldloc.2
0xe305  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_ClaimType()
0xe30a  ldloc.2
0xe30b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_Value()
0xe310  ldloc.2
0xe311  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_ValueType()
0xe316  ldnull
0xe317  ldnull
0xe318  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string, string, string, string)
0xe31d  stloc.s  8
0xe31f  ldloc.s  6
0xe321  ldloc.s  8
0xe323  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim>::Add(var<u1>)
0xe328  ldloc.s  6
0xe32a  ldstr    aForms_0// "Forms"
0xe32f  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentity::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim>, string)
0xe334  stloc.s  9
0xe336  ldc.i4.1
0xe337  newarr   [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity
0xe33c  stloc.s  0xC
0xe33e  ldloc.s  0xC
0xe340  ldc.i4.0
0xe341  ldloc.s  9
0xe343  stelem.ref
0xe344  ldloc.s  0xC
0xe346  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity>)
0xe34b  ret
```
