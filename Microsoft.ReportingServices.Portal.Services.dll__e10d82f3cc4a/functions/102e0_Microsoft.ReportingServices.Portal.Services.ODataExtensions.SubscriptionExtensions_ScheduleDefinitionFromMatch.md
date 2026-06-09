# Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ScheduleDefinitionFromMatchData

- ea: `0x102e0`
- end: `0x1030a`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ScheduleDefinitionFromMatchData`
- size: `42`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xfbf0`
- `0xfd90`
- `0x10190`

## callees

- `0xf060`
- `0x102e0`
- `0x10310`

## pseudocode

```c

```

## disassembly

```asm
0x102e0  ldarg.0
0x102e1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x102e6  brfalse.s loc_102EA
0x102e8  ldnull
0x102e9  ret
0x102ea  ldarg.0
0x102eb  call     bool Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::IsReference(string matchData)
0x102f0  brfalse.s loc_102F4
0x102f2  ldnull
0x102f3  ret
0x102f4  nop
0x102f5  ldarg.0
0x102f6  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::XmlToDefinition(string)
0x102fb  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToWebAPI(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition soapDefinition)
0x10300  stloc.0
0x10301  leave.s  loc_10308
0x10303  pop
0x10304  ldnull
0x10305  stloc.0
0x10306  leave.s  loc_10308
0x10308  ldloc.0
0x10309  ret
```
