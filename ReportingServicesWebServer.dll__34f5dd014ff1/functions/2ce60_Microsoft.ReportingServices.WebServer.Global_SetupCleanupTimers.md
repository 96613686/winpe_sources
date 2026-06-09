# Microsoft.ReportingServices.WebServer.Global::SetupCleanupTimers

- ea: `0x2ce60`
- end: `0x2ceed`
- name: `Microsoft.ReportingServices.WebServer.Global::SetupCleanupTimers`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2c510`

## callees

- `0x2ce60`

## string_xrefs

- `0x2cee2`: `Memory stats update`

## pseudocode

```c

```

## disassembly

```asm
0x2ce60  ldsfld   class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningRequestsScavenger Microsoft.ReportingServices.WebServer.Global::m_requestsScavenger
0x2ce65  brtrue.s loc_2CE8A
0x2ce67  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningRequestsScavenger::.ctor()
0x2ce6c  stsfld   class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningRequestsScavenger Microsoft.ReportingServices.WebServer.Global::m_requestsScavenger
0x2ce71  ldsfld   class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningRequestsScavenger Microsoft.ReportingServices.WebServer.Global::m_requestsScavenger
0x2ce76  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x2ce7b  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_RunningRequestsScavengerCycle()
0x2ce80  ldstr    aRunningRequest// "Running Requests Scavenger"
0x2ce85  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase::Start(int32, string)
0x2ce8a  ldsfld   class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RunningJobDbTimer Microsoft.ReportingServices.WebServer.Global::m_requestsDbTimer
0x2ce8f  brtrue.s loc_2CEB4
0x2ce91  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RunningJobDbTimer::.ctor()
0x2ce96  stsfld   class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RunningJobDbTimer Microsoft.ReportingServices.WebServer.Global::m_requestsDbTimer
0x2ce9b  ldsfld   class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RunningJobDbTimer Microsoft.ReportingServices.WebServer.Global::m_requestsDbTimer
0x2cea0  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x2cea5  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_RunningRequestsDBCycle()
0x2ceaa  ldstr    aRunningRequest_0// "Running Requests DB"
0x2ceaf  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase::Start(int32, string)
0x2ceb4  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x2ceb9  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x2cebe  ldc.i4.s 0x13
0x2cec0  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Sku::IsFeatureEnabled(string, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures)
0x2cec5  brtrue.s loc_2CEEC
0x2cec7  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.MemoryStatsTimer Microsoft.ReportingServices.WebServer.Global::m_memStatsTimer
0x2cecc  brtrue.s loc_2CEEC
0x2cece  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.MemoryStatsTimer::.ctor()
0x2ced3  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.MemoryStatsTimer Microsoft.ReportingServices.WebServer.Global::m_memStatsTimer
0x2ced8  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.MemoryStatsTimer Microsoft.ReportingServices.WebServer.Global::m_memStatsTimer
0x2cedd  call     int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ResourceUtilities::get_UpdateStatsTimerCycle()
0x2cee2  ldstr    aMemoryStatsUpd// "Memory stats update"
0x2cee7  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase::Start(int32, string)
0x2ceec  ret
```
