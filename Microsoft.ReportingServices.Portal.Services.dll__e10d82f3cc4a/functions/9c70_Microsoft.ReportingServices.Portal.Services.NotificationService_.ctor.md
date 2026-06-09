# Microsoft.ReportingServices.Portal.Services.NotificationService::.ctor

- ea: `0x9c70`
- end: `0x9ca1`
- name: `Microsoft.ReportingServices.Portal.Services.NotificationService::.ctor`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x9c70`

## string_xrefs

- `0x9c79`: `powerBIIntegrationService`
- `0x9c87`: `subscriptionService`

## pseudocode

```c

```

## disassembly

```asm
0x9c70  ldarg.0
0x9c71  call     instance void [mscorlib]System.Object::.ctor()
0x9c76  ldarg.1
0x9c77  brtrue.s loc_9C84
0x9c79  ldstr    aPowerbiintegra// "powerBIIntegrationService"
0x9c7e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9c83  throw
0x9c84  ldarg.2
0x9c85  brtrue.s loc_9C92
0x9c87  ldstr    aSubscriptionse// "subscriptionService"
0x9c8c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9c91  throw
0x9c92  ldarg.0
0x9c93  ldarg.1
0x9c94  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IPowerBIIntegrationService Microsoft.ReportingServices.Portal.Services.NotificationService::_powerBiIntegrationService
0x9c99  ldarg.0
0x9c9a  ldarg.2
0x9c9b  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.Services.NotificationService::_subscriptionService
0x9ca0  ret
```
