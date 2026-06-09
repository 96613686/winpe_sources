# Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthAuthenticationMiddleware::Invoke

- ea: `0x2be0`
- end: `0x2e47`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthAuthenticationMiddleware::Invoke`
- size: `615`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x2be0`

## string_xrefs

- `0x2c0c`: `Error retrieving user info from the authentication service. Exception: {0}`
- `0x2d78`: `Bearer authorization_uri="{0}"`
- `0x2dc4`: `oauthLogoutUrl_uri="{0}"`

## pseudocode

```c

```

## disassembly

```asm
0x2be0  ldarg.0
0x2be1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IOAuthClientConfigurationService Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthAuthenticationMiddleware::_oAuthClientConfigurationService
0x2be6  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IOAuthClientConfigurationService::IsOAuthRequired()
0x2beb  brfalse  loc_2E38
0x2bf0  ldarg.0
0x2bf1  ldfld    class [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.IAuthenticationService Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthAuthenticationMiddleware::_authService
0x2bf6  ldarg.1
0x2bf7  newobj   instance void [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.RsRequestContext::.ctor(class [Microsoft.Owin]Microsoft.Owin.IOwinContext)
0x2bfc  callvirt instance class [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.IWebHostUserContext [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.IAuthenticationService::GetUserInfo(class [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.RsRequestContext)
0x2c01  stloc.0
0x2c02  leave.s  loc_2C56
0x2c04  stloc.1
0x2c05  ldarg.0
0x2c06  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthAuthenticationMiddleware::_logger
0x2c0b  ldc.i4.1
0x2c0c  ldstr    aErrorRetrievin// "Error retrieving user info from the aut"...
0x2c11  ldloc.1
0x2c12  call     string [mscorlib]System.String::Format(string, object)
0x2c17  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2c1c  ldarg.1
0x2c1d  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x2c22  ldc.i4   0x1F4
0x2c27  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::set_StatusCode(int32)
0x2c2c  ldarg.1
0x2c2d  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x2c32  ldc.i4   0x1F4
0x2c37  stloc.2
0x2c38  ldloca.s 2
0x2c3a  constrained. [System]System.Net.HttpStatusCode
0x2c40  callvirt instance string [mscorlib]System.Object::ToString()
0x2c45  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::set_ReasonPhrase(string)
0x2c4a  ldc.i4.0
0x2c4b  call     T0x2B000008
0x2c50  stloc.3
0x2c51  leave    loc_2E45
0x2c56  ldloc.0
0x2c57  brfalse  loc_2D6B
0x2c5c  ldc.i4.2
0x2c5d  newarr   [mscorlib]System.String
0x2c62  dup
0x2c63  ldc.i4.0
0x2c64  ldstr    aOwin// "owin"
0x2c69  stelem.ref
0x2c6a  dup
0x2c6b  ldc.i4.1
0x2c6c  ldarg.0
0x2c6d  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2c72  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2c77  stelem.ref
0x2c78  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0x2c7d  stloc.s  4
0x2c7f  ldarg.0
0x2c80  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthAuthenticationMiddleware::_logger
0x2c85  ldc.i4.3
0x2c86  ldstr    aOauthAuthorize// "oAuth authorized: "
0x2c8b  ldloc.0
0x2c8c  callvirt instance string [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.IWebHostUserContext::get_UserName()
0x2c91  call     string [mscorlib]System.String::Concat(string, string)
0x2c96  dup
0x2c97  brtrue.s loc_2C9F
0x2c99  pop
0x2c9a  ldstr    aNull// "(null)"
0x2c9f  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2ca4  ldloc.0
0x2ca5  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.IWebHostUserContext::get_Identity()
0x2caa  newobj   instance void [mscorlib]System.Security.Claims.ClaimsPrincipal::.ctor(class [mscorlib]System.Security.Principal.IIdentity)
0x2caf  stloc.s  5
0x2cb1  ldarg.1
0x2cb2  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x2cb7  ldloc.s  5
0x2cb9  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinRequest::set_User(class [mscorlib]System.Security.Principal.IPrincipal)
0x2cbe  ldarg.1
0x2cbf  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x2cc4  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Headers()
0x2cc9  brfalse.s loc_2D01
0x2ccb  ldarg.1
0x2ccc  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x2cd1  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Headers()
0x2cd6  ldstr    aAuthorization// "Authorization"
0x2cdb  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary::get_Item(string)
0x2ce0  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2ce5  brtrue.s loc_2D01
0x2ce7  ldarg.1
0x2ce8  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x2ced  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Headers()
0x2cf2  ldstr    aAuthorization// "Authorization"
0x2cf7  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary::get_Item(string)
0x2cfc  call     void [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.OwinSynchronizationContext::SetAuthenticationHeader(string)
0x2d01  ldarg.1
0x2d02  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x2d07  callvirt instance class [Microsoft.Owin]Microsoft.Owin.RequestCookieCollection [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Cookies()
0x2d0c  brfalse.s loc_2D50
0x2d0e  ldarg.1
0x2d0f  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x2d14  callvirt instance class [Microsoft.Owin]Microsoft.Owin.RequestCookieCollection [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Cookies()
0x2d19  ldarg.0
0x2d1a  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IOAuthClientConfigurationService Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthAuthenticationMiddleware::_oAuthClientConfigurationService
0x2d1f  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IOAuthClientConfigurationService::get_Configuration()
0x2d24  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration::get_SessionCookieName()
0x2d29  callvirt instance string [Microsoft.Owin]Microsoft.Owin.RequestCookieCollection::get_Item(string)
0x2d2e  stloc.s  6
0x2d30  ldloc.s  6
0x2d32  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2d37  brtrue.s loc_2D50
0x2d39  ldarg.0
0x2d3a  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IOAuthClientConfigurationService Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthAuthenticationMiddleware::_oAuthClientConfigurationService
0x2d3f  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IOAuthClientConfigurationService::get_Configuration()
0x2d44  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration::get_SessionCookieName()
0x2d49  ldloc.s  6
0x2d4b  call     void [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.OwinSynchronizationContext::SetOAuthSessionCookie(string, string)
0x2d50  leave.s  loc_2D5E
0x2d52  ldloc.s  4
0x2d54  brfalse.s loc_2D5D
0x2d56  ldloc.s  4
0x2d58  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d5d  endfinally
0x2d5e  ldarg.0
0x2d5f  call     instance class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::get_Next()
0x2d64  ldarg.1
0x2d65  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::Invoke(class [Microsoft.Owin]Microsoft.Owin.IOwinContext)
0x2d6a  ret
0x2d6b  ldarg.0
0x2d6c  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IOAuthClientConfigurationService Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthAuthenticationMiddleware::_oAuthClientConfigurationService
0x2d71  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IOAuthClientConfigurationService::get_Configuration()
0x2d76  stloc.s  7
0x2d78  ldstr    aBearerAuthoriz// "Bearer authorization_uri=\"{0}\""
0x2d7d  ldloc.s  7
0x2d7f  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration::get_AuthorizationUrl()
0x2d84  call     string [mscorlib]System.String::Format(string, object)
0x2d89  stloc.s  8
0x2d8b  ldstr    aResourceId0// "resource_id=\"{0}\""
0x2d90  ldloc.s  7
0x2d92  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration::get_ResourceUrl()
0x2d97  call     string [mscorlib]System.String::Format(string, object)
0x2d9c  stloc.s  9
0x2d9e  ldstr    aClientId0// "client_id=\"{0}\""
0x2da3  ldloc.s  7
0x2da5  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration::get_ClientId()
0x2daa  call     string [mscorlib]System.String::Format(string, object)
0x2daf  stloc.s  0xA
0x2db1  ldstr    aNativeclientId// "nativeclient_id=\"{0}\""
0x2db6  ldloc.s  7
0x2db8  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration::get_NativeClientId()
0x2dbd  call     string [mscorlib]System.String::Format(string, object)
0x2dc2  stloc.s  0xB
0x2dc4  ldstr    aOauthlogouturl// "oauthLogoutUrl_uri=\"{0}\""
0x2dc9  ldloc.s  7
0x2dcb  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration::get_LogoutUrl()
0x2dd0  call     string [mscorlib]System.String::Format(string, object)
0x2dd5  stloc.s  0xC
0x2dd7  ldarg.1
0x2dd8  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x2ddd  ldc.i4   0x191
0x2de2  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::set_StatusCode(int32)
0x2de7  ldarg.1
0x2de8  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x2ded  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinResponse::get_Headers()
0x2df2  ldstr    aWwwAuthenticat// "WWW-Authenticate"
0x2df7  ldc.i4.5
0x2df8  newarr   [mscorlib]System.String
0x2dfd  dup
0x2dfe  ldc.i4.0
0x2dff  ldloc.s  8
0x2e01  stelem.ref
0x2e02  dup
0x2e03  ldc.i4.1
0x2e04  ldloc.s  9
0x2e06  stelem.ref
0x2e07  dup
0x2e08  ldc.i4.2
0x2e09  ldloc.s  0xA
0x2e0b  stelem.ref
0x2e0c  dup
0x2e0d  ldc.i4.3
0x2e0e  ldloc.s  0xB
0x2e10  stelem.ref
0x2e11  dup
0x2e12  ldc.i4.4
0x2e13  ldloc.s  0xC
0x2e15  stelem.ref
0x2e16  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary::AppendValues(string, string[])
0x2e1b  ldarg.1
0x2e1c  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x2e21  ldc.i4.6
0x2e22  newobj   instance void class <>f__AnonymousType1`1<int32>::.ctor(var<u1>)
0x2e27  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0x2e2c  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::Write(string)
0x2e31  ldc.i4.0
0x2e32  call     T0x2B000008
0x2e37  ret
0x2e38  ldarg.0
0x2e39  call     instance class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::get_Next()
0x2e3e  ldarg.1
0x2e3f  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::Invoke(class [Microsoft.Owin]Microsoft.Owin.IOwinContext)
0x2e44  ret
0x2e45  ldloc.3
0x2e46  ret
```
