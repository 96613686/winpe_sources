# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::.ctor

- ea: `0x7470`
- end: `0x748d`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::.ctor`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5d80`

## callees

- `0x7470`

## string_xrefs

- `0x747a`: `systemService`

## pseudocode

```c

```

## disassembly

```asm
0x7470  ldarg.0
0x7471  ldarg.2
0x7472  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule>::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x7477  ldarg.1
0x7478  brtrue.s loc_7485
0x747a  ldstr    aSystemservice// "systemService"
0x747f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7484  throw
0x7485  ldarg.0
0x7486  ldarg.1
0x7487  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::_systemService
0x748c  ret
```
