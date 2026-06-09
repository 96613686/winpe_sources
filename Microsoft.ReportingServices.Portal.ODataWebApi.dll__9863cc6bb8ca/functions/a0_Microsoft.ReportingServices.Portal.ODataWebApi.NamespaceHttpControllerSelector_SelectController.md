# Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::SelectController

- ea: `0xa0`
- end: `0x144`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::SelectController`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x90`
- `0xa0`
- `0x2b0`
- `0x300`

## pseudocode

```c

```

## disassembly

```asm
0xa0  ldarg.1
0xa1  call     class [System.Web.Http]System.Web.Http.Routing.IHttpRouteData [System.Web.Http]System.Net.Http.HttpRequestMessageExtensions::GetRouteData(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0xa6  dup
0xa7  brtrue.s loc_B4
0xa9  ldc.i4   0x194
0xae  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0xb3  throw
0xb4  ldstr    aController// "controller"
0xb9  call     T0x2B000001
0xbe  stloc.0
0xbf  ldloc.0
0xc0  brtrue.s loc_CD
0xc2  ldc.i4   0x194
0xc7  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0xcc  throw
0xcd  ldarg.0
0xce  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [System.Web.Http]System.Web.Http.Controllers.HttpControllerDescriptor> Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::GetControllerMapping()
0xd3  ldloc.0
0xd4  ldloca.s 1
0xd6  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [System.Web.Http]System.Web.Http.Controllers.HttpControllerDescriptor>::TryGetValue(var<u1>, !!T0)
0xdb  brfalse.s loc_DF
0xdd  ldloc.1
0xde  ret
0xdf  ldarg.1
0xe0  callvirt instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0xe5  ldloca.s 2
0xe7  call     bool Microsoft.ReportingServices.Portal.ODataWebApi.UrlParser::TryGetNamespaceFromUri(class [System]System.Uri uri, [out] string& nameSpace)
0xec  brtrue.s loc_F9
0xee  ldc.i4   0x194
0xf3  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0xf8  throw
0xf9  ldloc.2
0xfa  ldloc.0
0xfb  call     string Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::GetControllerKey(string versionString, string controllerName)
0x100  stloc.3
0x101  ldloc.3
0x102  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x107  brtrue.s loc_127
0x109  ldloc.3
0x10a  ldstr    aController_0// "Controller"
0x10f  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x114  brfalse.s loc_127
0x116  ldloc.3
0x117  ldc.i4.0
0x118  ldloc.3
0x119  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11e  ldc.i4.s 0xA
0x120  sub
0x121  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x126  stloc.3
0x127  ldarg.0
0x128  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [System.Web.Http]System.Web.Http.Controllers.HttpControllerDescriptor> Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::GetControllerMapping()
0x12d  ldloc.3
0x12e  ldloca.s 1
0x130  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [System.Web.Http]System.Web.Http.Controllers.HttpControllerDescriptor>::TryGetValue(var<u1>, !!T0)
0x135  brfalse.s loc_139
0x137  ldloc.1
0x138  ret
0x139  ldc.i4   0x194
0x13e  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x143  throw
```
