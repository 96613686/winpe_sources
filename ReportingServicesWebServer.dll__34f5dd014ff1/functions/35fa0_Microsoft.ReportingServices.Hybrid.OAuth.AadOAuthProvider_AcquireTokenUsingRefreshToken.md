# Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::AcquireTokenUsingRefreshToken

- ea: `0x35fa0`
- end: `0x36071`
- name: `Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::AcquireTokenUsingRefreshToken`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x35f60`

## callees

- `0x35990`
- `0x359b0`
- `0x35fa0`
- `0x36350`
- `0x36550`
- `0x36560`
- `0x36570`
- `0x368c0`
- `0x36900`
- `0x36910`
- `0x36920`
- `0x36940`

## string_xrefs

- `0x35fb7`: `refresh_token`
- `0x3603c`: `temporarily_unavailable`

## pseudocode

```c

```

## disassembly

```asm
0x35fa0  ldarg.0
0x35fa1  ldfld    class Microsoft.ReportingServices.Hybrid.OAuth.IAadCache Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_cache
0x35fa6  callvirt instance class Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken Microsoft.ReportingServices.Hybrid.OAuth.IAadCache::GetServiceTokenFromCache()
0x35fab  stloc.0
0x35fac  ldloc.0
0x35fad  brtrue.s loc_35FB1
0x35faf  ldnull
0x35fb0  ret
0x35fb1  ldarg.0
0x35fb2  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_refreshResponse
0x35fb7  ldstr    aRefreshToken// "refresh_token"
0x35fbc  ldloc.0
0x35fbd  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::get_RefreshToken()
0x35fc2  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x35fc7  ldloc.0
0x35fc8  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::get_IdToken()
0x35fcd  stloc.1
0x35fce  ldarg.0
0x35fcf  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x35fd4  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration::get_TokenUrl()
0x35fd9  call     class [System]System.UriBuilder Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthHelper::GetUrlBuilder(string url)
0x35fde  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x35fe3  ldarg.0
0x35fe4  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_refreshResponse
0x35fe9  ldarg.0
0x35fea  ldfld    class Microsoft.ReportingServices.Hybrid.OAuth.IServiceTokenStore Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceTokenStore
0x35fef  call     class Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthHelper::GetTokenFromRequestValues(class [System]System.Uri tokenUrl, class [System]System.Collections.Specialized.NameValueCollection values, class Microsoft.ReportingServices.Hybrid.OAuth.IServiceTokenStore store)
0x35ff4  stloc.0
0x35ff5  ldloc.1
0x35ff6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x35ffb  brtrue.s loc_36004
0x35ffd  ldloc.0
0x35ffe  ldloc.1
0x35fff  callvirt instance void Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::set_IdToken(string value)
0x36004  ldloc.0
0x36005  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::get_Error()
0x3600a  brfalse.s loc_36063
0x3600c  ldloc.0
0x3600d  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::get_Error()
0x36012  ldstr    asc_53790// ": "
0x36017  ldloc.0
0x36018  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::get_ErrorDescription()
0x3601d  call     string [mscorlib]System.String::Concat(string, string, string)
0x36022  stloc.2
0x36023  ldloc.0
0x36024  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::get_Error()
0x36029  ldstr    aInteractionReq// "interaction_required"
0x3602e  ldc.i4.5
0x3602f  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x36034  brtrue.s loc_36049
0x36036  ldloc.0
0x36037  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::get_Error()
0x3603c  ldstr    aTemporarilyUna// "temporarily_unavailable"
0x36041  ldc.i4.5
0x36042  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x36047  brfalse.s loc_36051
0x36049  ldloc.2
0x3604a  ldnull
0x3604b  newobj   instance void Microsoft.ReportingServices.Hybrid.OAuth.AadCommunicationException::.ctor(string msg, [opt] class [mscorlib]System.Exception innerException)
0x36050  throw
0x36051  ldarg.0
0x36052  ldfld    class Microsoft.ReportingServices.Hybrid.OAuth.IAadCache Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_cache
0x36057  callvirt instance void Microsoft.ReportingServices.Hybrid.OAuth.IAadCache::RemoveServiceTokenFromCache()
0x3605c  ldloc.2
0x3605d  newobj   instance void [mscorlib]System.UnauthorizedAccessException::.ctor(string)
0x36062  throw
0x36063  ldarg.0
0x36064  ldfld    class Microsoft.ReportingServices.Hybrid.OAuth.IAadCache Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_cache
0x36069  ldloc.0
0x3606a  callvirt instance void Microsoft.ReportingServices.Hybrid.OAuth.IAadCache::SaveServiceTokenInCache(class Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken value)
0x3606f  ldloc.0
0x36070  ret
```
