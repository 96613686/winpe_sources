# Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetMatchData

- ea: `0x7da0`
- end: `0x7de4`
- name: `Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetMatchData`
- size: `68`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7600`
- `0x7890`
- `0x7910`

## callees

- `0x7da0`
- `0xf490`

## string_xrefs

- `0x7da6`: `SnapshotUpdated`

## pseudocode

```c

```

## disassembly

```asm
0x7da0  ldarg.1
0x7da1  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_EventType()
0x7da6  ldstr    aSnapshotupdate// "SnapshotUpdated"
0x7dab  ldc.i4.5
0x7dac  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7db1  brtrue.s loc_7DB5
0x7db3  ldnull
0x7db4  ret
0x7db5  ldarg.1
0x7db6  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Schedule()
0x7dbb  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::get_ScheduleID()
0x7dc0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7dc5  brtrue.s loc_7DD3
0x7dc7  ldarg.1
0x7dc8  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Schedule()
0x7dcd  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::get_ScheduleID()
0x7dd2  ret
0x7dd3  ldarg.1
0x7dd4  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Schedule()
0x7dd9  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::get_Definition()
0x7dde  call     string Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToMatchData(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition scheduleDefinition)
0x7de3  ret
```
