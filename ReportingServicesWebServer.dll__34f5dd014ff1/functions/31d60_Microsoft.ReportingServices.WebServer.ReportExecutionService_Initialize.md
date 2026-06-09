# Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize

- ea: `0x31d60`
- end: `0x31e20`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize`
- size: `192`
- prototype: ``
- caller_count: `39`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x31290`
- `0x312c0`
- `0x31310`
- `0x31350`
- `0x313a0`
- `0x313e0`
- `0x31420`
- `0x31460`
- `0x314a0`
- `0x314e0`
- `0x31520`
- `0x31560`
- `0x315a0`
- `0x315e0`
- `0x31620`
- `0x31660`
- `0x316a0`
- `0x316e0`
- `0x31720`
- `0x31760`
- `0x317a0`
- `0x317e0`
- `0x31820`
- `0x31860`
- `0x318a0`
- `0x318e0`
- `0x31920`
- `0x31960`
- `0x319a0`
- `0x319e0`
- `0x31a20`
- `0x31a60`
- `0x31ab0`
- `0x31b00`
- `0x31b40`
- `0x31b80`
- `0x31bc0`
- `0x31c00`
- `0x31cc0`

## callees

- `0x2db60`
- `0x31d60`
- `0x31e40`
- `0x31e50`
- `0x32e00`
- `0x33310`

## pseudocode

```c

```

## disassembly

```asm
0x31d60  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x31d65  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x31d6a  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x31d6f  ldc.i4.s 0x7F
0x31d71  ldc.i4.2
0x31d72  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x31d77  ldstr    aReportexecutio_0// "ReportExecution2005.asmx"
0x31d7c  ldc.i4.5
0x31d7d  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x31d82  brfalse.s loc_31D93
0x31d84  ldarg.0
0x31d85  ldarg.1
0x31d86  ldarg.2
0x31d87  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.WebServer.WebServiceHelper::ExtractWebUserInfo(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31d8c  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::set_Service(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService value)
0x31d91  br.s     loc_31DA0
0x31d93  ldarg.0
0x31d94  ldarg.2
0x31d95  ldc.i4.1
0x31d96  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.WebServer.Global::ConstructRSServiceFromRequest(string item, bool checkSharePointAcces)
0x31d9b  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::set_Service(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService value)
0x31da0  ldarg.0
0x31da1  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.WebServer.ReportExecutionService::get_Service()
0x31da6  ldarg.2
0x31da7  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::EnsureSecurityZone(string)
0x31dac  ldarg.0
0x31dad  ldarg.0
0x31dae  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.WebServer.ReportExecutionService::get_Service()
0x31db3  ldarg.0
0x31db4  newobj   instance void Microsoft.ReportingServices.WebServer.SoapClientRequest2005::.ctor(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ISessionID service)
0x31db9  ldnull
0x31dba  ldftn    class [mscorlib]System.Exception Microsoft.ReportingServices.WebServer.WebServiceHelper::GetSoapException(class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException exception)
0x31dc0  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetExceptionForEndpoint::.ctor(object, native int)
0x31dc5  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::.ctor(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SessionfulClientRequest, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetExceptionForEndpoint)
0x31dca  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x31dcf  leave.s  loc_31E1F
0x31dd1  stloc.0
0x31dd2  ldnull
0x31dd3  stloc.1
0x31dd4  ldloc.0
0x31dd5  isinst   [mscorlib]System.IO.FileNotFoundException
0x31dda  brfalse.s loc_31DE5
0x31ddc  ldarg.2
0x31ddd  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemNotFoundException::.ctor(string)
0x31de2  stloc.1
0x31de3  br.s     loc_31E0E
0x31de5  ldloc.0
0x31de6  isinst   [System]System.UriFormatException
0x31deb  brfalse.s loc_31DF8
0x31ded  ldarg.2
0x31dee  ldnull
0x31def  ldloc.0
0x31df0  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidItemPathException::.ctor(string, string, class [mscorlib]System.Exception)
0x31df5  stloc.1
0x31df6  br.s     loc_31E0E
0x31df8  ldloc.0
0x31df9  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x31dfe  stloc.1
0x31dff  ldloc.1
0x31e00  brtrue.s loc_31E0E
0x31e02  ldloc.0
0x31e03  ldsfld   string [mscorlib]System.String::Empty
0x31e08  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0x31e0d  stloc.1
0x31e0e  ldloc.1
0x31e0f  call     bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Global::get_RecycleOnSevereErrors()
0x31e14  call     bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Global::get_EnableRemoteErrors()
0x31e19  call     class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ExceptionExtensions::WebServerToSoapException(class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException, bool, bool)
0x31e1e  throw
0x31e1f  ret
```
