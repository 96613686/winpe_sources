# Microsoft.SharePoint.IdentityModel.SPFormsOriginalIssuerBuilder::SetProviderNames

- ea: `0xcfd0`
- end: `0xd099`
- name: `Microsoft.SharePoint.IdentityModel.SPFormsOriginalIssuerBuilder::SetProviderNames`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xce10`

## callees

- `0xcdb0`
- `0xcfd0`
- `0xd0a0`
- `0xe5d0`
- `0xe5e0`

## string_xrefs

- `0xcfe4`: `SPFormsOriginalIssuerBuilder: SetProviderNames! RequestToken is null.`
- `0xcff3`: `RequestTokenMustBePresent`
- `0xd027`: `SecurityTokenIsInvalidType`
- `0xd052`: `UserNameSecurityToken`

## pseudocode

```c

```

## disassembly

```asm
0xcfd0  ldarg.0
0xcfd1  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken Microsoft.SharePoint.IdentityModel.SPOriginalIssuerBuilder::get_RequestToken()
0xcfd6  brtrue.s loc_D009
0xcfd8  ldc.i4   0xCB2CC
0xcfdd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xcfe2  ldc.i4.s 0xA
0xcfe4  ldstr    aSpformsorigina// "SPFormsOriginalIssuerBuilder: SetProvid"...
0xcfe9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xcfee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcff3  ldstr    aRequesttokenmu// "RequestTokenMustBePresent"
0xcff8  ldc.i4.0
0xcff9  newarr   [mscorlib]System.Object
0xcffe  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0xd003  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xd008  throw
0xd009  ldarg.0
0xd00a  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken Microsoft.SharePoint.IdentityModel.SPOriginalIssuerBuilder::get_RequestToken()
0xd00f  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_OnBehalfOf()
0xd014  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement::GetSecurityToken()
0xd019  isinst   [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken
0xd01e  stloc.0
0xd01f  ldloc.0
0xd020  brtrue.s loc_D064
0xd022  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd027  ldstr    aSecuritytokeni// "SecurityTokenIsInvalidType"
0xd02c  ldc.i4.2
0xd02d  newarr   [mscorlib]System.Object
0xd032  stloc.3
0xd033  ldloc.3
0xd034  ldc.i4.0
0xd035  ldarg.0
0xd036  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken Microsoft.SharePoint.IdentityModel.SPOriginalIssuerBuilder::get_RequestToken()
0xd03b  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_OnBehalfOf()
0xd040  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement::GetSecurityToken()
0xd045  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xd04a  callvirt instance string [mscorlib]System.Object::ToString()
0xd04f  stelem.ref
0xd050  ldloc.3
0xd051  ldc.i4.1
0xd052  ldstr    aUsernamesecuri// "UserNameSecurityToken"
0xd057  stelem.ref
0xd058  ldloc.3
0xd059  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0xd05e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xd063  throw
0xd064  ldloc.0
0xd065  call     string Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::GetMembershipProviderName(class [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken token)
0xd06a  stloc.1
0xd06b  ldloc.0
0xd06c  call     string Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::GetRoleProviderName(class [System.IdentityModel]System.IdentityModel.Tokens.UserNameSecurityToken token)
0xd071  stloc.2
0xd072  ldarg.0
0xd073  ldarg.0
0xd074  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken Microsoft.SharePoint.IdentityModel.SPOriginalIssuerBuilder::get_RequestToken()
0xd079  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.WSTrustMessage::get_AppliesTo()
0xd07e  callvirt instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Uri()
0xd083  ldloc.1
0xd084  ldloc.2
0xd085  call     instance void Microsoft.SharePoint.IdentityModel.SPFormsOriginalIssuerBuilder::ValidateFormsAuthProviderNames(class [System]System.Uri context, string membershipProvider, string roleProvider)
0xd08a  ldarg.0
0xd08b  ldloc.1
0xd08c  stfld    string Microsoft.SharePoint.IdentityModel.SPFormsOriginalIssuerBuilder::m_MembershipProviderName
0xd091  ldarg.0
0xd092  ldloc.2
0xd093  stfld    string Microsoft.SharePoint.IdentityModel.SPFormsOriginalIssuerBuilder::m_RoleProviderName
0xd098  ret
```
