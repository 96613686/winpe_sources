# Microsoft.ReportingServices.Common.RSPerfCounterInfo::GetWindowsServiceCounterInfo

- ea: `0x1ef0`
- end: `0x1fc2`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterInfo::GetWindowsServiceCounterInfo`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2500`

## callees

- `0x1a10`
- `0x1ef0`
- `0x2050`

## pseudocode

```c

```

## disassembly

```asm
0x1ef0  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1ef5  brtrue.s loc_1EFE
0x1ef7  ldc.i4.0
0x1ef8  call     class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::GetWebServiceCounterInfo(bool defaultOnly)
0x1efd  pop
0x1efe  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersDefault
0x1f03  brtrue   loc_1FB3
0x1f08  newobj   instance void [System]System.Diagnostics.CounterCreationDataCollection::.ctor()
0x1f0d  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersDefault
0x1f12  newobj   instance void [System]System.Diagnostics.CounterCreationDataCollection::.ctor()
0x1f17  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersAll
0x1f1c  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersDefault
0x1f21  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1f26  callvirt instance void [System]System.Diagnostics.CounterCreationDataCollection::AddRange(class [System]System.Diagnostics.CounterCreationDataCollection)
0x1f2b  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersAll
0x1f30  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1f35  callvirt instance void [System]System.Diagnostics.CounterCreationDataCollection::AddRange(class [System]System.Diagnostics.CounterCreationDataCollection)
0x1f3a  ldnull
0x1f3b  stloc.0
0x1f3c  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersAll
0x1f41  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1f46  stloc.1
0x1f47  br.s     loc_1F69
0x1f49  ldloc.1
0x1f4a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1f4f  castclass [System]System.Diagnostics.CounterCreationData
0x1f54  stloc.2
0x1f55  ldloc.2
0x1f56  callvirt instance string [System]System.Diagnostics.CounterCreationData::get_CounterName()
0x1f5b  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ActiveSessionsCount
0x1f60  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1f65  brfalse.s loc_1F69
0x1f67  ldloc.2
0x1f68  stloc.0
0x1f69  ldloc.1
0x1f6a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f6f  brtrue.s loc_1F49
0x1f71  leave.s  loc_1F84
0x1f73  ldloc.1
0x1f74  isinst   [mscorlib]System.IDisposable
0x1f79  stloc.3
0x1f7a  ldloc.3
0x1f7b  brfalse.s loc_1F83
0x1f7d  ldloc.3
0x1f7e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f83  endfinally
0x1f84  ldloc.0
0x1f85  brfalse.s loc_1F9D
0x1f87  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersAll
0x1f8c  ldloc.0
0x1f8d  callvirt instance void [System]System.Diagnostics.CounterCreationDataCollection::Remove(class [System]System.Diagnostics.CounterCreationData)
0x1f92  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersDefault
0x1f97  ldloc.0
0x1f98  callvirt instance void [System]System.Diagnostics.CounterCreationDataCollection::Remove(class [System]System.Diagnostics.CounterCreationData)
0x1f9d  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersDefault
0x1fa2  ldarg.1
0x1fa3  call     void Microsoft.ReportingServices.Common.RSPerfCounterInfo::AddAdditionalWinServicePerfCounters(class [System]System.Diagnostics.CounterCreationDataCollection list, bool isSharePointMode)
0x1fa8  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersAll
0x1fad  ldarg.1
0x1fae  call     void Microsoft.ReportingServices.Common.RSPerfCounterInfo::AddAdditionalWinServicePerfCounters(class [System]System.Diagnostics.CounterCreationDataCollection list, bool isSharePointMode)
0x1fb3  ldarg.0
0x1fb4  brfalse.s loc_1FBC
0x1fb6  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersDefault
0x1fbb  ret
0x1fbc  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersAll
0x1fc1  ret
```
