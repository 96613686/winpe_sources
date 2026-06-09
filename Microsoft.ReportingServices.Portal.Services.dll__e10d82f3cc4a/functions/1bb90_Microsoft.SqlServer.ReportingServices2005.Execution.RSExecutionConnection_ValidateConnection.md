# Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::ValidateConnection

- ea: `0x1bb90`
- end: `0x1bbc5`
- name: `Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::ValidateConnection`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x15e10`
- `0x16c90`
- `0x1bb90`
- `0x1bdc0`
- `0x1be50`
- `0x24170`
- `0x24190`

## pseudocode

```c

```

## disassembly

```asm
0x1bb90  ldarg.0
0x1bb91  ldstr    asc_25656// ""
0x1bb96  call     instance bool Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::IsSecureMethod(string methodname)
0x1bb9b  pop
0x1bb9c  ldarg.0
0x1bb9d  call     instance class Microsoft.SqlServer.ReportingServices2005.Execution.ServerInfoHeader Microsoft.SqlServer.ReportingServices2005.Execution.ReportExecutionService::get_ServerInfoHeaderValue()
0x1bba2  brtrue.s loc_1BBAB
0x1bba4  ldarg.0
0x1bba5  call     instance string[] Microsoft.SqlServer.ReportingServices2005.Execution.ReportExecutionService::ListSecureMethods()
0x1bbaa  pop
0x1bbab  leave.s  loc_1BBC4
0x1bbad  stloc.0
0x1bbae  ldarg.0
0x1bbaf  ldloc.0
0x1bbb0  callvirt instance void Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::OnSoapException(class [System.Web.Services]System.Web.Services.Protocols.SoapException e)
0x1bbb5  rethrow
0x1bbb7  call     void MissingEndpointException::ThrowIfEndpointMissing(class [System]System.Net.WebException e)
0x1bbbc  rethrow
0x1bbbe  newobj   instance void MissingEndpointException::.ctor(class [mscorlib]System.Exception inner)
0x1bbc3  throw
0x1bbc4  ret
```
