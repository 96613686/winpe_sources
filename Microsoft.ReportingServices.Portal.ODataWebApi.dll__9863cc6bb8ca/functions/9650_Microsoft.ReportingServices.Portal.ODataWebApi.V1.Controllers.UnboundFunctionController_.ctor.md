# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::.ctor

- ea: `0x9650`
- end: `0x9696`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::.ctor`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6080`

## callees

- `0x9650`

## string_xrefs

- `0x9667`: `systemService`
- `0x9675`: `systemResourceService`

## pseudocode

```c

```

## disassembly

```asm
0x9650  ldarg.0
0x9651  call     instance void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataController::.ctor()
0x9656  ldarg.1
0x9657  brtrue.s loc_9664
0x9659  ldstr    aCatalogreposit// "catalogRepository"
0x965e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9663  throw
0x9664  ldarg.2
0x9665  brtrue.s loc_9672
0x9667  ldstr    aSystemservice// "systemService"
0x966c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9671  throw
0x9672  ldarg.3
0x9673  brtrue.s loc_9680
0x9675  ldstr    aSystemresource_1// "systemResourceService"
0x967a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x967f  throw
0x9680  ldarg.0
0x9681  ldarg.1
0x9682  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::_catalogRepository
0x9687  ldarg.0
0x9688  ldarg.2
0x9689  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::_systemService
0x968e  ldarg.0
0x968f  ldarg.3
0x9690  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ISystemResourceService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::_systemResourceService
0x9695  ret
```
