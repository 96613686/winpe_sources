# Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapAuthenticationHelper::PrepareWebRequest

- ea: `0xae30`
- end: `0xaf18`
- name: `Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapAuthenticationHelper::PrepareWebRequest`
- size: `232`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xacd0`
- `0xaf20`
- `0xbe00`

## callees

- `0xadb0`
- `0xae30`
- `0x12d70`

## pseudocode

```c

```

## disassembly

```asm
0xae30  ldarg.0
0xae31  brfalse  loc_AF16
0xae36  ldarg.0
0xae37  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0xae3c  ldstr    aAcceptLanguage// "Accept-Language"
0xae41  call     class [mscorlib]System.Threading.SynchronizationContext [mscorlib]System.Threading.SynchronizationContext::get_Current()
0xae46  call     string [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.SynchronizationContextExtensions::GetAcceptLanguage(class [mscorlib]System.Threading.SynchronizationContext)
0xae4b  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xae50  ldarg.1
0xae51  brfalse.s loc_AECE
0xae53  ldarg.1
0xae54  call     bool Microsoft.ReportingServices.Portal.Services.Extensions.IdentityExtensions::IsOAuthAuthenticated(class [mscorlib]System.Security.Principal.IIdentity identity)
0xae59  brfalse.s loc_AECE
0xae5b  call     class [mscorlib]System.Threading.SynchronizationContext [mscorlib]System.Threading.SynchronizationContext::get_Current()
0xae60  call     string [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.SynchronizationContextExtensions::GetAuthenticationHeader(class [mscorlib]System.Threading.SynchronizationContext)
0xae65  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xae6a  brtrue.s loc_AE86
0xae6c  ldarg.0
0xae6d  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0xae72  ldstr    aAuthorization// "Authorization"
0xae77  call     class [mscorlib]System.Threading.SynchronizationContext [mscorlib]System.Threading.SynchronizationContext::get_Current()
0xae7c  call     string [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.SynchronizationContextExtensions::GetAuthenticationHeader(class [mscorlib]System.Threading.SynchronizationContext)
0xae81  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xae86  call     class [mscorlib]System.Threading.SynchronizationContext [mscorlib]System.Threading.SynchronizationContext::get_Current()
0xae8b  call     valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.SynchronizationContextExtensions::GetOAuthSessionCookie(class [mscorlib]System.Threading.SynchronizationContext)
0xae90  stloc.0
0xae91  ldloca.s 0
0xae93  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0xae98  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xae9d  brtrue.s loc_AECE
0xae9f  ldarg.0
0xaea0  newobj   instance void [System]System.Net.CookieContainer::.ctor()
0xaea5  callvirt instance void [System]System.Net.HttpWebRequest::set_CookieContainer(class [System]System.Net.CookieContainer)
0xaeaa  ldarg.0
0xaeab  callvirt instance class [System]System.Net.CookieContainer [System]System.Net.HttpWebRequest::get_CookieContainer()
0xaeb0  ldloca.s 0
0xaeb2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0xaeb7  ldloca.s 0
0xaeb9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0xaebe  ldstr    asc_25576// "/"
0xaec3  ldarg.2
0xaec4  newobj   instance void [System]System.Net.Cookie::.ctor(string, string, string, string)
0xaec9  callvirt instance void [System]System.Net.CookieContainer::Add(class [System]System.Net.Cookie)
0xaece  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.WebRequestUtil::IsClientLocal()
0xaed3  brtrue.s loc_AEEA
0xaed5  ldarg.0
0xaed6  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0xaedb  ldstr    aRsclientnotloc// "RSClientNotLocalHeader"
0xaee0  ldstr    aTrue// "true"
0xaee5  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xaeea  ldarg.0
0xaeeb  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0xaef0  ldstr    aRsviawebapp// "RSViaWebApp"
0xaef5  ldstr    aTrue// "true"
0xaefa  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xaeff  ldarg.1
0xaf00  isinst   [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.IUserContextContainer
0xaf05  brfalse.s loc_AF16
0xaf07  ldarg.1
0xaf08  isinst   [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.IUserContextContainer
0xaf0d  stloc.1
0xaf0e  ldarg.0
0xaf0f  ldloc.1
0xaf10  ldarg.2
0xaf11  call     void Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapAuthenticationHelper::SetRequestProperties(class [System]System.Net.HttpWebRequest request, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.IUserContextContainer userContextContainer, string reportServerHostName)
0xaf16  ldarg.0
0xaf17  ret
```
