# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.NotificationsController::.ctor

- ea: `0x73b0`
- end: `0x73cd`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.NotificationsController::.ctor`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5390`

## callees

- `0x73b0`

## string_xrefs

- `0x73ba`: `notificationService`

## pseudocode

```c

```

## disassembly

```asm
0x73b0  ldarg.0
0x73b1  ldarg.2
0x73b2  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Notification>::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x73b7  ldarg.1
0x73b8  brtrue.s loc_73C5
0x73ba  ldstr    aNotificationse// "notificationService"
0x73bf  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x73c4  throw
0x73c5  ldarg.0
0x73c6  ldarg.1
0x73c7  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.INotificationService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.NotificationsController::_notificationService
0x73cc  ret
```
