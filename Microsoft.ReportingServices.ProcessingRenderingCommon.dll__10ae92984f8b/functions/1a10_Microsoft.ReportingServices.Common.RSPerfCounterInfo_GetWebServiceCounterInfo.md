# Microsoft.ReportingServices.Common.RSPerfCounterInfo::GetWebServiceCounterInfo

- ea: `0x1a10`
- end: `0x1ee6`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterInfo::GetWebServiceCounterInfo`
- size: `1238`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ef0`
- `0x24d0`

## callees

- `0x15a0`
- `0x15b0`
- `0x15c0`
- `0x15d0`
- `0x15e0`
- `0x15f0`
- `0x1600`
- `0x1610`
- `0x1620`
- `0x1630`
- `0x1640`
- `0x1650`
- `0x1660`
- `0x1670`
- `0x1680`
- `0x1690`
- `0x16a0`
- `0x16b0`
- `0x16c0`
- `0x16d0`
- `0x16e0`
- `0x16f0`
- `0x1a10`

## pseudocode

```c

```

## disassembly

```asm
0x1a10  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1a15  brtrue   loc_1ED7
0x1a1a  newobj   instance void [System]System.Diagnostics.CounterCreationDataCollection::.ctor()
0x1a1f  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1a24  newobj   instance void [System]System.Diagnostics.CounterCreationDataCollection::.ctor()
0x1a29  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1a2e  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1a33  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ReportRequests
0x1a38  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_REPORTREQUESTS()
0x1a3d  ldc.i4   0x10000
0x1a42  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1a47  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1a4c  pop
0x1a4d  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1a52  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ExecutionCount
0x1a57  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_REPORTSEXECUTED()
0x1a5c  ldc.i4   0x10000
0x1a61  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1a66  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1a6b  pop
0x1a6c  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1a71  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ExecutionsPerSecond
0x1a76  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_REPORTSEXECUTEDPERSECOND()
0x1a7b  ldc.i4   0x10410400
0x1a80  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1a85  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1a8a  pop
0x1a8b  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1a90  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ReportProcessingErrorCount
0x1a95  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_PROCESSINGFAILURES()
0x1a9a  ldc.i4   0x10000
0x1a9f  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1aa4  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1aa9  pop
0x1aaa  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1aaf  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::RejectedThreads
0x1ab4  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_REJECTEDTHREADS()
0x1ab9  ldc.i4   0x10000
0x1abe  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1ac3  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1ac8  pop
0x1ac9  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1ace  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ActiveSessionsCount
0x1ad3  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_ACTIVESESSIONS()
0x1ad8  ldc.i4   0x10000
0x1add  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1ae2  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1ae7  pop
0x1ae8  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1aed  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::FirstSessionRequests
0x1af2  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_FIRSTSESSIONPERSECOND()
0x1af7  ldc.i4   0x10410400
0x1afc  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1b01  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1b06  pop
0x1b07  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1b0c  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::NextSessionRequests
0x1b11  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_NEXTSESSIONPERSECOND()
0x1b16  ldc.i4   0x10410400
0x1b1b  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1b20  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1b25  pop
0x1b26  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1b2b  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalCacheHitsCount
0x1b30  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEHITS()
0x1b35  ldc.i4   0x10000
0x1b3a  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1b3f  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1b44  pop
0x1b45  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1b4a  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalCacheHitsPerSecond
0x1b4f  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEHITSPERSECOND()
0x1b54  ldc.i4   0x10410400
0x1b59  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1b5e  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1b63  pop
0x1b64  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1b69  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalCacheMissCount
0x1b6e  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEMISSES()
0x1b73  ldc.i4   0x10000
0x1b78  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1b7d  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1b82  pop
0x1b83  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1b88  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalCacheMissPerSecond
0x1b8d  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEMISSESPERSECOND()
0x1b92  ldc.i4   0x10410400
0x1b97  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1b9c  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1ba1  pop
0x1ba2  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1ba7  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalRequestCount
0x1bac  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_TOTALREQUESTS()
0x1bb1  ldc.i4   0x10000
0x1bb6  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1bbb  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1bc0  pop
0x1bc1  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1bc6  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalRequestPerSecond
0x1bcb  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_REQUESTSPERSECOND()
0x1bd0  ldc.i4   0x10410400
0x1bd5  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1bda  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1bdf  pop
0x1be0  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1be5  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalMemoryCacheHitsCount
0x1bea  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYCACHEHITS()
0x1bef  ldc.i4   0x10000
0x1bf4  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1bf9  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1bfe  pop
0x1bff  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1c04  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryCacheHitsPerSecond
0x1c09  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYCACHEHITSPERSECOND()
0x1c0e  ldc.i4   0x10410400
0x1c13  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1c18  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1c1d  pop
0x1c1e  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1c23  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalMemoryCacheMissCount
0x1c28  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYCACHEMISSES()
0x1c2d  ldc.i4   0x10000
0x1c32  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1c37  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1c3c  pop
0x1c3d  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1c42  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryCacheMissPerSecond
0x1c47  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYCACHEMISSESPERSECOND()
0x1c4c  ldc.i4   0x10410400
0x1c51  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1c56  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1c5b  pop
0x1c5c  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1c61  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ModelsTotalCacheHitsCount
0x1c66  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MODELCACHEHITS()
0x1c6b  ldc.i4   0x10000
0x1c70  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1c75  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1c7a  pop
0x1c7b  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1c80  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ModelsTotalCacheHitsPerSecond
0x1c85  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MODELCACHEHITSPERSECOND()
0x1c8a  ldc.i4   0x10410400
0x1c8f  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1c94  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1c99  pop
0x1c9a  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1c9f  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ModelsTotalCacheMissCount
0x1ca4  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MODELCACHEMISS()
0x1ca9  ldc.i4   0x10000
0x1cae  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1cb3  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1cb8  pop
0x1cb9  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1cbe  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ModelsTotalCacheMissPerSecond
0x1cc3  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MODELCACHEMISSPERSECOND()
0x1cc8  ldc.i4   0x10410400
0x1ccd  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1cd2  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1cd7  pop
0x1cd8  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1cdd  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1ce2  callvirt instance void [System]System.Diagnostics.CounterCreationDataCollection::AddRange(class [System]System.Diagnostics.CounterCreationDataCollection)
0x1ce7  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1cec  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::SqlConnections
0x1cf1  ldstr    asc_19000// ""
0x1cf6  ldc.i4   0x10000
0x1cfb  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1d00  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1d05  pop
0x1d06  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1d0b  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ProcessingDatasourceConnections
0x1d10  ldstr    asc_19000// ""
0x1d15  ldc.i4   0x10000
0x1d1a  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1d1f  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1d24  pop
0x1d25  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1d2a  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ReportServerActiveThreads
0x1d2f  ldstr    asc_19000// ""
0x1d34  ldc.i4   0x10000
0x1d39  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1d3e  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1d43  pop
0x1d44  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1d49  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInProcessingName
0x1d4e  ldstr    asc_19000// ""
0x1d53  ldc.i4   0x10000
0x1d58  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1d5d  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1d62  pop
0x1d63  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1d68  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInRenderingName
0x1d6d  ldstr    asc_19000// ""
0x1d72  ldc.i4   0x10000
0x1d77  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1d7c  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1d81  pop
0x1d82  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1d87  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInDatasourceAccessName
0x1d8c  ldstr    asc_19000// ""
0x1d91  ldc.i4   0x10000
0x1d96  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1d9b  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1da0  pop
0x1da1  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1da6  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInDatabaseName
0x1dab  ldstr    asc_19000// ""
0x1db0  ldc.i4   0x10000
0x1db5  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1dba  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1dbf  pop
0x1dc0  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1dc5  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInCompressionName
0x1dca  ldstr    asc_19000// ""
0x1dcf  ldc.i4   0x10000
0x1dd4  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1dd9  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1dde  pop
0x1ddf  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1de4  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInUncompressionName
0x1de9  ldstr    asc_19000// ""
0x1dee  ldc.i4   0x10000
0x1df3  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1df8  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1dfd  pop
0x1dfe  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1e03  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::RequestTimeName
0x1e08  ldstr    asc_19000// ""
0x1e0d  ldc.i4   0x10000
0x1e12  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1e17  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1e1c  pop
0x1e1d  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1e22  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::RowCountName
0x1e27  ldstr    asc_19000// ""
0x1e2c  ldc.i4   0x10000
0x1e31  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1e36  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1e3b  pop
0x1e3c  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1e41  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ByteCountName
0x1e46  ldstr    asc_19000// ""
0x1e4b  ldc.i4   0x10000
0x1e50  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1e55  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1e5a  pop
0x1e5b  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1e60  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeBetweenFinishName
0x1e65  ldstr    asc_19000// ""
0x1e6a  ldc.i4   0x10000
0x1e6f  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1e74  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1e79  pop
0x1e7a  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1e7f  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::WaitOnNextStreamName
0x1e84  ldstr    asc_19000// ""
0x1e89  ldc.i4   0x10000
0x1e8e  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1e93  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1e98  pop
0x1e99  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1e9e  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::SnapshotCompressionRatioName
0x1ea3  ldstr    asc_19000// ""
0x1ea8  ldc.i4   0x10000
0x1ead  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1eb2  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1eb7  pop
0x1eb8  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1ebd  ldsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::SnapshotBufferingRatioName
0x1ec2  ldstr    asc_19000// ""
0x1ec7  ldc.i4   0x10000
0x1ecc  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1ed1  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1ed6  pop
0x1ed7  ldarg.0
0x1ed8  brfalse.s loc_1EE0
0x1eda  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x1edf  ret
0x1ee0  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x1ee5  ret
```
