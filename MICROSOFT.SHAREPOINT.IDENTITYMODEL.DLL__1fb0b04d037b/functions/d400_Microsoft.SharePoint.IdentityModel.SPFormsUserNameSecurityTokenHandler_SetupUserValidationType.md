# Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::SetupUserValidationType

- ea: `0xd400`
- end: `0xd6a9`
- name: `Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::SetupUserValidationType`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0xe1c0`

## callees

- `0x1ad0`
- `0x1b10`
- `0xd240`
- `0xd310`
- `0xd350`
- `0xd3c0`
- `0xd400`
- `0xd6b0`
- `0x28160`
- `0x2c520`

## string_xrefs

- `0xd40f`: `userToken`
- `0xd460`: `Token Handler: Failed to get cookie value handler object so rejecting the request because we can't process it.`
- `0xd5f7`: `SetupUserValidationType: Incoming cookie authentication valid-from time. User: '{0}' Cookie time: '{1}', OperationType: '{2}'.`

## pseudocode

```c

```

## disassembly

```asm
0xd400  ldc.i4   0x12991CC
0xd405  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xd40a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xd40f  ldstr    aUsertoken// "userToken"
0xd414  ldarg.1
0xd415  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0xd41a  ldc.i4   0x12991CD
0xd41f  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xd424  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xd429  ldstr    aMembershipprov// "membershipProvider"
0xd42e  ldarg.2
0xd42f  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0xd434  ldarg.3
0xd435  ldnull
0xd436  stind.ref
0xd437  ldarg.s  4
0xd439  ldnull
0xd43a  stind.ref
0xd43b  ldarg.s  5
0xd43d  ldnull
0xd43e  stind.ref
0xd43f  ldarg.s  7
0xd441  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0xd447  ldarg.s  6
0xd449  ldc.i4.0
0xd44a  stind.i4
0xd44b  call     class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetCookieValueHandler()
0xd450  stloc.0
0xd451  ldloc.0
0xd452  brtrue.s loc_D471
0xd454  ldc.i4   0xDF485
0xd459  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xd45e  ldc.i4.s 0xA
0xd460  ldstr    aTokenHandlerFa// "Token Handler: Failed to get cookie val"...
0xd465  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xd46a  ldarg.0
0xd46b  call     instance class [mscorlib]System.Exception Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::CreateFailureException()
0xd470  throw
0xd471  ldarg.1
0xd472  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken::get_Password()
0xd477  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd47c  brfalse.s loc_D4D0
0xd47e  ldc.i4   0x121B34C
0xd483  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xd488  ldc.i4.s 0xA
0xd48a  ldstr    aSetupuservalid// "SetupUserValidationType: Password not s"...
0xd48f  ldc.i4.1
0xd490  newarr   [mscorlib]System.Object
0xd495  stloc.s  7
0xd497  ldloc.s  7
0xd499  ldc.i4.0
0xd49a  ldarg.1
0xd49b  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken::get_UserName()
0xd4a0  dup
0xd4a1  brtrue.s loc_D4A9
0xd4a3  pop
0xd4a4  ldstr    aNull_0// "Null"
0xd4a9  stelem.ref
0xd4aa  ldloc.s  7
0xd4ac  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xd4b1  ldarg.2
0xd4b2  callvirt instance string [System.Configuration]System.Configuration.Provider.ProviderBase::get_Name()
0xd4b7  ldarg.1
0xd4b8  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken::get_UserName()
0xd4bd  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::FormatAccountName(string, string)
0xd4c2  stloc.1
0xd4c3  ldarg.3
0xd4c4  ldloc.1
0xd4c5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPFormsClaimProvider::CreateMembershipClaim(string)
0xd4ca  stind.ref
0xd4cb  ldarg.s  6
0xd4cd  ldc.i4.0
0xd4ce  stind.i4
0xd4cf  ret
0xd4d0  ldarg.0
0xd4d1  ldarg.1
0xd4d2  call     instance bool Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::IsSignInRequest(class [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken userToken)
0xd4d7  brfalse.s loc_D52B
0xd4d9  ldc.i4   0x12628D2
0xd4de  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xd4e3  ldc.i4.s 0x32
0xd4e5  ldstr    aSetupuservalid_0// "SetupUserValidationType: Sign-in operat"...
0xd4ea  ldc.i4.1
0xd4eb  newarr   [mscorlib]System.Object
0xd4f0  stloc.s  8
0xd4f2  ldloc.s  8
0xd4f4  ldc.i4.0
0xd4f5  ldarg.1
0xd4f6  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken::get_UserName()
0xd4fb  dup
0xd4fc  brtrue.s loc_D504
0xd4fe  pop
0xd4ff  ldstr    aNull_0// "Null"
0xd504  stelem.ref
0xd505  ldloc.s  8
0xd507  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xd50c  ldarg.2
0xd50d  callvirt instance string [System.Configuration]System.Configuration.Provider.ProviderBase::get_Name()
0xd512  ldarg.1
0xd513  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken::get_UserName()
0xd518  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::FormatAccountName(string, string)
0xd51d  stloc.2
0xd51e  ldarg.3
0xd51f  ldloc.2
0xd520  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPFormsClaimProvider::CreateMembershipClaim(string)
0xd525  stind.ref
0xd526  ldarg.s  6
0xd528  ldc.i4.0
0xd529  stind.i4
0xd52a  ret
0xd52b  ldarg.0
0xd52c  ldarg.1
0xd52d  ldloca.s 0
0xd52f  call     instance bool Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::InitializeAndValidateCookieValueFromToken(class [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken userToken, [out] class Microsoft.SharePoint.IdentityModel.ISPSessionSecurityTokenCookieValue& resultCookie)
0xd534  brfalse  loc_D655
0xd539  ldarg.s  6
0xd53b  ldc.i4.1
0xd53c  stind.i4
0xd53d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager::get_Local()
0xd542  stloc.3
0xd543  ldarg.s  5
0xd545  ldarg.1
0xd546  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken::get_UserName()
0xd54b  stind.ref
0xd54c  ldarg.3
0xd54d  ldloc.3
0xd54e  ldarg.1
0xd54f  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken::get_UserName()
0xd554  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager::DecodeClaimFromFormsSuffix(string)
0xd559  stind.ref
0xd55a  ldarg.s  4
0xd55c  ldarg.3
0xd55d  ldind.ref
0xd55e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager::GetProviderUserKeyClaim(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim)
0xd563  stind.ref
0xd564  ldarg.s  4
0xd566  ldind.ref
0xd567  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_ClaimType()
0xd56c  ldarg.s  4
0xd56e  ldind.ref
0xd56f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_Value()
0xd574  ldarg.s  4
0xd576  ldind.ref
0xd577  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_ValueType()
0xd57c  ldarg.s  4
0xd57e  ldind.ref
0xd57f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_OriginalIssuer()
0xd584  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimEncodingManager::EncodeClaimIntoFormsSuffix(string, string, string, string)
0xd589  stloc.s  4
0xd58b  ldloc.0
0xd58c  callvirt instance string Microsoft.SharePoint.IdentityModel.ISPSessionSecurityTokenCookieValue::get_UserKey()
0xd591  ldloc.s  4
0xd593  ldc.i4.5
0xd594  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xd599  brtrue.s loc_D5DE
0xd59b  ldarg.0
0xd59c  ldarg.s  6
0xd59e  ldind.i4
0xd59f  call     instance string Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::GetLogMessagePrefixForOperationType(valuetype Microsoft.SharePoint.IdentityModel.SPFormOperation operationType)
0xd5a4  stloc.s  5
0xd5a6  ldc.i4   0xDF486
0xd5ab  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xd5b0  ldc.i4.s 0xA
0xd5b2  ldloc.s  5
0xd5b4  ldstr    aUserKeysFailed// "User keys failed to match for user '{0}"...
0xd5b9  call     string [mscorlib]System.String::Concat(string, string)
0xd5be  ldc.i4.1
0xd5bf  newarr   [mscorlib]System.Object
0xd5c4  stloc.s  9
0xd5c6  ldloc.s  9
0xd5c8  ldc.i4.0
0xd5c9  ldarg.1
0xd5ca  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken::get_UserName()
0xd5cf  stelem.ref
0xd5d0  ldloc.s  9
0xd5d2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xd5d7  ldarg.0
0xd5d8  call     instance class [mscorlib]System.Exception Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::CreateFailureException()
0xd5dd  throw
0xd5de  ldarg.s  7
0xd5e0  ldloc.0
0xd5e1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.ISPSessionSecurityTokenCookieValue::get_AuthenticationValidFromUtc()
0xd5e6  stobj    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0xd5eb  ldc.i4   0x5D4889
0xd5f0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xd5f5  ldc.i4.s 0x32
0xd5f7  ldstr    aSetupuservalid_1// "SetupUserValidationType: Incoming cooki"...
0xd5fc  ldc.i4.3
0xd5fd  newarr   [mscorlib]System.Object
0xd602  stloc.s  0xA
0xd604  ldloc.s  0xA
0xd606  ldc.i4.0
0xd607  ldarg.1
0xd608  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken::get_UserName()
0xd60d  dup
0xd60e  brtrue.s loc_D616
0xd610  pop
0xd611  ldstr    aNull_0// "Null"
0xd616  stelem.ref
0xd617  ldloc.s  0xA
0xd619  ldc.i4.1
0xd61a  ldarg.s  7
0xd61c  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0xd621  brtrue.s loc_D62A
0xd623  ldstr    aNoValue// "No value"
0xd628  br.s     loc_D640
0xd62a  ldarg.s  7
0xd62c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0xd631  stloc.s  0xB
0xd633  ldloca.s 0xB
0xd635  constrained. [mscorlib]System.DateTime
0xd63b  callvirt instance string [mscorlib]System.Object::ToString()
0xd640  stelem.ref
0xd641  ldloc.s  0xA
0xd643  ldc.i4.2
0xd644  ldarg.s  6
0xd646  ldind.i4
0xd647  box      Microsoft.SharePoint.IdentityModel.SPFormOperation
0xd64c  stelem.ref
0xd64d  ldloc.s  0xA
0xd64f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xd654  ret
0xd655  ldc.i4   0x11D44D9
0xd65a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xd65f  ldc.i4.s 0x32
0xd661  ldstr    aSetupuservalid_2// "SetupUserValidationType: Cookie validat"...
0xd666  ldc.i4.1
0xd667  newarr   [mscorlib]System.Object
0xd66c  stloc.s  0xC
0xd66e  ldloc.s  0xC
0xd670  ldc.i4.0
0xd671  ldarg.1
0xd672  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken::get_UserName()
0xd677  dup
0xd678  brtrue.s loc_D680
0xd67a  pop
0xd67b  ldstr    aNull_0// "Null"
0xd680  stelem.ref
0xd681  ldloc.s  0xC
0xd683  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xd688  ldarg.2
0xd689  callvirt instance string [System.Configuration]System.Configuration.Provider.ProviderBase::get_Name()
0xd68e  ldarg.1
0xd68f  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken::get_UserName()
0xd694  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::FormatAccountName(string, string)
0xd699  stloc.s  6
0xd69b  ldarg.3
0xd69c  ldloc.s  6
0xd69e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPFormsClaimProvider::CreateMembershipClaim(string)
0xd6a3  stind.ref
0xd6a4  ldarg.s  6
0xd6a6  ldc.i4.0
0xd6a7  stind.i4
0xd6a8  ret
```
