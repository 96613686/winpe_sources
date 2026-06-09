# Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::GetProgressiveReportPerfCounters

- ea: `0x1180`
- end: `0x14df`
- name: `Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::GetProgressiveReportPerfCounters`
- size: `863`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callers

- `0x2560`

## callees

- `0x1180`
- `0x1840`
- `0x1850`
- `0x1860`
- `0x1870`
- `0x1880`
- `0x1890`
- `0x18a0`
- `0x18b0`
- `0x18c0`
- `0x18d0`
- `0x18e0`
- `0x18f0`
- `0x1900`
- `0x1910`
- `0x1920`
- `0x1930`
- `0x1940`
- `0x1950`
- `0x1960`
- `0x1970`
- `0x1980`
- `0x1990`
- `0x19a0`
- `0x19b0`

## string_xrefs

- `0x14bf`: `Threads Active`

## pseudocode

```c

```

## disassembly

```asm
0x1180  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x1185  brtrue   loc_14D9
0x118a  newobj   instance void [System]System.Diagnostics.CounterCreationDataCollection::.ctor()
0x118f  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x1194  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x1199  ldstr    aReportRequests// "Report Requests Active"
0x119e  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_ReportRequestsActive()
0x11a3  ldc.i4   0x10000
0x11a8  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x11ad  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x11b2  pop
0x11b3  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x11b8  ldstr    aReportRequests_0// "Report Requests Total"
0x11bd  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_ReportRequestsTotal()
0x11c2  ldc.i4   0x10000
0x11c7  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x11cc  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x11d1  pop
0x11d2  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x11d7  ldstr    aReportRequests_1// "Report Requests/sec"
0x11dc  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_ReportRequestsPerSecond()
0x11e1  ldc.i4   0x10410400
0x11e6  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x11eb  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x11f0  pop
0x11f1  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x11f6  ldstr    aReportRequests_2// "Report Requests Average Duration (ms)"
0x11fb  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_ReportRequestsAverageDuration()
0x1200  ldc.i4   0x40020500
0x1205  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x120a  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x120f  pop
0x1210  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x1215  ldstr    aReportRequests_3// "Report Requests Average Duration base"
0x121a  ldsfld   string [mscorlib]System.String::Empty
0x121f  ldc.i4   0x40030402
0x1224  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1229  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x122e  pop
0x122f  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x1234  ldstr    aModelRequestsA// "Model Requests Active"
0x1239  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_ModelRequestsActive()
0x123e  ldc.i4   0x10000
0x1243  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1248  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x124d  pop
0x124e  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x1253  ldstr    aModelRequestsT// "Model Requests Total"
0x1258  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_ModelRequestsTotal()
0x125d  ldc.i4   0x10000
0x1262  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1267  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x126c  pop
0x126d  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x1272  ldstr    aModelRequestsS// "Model Requests/sec"
0x1277  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_ModelRequestsPerSecond()
0x127c  ldc.i4   0x10410400
0x1281  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1286  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x128b  pop
0x128c  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x1291  ldstr    aModelRequestsA_0// "Model Requests Average Duration (ms)"
0x1296  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_ModelRequestsAverageDuration()
0x129b  ldc.i4   0x40020500
0x12a0  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x12a5  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x12aa  pop
0x12ab  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x12b0  ldstr    aModelRequestsA_1// "Model Requests Average Duration base"
0x12b5  ldsfld   string [mscorlib]System.String::Empty
0x12ba  ldc.i4   0x40030402
0x12bf  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x12c4  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x12c9  pop
0x12ca  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x12cf  ldstr    aQueryRequestsA// "Query Requests Active"
0x12d4  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_QueryRequestsActive()
0x12d9  ldc.i4   0x10000
0x12de  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x12e3  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x12e8  pop
0x12e9  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x12ee  ldstr    aQueryRequestsT// "Query Requests Total"
0x12f3  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_QueryRequestsTotal()
0x12f8  ldc.i4   0x10000
0x12fd  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1302  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1307  pop
0x1308  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x130d  ldstr    aQueryRequestsS// "Query Requests/sec"
0x1312  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_QueryRequestsPerSecond()
0x1317  ldc.i4   0x10410400
0x131c  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1321  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1326  pop
0x1327  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x132c  ldstr    aQueryRequestsA_0// "Query Requests Average Duration (ms)"
0x1331  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_QueryRequestsAverageDuration()
0x1336  ldc.i4   0x40020500
0x133b  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1340  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1345  pop
0x1346  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x134b  ldstr    aQueryRequestsA_1// "Query Requests Average Duration base"
0x1350  ldsfld   string [mscorlib]System.String::Empty
0x1355  ldc.i4   0x40030402
0x135a  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x135f  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1364  pop
0x1365  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x136a  ldstr    aFailuresTotal// "Failures Total"
0x136f  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_FailuresTotal()
0x1374  ldc.i4   0x10000
0x1379  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x137e  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1383  pop
0x1384  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x1389  ldstr    aFailuresSec// "Failures/sec"
0x138e  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_FailuresPerSecond()
0x1393  ldc.i4   0x10410400
0x1398  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x139d  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x13a2  pop
0x13a3  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x13a8  ldstr    aSessionsActive// "Sessions Active"
0x13ad  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_SessionsActive()
0x13b2  ldc.i4   0x10000
0x13b7  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x13bc  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x13c1  pop
0x13c2  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x13c7  ldstr    aRequestsInNewS// "Requests in New Sessions Total"
0x13cc  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_NewSessionTotal()
0x13d1  ldc.i4   0x10000
0x13d6  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x13db  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x13e0  pop
0x13e1  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x13e6  ldstr    aRequestsInNewS_0// "Requests in New Sessions/sec"
0x13eb  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_NewSessionPerSecond()
0x13f0  ldc.i4   0x10410400
0x13f5  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x13fa  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x13ff  pop
0x1400  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x1405  ldstr    aRequestsInExis// "Requests in Existing Sessions Total"
0x140a  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_ExistingSessionTotal()
0x140f  ldc.i4   0x10000
0x1414  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1419  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x141e  pop
0x141f  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x1424  ldstr    aRequestsInExis_0// "Requests in Existing Sessions/sec"
0x1429  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_ExistingSessionPerSecond()
0x142e  ldc.i4   0x10410400
0x1433  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1438  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x143d  pop
0x143e  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x1443  ldstr    aRequestsTotal// "Requests Total"
0x1448  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_AllRequestsTotal()
0x144d  ldc.i4   0x10000
0x1452  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1457  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x145c  pop
0x145d  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x1462  ldstr    aRequestsSec// "Requests/sec"
0x1467  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_AllRequestsPerSecond()
0x146c  ldc.i4   0x10410400
0x1471  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1476  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x147b  pop
0x147c  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x1481  ldstr    aDataSourceConn// "Data Source Connection Failures Total"
0x1486  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_DataSourceConnectionFailuresTotal()
0x148b  ldc.i4   0x10000
0x1490  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1495  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x149a  pop
0x149b  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x14a0  ldstr    aDataSourceConn_0// "Data Source Connection Failures/sec"
0x14a5  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_DataSourceConnectionFailuresPerSecond()
0x14aa  ldc.i4   0x10410400
0x14af  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x14b4  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x14b9  pop
0x14ba  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x14bf  ldstr    aThreadsActive// "Threads Active"
0x14c4  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_ThreadsActive()
0x14c9  ldc.i4   0x10000
0x14ce  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x14d3  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x14d8  pop
0x14d9  ldsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.ProgressiveReportCounterInfo::m_progressiveReportPerfCounters
0x14de  ret
```
