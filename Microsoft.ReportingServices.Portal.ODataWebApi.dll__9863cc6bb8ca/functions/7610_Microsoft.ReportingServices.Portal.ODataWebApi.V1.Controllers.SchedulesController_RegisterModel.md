# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::RegisterModel

- ea: `0x7610`
- end: `0x7697`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::RegisterModel`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xbd0`
- `0x5e40`

## pseudocode

```c

```

## disassembly

```asm
0x7610  ldarg.0
0x7611  ldstr    aSchedules// "Schedules"
0x7616  callvirt T0x2B0000A0
0x761b  pop
0x761c  ldarg.0
0x761d  callvirt T0x2B0000A1
0x7622  ldstr    aPause// "Pause"
0x7627  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule>::Action(string)
0x762c  pop
0x762d  ldarg.0
0x762e  callvirt T0x2B0000A1
0x7633  ldstr    aResume// "Resume"
0x7638  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule>::Action(string)
0x763d  pop
0x763e  ldarg.0
0x763f  callvirt T0x2B0000A1
0x7644  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<var<u1>> class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule>::get_Collection()
0x7649  ldstr    aDescribe// "Describe"
0x764e  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule>::Action(string)
0x7653  ldstr    aSchedule// "schedule"
0x7658  callvirt T0x2B0000A2
0x765d  pop
0x765e  ldarg.0
0x765f  callvirt T0x2B0000A3
0x7664  pop
0x7665  ldarg.0
0x7666  callvirt T0x2B0000A4
0x766b  pop
0x766c  ldarg.0
0x766d  callvirt T0x2B0000A5
0x7672  pop
0x7673  ldarg.0
0x7674  callvirt T0x2B0000A6
0x7679  pop
0x767a  ldarg.0
0x767b  callvirt T0x2B0000A7
0x7680  pop
0x7681  ldarg.0
0x7682  callvirt T0x2B0000A8
0x7687  pop
0x7688  ldarg.0
0x7689  callvirt T0x2B0000A9
0x768e  pop
0x768f  ldarg.0
0x7690  callvirt T0x2B0000AA
0x7695  pop
0x7696  ret
```
