# Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::.ctor_0

- ea: `0x35cc0`
- end: `0x35f31`
- name: `Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::.ctor_0`
- size: `625`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x35cb0`
- `0x370a0`

## callees

- `0x35990`
- `0x35a50`
- `0x35cc0`
- `0x365a0`
- `0x365b0`
- `0x3ce10`

## string_xrefs

- `0x35d18`: `PowerBI Connection configuration is either invalid or missing.`
- `0x35dbf`: `redirect_uri`
- `0x35ed9`: `redirect_uri`
- `0x35f1f`: `refresh_token`

## pseudocode

```c

```

## disassembly

```asm
0x35cc0  ldarg.0
0x35cc1  call     instance void [mscorlib]System.Object::.ctor()
0x35cc6  newobj   instance void <>c__DisplayClass18_0::.ctor()
0x35ccb  stloc.0
0x35ccc  ldarg.0
0x35ccd  ldarg.1
0x35cce  stfld    class Microsoft.ReportingServices.Hybrid.OAuth.IAadCache Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_cache
0x35cd3  ldarg.0
0x35cd4  ldarg.2
0x35cd5  stfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x35cda  ldarg.0
0x35cdb  ldfld    class Microsoft.ReportingServices.Hybrid.OAuth.IAadCache Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_cache
0x35ce0  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.IAadCache::GetSessionState()
0x35ce5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x35cea  brfalse.s loc_35D0A
0x35cec  ldarg.0
0x35ced  ldfld    class Microsoft.ReportingServices.Hybrid.OAuth.IAadCache Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_cache
0x35cf2  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x35cf7  stloc.3
0x35cf8  ldloca.s 3
0x35cfa  constrained. [mscorlib]System.Guid
0x35d00  callvirt instance string [mscorlib]System.Object::ToString()
0x35d05  callvirt instance void Microsoft.ReportingServices.Hybrid.OAuth.IAadCache::SetSessionState(string value)
0x35d0a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x35d0f  ldarg.0
0x35d10  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x35d15  ldnull
0x35d16  cgt.un
0x35d18  ldstr    aPowerbiConnect// "PowerBI Connection configuration is eit"...
0x35d1d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x35d22  ldarg.0
0x35d23  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x35d28  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration::get_AuthorizationUrl()
0x35d2d  call     class [System]System.UriBuilder Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthHelper::GetUrlBuilder(string url)
0x35d32  stloc.1
0x35d33  ldarg.0
0x35d34  ldloc.1
0x35d35  callvirt instance string [System]System.UriBuilder::get_Query()
0x35d3a  call     class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpUtility::ParseQueryString(string)
0x35d3f  stfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_authResponse
0x35d44  ldarg.0
0x35d45  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_authResponse
0x35d4a  ldstr    aClientId// "client_id"
0x35d4f  ldarg.0
0x35d50  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x35d55  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration::get_ClientId()
0x35d5a  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x35d5f  ldarg.0
0x35d60  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_authResponse
0x35d65  ldstr    aResponseType// "response_type"
0x35d6a  ldstr    aCode// "code"
0x35d6f  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x35d74  ldloc.0
0x35d75  call     class [System]System.Uri Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthHelper::GetReportManagerAADUrl()
0x35d7a  stfld    class [System]System.Uri <>c__DisplayClass18_0::requestRedirectUrl
0x35d7f  ldnull
0x35d80  stloc.2
0x35d81  ldloc.0
0x35d82  ldfld    class [System]System.Uri <>c__DisplayClass18_0::requestRedirectUrl
0x35d87  ldnull
0x35d88  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x35d8d  brfalse.s loc_35DB9
0x35d8f  ldarg.0
0x35d90  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x35d95  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration::get_RedirectUrls()
0x35d9a  brfalse.s loc_35DB9
0x35d9c  ldarg.0
0x35d9d  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x35da2  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration::get_RedirectUrls()
0x35da7  ldloc.0
0x35da8  ldftn    instance bool <>c__DisplayClass18_0::<.ctor>b__0(string u)
0x35dae  newobj   instance void class [mscorlib]System.Predicate`1<string>::.ctor(object, native int)
0x35db3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::Find(!!T0)
0x35db8  stloc.2
0x35db9  ldarg.0
0x35dba  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_authResponse
0x35dbf  ldstr    aRedirectUri// "redirect_uri"
0x35dc4  ldloc.2
0x35dc5  dup
0x35dc6  brtrue.s loc_35DDA
0x35dc8  pop
0x35dc9  ldarg.0
0x35dca  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x35dcf  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration::get_RedirectUrls()
0x35dd4  ldc.i4.0
0x35dd5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x35dda  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x35ddf  ldarg.0
0x35de0  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_authResponse
0x35de5  ldstr    aResource_0// "resource"
0x35dea  ldarg.0
0x35deb  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x35df0  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration::get_ResourceUrl()
0x35df5  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x35dfa  ldarg.0
0x35dfb  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_authResponse
0x35e00  ldstr    aNux// "nux"
0x35e05  ldstr    a1_0// "1"
0x35e0a  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x35e0f  ldarg.0
0x35e10  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_authResponse
0x35e15  ldstr    aMkt// "mkt"
0x35e1a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x35e1f  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x35e24  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x35e29  ldarg.0
0x35e2a  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x35e2f  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration::get_ClientSecret()
0x35e34  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x35e39  brfalse.s loc_35E55
0x35e3b  ldarg.0
0x35e3c  ldc.i4.4
0x35e3d  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor(int32)
0x35e42  stfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_tokenResponse
0x35e47  ldarg.0
0x35e48  ldc.i4.3
0x35e49  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor(int32)
0x35e4e  stfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_refreshResponse
0x35e53  br.s     loc_35EA3
0x35e55  ldarg.0
0x35e56  ldc.i4.5
0x35e57  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor(int32)
0x35e5c  stfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_tokenResponse
0x35e61  ldarg.0
0x35e62  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_tokenResponse
0x35e67  ldstr    aClientSecret// "client_secret"
0x35e6c  ldarg.0
0x35e6d  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x35e72  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration::get_ClientSecret()
0x35e77  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x35e7c  ldarg.0
0x35e7d  ldc.i4.4
0x35e7e  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor(int32)
0x35e83  stfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_refreshResponse
0x35e88  ldarg.0
0x35e89  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_refreshResponse
0x35e8e  ldstr    aClientSecret// "client_secret"
0x35e93  ldarg.0
0x35e94  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x35e99  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration::get_ClientSecret()
0x35e9e  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x35ea3  ldarg.0
0x35ea4  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_tokenResponse
0x35ea9  ldstr    aClientId// "client_id"
0x35eae  ldarg.0
0x35eaf  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x35eb4  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration::get_ClientId()
0x35eb9  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x35ebe  ldarg.0
0x35ebf  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_tokenResponse
0x35ec4  ldstr    aGrantType// "grant_type"
0x35ec9  ldstr    aAuthorizationC// "authorization_code"
0x35ece  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x35ed3  ldarg.0
0x35ed4  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_tokenResponse
0x35ed9  ldstr    aRedirectUri// "redirect_uri"
0x35ede  ldloc.2
0x35edf  dup
0x35ee0  brtrue.s loc_35EF4
0x35ee2  pop
0x35ee3  ldarg.0
0x35ee4  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x35ee9  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration::get_RedirectUrls()
0x35eee  ldc.i4.0
0x35eef  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x35ef4  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x35ef9  ldarg.0
0x35efa  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_refreshResponse
0x35eff  ldstr    aClientId// "client_id"
0x35f04  ldarg.0
0x35f05  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceConfig
0x35f0a  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPowerBIOAuthConfiguration::get_ClientId()
0x35f0f  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x35f14  ldarg.0
0x35f15  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_refreshResponse
0x35f1a  ldstr    aGrantType// "grant_type"
0x35f1f  ldstr    aRefreshToken// "refresh_token"
0x35f24  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x35f29  ldarg.0
0x35f2a  ldarg.3
0x35f2b  stfld    class Microsoft.ReportingServices.Hybrid.OAuth.IServiceTokenStore Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_serviceTokenStore
0x35f30  ret
```
