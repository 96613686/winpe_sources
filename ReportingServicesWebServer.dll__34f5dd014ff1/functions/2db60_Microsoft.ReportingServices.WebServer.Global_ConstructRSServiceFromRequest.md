# Microsoft.ReportingServices.WebServer.Global::ConstructRSServiceFromRequest

- ea: `0x2db60`
- end: `0x2dc15`
- name: `Microsoft.ReportingServices.WebServer.Global::ConstructRSServiceFromRequest`
- size: `181`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xa0`
- `0x2db50`
- `0x31d60`

## callees

- `0x2db60`
- `0x2dc20`
- `0x33320`
- `0x333a0`

## string_xrefs

- `0x2db7c`: `rs:TrustedUserToken`
- `0x2dbb9`: `rs:TrustedUserToken`
- `0x2dbc7`: `rs:TrustedUserToken`
- `0x2dc00`: `Found either TrustedUserToken or TrustedUserName parameter, expect both. Ignored.`

## pseudocode

```c

```

## disassembly

```asm
0x2db60  ldnull
0x2db61  stloc.0
0x2db62  call     bool Microsoft.ReportingServices.WebServer.Global::get_IsSPInfoInFormParameters()
0x2db67  brfalse  loc_2DC0A
0x2db6c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2db71  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2db76  dup
0x2db77  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x2db7c  ldstr    aRsTrustedusert// "rs:TrustedUserToken"
0x2db81  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2db86  stloc.1
0x2db87  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x2db8c  ldstr    aRsTrustedusern// "rs:TrustedUserName"
0x2db91  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2db96  stloc.2
0x2db97  ldloc.1
0x2db98  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2db9d  brtrue.s loc_2DBDF
0x2db9f  ldloc.2
0x2dba0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2dba5  brtrue.s loc_2DBDF
0x2dba7  ldloc.2
0x2dba8  ldarg.0
0x2dba9  call     void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.TrustedAccountVerification::VerifyTrustedAccountAccess(string, string)
0x2dbae  ldloc.1
0x2dbaf  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x2dbb4  stloc.3
0x2dbb5  leave.s  loc_2DBC6
0x2dbb7  stloc.s  5
0x2dbb9  ldstr    aRsTrustedusert// "rs:TrustedUserToken"
0x2dbbe  ldloc.s  5
0x2dbc0  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string, class [mscorlib]System.Exception)
0x2dbc5  throw
0x2dbc6  ldloc.3
0x2dbc7  ldstr    aRsTrustedusert// "rs:TrustedUserToken"
0x2dbcc  call     unsigned int8[] Microsoft.ReportingServices.WebServer.WebServiceHelper::Uncompress(unsigned int8[] compressedBuffer, string parameterName)
0x2dbd1  stloc.s  4
0x2dbd3  ldloc.2
0x2dbd4  ldloc.s  4
0x2dbd6  ldc.i4.4
0x2dbd7  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::.ctor(string, object, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType)
0x2dbdc  stloc.0
0x2dbdd  br.s     loc_2DC0A
0x2dbdf  ldloc.1
0x2dbe0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2dbe5  brfalse.s loc_2DBEF
0x2dbe7  ldloc.2
0x2dbe8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2dbed  brtrue.s loc_2DC0A
0x2dbef  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_WebServerTracer()
0x2dbf4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x2dbf9  brfalse.s loc_2DC0A
0x2dbfb  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_WebServerTracer()
0x2dc00  ldstr    aFoundEitherTru// "Found either TrustedUserToken or Truste"...
0x2dc05  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string)
0x2dc0a  ldloc.0
0x2dc0b  brtrue.s loc_2DC13
0x2dc0d  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.WebServer.WebServiceHelper::ConstructRSServiceObjectFromSecurityExtension()
0x2dc12  stloc.0
0x2dc13  ldloc.0
0x2dc14  ret
```
