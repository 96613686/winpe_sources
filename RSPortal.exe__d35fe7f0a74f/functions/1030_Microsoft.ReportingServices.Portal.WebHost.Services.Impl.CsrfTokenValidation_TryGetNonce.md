# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::TryGetNonce

- ea: `0x1030`
- end: `0x10a4`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::TryGetNonce`
- size: `116`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xcf0`
- `0xf20`

## callees

- `0x1030`

## pseudocode

```c

```

## disassembly

```asm
0x1030  ldarg.2
0x1031  ldc.i4.0
0x1032  stind.i4
0x1033  ldarg.1
0x1034  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x1039  callvirt instance class [Microsoft.Owin]Microsoft.Owin.RequestCookieCollection [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Cookies()
0x103e  ldstr    aXsrfNonce// "XSRF-NONCE"
0x1043  callvirt instance string [Microsoft.Owin]Microsoft.Owin.RequestCookieCollection::get_Item(string)
0x1048  stloc.0
0x1049  ldloc.0
0x104a  brtrue.s loc_1069
0x104c  ldarg.0
0x104d  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_logger
0x1052  ldc.i4.4
0x1053  ldstr    aCookie0NotFoun// "Cookie '{0}' not found"
0x1058  ldstr    aXsrfNonce// "XSRF-NONCE"
0x105d  call     string [mscorlib]System.String::Format(string, object)
0x1062  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1067  ldc.i4.1
0x1068  ret
0x1069  ldarg.0
0x106a  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.IEncryptionService Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_encryptionService
0x106f  ldloc.0
0x1070  ldloca.s 0
0x1072  call     bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.EncryptionServiceExtensions::TryDecryptToString(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.IEncryptionService, string, string&)
0x1077  brtrue.s loc_107C
0x1079  ldc.i4.s 0xB
0x107b  ret
0x107c  ldloc.0
0x107d  ldarg.2
0x107e  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x1083  brtrue.s loc_10A2
0x1085  ldarg.0
0x1086  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::_logger
0x108b  ldc.i4.4
0x108c  ldstr    aCookie0NotVali// "Cookie '{0}' not valid int"
0x1091  ldstr    aXsrfNonce// "XSRF-NONCE"
0x1096  call     string [mscorlib]System.String::Format(string, object)
0x109b  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x10a0  ldc.i4.2
0x10a1  ret
0x10a2  ldc.i4.0
0x10a3  ret
```
