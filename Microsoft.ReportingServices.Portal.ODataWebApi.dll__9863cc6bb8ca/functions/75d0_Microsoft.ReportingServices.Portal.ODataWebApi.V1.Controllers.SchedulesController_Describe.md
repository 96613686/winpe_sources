# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::Describe

- ea: `0x75d0`
- end: `0x7604`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::Describe`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5e30`

## callees

- `0x75d0`

## pseudocode

```c

```

## disassembly

```asm
0x75d0  ldarg.1
0x75d1  brfalse.s loc_75FD
0x75d3  ldarg.1
0x75d4  ldstr    aSchedule// "schedule"
0x75d9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x75de  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule
0x75e3  stloc.0
0x75e4  ldarg.0
0x75e5  ldarg.0
0x75e6  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::_systemService
0x75eb  ldloc.0
0x75ec  ldarg.0
0x75ed  call     instance int32 class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule>::GetUtcOffsetInMinutes()
0x75f2  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::GetScheduleDescription(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule, int32)
0x75f7  callvirt T0x2B00009F
0x75fc  ret
0x75fd  ldarg.0
0x75fe  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule>::BadRequest()
0x7603  ret
```
