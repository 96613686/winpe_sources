# Microsoft.ReportingServices.Common.RSPerfCounterInfo::.cctor

- ea: `0x2230`
- end: `0x24b1`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterInfo::.cctor`
- size: `641`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x2258`: `Total Rejected Threads`
- `0x2280`: `Total Cache Hits`
- `0x228a`: `Cache Hits/Sec`
- `0x2294`: `Total Cache Misses`
- `0x229e`: `Cache Misses/Sec`
- `0x22a8`: `Percent Reports from cache`
- `0x22c6`: `Total Memory Cache Hits`
- `0x22d0`: `Memory Cache Hits/Sec`
- `0x22da`: `Total Memory Cache Misses`
- `0x22e4`: `Memory Cache Miss/Sec`
- `0x22ee`: `Total Cache Hits (Semantic Models)`
- `0x22f8`: `Cache Hits/Sec (Semantic Models)`
- `0x2302`: `Total Cache Misses (Semantic Models)`
- `0x230c`: `Cache Misses/Sec (Semantic Models)`
- `0x232a`: `Memory Shrink Amount`
- `0x235c`: `Active Threads`
- `0x237a`: `Time in data source access`
- `0x238e`: `Time compressing`
- `0x2398`: `Time uncompressing`
- `0x23d4`: `Snapshot compression ratio`
- `0x241a`: `Total Snapshot Updates`
- `0x2424`: `Snapshot Updates/Sec`
- `0x242e`: `Total Cache Flushes`
- `0x2438`: `Cache Flushes/Sec`
- `0x2460`: `Alerting: events processed - CreateSchedule`
- `0x246a`: `Alerting: events processed - UpdateSchedule`
- `0x2474`: `Alerting: events processed - DeleteSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x2230  ldstr    aReportRequests_4// "Report Requests"
0x2235  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ReportRequests
0x223a  ldstr    aTotalReportsEx// "Total Reports Executed"
0x223f  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ExecutionCount
0x2244  ldstr    aReportsExecute// "Reports Executed/Sec"
0x2249  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ExecutionsPerSecond
0x224e  ldstr    aTotalProcessin// "Total Processing Failures"
0x2253  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ReportProcessingErrorCount
0x2258  ldstr    aTotalRejectedT// "Total Rejected Threads"
0x225d  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::RejectedThreads
0x2262  ldstr    aActiveSessions// "Active Sessions"
0x2267  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ActiveSessionsCount
0x226c  ldstr    aFirstSessionRe// "First Session Requests/Sec"
0x2271  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::FirstSessionRequests
0x2276  ldstr    aNextSessionReq// "Next Session Requests/Sec"
0x227b  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::NextSessionRequests
0x2280  ldstr    aTotalCacheHits// "Total Cache Hits"
0x2285  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalCacheHitsCount
0x228a  ldstr    aCacheHitsSec// "Cache Hits/Sec"
0x228f  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalCacheHitsPerSecond
0x2294  ldstr    aTotalCacheMiss// "Total Cache Misses"
0x2299  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalCacheMissCount
0x229e  ldstr    aCacheMissesSec// "Cache Misses/Sec"
0x22a3  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalCacheMissPerSecond
0x22a8  ldstr    aPercentReports// "Percent Reports from cache"
0x22ad  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::RequestFromCachePercent
0x22b2  ldstr    aTotalRequests// "Total Requests"
0x22b7  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalRequestCount
0x22bc  ldstr    aRequestsSec_0// "Requests/Sec"
0x22c1  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalRequestPerSecond
0x22c6  ldstr    aTotalMemoryCac// "Total Memory Cache Hits"
0x22cb  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalMemoryCacheHitsCount
0x22d0  ldstr    aMemoryCacheHit// "Memory Cache Hits/Sec"
0x22d5  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryCacheHitsPerSecond
0x22da  ldstr    aTotalMemoryCac_0// "Total Memory Cache Misses"
0x22df  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalMemoryCacheMissCount
0x22e4  ldstr    aMemoryCacheMis// "Memory Cache Miss/Sec"
0x22e9  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryCacheMissPerSecond
0x22ee  ldstr    aTotalCacheHits_0// "Total Cache Hits (Semantic Models)"
0x22f3  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ModelsTotalCacheHitsCount
0x22f8  ldstr    aCacheHitsSecSe// "Cache Hits/Sec (Semantic Models)"
0x22fd  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ModelsTotalCacheHitsPerSecond
0x2302  ldstr    aTotalCacheMiss_0// "Total Cache Misses (Semantic Models)"
0x2307  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ModelsTotalCacheMissCount
0x230c  ldstr    aCacheMissesSec_0// "Cache Misses/Sec (Semantic Models)"
0x2311  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ModelsTotalCacheMissPerSecond
0x2316  ldstr    aTotalMemoryShr// "Total Memory Shrink Notification"
0x231b  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryShrinkNotificationCount
0x2320  ldstr    aMemoryShrinkNo// "Memory Shrink Notifications/Sec"
0x2325  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryShrinkNotificationPerSecond
0x232a  ldstr    aMemoryShrinkAm// "Memory Shrink Amount"
0x232f  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryShrinkAmount
0x2334  ldstr    aMemoryPressure// "Memory Pressure State"
0x2339  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryPressureLevel
0x233e  ldstr    aActiveDatabase// "Active Database Connections"
0x2343  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::SqlConnections
0x2348  ldstr    aActiveDatasour// "Active Datasource Connections"
0x234d  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ProcessingDatasourceConnections
0x2352  ldstr    aTotalDataSourc// "Total Data Source connection failures"
0x2357  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalDataSourceConnectionFailures
0x235c  ldstr    aActiveThreads// "Active Threads"
0x2361  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ReportServerActiveThreads
0x2366  ldstr    aTimeInProcessi// "Time in Processing"
0x236b  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInProcessingName
0x2370  ldstr    aTimeInRenderin// "Time in Rendering"
0x2375  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInRenderingName
0x237a  ldstr    aTimeInDataSour// "Time in data source access"
0x237f  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInDatasourceAccessName
0x2384  ldstr    aTimeInDatabase// "Time in database"
0x2389  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInDatabaseName
0x238e  ldstr    aTimeCompressin// "Time compressing"
0x2393  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInCompressionName
0x2398  ldstr    aTimeUncompress// "Time uncompressing"
0x239d  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInUncompressionName
0x23a2  ldstr    aRequestTime// "Request time"
0x23a7  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::RequestTimeName
0x23ac  ldstr    aRowCount// "Row count"
0x23b1  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::RowCountName
0x23b6  ldstr    aByteCount// "Byte count"
0x23bb  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ByteCountName
0x23c0  ldstr    aTimeBetweenFin// "Time between Finish calls"
0x23c5  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeBetweenFinishName
0x23ca  ldstr    aTimeWaitingOnT// "Time waiting on the next stream"
0x23cf  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::WaitOnNextStreamName
0x23d4  ldstr    aSnapshotCompre// "Snapshot compression ratio"
0x23d9  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::SnapshotCompressionRatioName
0x23de  ldstr    aSnapshotBuffer// "Snapshot buffering ratio"
0x23e3  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::SnapshotBufferingRatioName
0x23e8  ldstr    aTotalAppDomain// "Total App Domain Recycles"
0x23ed  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::AppDomainRecycles
0x23f2  ldstr    aTotalDeliverie// "Total Deliveries"
0x23f7  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::DeliveryCountStr
0x23fc  ldstr    aDeliversSec// "Delivers/Sec"
0x2401  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::DeliveriesPerSecond
0x2406  ldstr    aTotalEvents// "Total Events"
0x240b  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::EventHandleCount
0x2410  ldstr    aEventsSec// "Events/Sec"
0x2415  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::EventsPerSecond
0x241a  ldstr    aTotalSnapshotU// "Total Snapshot Updates"
0x241f  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::SnapshotUpdates
0x2424  ldstr    aSnapshotUpdate// "Snapshot Updates/Sec"
0x2429  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ShapshotUpdatesPerSecond
0x242e  ldstr    aTotalCacheFlus// "Total Cache Flushes"
0x2433  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::CacheFlushCount
0x2438  ldstr    aCacheFlushesSe// "Cache Flushes/Sec"
0x243d  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::CacheFlushPerSecond
0x2442  ldstr    aAlertingEventQ// "Alerting: event queue length"
0x2447  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::AlertingQueueSize
0x244c  ldstr    aAlertingEvents// "Alerting: events processed - FireAlert"
0x2451  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::FireAlertEventsProcessed
0x2456  ldstr    aAlertingEvents_0// "Alerting: events processed - FireSchedu"...
0x245b  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::FireScheduleEventsProcessed
0x2460  ldstr    aAlertingEvents_1// "Alerting: events processed - CreateSche"...
0x2465  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::CreateScheduleEventsProcessed
0x246a  ldstr    aAlertingEvents_2// "Alerting: events processed - UpdateSche"...
0x246f  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::UpdateScheduleEventsProcessed
0x2474  ldstr    aAlertingEvents_3// "Alerting: events processed - DeleteSche"...
0x2479  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::DeleteScheduleEventsProcessed
0x247e  ldstr    aAlertingEvents_4// "Alerting: events processed - GenerateAl"...
0x2483  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::GenerateAlertEventsProcessed
0x2488  ldstr    aAlertingEvents_5// "Alerting: events processed - DeliverAle"...
0x248d  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::DeliverAlertEventsProcessed
0x2492  ldnull
0x2493  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x2498  ldnull
0x2499  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x249e  ldnull
0x249f  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersDefault
0x24a4  ldnull
0x24a5  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersAll
0x24aa  ldnull
0x24ab  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_sharepointServicePerfCounters
0x24b0  ret
```
