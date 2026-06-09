# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::HasValidToken

- ea: `0xcf0`
- end: `0xe9d`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::HasValidToken`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xcf0`
- `0xea0`
- `0x1030`

## string_xrefs

- `0xd15`: `X-XSRF-TOKEN`
- `0xd2f`: `X-XSRF-TOKEN`
- `0xd5c`: `X-XSRF-TOKEN`
- `0xd91`: `X-XSRF-TOKEN`
- `0xdc5`: `X-XSRF-TOKEN`
- `0xdee`: `X-XSRF-TOKEN`
- `0xe41`: `X-XSRF-TOKEN`
- `0xe8a`: `X-XSRF-TOKEN`

## pseudocode

```c

```

## disassembly

```asm
0xcf0  ldarg.0
0xcf1  ldarg.1
0xcf2  call     instance bool Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::IsTrustedServiceCall(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context)
0xcf7  brfalse.s loc_CFB
0xcf9  ldc.i4.0
0xcfa  ret
0xcfb  ldarg.0
0xcfc  ldarg.1
0xcfd  ldloca.s 0
0xcff  call     instance valuetype Microsoft.ReportingServices.Portal.WebHost.Services.ValidationResult Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::TryGetNonce(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context, [out] int32& nonce)
0xd04  stloc.1
0xd05  ldloc.1
0xd06  brfalse.s loc_D0A
0xd08  ldloc.1
0xd09  ret
0xd0a  ldarg.1
0xd0b  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0xd10  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Headers()
0xd15  ldstr    aXXsrfToken// "X-XSRF-TOKEN"
0xd1a  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary::get_Item(string)
0xd1f  stloc.2
0xd20  ldloc.2
0xd21  brtrue.s loc_D40
0xd23  ldarg.0
0xd24  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_logger
0xd29  ldc.i4.2
0xd2a  ldstr    aHeader0NotFoun// "Header '{0}' not found"
0xd2f  ldstr    aXXsrfToken// "X-XSRF-TOKEN"
0xd34  call     string [mscorlib]System.String::Format(string, object)
0xd39  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xd3e  ldc.i4.3
0xd3f  ret
0xd40  ldarg.0
0xd41  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.IEncryptionService Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_encryptionService
0xd46  ldloc.2
0xd47  ldloca.s 2
0xd49  call     bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.EncryptionServiceExtensions::TryDecryptToString(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.IEncryptionService, string, string&)
0xd4e  brtrue.s loc_D6D
0xd50  ldarg.0
0xd51  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_logger
0xd56  ldc.i4.2
0xd57  ldstr    aHeader0Invalid// "Header '{0}' invalid format"
0xd5c  ldstr    aXXsrfToken// "X-XSRF-TOKEN"
0xd61  call     string [mscorlib]System.String::Format(string, object)
0xd66  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xd6b  ldc.i4.4
0xd6c  ret
0xd6d  ldloc.2
0xd6e  ldc.i4.1
0xd6f  newarr   [mscorlib]System.Char
0xd74  dup
0xd75  ldc.i4.0
0xd76  ldc.i4.s 0x7C
0xd78  stelem.i2
0xd79  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xd7e  stloc.3
0xd7f  ldloc.3
0xd80  ldlen
0xd81  conv.i4
0xd82  ldc.i4.3
0xd83  beq.s    loc_DA3
0xd85  ldarg.0
0xd86  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_logger
0xd8b  ldc.i4.2
0xd8c  ldstr    aHeader0Invalid_0// "Header '{0}' invalid syntax"
0xd91  ldstr    aXXsrfToken// "X-XSRF-TOKEN"
0xd96  call     string [mscorlib]System.String::Format(string, object)
0xd9b  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xda0  ldc.i4.s 0xA
0xda2  ret
0xda3  ldloc.3
0xda4  ldc.i4.1
0xda5  ldelem.ref
0xda6  stloc.s  5
0xda8  ldloc.3
0xda9  ldc.i4.0
0xdaa  ldelem.ref
0xdab  ldloca.s 4
0xdad  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0xdb2  brfalse.s loc_DB9
0xdb4  ldloc.s  4
0xdb6  ldloc.0
0xdb7  beq.s    loc_DD6
0xdb9  ldarg.0
0xdba  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_logger
0xdbf  ldc.i4.2
0xdc0  ldstr    aHeader0DoesNot// "Header '{0}' does not contain matching "...
0xdc5  ldstr    aXXsrfToken// "X-XSRF-TOKEN"
0xdca  call     string [mscorlib]System.String::Format(string, object)
0xdcf  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xdd4  ldc.i4.5
0xdd5  ret
0xdd6  ldloc.3
0xdd7  ldc.i4.2
0xdd8  ldelem.ref
0xdd9  ldloca.s 6
0xddb  call     bool [mscorlib]System.DateTimeOffset::TryParse(string, valuetype [mscorlib]System.DateTimeOffset&)
0xde0  brtrue.s loc_DFF
0xde2  ldarg.0
0xde3  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_logger
0xde8  ldc.i4.2
0xde9  ldstr    aHeader0DoesNot_0// "Header '{0}' does not contain valid tim"...
0xdee  ldstr    aXXsrfToken// "X-XSRF-TOKEN"
0xdf3  call     string [mscorlib]System.String::Format(string, object)
0xdf8  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xdfd  ldc.i4.8
0xdfe  ret
0xdff  ldarg.0
0xe00  ldfld    class [mscorlib]System.Func`1<valuetype [mscorlib]System.DateTimeOffset> Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::NowFn
0xe05  callvirt instance var<u1> class [mscorlib]System.Func`1<valuetype [mscorlib]System.DateTimeOffset>::Invoke()
0xe0a  stloc.s  7
0xe0c  ldloc.s  7
0xe0e  ldloc.s  6
0xe10  call     bool [mscorlib]System.DateTimeOffset::op_LessThan(valuetype [mscorlib]System.DateTimeOffset, valuetype [mscorlib]System.DateTimeOffset)
0xe15  brtrue.s loc_E35
0xe17  ldloc.s  7
0xe19  ldloc.s  6
0xe1b  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTimeOffset::op_Subtraction(valuetype [mscorlib]System.DateTimeOffset, valuetype [mscorlib]System.DateTimeOffset)
0xe20  ldc.r8   1.0
0xe29  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromDays(float64)
0xe2e  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xe33  brfalse.s loc_E53
0xe35  ldarg.0
0xe36  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_logger
0xe3b  ldc.i4.2
0xe3c  ldstr    aHeader0Contain// "Header '{0}' contains an expired timest"...
0xe41  ldstr    aXXsrfToken// "X-XSRF-TOKEN"
0xe46  call     string [mscorlib]System.String::Format(string, object)
0xe4b  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe50  ldc.i4.s 9
0xe52  ret
0xe53  ldarg.1
0xe54  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0xe59  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_User()
0xe5e  brfalse.s loc_E7E
0xe60  ldloc.s  5
0xe62  ldarg.1
0xe63  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0xe68  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_User()
0xe6d  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0xe72  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0xe77  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xe7c  brfalse.s loc_E9B
0xe7e  ldarg.0
0xe7f  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_logger
0xe84  ldc.i4.2
0xe85  ldstr    aHeader0DoesNot_1// "Header '{0}' does not contain matching "...
0xe8a  ldstr    aXXsrfToken// "X-XSRF-TOKEN"
0xe8f  call     string [mscorlib]System.String::Format(string, object)
0xe94  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe99  ldc.i4.7
0xe9a  ret
0xe9b  ldc.i4.0
0xe9c  ret
```
