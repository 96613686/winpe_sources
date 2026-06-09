# Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::Invoke

- ea: `0x1d10`
- end: `0x1da6`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::Invoke`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1d10`
- `0x1e70`
- `0x1f40`

## pseudocode

```c

```

## disassembly

```asm
0x1d10  ldarg.1
0x1d11  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x1d16  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Path()
0x1d1b  stloc.0
0x1d1c  ldloca.s 0
0x1d1e  call     instance string [Microsoft.Owin]Microsoft.Owin.PathString::get_Value()
0x1d23  ldstr    asc_571A// "/"
0x1d28  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1d2d  brtrue.s loc_1D4F
0x1d2f  ldarg.1
0x1d30  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x1d35  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Path()
0x1d3a  stloc.0
0x1d3b  ldloca.s 0
0x1d3d  call     instance string [Microsoft.Owin]Microsoft.Owin.PathString::get_Value()
0x1d42  ldstr    aIndexHtml// "/index.html"
0x1d47  ldc.i4.3
0x1d48  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1d4d  brfalse.s loc_1D99
0x1d4f  ldarg.1
0x1d50  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x1d55  ldc.i4   0xC8
0x1d5a  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::set_StatusCode(int32)
0x1d5f  ldarg.1
0x1d60  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x1d65  ldstr    aTextHtmlCharse// "text/html; charset=UTF-8"
0x1d6a  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::set_ContentType(string)
0x1d6f  ldarg.0
0x1d70  ldarg.0
0x1d71  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::_indexContents
0x1d76  ldarg.1
0x1d77  call     instance string Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::UpdateBasePathIfRequired(string indexContent, class [Microsoft.Owin]Microsoft.Owin.IOwinContext context)
0x1d7c  stloc.1
0x1d7d  ldarg.0
0x1d7e  ldloc.1
0x1d7f  ldarg.1
0x1d80  call     instance string Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::AddErrorIEMessageIfRequired(string indexContent, class [Microsoft.Owin]Microsoft.Owin.IOwinContext context)
0x1d85  stloc.1
0x1d86  ldarg.1
0x1d87  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x1d8c  ldloc.1
0x1d8d  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::Write(string)
0x1d92  ldc.i4.0
0x1d93  call     T0x2B000008
0x1d98  ret
0x1d99  ldarg.0
0x1d9a  call     instance class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::get_Next()
0x1d9f  ldarg.1
0x1da0  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::Invoke(class [Microsoft.Owin]Microsoft.Owin.IOwinContext)
0x1da5  ret
```
