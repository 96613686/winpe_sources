# Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::GetTokenLifetime

- ea: `0x1df00`
- end: `0x1e122`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::GetTokenLifetime`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f380`

## callees

- `0x198d0`
- `0x19900`
- `0x19910`
- `0x1b880`
- `0x1df00`
- `0x1e130`
- `0x1e300`
- `0x2c520`

## string_xrefs

- `0x1df1c`: `SPSecurityTokenService.GetTokenLifetime()`
- `0x1df5f`: `Token lifetime set to '{0}'.`
- `0x1dfc3`: `Token lifetime set to '{0}'.`
- `0x1dff4`: `Token lifetime set to '{0}'.`
- `0x1e015`: `GetTokenLifetime: This is an OAuth Request, so we will look into the user identity to figure out the correct token lifetime.`
- `0x1e054`: `Token lifetime set to incoming token lifetime '{0}'.`
- `0x1e06f`: `Token lifetime for unkown request type set to '{0}'.`
- `0x1e0ec`: `Problem getting token lifetime. Exception: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1df00  ldc.i4   0x1299242
0x1df05  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x1df0a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1df0f  ldstr    aRequestinfo// "requestInfo"
0x1df14  ldarg.1
0x1df15  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x1df1a  ldnull
0x1df1b  stloc.0
0x1df1c  ldstr    aSpsecuritytoke_3// "SPSecurityTokenService.GetTokenLifetime"...
0x1df21  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0x1df26  stloc.s  7
0x1df28  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_Local()
0x1df2d  stloc.1
0x1df2e  ldc.i4   0xC8
0x1df33  stloc.2
0x1df34  ldnull
0x1df35  stloc.3
0x1df36  ldarg.1
0x1df37  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_IsActAs()
0x1df3c  brfalse.s loc_1DF6F
0x1df3e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1df43  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1df48  ldloc.1
0x1df49  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_ServiceTokenLifetime()
0x1df4e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x1df53  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.Lifetime::.ctor(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1df58  stloc.0
0x1df59  ldarg.1
0x1df5a  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1df5f  ldstr    aTokenLifetimeS// "Token lifetime set to '{0}'."
0x1df64  call     string [mscorlib]System.String::Concat(string, string)
0x1df69  stloc.3
0x1df6a  br       loc_1E07D
0x1df6f  ldarg.1
0x1df70  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_IsLogonRequest()
0x1df75  brfalse  loc_1E061
0x1df7a  ldarg.1
0x1df7b  callvirt instance valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestSource Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_Source()
0x1df80  stloc.s  8
0x1df82  ldloc.s  8
0x1df84  switch   loc_1DFA2, loc_1DFD3, loc_1E07D, loc_1E07D, loc_1E001
0x1df9d  br       loc_1E07D
0x1dfa2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1dfa7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1dfac  ldloc.1
0x1dfad  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_WindowsTokenLifetime()
0x1dfb2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x1dfb7  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.Lifetime::.ctor(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1dfbc  stloc.0
0x1dfbd  ldarg.1
0x1dfbe  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1dfc3  ldstr    aTokenLifetimeS// "Token lifetime set to '{0}'."
0x1dfc8  call     string [mscorlib]System.String::Concat(string, string)
0x1dfcd  stloc.3
0x1dfce  br       loc_1E07D
0x1dfd3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1dfd8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1dfdd  ldloc.1
0x1dfde  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_FormsTokenLifetime()
0x1dfe3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x1dfe8  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.Lifetime::.ctor(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1dfed  stloc.0
0x1dfee  ldarg.1
0x1dfef  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1dff4  ldstr    aTokenLifetimeS// "Token lifetime set to '{0}'."
0x1dff9  call     string [mscorlib]System.String::Concat(string, string)
0x1dffe  stloc.3
0x1dfff  br.s     loc_1E07D
0x1e001  ldarg.1
0x1e002  call     bool Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::IsOAuthRequest(class Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext requestInfo)
0x1e007  brfalse.s loc_1E028
0x1e009  ldc.i4   0x35D0D6
0x1e00e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e013  ldc.i4.s 0x32
0x1e015  ldstr    aGettokenlifeti// "GetTokenLifetime: This is an OAuth Requ"...
0x1e01a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1e01f  ldarg.0
0x1e020  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.Lifetime Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::GetTokenLifetimeForOAuthRequest()
0x1e025  stloc.0
0x1e026  br.s     loc_1E04E
0x1e028  ldarg.0
0x1e029  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.SecurityTokenService::get_Request()
0x1e02e  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_OnBehalfOf()
0x1e033  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement::GetSecurityToken()
0x1e038  stloc.s  4
0x1e03a  ldloc.s  4
0x1e03c  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0x1e041  ldloc.s  4
0x1e043  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0x1e048  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.Lifetime::.ctor(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1e04d  stloc.0
0x1e04e  ldarg.1
0x1e04f  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1e054  ldstr    aTokenLifetimeS_0// "Token lifetime set to incoming token li"...
0x1e059  call     string [mscorlib]System.String::Concat(string, string)
0x1e05e  stloc.3
0x1e05f  br.s     loc_1E07D
0x1e061  ldarg.0
0x1e062  ldarg.2
0x1e063  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.Lifetime [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.SecurityTokenService::GetTokenLifetime(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.Lifetime)
0x1e068  stloc.0
0x1e069  ldarg.1
0x1e06a  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1e06f  ldstr    aTokenLifetimeF// "Token lifetime for unkown request type "...
0x1e074  call     string [mscorlib]System.String::Concat(string, string)
0x1e079  stloc.3
0x1e07a  ldc.i4.s 0xA
0x1e07c  stloc.2
0x1e07d  ldsfld   string [mscorlib]System.String::Empty
0x1e082  stloc.s  5
0x1e084  ldloc.0
0x1e085  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.Lifetime::get_Expires()
0x1e08a  stloc.s  9
0x1e08c  ldloca.s 9
0x1e08e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x1e093  brfalse.s loc_1E0B5
0x1e095  ldloc.0
0x1e096  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.Lifetime::get_Expires()
0x1e09b  stloc.s  0xA
0x1e09d  ldloca.s 0xA
0x1e09f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x1e0a4  stloc.s  0xB
0x1e0a6  ldloca.s 0xB
0x1e0a8  constrained. [mscorlib]System.DateTime
0x1e0ae  callvirt instance string [mscorlib]System.Object::ToString()
0x1e0b3  stloc.s  5
0x1e0b5  ldc.i4   0x15D621
0x1e0ba  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e0bf  ldloc.2
0x1e0c0  ldloc.3
0x1e0c1  ldc.i4.1
0x1e0c2  newarr   [mscorlib]System.Object
0x1e0c7  stloc.s  0xC
0x1e0c9  ldloc.s  0xC
0x1e0cb  ldc.i4.0
0x1e0cc  ldloc.s  5
0x1e0ce  stelem.ref
0x1e0cf  ldloc.s  0xC
0x1e0d1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1e0d6  leave.s  loc_1E112
0x1e0d8  stloc.s  6
0x1e0da  ldc.i4   0x15D622
0x1e0df  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e0e4  ldc.i4.s 0xA
0x1e0e6  ldarg.1
0x1e0e7  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1e0ec  ldstr    aProblemGetting// "Problem getting token lifetime. Excepti"...
0x1e0f1  call     string [mscorlib]System.String::Concat(string, string)
0x1e0f6  ldc.i4.1
0x1e0f7  newarr   [mscorlib]System.Object
0x1e0fc  stloc.s  0xD
0x1e0fe  ldloc.s  0xD
0x1e100  ldc.i4.0
0x1e101  ldloc.s  6
0x1e103  callvirt instance string [mscorlib]System.Object::ToString()
0x1e108  stelem.ref
0x1e109  ldloc.s  0xD
0x1e10b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1e110  rethrow
0x1e112  leave.s  loc_1E120
0x1e114  ldloc.s  7
0x1e116  brfalse.s loc_1E11F
0x1e118  ldloc.s  7
0x1e11a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e11f  endfinally
0x1e120  ldloc.0
0x1e121  ret
```
