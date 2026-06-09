# Microsoft.ReportingServices.Common.RSPerfCounterInfo::.cctor

- ea: `0x76f00`
- end: `0x77181`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterInfo::.cctor`
- size: `641`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x76f28`: `Total Rejected Threads`
- `0x76f50`: `Total Cache Hits`
- `0x76f5a`: `Cache Hits/Sec`
- `0x76f64`: `Total Cache Misses`
- `0x76f6e`: `Cache Misses/Sec`
- `0x76f78`: `Percent Reports from cache`
- `0x76f96`: `Total Memory Cache Hits`
- `0x76fa0`: `Memory Cache Hits/Sec`
- `0x76faa`: `Total Memory Cache Misses`
- `0x76fb4`: `Memory Cache Miss/Sec`
- `0x76fbe`: `Total Cache Hits (Semantic Models)`
- `0x76fc8`: `Cache Hits/Sec (Semantic Models)`
- `0x76fd2`: `Total Cache Misses (Semantic Models)`
- `0x76fdc`: `Cache Misses/Sec (Semantic Models)`
- `0x76ffa`: `Memory Shrink Amount`
- `0x7702c`: `Active Threads`
- `0x7704a`: `Time in data source access`
- `0x7705e`: `Time compressing`
- `0x77068`: `Time uncompressing`
- `0x770a4`: `Snapshot compression ratio`
- `0x770ea`: `Total Snapshot Updates`
- `0x770f4`: `Snapshot Updates/Sec`
- `0x770fe`: `Total Cache Flushes`
- `0x77108`: `Cache Flushes/Sec`
- `0x77130`: `Alerting: events processed - CreateSchedule`
- `0x7713a`: `Alerting: events processed - UpdateSchedule`
- `0x77144`: `Alerting: events processed - DeleteSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x76f00  ldstr    aReportRequests// "Report Requests"
0x76f05  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ReportRequests
0x76f0a  ldstr    aTotalReportsEx// "Total Reports Executed"
0x76f0f  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ExecutionCount
0x76f14  ldstr    aReportsExecute// "Reports Executed/Sec"
0x76f19  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ExecutionsPerSecond
0x76f1e  ldstr    aTotalProcessin// "Total Processing Failures"
0x76f23  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ReportProcessingErrorCount
0x76f28  ldstr    aTotalRejectedT// "Total Rejected Threads"
0x76f2d  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::RejectedThreads
0x76f32  ldstr    aActiveSessions// "Active Sessions"
0x76f37  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ActiveSessionsCount
0x76f3c  ldstr    aFirstSessionRe// "First Session Requests/Sec"
0x76f41  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::FirstSessionRequests
0x76f46  ldstr    aNextSessionReq// "Next Session Requests/Sec"
0x76f4b  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::NextSessionRequests
0x76f50  ldstr    aTotalCacheHits// "Total Cache Hits"
0x76f55  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalCacheHitsCount
0x76f5a  ldstr    aCacheHitsSec// "Cache Hits/Sec"
0x76f5f  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalCacheHitsPerSecond
0x76f64  ldstr    aTotalCacheMiss// "Total Cache Misses"
0x76f69  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalCacheMissCount
0x76f6e  ldstr    aCacheMissesSec// "Cache Misses/Sec"
0x76f73  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalCacheMissPerSecond
0x76f78  ldstr    aPercentReports// "Percent Reports from cache"
0x76f7d  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::RequestFromCachePercent
0x76f82  ldstr    aTotalRequests// "Total Requests"
0x76f87  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalRequestCount
0x76f8c  ldstr    aRequestsSec// "Requests/Sec"
0x76f91  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalRequestPerSecond
0x76f96  ldstr    aTotalMemoryCac// "Total Memory Cache Hits"
0x76f9b  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalMemoryCacheHitsCount
0x76fa0  ldstr    aMemoryCacheHit// "Memory Cache Hits/Sec"
0x76fa5  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryCacheHitsPerSecond
0x76faa  ldstr    aTotalMemoryCac_0// "Total Memory Cache Misses"
0x76faf  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalMemoryCacheMissCount
0x76fb4  ldstr    aMemoryCacheMis// "Memory Cache Miss/Sec"
0x76fb9  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryCacheMissPerSecond
0x76fbe  ldstr    aTotalCacheHits_0// "Total Cache Hits (Semantic Models)"
0x76fc3  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ModelsTotalCacheHitsCount
0x76fc8  ldstr    aCacheHitsSecSe// "Cache Hits/Sec (Semantic Models)"
0x76fcd  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ModelsTotalCacheHitsPerSecond
0x76fd2  ldstr    aTotalCacheMiss_0// "Total Cache Misses (Semantic Models)"
0x76fd7  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ModelsTotalCacheMissCount
0x76fdc  ldstr    aCacheMissesSec_0// "Cache Misses/Sec (Semantic Models)"
0x76fe1  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ModelsTotalCacheMissPerSecond
0x76fe6  ldstr    aTotalMemoryShr// "Total Memory Shrink Notification"
0x76feb  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryShrinkNotificationCount
0x76ff0  ldstr    aMemoryShrinkNo// "Memory Shrink Notifications/Sec"
0x76ff5  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryShrinkNotificationPerSecond
0x76ffa  ldstr    aMemoryShrinkAm// "Memory Shrink Amount"
0x76fff  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryShrinkAmount
0x77004  ldstr    aMemoryPressure// "Memory Pressure State"
0x77009  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::MemoryPressureLevel
0x7700e  ldstr    aActiveDatabase// "Active Database Connections"
0x77013  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::SqlConnections
0x77018  ldstr    aActiveDatasour// "Active Datasource Connections"
0x7701d  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ProcessingDatasourceConnections
0x77022  ldstr    aTotalDataSourc// "Total Data Source connection failures"
0x77027  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TotalDataSourceConnectionFailures
0x7702c  ldstr    aActiveThreads// "Active Threads"
0x77031  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ReportServerActiveThreads
0x77036  ldstr    aTimeInProcessi// "Time in Processing"
0x7703b  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInProcessingName
0x77040  ldstr    aTimeInRenderin// "Time in Rendering"
0x77045  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInRenderingName
0x7704a  ldstr    aTimeInDataSour// "Time in data source access"
0x7704f  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInDatasourceAccessName
0x77054  ldstr    aTimeInDatabase// "Time in database"
0x77059  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInDatabaseName
0x7705e  ldstr    aTimeCompressin// "Time compressing"
0x77063  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInCompressionName
0x77068  ldstr    aTimeUncompress// "Time uncompressing"
0x7706d  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeInUncompressionName
0x77072  ldstr    aRequestTime// "Request time"
0x77077  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::RequestTimeName
0x7707c  ldstr    aRowCount// "Row count"
0x77081  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::RowCountName
0x77086  ldstr    aByteCount// "Byte count"
0x7708b  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ByteCountName
0x77090  ldstr    aTimeBetweenFin// "Time between Finish calls"
0x77095  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::TimeBetweenFinishName
0x7709a  ldstr    aTimeWaitingOnT// "Time waiting on the next stream"
0x7709f  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::WaitOnNextStreamName
0x770a4  ldstr    aSnapshotCompre// "Snapshot compression ratio"
0x770a9  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::SnapshotCompressionRatioName
0x770ae  ldstr    aSnapshotBuffer// "Snapshot buffering ratio"
0x770b3  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::SnapshotBufferingRatioName
0x770b8  ldstr    aTotalAppDomain// "Total App Domain Recycles"
0x770bd  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::AppDomainRecycles
0x770c2  ldstr    aTotalDeliverie// "Total Deliveries"
0x770c7  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::DeliveryCountStr
0x770cc  ldstr    aDeliversSec// "Delivers/Sec"
0x770d1  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::DeliveriesPerSecond
0x770d6  ldstr    aTotalEvents// "Total Events"
0x770db  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::EventHandleCount
0x770e0  ldstr    aEventsSec// "Events/Sec"
0x770e5  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::EventsPerSecond
0x770ea  ldstr    aTotalSnapshotU// "Total Snapshot Updates"
0x770ef  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::SnapshotUpdates
0x770f4  ldstr    aSnapshotUpdate// "Snapshot Updates/Sec"
0x770f9  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::ShapshotUpdatesPerSecond
0x770fe  ldstr    aTotalCacheFlus// "Total Cache Flushes"
0x77103  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::CacheFlushCount
0x77108  ldstr    aCacheFlushesSe// "Cache Flushes/Sec"
0x7710d  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::CacheFlushPerSecond
0x77112  ldstr    aAlertingEventQ// "Alerting: event queue length"
0x77117  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::AlertingQueueSize
0x7711c  ldstr    aAlertingEvents// "Alerting: events processed - FireAlert"
0x77121  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::FireAlertEventsProcessed
0x77126  ldstr    aAlertingEvents_0// "Alerting: events processed - FireSchedu"...
0x7712b  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::FireScheduleEventsProcessed
0x77130  ldstr    aAlertingEvents_1// "Alerting: events processed - CreateSche"...
0x77135  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::CreateScheduleEventsProcessed
0x7713a  ldstr    aAlertingEvents_2// "Alerting: events processed - UpdateSche"...
0x7713f  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::UpdateScheduleEventsProcessed
0x77144  ldstr    aAlertingEvents_3// "Alerting: events processed - DeleteSche"...
0x77149  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::DeleteScheduleEventsProcessed
0x7714e  ldstr    aAlertingEvents_4// "Alerting: events processed - GenerateAl"...
0x77153  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::GenerateAlertEventsProcessed
0x77158  ldstr    aAlertingEvents_5// "Alerting: events processed - DeliverAle"...
0x7715d  stsfld   string Microsoft.ReportingServices.Common.RSPerfCounterInfo::DeliverAlertEventsProcessed
0x77162  ldnull
0x77163  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersDefault
0x77168  ldnull
0x77169  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_webServicePerfCountersAll
0x7716e  ldnull
0x7716f  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersDefault
0x77174  ldnull
0x77175  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_winServicePerfCountersAll
0x7717a  ldnull
0x7717b  stsfld   class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::m_sharepointServicePerfCounters
0x77180  ret
```
