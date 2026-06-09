# Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthClientScriptMiddleware::Invoke

- ea: `0x20c0`
- end: `0x212a`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthClientScriptMiddleware::Invoke`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x20c0`

## pseudocode

```c

```

## disassembly

```asm
0x20c0  ldarg.0
0x20c1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IOAuthClientConfigurationService Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthClientScriptMiddleware::_oAuthClientConfigurationService
0x20c6  ldarg.1
0x20c7  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x20cc  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Path()
0x20d1  stloc.0
0x20d2  ldloca.s 0
0x20d4  call     instance string [Microsoft.Owin]Microsoft.Owin.PathString::get_Value()
0x20d9  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IOAuthClientConfigurationService::IsScriptRequest(string)
0x20de  brfalse.s loc_211D
0x20e0  ldarg.1
0x20e1  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x20e6  ldc.i4   0xC8
0x20eb  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::set_StatusCode(int32)
0x20f0  ldarg.1
0x20f1  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x20f6  ldstr    aTextJavascript// "text/javascript"
0x20fb  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::set_ContentType(string)
0x2100  ldarg.1
0x2101  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x2106  ldarg.0
0x2107  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IOAuthClientConfigurationService Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthClientScriptMiddleware::_oAuthClientConfigurationService
0x210c  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IOAuthClientConfigurationService::GetConfigInfoScript()
0x2111  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::Write(string)
0x2116  ldc.i4.0
0x2117  call     T0x2B000008
0x211c  ret
0x211d  ldarg.0
0x211e  call     instance class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::get_Next()
0x2123  ldarg.1
0x2124  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::Invoke(class [Microsoft.Owin]Microsoft.Owin.IOwinContext)
0x2129  ret
```
