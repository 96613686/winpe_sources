# Microsoft.ReportingServices.Portal.WebHost.Owin.PopulateHeadersMiddleware::Invoke

- ea: `0x3580`
- end: `0x3642`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PopulateHeadersMiddleware::Invoke`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x3580`

## string_xrefs

- `0x35c9`: `Cache-Control`
- `0x35ee`: `Cache-Control`
- `0x35fb`: `no-cache`

## pseudocode

```c

```

## disassembly

```asm
0x3580  ldc.i4.2
0x3581  newarr   [mscorlib]System.String
0x3586  dup
0x3587  ldc.i4.0
0x3588  ldstr    aOwin// "owin"
0x358d  stelem.ref
0x358e  dup
0x358f  ldc.i4.1
0x3590  ldarg.0
0x3591  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3596  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x359b  stelem.ref
0x359c  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0x35a1  stloc.0
0x35a2  ldarg.1
0x35a3  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x35a8  callvirt instance class [System]System.Uri [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Uri()
0x35ad  callvirt instance string [System]System.Uri::get_LocalPath()
0x35b2  ldstr    aSafegetsystemr// "SafeGetSystemResourceContent(type='mobi"...
0x35b7  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x35bc  brfalse.s loc_35E3
0x35be  ldarg.1
0x35bf  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x35c4  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinResponse::get_Headers()
0x35c9  ldstr    aCacheControl// "Cache-Control"
0x35ce  ldc.i4.1
0x35cf  newarr   [mscorlib]System.String
0x35d4  dup
0x35d5  ldc.i4.0
0x35d6  ldstr    aMaxAge31536000// "max-age=31536000"
0x35db  stelem.ref
0x35dc  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string[]>::Add(var<u1>, !!T0)
0x35e1  br.s     loc_3606
0x35e3  ldarg.1
0x35e4  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x35e9  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinResponse::get_Headers()
0x35ee  ldstr    aCacheControl// "Cache-Control"
0x35f3  ldc.i4.1
0x35f4  newarr   [mscorlib]System.String
0x35f9  dup
0x35fa  ldc.i4.0
0x35fb  ldstr    aNoCache// "no-cache"
0x3600  stelem.ref
0x3601  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string[]>::Add(var<u1>, !!T0)
0x3606  ldarg.1
0x3607  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x360c  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinResponse::get_Headers()
0x3611  ldstr    aXContentTypeOp// "X-Content-Type-Options"
0x3616  ldc.i4.1
0x3617  newarr   [mscorlib]System.String
0x361c  dup
0x361d  ldc.i4.0
0x361e  ldstr    aNosniff// "nosniff"
0x3623  stelem.ref
0x3624  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string[]>::Add(var<u1>, !!T0)
0x3629  leave.s  loc_3635
0x362b  ldloc.0
0x362c  brfalse.s loc_3634
0x362e  ldloc.0
0x362f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3634  endfinally
0x3635  ldarg.0
0x3636  call     instance class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::get_Next()
0x363b  ldarg.1
0x363c  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::Invoke(class [Microsoft.Owin]Microsoft.Owin.IOwinContext)
0x3641  ret
```
