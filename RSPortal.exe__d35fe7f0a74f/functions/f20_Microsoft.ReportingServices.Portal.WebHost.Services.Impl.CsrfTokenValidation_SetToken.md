# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::SetToken

- ea: `0xf20`
- end: `0x1026`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::SetToken`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xf20`
- `0x1030`

## string_xrefs

- `0x1003`: `XSRF-TOKEN`

## pseudocode

```c

```

## disassembly

```asm
0xf20  ldarg.1
0xf21  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0xf26  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_User()
0xf2b  brtrue.s loc_F2E
0xf2d  ret
0xf2e  ldarg.0
0xf2f  ldarg.1
0xf30  ldloca.s 0
0xf32  call     instance valuetype Microsoft.ReportingServices.Portal.WebHost.Services.ValidationResult Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::TryGetNonce(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context, [out] int32& nonce)
0xf37  brfalse.s loc_F56
0xf39  ldarg.0
0xf3a  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_logger
0xf3f  ldc.i4.4
0xf40  ldstr    aGeneratingNewN// "Generating new nonce"
0xf45  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xf4a  ldarg.0
0xf4b  ldfld    class [mscorlib]System.Func`1<int32> Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::RandomNext
0xf50  callvirt instance var<u1> class [mscorlib]System.Func`1<int32>::Invoke()
0xf55  stloc.0
0xf56  ldarg.1
0xf57  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0xf5c  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_User()
0xf61  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0xf66  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0xf6b  stloc.1
0xf6c  ldstr    a012O// "{0}|{1}|{2:O}"
0xf71  ldloc.0
0xf72  box      [mscorlib]System.Int32
0xf77  ldloc.1
0xf78  ldarg.0
0xf79  ldfld    class [mscorlib]System.Func`1<valuetype [mscorlib]System.DateTimeOffset> Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::NowFn
0xf7e  callvirt instance var<u1> class [mscorlib]System.Func`1<valuetype [mscorlib]System.DateTimeOffset>::Invoke()
0xf83  box      [mscorlib]System.DateTimeOffset
0xf88  call     string [mscorlib]System.String::Format(string, object, object, object)
0xf8d  pop
0xf8e  ldarg.1
0xf8f  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0xf94  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_PathBase()
0xf99  stloc.3
0xf9a  ldloca.s 3
0xf9c  call     instance bool [Microsoft.Owin]Microsoft.Owin.PathString::get_HasValue()
0xfa1  brtrue.s loc_FAA
0xfa3  ldstr    asc_571A// "/"
0xfa8  br.s     loc_FBD
0xfaa  ldarg.1
0xfab  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0xfb0  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_PathBase()
0xfb5  stloc.3
0xfb6  ldloca.s 3
0xfb8  call     instance string [Microsoft.Owin]Microsoft.Owin.PathString::get_Value()
0xfbd  stloc.2
0xfbe  ldarg.1
0xfbf  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0xfc4  callvirt instance class [Microsoft.Owin]Microsoft.Owin.ResponseCookieCollection [Microsoft.Owin]Microsoft.Owin.IOwinResponse::get_Cookies()
0xfc9  ldstr    aXsrfNonce// "XSRF-NONCE"
0xfce  ldarg.0
0xfcf  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.IEncryptionService Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_encryptionService
0xfd4  ldloca.s 0
0xfd6  call     instance string [mscorlib]System.Int32::ToString()
0xfdb  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.IEncryptionService::EncryptToString(string)
0xfe0  newobj   instance void [Microsoft.Owin]Microsoft.Owin.CookieOptions::.ctor()
0xfe5  dup
0xfe6  ldc.i4.1
0xfe7  callvirt instance void [Microsoft.Owin]Microsoft.Owin.CookieOptions::set_HttpOnly(bool)
0xfec  dup
0xfed  ldloc.2
0xfee  callvirt instance void [Microsoft.Owin]Microsoft.Owin.CookieOptions::set_Path(string)
0xff3  callvirt instance void [Microsoft.Owin]Microsoft.Owin.ResponseCookieCollection::Append(string, string, class [Microsoft.Owin]Microsoft.Owin.CookieOptions)
0xff8  ldarg.1
0xff9  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0xffe  callvirt instance class [Microsoft.Owin]Microsoft.Owin.ResponseCookieCollection [Microsoft.Owin]Microsoft.Owin.IOwinResponse::get_Cookies()
0x1003  ldstr    aXsrfToken// "XSRF-TOKEN"
0x1008  ldstr    aDeprecated// "deprecated"
0x100d  newobj   instance void [Microsoft.Owin]Microsoft.Owin.CookieOptions::.ctor()
0x1012  dup
0x1013  ldc.i4.0
0x1014  callvirt instance void [Microsoft.Owin]Microsoft.Owin.CookieOptions::set_HttpOnly(bool)
0x1019  dup
0x101a  ldloc.2
0x101b  callvirt instance void [Microsoft.Owin]Microsoft.Owin.CookieOptions::set_Path(string)
0x1020  callvirt instance void [Microsoft.Owin]Microsoft.Owin.ResponseCookieCollection::Append(string, string, class [Microsoft.Owin]Microsoft.Owin.CookieOptions)
0x1025  ret
```
