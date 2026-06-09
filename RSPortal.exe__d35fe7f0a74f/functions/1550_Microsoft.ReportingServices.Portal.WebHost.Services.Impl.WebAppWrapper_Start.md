# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppWrapper::Start

- ea: `0x1550`
- end: `0x1577`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppWrapper::Start`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x3b70`

## pseudocode

```c

```

## disassembly

```asm
0x1550  newobj   instance void <>c__DisplayClass0_0::.ctor()
0x1555  stloc.0
0x1556  ldloc.0
0x1557  ldarg.2
0x1558  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager <>c__DisplayClass0_0::rsConfigManager
0x155d  ldloc.0
0x155e  ldarg.3
0x155f  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger <>c__DisplayClass0_0::logger
0x1564  ldarg.1
0x1565  ldloc.0
0x1566  ldftn    instance void <>c__DisplayClass0_0::<Start>b__0(class [Owin]Owin.IAppBuilder app)
0x156c  newobj   instance void class [mscorlib]System.Action`1<class [Owin]Owin.IAppBuilder>::.ctor(object, native int)
0x1571  call     class [mscorlib]System.IDisposable [Microsoft.Owin.Hosting]Microsoft.Owin.Hosting.WebApp::Start(class [Microsoft.Owin.Hosting]Microsoft.Owin.Hosting.StartOptions, class [mscorlib]System.Action`1<class [Owin]Owin.IAppBuilder>)
0x1576  ret
```
