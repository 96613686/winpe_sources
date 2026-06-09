# Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetSubscriptionCulture

- ea: `0x7d10`
- end: `0x7d52`
- name: `Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetSubscriptionCulture`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x76d0`
- `0x77c0`
- `0x7c30`

## callees

- `0x9e80`
- `0x128c0`
- `0x1f9b0`

## pseudocode

```c

```

## disassembly

```asm
0x7d10  newobj   instance void <>c__DisplayClass23_0::.ctor()
0x7d15  stloc.0
0x7d16  ldloc.0
0x7d17  ldarg.2
0x7d18  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass23_0::key
0x7d1d  ldloc.0
0x7d1e  ldarg.1
0x7d1f  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x7d24  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass23_0::rsService
0x7d29  ldloc.0
0x7d2a  ldsfld   string [mscorlib]System.String::Empty
0x7d2f  stfld    string <>c__DisplayClass23_0::culture
0x7d34  ldloc.0
0x7d35  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass23_0::rsService
0x7d3a  ldloc.0
0x7d3b  ldftn    instance void <>c__DisplayClass23_0::<GetSubscriptionCulture>b__0()
0x7d41  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x7d46  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action)
0x7d4b  ldloc.0
0x7d4c  ldfld    string <>c__DisplayClass23_0::culture
0x7d51  ret
```
