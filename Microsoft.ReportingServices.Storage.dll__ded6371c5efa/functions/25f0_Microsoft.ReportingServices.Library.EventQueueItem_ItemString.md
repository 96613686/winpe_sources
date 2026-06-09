# Microsoft.ReportingServices.Library.EventQueueItem::ItemString

- ea: `0x25f0`
- end: `0x26e1`
- name: `Microsoft.ReportingServices.Library.EventQueueItem::ItemString`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2040`
- `0x25f0`

## string_xrefs

- `0x2640`: `RefreshCache`
- `0x266e`: `ReportExecutionUpdateSchedule`
- `0x2681`: `SnapshotUpdated`
- `0x2694`: `CacheInvalidateSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x25f0  ldstr    aEventdata// "EventData"
0x25f5  stloc.0
0x25f6  ldarg.0
0x25f7  ldfld    string Microsoft.ReportingServices.Library.EventQueueItem::EventType
0x25fc  ldstr    aSharedschedule// "SharedSchedule"
0x2601  ldc.i4.5
0x2602  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2607  brtrue.s loc_2614
0x2609  ldstr    aScheduleid// "ScheduleID"
0x260e  stloc.0
0x260f  br       loc_26A7
0x2614  ldarg.0
0x2615  ldfld    string Microsoft.ReportingServices.Library.EventQueueItem::EventType
0x261a  ldstr    aDatadrivensubs// "DataDrivenSubscription"
0x261f  ldc.i4.5
0x2620  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2625  brfalse.s loc_264D
0x2627  ldarg.0
0x2628  ldfld    string Microsoft.ReportingServices.Library.EventQueueItem::EventType
0x262d  ldstr    aTimedsubscript// "TimedSubscription"
0x2632  ldc.i4.5
0x2633  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2638  brfalse.s loc_264D
0x263a  ldarg.0
0x263b  ldfld    string Microsoft.ReportingServices.Library.EventQueueItem::EventType
0x2640  ldstr    aRefreshcache// "RefreshCache"
0x2645  ldc.i4.5
0x2646  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x264b  brtrue.s loc_2655
0x264d  ldstr    aSubscriptionid// "SubscriptionID"
0x2652  stloc.0
0x2653  br.s     loc_26A7
0x2655  ldarg.0
0x2656  ldfld    string Microsoft.ReportingServices.Library.EventQueueItem::EventType
0x265b  ldstr    aReporthistorys// "ReportHistorySchedule"
0x2660  ldc.i4.5
0x2661  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2666  brfalse.s loc_26A1
0x2668  ldarg.0
0x2669  ldfld    string Microsoft.ReportingServices.Library.EventQueueItem::EventType
0x266e  ldstr    aReportexecutio// "ReportExecutionUpdateSchedule"
0x2673  ldc.i4.5
0x2674  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2679  brfalse.s loc_26A1
0x267b  ldarg.0
0x267c  ldfld    string Microsoft.ReportingServices.Library.EventQueueItem::EventType
0x2681  ldstr    aSnapshotupdate// "SnapshotUpdated"
0x2686  ldc.i4.5
0x2687  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x268c  brfalse.s loc_26A1
0x268e  ldarg.0
0x268f  ldfld    string Microsoft.ReportingServices.Library.EventQueueItem::EventType
0x2694  ldstr    aCacheinvalidat// "CacheInvalidateSchedule"
0x2699  ldc.i4.5
0x269a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x269f  brtrue.s loc_26A7
0x26a1  ldstr    aReportid// "ReportID"
0x26a6  stloc.0
0x26a7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26ac  ldstr    aTimeentered0Ty// "TimeEntered: {0}, Type: Event, EventTyp"...
0x26b1  ldc.i4.4
0x26b2  newarr   [mscorlib]System.Object
0x26b7  dup
0x26b8  ldc.i4.0
0x26b9  ldarg.0
0x26ba  call     instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.QueueItem::get_TimeEntered()
0x26bf  box      [mscorlib]System.DateTime
0x26c4  stelem.ref
0x26c5  dup
0x26c6  ldc.i4.1
0x26c7  ldarg.0
0x26c8  ldfld    string Microsoft.ReportingServices.Library.EventQueueItem::EventType
0x26cd  stelem.ref
0x26ce  dup
0x26cf  ldc.i4.2
0x26d0  ldloc.0
0x26d1  stelem.ref
0x26d2  dup
0x26d3  ldc.i4.3
0x26d4  ldarg.0
0x26d5  ldfld    string Microsoft.ReportingServices.Library.EventQueueItem::EventData
0x26da  stelem.ref
0x26db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26e0  ret
```
