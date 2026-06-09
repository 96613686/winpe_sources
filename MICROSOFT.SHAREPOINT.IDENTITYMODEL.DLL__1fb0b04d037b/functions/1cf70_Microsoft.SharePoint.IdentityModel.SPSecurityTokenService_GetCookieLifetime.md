# Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::GetCookieLifetime

- ea: `0x1cf70`
- end: `0x1d1f2`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::GetCookieLifetime`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ce30`

## callees

- `0x19ce0`
- `0x1b880`
- `0x1cf70`

## string_xrefs

- `0x1cf9e`: `STS Call: No context for security token request.`
- `0x1d14b`: `For Compliant Device, the cookie is persistent.`

## pseudocode

```c

```

## disassembly

```asm
0x1cf70  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1cf75  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1cf7a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalOrThrow()
0x1cf7f  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_CookieLifetime()
0x1cf84  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x1cf89  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.Lifetime::.ctor(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1cf8e  stloc.0
0x1cf8f  ldarg.0
0x1cf90  brtrue.s loc_1CFAD
0x1cf92  ldc.i4   0x180378A
0x1cf97  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1cf9c  ldc.i4.s 0xA
0x1cf9e  ldstr    aStsCallNoConte// "STS Call: No context for security token"...
0x1cfa3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1cfa8  br       loc_1D19C
0x1cfad  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::get_Current()
0x1cfb2  brtrue.s loc_1CFDA
0x1cfb4  ldc.i4   0x180378B
0x1cfb9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1cfbe  ldc.i4.s 0xA
0x1cfc0  ldarg.0
0x1cfc1  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1cfc6  ldstr    aNoContextForCo// "No context for cookie lifetime operatio"...
0x1cfcb  call     string [mscorlib]System.String::Concat(string, string)
0x1cfd0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1cfd5  br       loc_1D19C
0x1cfda  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::SessionCookieLifetimeKillSwitch
0x1cfdf  ldstr    a10132017// "10/13/2017"
0x1cfe4  ldstr    aAuthzenSession// "AuthZen_SessionCookieLifetime"
0x1cfe9  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x1cfee  brfalse.s loc_1D016
0x1cff0  ldc.i4   0x180378C
0x1cff5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1cffa  ldc.i4.s 0xA
0x1cffc  ldarg.0
0x1cffd  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1d002  ldstr    aKillswitchAuth// "Killswitch AuthZen_SessionCookieLifetim"...
0x1d007  call     string [mscorlib]System.String::Concat(string, string)
0x1d00c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1d011  br       loc_1D19C
0x1d016  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::get_Current()
0x1d01b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::get_SiteSubscriptionId()
0x1d020  stloc.3
0x1d021  ldloca.s 3
0x1d023  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x1d028  brtrue.s loc_1D05C
0x1d02a  ldc.i4.s 0x64
0x1d02c  stloc.1
0x1d02d  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPGlobal::get_IsSPO()
0x1d032  brfalse.s loc_1D037
0x1d034  ldc.i4.s 0xA
0x1d036  stloc.1
0x1d037  ldc.i4   0x180378D
0x1d03c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1d041  ldloc.1
0x1d042  ldarg.0
0x1d043  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1d048  ldstr    aNoSiteSubscrip// "No site subscription on scope."
0x1d04d  call     string [mscorlib]System.String::Concat(string, string)
0x1d052  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1d057  br       loc_1D19C
0x1d05c  ldc.i4   0x37A8
0x1d061  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::get_Current()
0x1d066  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::get_SiteSubscriptionId()
0x1d06b  stloc.s  4
0x1d06d  ldloca.s 4
0x1d06f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x1d074  ldc.i4.0
0x1d075  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.FederatedDirectory.Flighting::IsExpFeatureEnabledForSubscriptionId(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId, valuetype [mscorlib]System.Guid, bool)
0x1d07a  brtrue.s loc_1D0BF
0x1d07c  ldc.i4   0x180378E
0x1d081  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1d086  ldc.i4.s 0x64
0x1d088  ldarg.0
0x1d089  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1d08e  ldstr    aTheAuthzensess// "The AuthZenSessionCookieLifetime flight"...
0x1d093  call     string [mscorlib]System.String::Concat(string, string)
0x1d098  ldc.i4.1
0x1d099  newarr   [mscorlib]System.Object
0x1d09e  stloc.s  5
0x1d0a0  ldloc.s  5
0x1d0a2  ldc.i4.0
0x1d0a3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::get_Current()
0x1d0a8  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::get_SiteSubscriptionId()
0x1d0ad  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x1d0b2  stelem.ref
0x1d0b3  ldloc.s  5
0x1d0b5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1d0ba  br       loc_1D19C
0x1d0bf  ldc.i4.1
0x1d0c0  conv.i8
0x1d0c1  ldarg.0
0x1d0c2  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPAuthenticationSessionAttributes Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_SessionAttributes()
0x1d0c7  ldc.i4.1
0x1d0c8  conv.i8
0x1d0c9  and
0x1d0ca  bne.un.s loc_1D0F2
0x1d0cc  ldc.i4   0x180378F
0x1d0d1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1d0d6  ldc.i4.s 0x64
0x1d0d8  ldarg.0
0x1d0d9  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1d0de  ldstr    aTheCookieIsPer// "The cookie is persistent."
0x1d0e3  call     string [mscorlib]System.String::Concat(string, string)
0x1d0e8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1d0ed  br       loc_1D19C
0x1d0f2  ldc.i4.s 0x20
0x1d0f4  conv.i8
0x1d0f5  ldarg.0
0x1d0f6  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPAuthenticationSessionAttributes Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_SessionAttributes()
0x1d0fb  ldc.i4.s 0x20
0x1d0fd  conv.i8
0x1d0fe  and
0x1d0ff  bne.un.s loc_1D124
0x1d101  ldc.i4   0x1803790
0x1d106  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1d10b  ldc.i4.s 0x64
0x1d10d  ldarg.0
0x1d10e  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1d113  ldstr    aForDomainJoine// "For Domain Joined Device, the cookie is"...
0x1d118  call     string [mscorlib]System.String::Concat(string, string)
0x1d11d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1d122  br.s     loc_1D19C
0x1d124  ldc.i4   0x80
0x1d129  conv.i8
0x1d12a  ldarg.0
0x1d12b  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPAuthenticationSessionAttributes Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_SessionAttributes()
0x1d130  ldc.i4   0x80
0x1d135  conv.i8
0x1d136  and
0x1d137  bne.un.s loc_1D15C
0x1d139  ldc.i4   0x1803791
0x1d13e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1d143  ldc.i4.s 0x64
0x1d145  ldarg.0
0x1d146  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1d14b  ldstr    aForCompliantDe// "For Compliant Device, the cookie is per"...
0x1d150  call     string [mscorlib]System.String::Concat(string, string)
0x1d155  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1d15a  br.s     loc_1D19C
0x1d15c  ldc.i4   0x1803792
0x1d161  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1d166  ldc.i4.s 0x64
0x1d168  ldarg.0
0x1d169  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1d16e  ldstr    aTheCookieIsSes// "The cookie is session cookie."
0x1d173  call     string [mscorlib]System.String::Concat(string, string)
0x1d178  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1d17d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1d182  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1d187  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalOrThrow()
0x1d18c  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_SessionCookieLifetime()
0x1d191  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x1d196  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.Lifetime::.ctor(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1d19b  stloc.0
0x1d19c  leave.s  loc_1D1CB
0x1d19e  stloc.2
0x1d19f  ldc.i4   0x1803793
0x1d1a4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1d1a9  ldc.i4.s 0xA
0x1d1ab  ldstr    aStsCallProblem// "STS Call: Problem checking session cook"...
0x1d1b0  ldc.i4.1
0x1d1b1  newarr   [mscorlib]System.Object
0x1d1b6  stloc.s  6
0x1d1b8  ldloc.s  6
0x1d1ba  ldc.i4.0
0x1d1bb  ldloc.2
0x1d1bc  callvirt instance string [mscorlib]System.Object::ToString()
0x1d1c1  stelem.ref
0x1d1c2  ldloc.s  6
0x1d1c4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1d1c9  leave.s  loc_1D1CB
0x1d1cb  ldc.i4   0x1803794
0x1d1d0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1d1d5  ldc.i4.s 0x32
0x1d1d7  ldstr    aStsCallCookieL// "STS Call: Cookie Lifetime: '{0}'."
0x1d1dc  ldc.i4.1
0x1d1dd  newarr   [mscorlib]System.Object
0x1d1e2  stloc.s  7
0x1d1e4  ldloc.s  7
0x1d1e6  ldc.i4.0
0x1d1e7  ldloc.0
0x1d1e8  stelem.ref
0x1d1e9  ldloc.s  7
0x1d1eb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1d1f0  ldloc.0
0x1d1f1  ret
```
