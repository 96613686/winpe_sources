# Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::CreateSessionManager

- ea: `0x32a10`
- end: `0x32a51`
- name: `Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::CreateSessionManager`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x32280`
- `0x32a00`
- `0x32a10`
- `0x32ae0`
- `0x32d80`

## string_xrefs

- `0x32a10`: `ReportServiceHttpHandler.CreateSessionManager`

## pseudocode

```c

```

## disassembly

```asm
0x32a10  ldstr    aReportserviceh_12// "ReportServiceHttpHandler.CreateSessionM"...
0x32a15  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x32a1a  stloc.0
0x32a1b  ldarg.0
0x32a1c  call     instance bool Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_UseCookieSession()
0x32a21  brfalse.s loc_32A31
0x32a23  ldarg.0
0x32a24  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.DatabaseSessionStorage Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_SessionDatabase()
0x32a29  newobj   instance void Microsoft.ReportingServices.WebServer.HttpClientRequest::.ctor(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.DatabaseSessionStorage sessionDB)
0x32a2e  stloc.1
0x32a2f  leave.s  loc_32A4F
0x32a31  ldarg.0
0x32a32  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.DatabaseSessionStorage Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_SessionDatabase()
0x32a37  ldarg.0
0x32a38  ldfld    string Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::m_sessionIDInPath
0x32a3d  newobj   instance void Microsoft.ReportingServices.WebServer.CookielessClientRequest::.ctor(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.DatabaseSessionStorage sessionDB, string sessionID)
0x32a42  stloc.1
0x32a43  leave.s  loc_32A4F
0x32a45  ldloc.0
0x32a46  brfalse.s loc_32A4E
0x32a48  ldloc.0
0x32a49  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32a4e  endfinally
0x32a4f  ldloc.1
0x32a50  ret
```
