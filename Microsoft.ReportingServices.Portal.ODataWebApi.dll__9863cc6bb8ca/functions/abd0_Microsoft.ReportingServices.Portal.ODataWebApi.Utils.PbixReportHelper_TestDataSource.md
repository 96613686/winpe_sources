# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::TestDataSource

- ea: `0xabd0`
- end: `0xacca`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::TestDataSource`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xabd0`

## string_xrefs

- `0xac27`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0xabd0  ldarg.s  4
0xabd2  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0xabd7  stloc.0
0xabd8  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xabdd  ldloc.0
0xabde  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0xabe3  stloc.1
0xabe4  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext::GetFromCallContext()
0xabe9  stloc.2
0xabea  ldstr    a0ApiCheckdatas// "{0}/api/checkdatasourceconnection"
0xabef  ldarg.1
0xabf0  call     string [mscorlib]System.String::Format(string, object)
0xabf5  stloc.3
0xabf6  ldarg.2
0xabf7  ldc.i4.4
0xabf8  ldstr    aTestingDataMod// "Testing Data Model Data Source using: {"...
0xabfd  ldloc.3
0xabfe  call     string [mscorlib]System.String::Format(string, object)
0xac03  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xac08  ldloc.3
0xac09  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(string)
0xac0e  castclass [System]System.Net.HttpWebRequest
0xac13  ldarg.3
0xac14  ldarg.s  5
0xac16  call     class [System]System.Net.HttpWebRequest [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapAuthenticationHelper::PrepareWebRequestWithCorrespondingAuthMechanism(class [System]System.Net.HttpWebRequest, class [mscorlib]System.Security.Principal.IPrincipal, string)
0xac1b  dup
0xac1c  ldstr    aPost// "POST"
0xac21  callvirt instance void [System]System.Net.WebRequest::set_Method(string)
0xac26  dup
0xac27  ldstr    aApplicationJso// "application/json"
0xac2c  callvirt instance void [System]System.Net.WebRequest::set_ContentType(string)
0xac31  dup
0xac32  ldloc.1
0xac33  ldlen
0xac34  conv.i4
0xac35  conv.i8
0xac36  callvirt instance void [System]System.Net.WebRequest::set_ContentLength(int64)
0xac3b  dup
0xac3c  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0xac41  ldstr    aRequestid// "RequestId"
0xac46  ldloc.2
0xac47  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext::get_RequestID()
0xac4c  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xac51  dup
0xac52  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0xac57  ldstr    aXSsrsClientses// "X-SSRS-ClientSessionId"
0xac5c  ldloc.2
0xac5d  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext::get_ClientSessionID()
0xac62  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xac67  dup
0xac68  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebRequest::GetRequestStream()
0xac6d  dup
0xac6e  ldloc.1
0xac6f  ldc.i4.0
0xac70  ldloc.1
0xac71  ldlen
0xac72  conv.i4
0xac73  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0xac78  callvirt instance void [mscorlib]System.IO.Stream::Close()
0xac7d  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebRequest::GetResponse()
0xac82  castclass [System]System.Net.HttpWebResponse
0xac87  dup
0xac88  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0xac8d  ldc.i4   0xC8
0xac92  beq.s    loc_AC9F
0xac94  ldstr    aFailedToCallCh// "Failed to call checkdatasourceconnectio"...
0xac99  newobj   instance void [System]System.Net.WebException::.ctor(string)
0xac9e  throw
0xac9f  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0xaca4  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0xaca9  stloc.s  4
0xacab  ldloc.s  4
0xacad  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0xacb2  call     T0x2B0000E3
0xacb7  stloc.s  5
0xacb9  leave.s  loc_ACC7
0xacbb  ldloc.s  4
0xacbd  brfalse.s loc_ACC6
0xacbf  ldloc.s  4
0xacc1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xacc6  endfinally
0xacc7  ldloc.s  5
0xacc9  ret
```
