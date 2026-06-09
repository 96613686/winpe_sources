# Microsoft.ReportingServices.Common.RSPerfCounterInfo::AddAdditionalWinServicePerfCounters

- ea: `0x2050`
- end: `0x2222`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterInfo::AddAdditionalWinServicePerfCounters`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ef0`

## callees

- `0x1700`
- `0x1710`
- `0x1720`
- `0x1730`
- `0x1740`
- `0x1750`
- `0x1760`
- `0x1770`
- `0x1780`
- `0x17c0`
- `0x17d0`
- `0x17e0`
- `0x17f0`
- `0x1800`
- `0x1810`
- `0x1820`
- `0x1830`
- `0x2050`

## pseudocode

```c

```

## disassembly

```asm
0x2050  ldarg.0
0x2051  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::AppDomainRecycles
0x2056  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_APPDOMAINRECYCLES()
0x205b  ldc.i4   0x10000
0x2060  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x2065  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x206a  pop
0x206b  ldarg.0
0x206c  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::DeliveryCountStr
0x2071  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_DELIVERIES()
0x2076  ldc.i4   0x10000
0x207b  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x2080  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x2085  pop
0x2086  ldarg.0
0x2087  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::DeliveriesPerSecond
0x208c  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_DELIVERIESPERSECOND()
0x2091  ldc.i4   0x10410400
0x2096  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x209b  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x20a0  pop
0x20a1  ldarg.0
0x20a2  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::EventHandleCount
0x20a7  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_EVENTS()
0x20ac  ldc.i4   0x10000
0x20b1  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x20b6  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x20bb  pop
0x20bc  ldarg.0
0x20bd  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::EventsPerSecond
0x20c2  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_EVENTSPERSECOND()
0x20c7  ldc.i4   0x10410400
0x20cc  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x20d1  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x20d6  pop
0x20d7  ldarg.0
0x20d8  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::SnapshotUpdates
0x20dd  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_SNAPSHOTUPDATES()
0x20e2  ldc.i4   0x10000
0x20e7  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x20ec  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x20f1  pop
0x20f2  ldarg.0
0x20f3  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ShapshotUpdatesPerSecond
0x20f8  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_SNAPSHOTUPDATESPERSECOND()
0x20fd  ldc.i4   0x10410400
0x2102  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x2107  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x210c  pop
0x210d  ldarg.0
0x210e  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::CacheFlushCount
0x2113  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEFLUSHES()
0x2118  ldc.i4   0x10000
0x211d  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x2122  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x2127  pop
0x2128  ldarg.0
0x2129  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::CacheFlushPerSecond
0x212e  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEFLUSHESPERSECOND()
0x2133  ldc.i4   0x10000
0x2138  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x213d  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x2142  pop
0x2143  ldarg.1
0x2144  brfalse  loc_2221
0x2149  ldarg.0
0x214a  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::AlertingQueueSize
0x214f  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_ALERTINGQUEUESIZE()
0x2154  ldc.i4   0x10000
0x2159  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x215e  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x2163  pop
0x2164  ldarg.0
0x2165  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::FireAlertEventsProcessed
0x216a  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_FIREALERTEVENTSPROCESSED()
0x216f  ldc.i4   0x10000
0x2174  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x2179  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x217e  pop
0x217f  ldarg.0
0x2180  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::FireScheduleEventsProcessed
0x2185  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_FIRESCHEDULEEVENTSPROCESSED()
0x218a  ldc.i4   0x10000
0x218f  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x2194  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x2199  pop
0x219a  ldarg.0
0x219b  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::CreateScheduleEventsProcessed
0x21a0  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CREATESCHEDULEEVENTSPROCESSED()
0x21a5  ldc.i4   0x10000
0x21aa  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x21af  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x21b4  pop
0x21b5  ldarg.0
0x21b6  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::UpdateScheduleEventsProcessed
0x21bb  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_UPDATESCHEDULEEVENTSPROCESSED()
0x21c0  ldc.i4   0x10000
0x21c5  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x21ca  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x21cf  pop
0x21d0  ldarg.0
0x21d1  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::DeleteScheduleEventsProcessed
0x21d6  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_DELETESCHEDULEEVENTSPROCESSED()
0x21db  ldc.i4   0x10000
0x21e0  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x21e5  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x21ea  pop
0x21eb  ldarg.0
0x21ec  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::GenerateAlertEventsProcessed
0x21f1  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_GENERATEALERTEVENTSPROCESSED()
0x21f6  ldc.i4   0x10000
0x21fb  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x2200  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x2205  pop
0x2206  ldarg.0
0x2207  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::DeliverAlertEventsProcessed
0x220c  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_DELIVERALERTEVENTSPROCESSED()
0x2211  ldc.i4   0x10000
0x2216  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x221b  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x2220  pop
0x2221  ret
```
