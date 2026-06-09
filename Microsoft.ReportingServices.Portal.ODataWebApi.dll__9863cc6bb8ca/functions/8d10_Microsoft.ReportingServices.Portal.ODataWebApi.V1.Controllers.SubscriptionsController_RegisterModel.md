# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::RegisterModel

- ea: `0x8d10`
- end: `0x8d3f`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::RegisterModel`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xbd0`
- `0x5f50`

## pseudocode

```c

```

## disassembly

```asm
0x8d10  ldarg.0
0x8d11  ldstr    aSubscriptions// "Subscriptions"
0x8d16  callvirt T0x2B0000C1
0x8d1b  pop
0x8d1c  ldarg.0
0x8d1d  callvirt T0x2B000090
0x8d22  ldstr    aEnable// "Enable"
0x8d27  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription>::Action(string)
0x8d2c  pop
0x8d2d  ldarg.0
0x8d2e  callvirt T0x2B000090
0x8d33  ldstr    aDisable// "Disable"
0x8d38  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription>::Action(string)
0x8d3d  pop
0x8d3e  ret
```
