# Microsoft.ReportingServices.Common.RSPerfCounterInfo::GetSharePointServicePerfCounters

- ea: `0x1fd0`
- end: `0x2044`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterInfo::GetSharePointServicePerfCounters`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x2530`

## callees

- `0x1790`
- `0x17a0`
- `0x17b0`
- `0x1fd0`

## pseudocode

```c

```

## disassembly

```asm
0x1fd0  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_sharepointServicePerfCounters
0x1fd5  brtrue.s loc_203E
0x1fd7  newobj   instance void [System]System.Diagnostics.CounterCreationDataCollection::.ctor()
0x1fdc  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_sharepointServicePerfCounters
0x1fe1  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_sharepointServicePerfCounters
0x1fe6  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryPressureLevel
0x1feb  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYPRESSURELEVEL()
0x1ff0  ldc.i4   0x10000
0x1ff5  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1ffa  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1fff  pop
0x2000  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_sharepointServicePerfCounters
0x2005  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryShrinkAmount
0x200a  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYSHRINKAMOUNT()
0x200f  ldc.i4   0x10000
0x2014  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x2019  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x201e  pop
0x201f  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_sharepointServicePerfCounters
0x2024  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryShrinkNotificationPerSecond
0x2029  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMNOTIFICATIONPERSECOND()
0x202e  ldc.i4   0x10410400
0x2033  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x2038  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x203d  pop
0x203e  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_sharepointServicePerfCounters
0x2043  ret
```
