# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::IsTrustedServiceCall

- ea: `0xea0`
- end: `0xf19`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::IsTrustedServiceCall`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xcf0`

## callees

- `0xea0`
- `0x3ab0`

## string_xrefs

- `0xeb8`: `RSTrustedServiceToken`
- `0xecf`: `RSTrustedServiceToken`
- `0xf02`: `RSTrustedServiceToken`
- `0xefd`: `Request marked as internal but header '{0}' contains invalid trusted token`

## pseudocode

```c

```

## disassembly

```asm
0xea0  ldarg.1
0xea1  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0xea6  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Headers()
0xeab  brfalse.s loc_F15
0xead  ldarg.1
0xeae  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0xeb3  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Headers()
0xeb8  ldstr    aRstrustedservi// "RSTrustedServiceToken"
0xebd  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string[]>::ContainsKey(var<u1>)
0xec2  brfalse.s loc_F15
0xec4  ldarg.1
0xec5  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0xeca  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Headers()
0xecf  ldstr    aRstrustedservi// "RSTrustedServiceToken"
0xed4  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary::get_Item(string)
0xed9  stloc.0
0xeda  ldarg.0
0xedb  ldfld    class IProcessTokenService Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_processTokenService
0xee0  ldloc.0
0xee1  ldarg.1
0xee2  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0xee7  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_User()
0xeec  callvirt instance void IProcessTokenService::ValidateTokenOrException(string token, class [mscorlib]System.Security.Principal.IPrincipal principal)
0xef1  ldc.i4.1
0xef2  stloc.1
0xef3  leave.s  loc_F17
0xef5  pop
0xef6  ldarg.0
0xef7  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_logger
0xefc  ldc.i4.2
0xefd  ldstr    aRequestMarkedA// "Request marked as internal but header '"...
0xf02  ldstr    aRstrustedservi// "RSTrustedServiceToken"
0xf07  call     string [mscorlib]System.String::Format(string, object)
0xf0c  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xf11  ldc.i4.0
0xf12  stloc.1
0xf13  leave.s  loc_F17
0xf15  ldc.i4.0
0xf16  ret
0xf17  ldloc.1
0xf18  ret
```
