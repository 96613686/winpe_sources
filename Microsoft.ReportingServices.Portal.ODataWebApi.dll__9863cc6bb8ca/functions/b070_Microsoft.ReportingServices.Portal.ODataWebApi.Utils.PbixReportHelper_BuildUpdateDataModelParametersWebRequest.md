# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::BuildUpdateDataModelParametersWebRequest

- ea: `0xb070`
- end: `0xb13c`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::BuildUpdateDataModelParametersWebRequest`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xab80`

## callees

- `0xb070`

## string_xrefs

- `0xb0d1`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0xb070  ldarg.2
0xb071  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0xb076  stloc.0
0xb077  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext::GetFromCallContext()
0xb07c  stloc.1
0xb07d  ldstr    a0ApiReport1Par// "{0}/api/report/{1}/parameters"
0xb082  ldarg.3
0xb083  ldarga.s 1
0xb085  constrained. [mscorlib]System.Guid
0xb08b  callvirt instance string [mscorlib]System.Object::ToString()
0xb090  callvirt instance string [mscorlib]System.String::ToUpper()
0xb095  call     string [mscorlib]System.String::Format(string, object, object)
0xb09a  stloc.2
0xb09b  ldarg.s  4
0xb09d  ldc.i4.4
0xb09e  ldstr    aUpdatingDataMo// "Updating Data Model Data Source Paramet"...
0xb0a3  ldloc.2
0xb0a4  call     string [mscorlib]System.String::Format(string, object)
0xb0a9  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xb0ae  ldloc.2
0xb0af  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(string)
0xb0b4  castclass [System]System.Net.HttpWebRequest
0xb0b9  stloc.3
0xb0ba  ldloc.3
0xb0bb  ldarg.s  5
0xb0bd  ldarg.s  6
0xb0bf  call     class [System]System.Net.HttpWebRequest [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapAuthenticationHelper::PrepareWebRequestWithCorrespondingAuthMechanism(class [System]System.Net.HttpWebRequest, class [mscorlib]System.Security.Principal.IPrincipal, string)
0xb0c4  stloc.3
0xb0c5  ldloc.3
0xb0c6  ldstr    aPost// "POST"
0xb0cb  callvirt instance void [System]System.Net.WebRequest::set_Method(string)
0xb0d0  ldloc.3
0xb0d1  ldstr    aApplicationJso// "application/json"
0xb0d6  callvirt instance void [System]System.Net.WebRequest::set_ContentType(string)
0xb0db  ldloc.3
0xb0dc  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0xb0e1  ldstr    aRequestid// "RequestId"
0xb0e6  ldloc.1
0xb0e7  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext::get_RequestID()
0xb0ec  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xb0f1  ldloc.3
0xb0f2  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0xb0f7  ldstr    aXSsrsClientses// "X-SSRS-ClientSessionId"
0xb0fc  ldloc.1
0xb0fd  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext::get_ClientSessionID()
0xb102  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xb107  ldloc.3
0xb108  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebRequest::GetRequestStream()
0xb10d  stloc.s  4
0xb10f  ldloc.s  4
0xb111  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream)
0xb116  stloc.s  5
0xb118  ldloc.s  5
0xb11a  ldloc.0
0xb11b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb120  leave.s  loc_B13A
0xb122  ldloc.s  5
0xb124  brfalse.s loc_B12D
0xb126  ldloc.s  5
0xb128  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb12d  endfinally
0xb12e  ldloc.s  4
0xb130  brfalse.s loc_B139
0xb132  ldloc.s  4
0xb134  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb139  endfinally
0xb13a  ldloc.3
0xb13b  ret
```
