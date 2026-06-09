# Microsoft.ReportingServices.Portal.WebApi.V2.Controllers.SessionController::Logoff

- ea: `0x240`
- end: `0x2cf`
- name: `Microsoft.ReportingServices.Portal.WebApi.V2.Controllers.SessionController::Logoff`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x240`

## pseudocode

```c

```

## disassembly

```asm
0x240  ldarg.0
0x241  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.ReportingServices.Portal.WebApi.V2.Controllers.SessionController::_serverConfiguration
0x246  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_FormsCookieName()
0x24b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x250  brtrue.s loc_2C8
0x252  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor()
0x257  stloc.0
0x258  ldarg.0
0x259  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.ReportingServices.Portal.WebApi.V2.Controllers.SessionController::_serverConfiguration
0x25e  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_FormsCookieName()
0x263  ldsfld   string [mscorlib]System.String::Empty
0x268  newobj   instance void [System.Net.Http.Formatting]System.Net.Http.Headers.CookieHeaderValue::.ctor(string, string)
0x26d  stloc.1
0x26e  ldloc.1
0x26f  ldarg.0
0x270  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.ReportingServices.Portal.WebApi.V2.Controllers.SessionController::_serverConfiguration
0x275  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_FormsCookiePath()
0x27a  callvirt instance void [System.Net.Http.Formatting]System.Net.Http.Headers.CookieHeaderValue::set_Path(string)
0x27f  ldloc.1
0x280  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::get_Now()
0x285  stloc.3
0x286  ldloca.s 3
0x288  ldc.r8   1.0
0x291  call     instance valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::AddMinutes(float64)
0x296  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>::.ctor(var<u1>)
0x29b  callvirt instance void [System.Net.Http.Formatting]System.Net.Http.Headers.CookieHeaderValue::set_Expires(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>)
0x2a0  ldloc.1
0x2a1  ldc.i4.1
0x2a2  callvirt instance void [System.Net.Http.Formatting]System.Net.Http.Headers.CookieHeaderValue::set_HttpOnly(bool)
0x2a7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Net.Http.Formatting]System.Net.Http.Headers.CookieHeaderValue>::.ctor()
0x2ac  stloc.2
0x2ad  ldloc.2
0x2ae  ldloc.1
0x2af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Net.Http.Formatting]System.Net.Http.Headers.CookieHeaderValue>::Add(var<u1>)
0x2b4  ldloc.0
0x2b5  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x2ba  ldloc.2
0x2bb  call     void [System.Net.Http.Formatting]System.Net.Http.HttpResponseHeadersExtensions::AddCookies(class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Net.Http.Formatting]System.Net.Http.Headers.CookieHeaderValue>)
0x2c0  ldarg.0
0x2c1  ldloc.0
0x2c2  callvirt instance class [System.Web.Http]System.Web.Http.Results.ResponseMessageResult [System.Web.Http]System.Web.Http.ApiController::ResponseMessage(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0x2c7  ret
0x2c8  ldarg.0
0x2c9  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult [System.Web.Http]System.Web.Http.ApiController::BadRequest()
0x2ce  ret
```
