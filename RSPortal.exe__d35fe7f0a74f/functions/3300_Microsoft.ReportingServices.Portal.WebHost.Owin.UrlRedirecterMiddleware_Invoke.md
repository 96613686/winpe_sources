# Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::Invoke

- ea: `0x3300`
- end: `0x338c`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::Invoke`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x27e0`
- `0x27f0`
- `0x2800`
- `0x3300`
- `0x3390`

## pseudocode

```c

```

## disassembly

```asm
0x3300  ldc.i4.2
0x3301  newarr   [mscorlib]System.String
0x3306  dup
0x3307  ldc.i4.0
0x3308  ldstr    aOwin// "owin"
0x330d  stelem.ref
0x330e  dup
0x330f  ldc.i4.1
0x3310  ldarg.0
0x3311  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3316  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x331b  stelem.ref
0x331c  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0x3321  stloc.0
0x3322  ldarg.1
0x3323  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x3328  callvirt instance class [System]System.Uri [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Uri()
0x332d  stloc.1
0x332e  ldarg.1
0x332f  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x3334  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IReadableStringCollection [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Query()
0x3339  stloc.2
0x333a  ldarg.0
0x333b  ldfld    class Microsoft.ReportingServices.Portal.WebHost.Owin.IUrlRedirecterRule Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::_redirectRule
0x3340  ldloc.1
0x3341  ldloc.2
0x3342  callvirt instance bool Microsoft.ReportingServices.Portal.WebHost.Owin.IUrlRedirecterRule::IsRedirectNeeded(class [System]System.Uri uri, class [Microsoft.Owin]Microsoft.Owin.IReadableStringCollection query)
0x3347  brfalse.s loc_3371
0x3349  ldarg.0
0x334a  ldarg.1
0x334b  ldarg.0
0x334c  ldfld    class Microsoft.ReportingServices.Portal.WebHost.Owin.IUrlRedirecterRule Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::_redirectRule
0x3351  ldloc.1
0x3352  ldloc.2
0x3353  callvirt instance string Microsoft.ReportingServices.Portal.WebHost.Owin.IUrlRedirecterRule::GetRedirectUri(class [System]System.Uri requestedUri, class [Microsoft.Owin]Microsoft.Owin.IReadableStringCollection query)
0x3358  ldarg.0
0x3359  ldfld    class Microsoft.ReportingServices.Portal.WebHost.Owin.IUrlRedirecterRule Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::_redirectRule
0x335e  callvirt instance int32 Microsoft.ReportingServices.Portal.WebHost.Owin.IUrlRedirecterRule::get_RedirectHttpCode()
0x3363  call     instance void Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::RedirectToUri(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context, string url, int32 redirectWithCode)
0x3368  ldc.i4.0
0x3369  call     T0x2B000008
0x336e  stloc.3
0x336f  leave.s  loc_338A
0x3371  leave.s  loc_337D
0x3373  ldloc.0
0x3374  brfalse.s loc_337C
0x3376  ldloc.0
0x3377  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x337c  endfinally
0x337d  ldarg.0
0x337e  call     instance class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::get_Next()
0x3383  ldarg.1
0x3384  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::Invoke(class [Microsoft.Owin]Microsoft.Owin.IOwinContext)
0x3389  ret
0x338a  ldloc.3
0x338b  ret
```
