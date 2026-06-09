# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::GetUpdateDataModelParametersResponse

- ea: `0xb140`
- end: `0xb193`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::GetUpdateDataModelParametersResponse`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xab80`

## callees

- `0xb140`

## pseudocode

```c

```

## disassembly

```asm
0xb140  ldarg.1
0xb141  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebRequest::GetResponse()
0xb146  castclass [System]System.Net.HttpWebResponse
0xb14b  dup
0xb14c  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0xb151  ldc.i4   0xC8
0xb156  beq.s    loc_B173
0xb158  ldstr    aFailedToCallPo// "Failed to call PowerBI API: {0}"
0xb15d  ldarg.1
0xb15e  callvirt instance class [System]System.Uri [System]System.Net.WebRequest::get_RequestUri()
0xb163  callvirt instance string [System]System.Uri::get_OriginalString()
0xb168  call     string [mscorlib]System.String::Format(string, object)
0xb16d  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.FailedToSetDataModelParameterException::.ctor(string)
0xb172  throw
0xb173  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0xb178  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0xb17d  stloc.0
0xb17e  ldloc.0
0xb17f  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0xb184  stloc.1
0xb185  leave.s  loc_B191
0xb187  ldloc.0
0xb188  brfalse.s loc_B190
0xb18a  ldloc.0
0xb18b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb190  endfinally
0xb191  ldloc.1
0xb192  ret
```
