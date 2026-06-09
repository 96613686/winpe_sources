# Microsoft.ReportingServices.Portal.WebHost.Owin.DatabaseAvailableMiddleware::TestAvailable

- ea: `0x2aa0`
- end: `0x2ae1`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.DatabaseAvailableMiddleware::TestAvailable`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2aa0`

## pseudocode

```c

```

## disassembly

```asm
0x2aa0  ldc.i4.2
0x2aa1  newarr   [mscorlib]System.String
0x2aa6  dup
0x2aa7  ldc.i4.0
0x2aa8  ldstr    aOwin// "owin"
0x2aad  stelem.ref
0x2aae  dup
0x2aaf  ldc.i4.1
0x2ab0  ldarg.0
0x2ab1  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2ab6  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2abb  stelem.ref
0x2abc  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0x2ac1  stloc.0
0x2ac2  ldarg.0
0x2ac3  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDatabaseService Microsoft.ReportingServices.Portal.WebHost.Owin.DatabaseAvailableMiddleware::databaseService
0x2ac8  ldarg.0
0x2ac9  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Owin.DatabaseAvailableMiddleware::_logger
0x2ace  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDatabaseService::EnsureDatabaseAvailable(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x2ad3  leave.s  loc_2ADF
0x2ad5  ldloc.0
0x2ad6  brfalse.s loc_2ADE
0x2ad8  ldloc.0
0x2ad9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ade  endfinally
0x2adf  ldc.i4.1
0x2ae0  ret
```
