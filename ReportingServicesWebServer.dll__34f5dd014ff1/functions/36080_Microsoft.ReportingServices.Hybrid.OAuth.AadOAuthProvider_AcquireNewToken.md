# Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::AcquireNewToken

- ea: `0x36080`
- end: `0x36167`
- name: `Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::AcquireNewToken`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x36210`

## callees

- `0x35910`
- `0x35990`
- `0x359b0`
- `0x35f40`
- `0x36080`
- `0x36170`
- `0x36190`
- `0x36350`
- `0x36370`
- `0x36550`
- `0x36900`
- `0x36920`
- `0x36940`

## string_xrefs

- `0x3610f`: `temporarily_unavailable`
- `0x36153`: `Failed to get Authorization Token`

## pseudocode

```c

```

## disassembly

```asm
0x36080  ldarg.0
0x36081  call     instance string Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::get_AuthorizationCode()
0x36086  brfalse  loc_36152
0x3608b  ldarg.0
0x3608c  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_tokenResponse
0x36091  ldstr    aCode// "code"
0x36096  ldarg.0
0x36097  call     instance string Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::get_AuthorizationCode()
0x3609c  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x360a1  ldarg.0
0x360a2  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x360a7  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration::get_TokenUrl()
0x360ac  call     class [System]System.UriBuilder Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthHelper::GetUrlBuilder(string url)
0x360b1  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x360b6  ldarg.0
0x360b7  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_tokenResponse
0x360bc  ldarg.0
0x360bd  ldfld    class Microsoft.ReportingServices.Hybrid.OAuth.IServiceTokenStore Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceTokenStore
0x360c2  call     class Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthHelper::GetTokenFromRequestValues(class [System]System.Uri tokenUrl, class [System]System.Collections.Specialized.NameValueCollection values, class Microsoft.ReportingServices.Hybrid.OAuth.IServiceTokenStore store)
0x360c7  stloc.1
0x360c8  ldloc.1
0x360c9  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::get_Error()
0x360ce  brfalse.s loc_3612B
0x360d0  ldloc.1
0x360d1  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::get_Error()
0x360d6  ldstr    asc_53790// ": "
0x360db  ldloc.1
0x360dc  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::get_ErrorDescription()
0x360e1  call     string [mscorlib]System.String::Concat(string, string, string)
0x360e6  stloc.2
0x360e7  ldnull
0x360e8  ldloc.2
0x360e9  newobj   instance void Microsoft.ReportingServices.Hybrid.OAuth.LogInEventArgs::.ctor(class Microsoft.ReportingServices.Hybrid.OAuth.ServiceIdToken userInfo, string error)
0x360ee  stloc.0
0x360ef  ldarg.0
0x360f0  ldloc.0
0x360f1  call     instance void Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::OnLoginFailed(class Microsoft.ReportingServices.Hybrid.OAuth.LogInEventArgs args)
0x360f6  ldloc.1
0x360f7  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::get_Error()
0x360fc  ldstr    aInteractionReq// "interaction_required"
0x36101  ldc.i4.5
0x36102  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x36107  brtrue.s loc_3611C
0x36109  ldloc.1
0x3610a  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::get_Error()
0x3610f  ldstr    aTemporarilyUna// "temporarily_unavailable"
0x36114  ldc.i4.5
0x36115  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3611a  brfalse.s loc_36124
0x3611c  ldloc.2
0x3611d  ldnull
0x3611e  newobj   instance void Microsoft.ReportingServices.Hybrid.OAuth.AadCommunicationException::.ctor(string msg, [opt] class [mscorlib]System.Exception innerException)
0x36123  throw
0x36124  ldloc.2
0x36125  newobj   instance void [mscorlib]System.UnauthorizedAccessException::.ctor(string)
0x3612a  throw
0x3612b  ldloc.1
0x3612c  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::get_IdToken()
0x36131  call     class Microsoft.ReportingServices.Hybrid.OAuth.ServiceIdToken Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthHelper::GetIdTokenFromResponseString(string responseString)
0x36136  ldarg.0
0x36137  ldfld    class Microsoft.ReportingServices.Hybrid.OAuth.IAadCache Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_cache
0x3613c  ldloc.1
0x3613d  callvirt instance void Microsoft.ReportingServices.Hybrid.OAuth.IAadCache::SaveServiceTokenInCache(class Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken value)
0x36142  ldnull
0x36143  newobj   instance void Microsoft.ReportingServices.Hybrid.OAuth.LogInEventArgs::.ctor(class Microsoft.ReportingServices.Hybrid.OAuth.ServiceIdToken userInfo, string error)
0x36148  stloc.0
0x36149  ldarg.0
0x3614a  ldloc.0
0x3614b  call     instance void Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::OnLoginSuccessful(class Microsoft.ReportingServices.Hybrid.OAuth.LogInEventArgs args)
0x36150  ldloc.1
0x36151  ret
0x36152  ldnull
0x36153  ldstr    aFailedToGetAut// "Failed to get Authorization Token"
0x36158  newobj   instance void Microsoft.ReportingServices.Hybrid.OAuth.LogInEventArgs::.ctor(class Microsoft.ReportingServices.Hybrid.OAuth.ServiceIdToken userInfo, string error)
0x3615d  stloc.0
0x3615e  ldarg.0
0x3615f  ldloc.0
0x36160  call     instance void Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::OnLoginFailed(class Microsoft.ReportingServices.Hybrid.OAuth.LogInEventArgs args)
0x36165  ldnull
0x36166  ret
```
