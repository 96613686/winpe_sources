# Microsoft.ReportingServices.Library.ServiceController::StartTimers

- ea: `0x4fd80`
- end: `0x4ffc5`
- name: `Microsoft.ReportingServices.Library.ServiceController::StartTimers`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x506e0`

## callees

- `0xbf50`
- `0xc320`
- `0xfd60`
- `0xfe80`
- `0xff40`
- `0x4fd80`
- `0x50030`
- `0x66c10`

## string_xrefs

- `0x4fdbc`: `Database Cleanup (NT Service)`
- `0x4fef3`: `Username refresh based on the SID stored in the database`
- `0x4ff2c`: `Update Policies`
- `0x4ff99`: `Memory stats update`

## pseudocode

```c

```

## disassembly

```asm
0x4fd80  ldarg.0
0x4fd81  ldfld    bool Microsoft.ReportingServices.Library.ServiceController::m_startThreadExitStarted
0x4fd86  brfalse.s loc_4FD89
0x4fd88  ret
0x4fd89  ldarg.0
0x4fd8a  ldfld    object Microsoft.ReportingServices.Library.ServiceController::m_timersSync
0x4fd8f  stloc.0
0x4fd90  ldc.i4.0
0x4fd91  stloc.1
0x4fd92  ldloc.0
0x4fd93  ldloca.s 1
0x4fd95  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x4fd9a  newobj   instance void Microsoft.ReportingServices.Library.DatabaseCleanupTimer::.ctor()
0x4fd9f  stloc.2
0x4fda0  ldarg.0
0x4fda1  ldloc.2
0x4fda2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4fda7  call     instance bool Microsoft.ReportingServices.Library.ServiceController::FoundTimer(class [mscorlib]System.Type timerType)
0x4fdac  brtrue.s loc_4FDD2
0x4fdae  ldloc.2
0x4fdaf  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4fdb4  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_CleanupCycleMinutes()
0x4fdb9  ldc.i4.s 0x3C
0x4fdbb  mul
0x4fdbc  ldstr    aDatabaseCleanu_0// "Database Cleanup (NT Service)"
0x4fdc1  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase::Start(int32, string)
0x4fdc6  ldarg.0
0x4fdc7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase> Microsoft.ReportingServices.Library.ServiceController::m_timers
0x4fdcc  ldloc.2
0x4fdcd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase>::Add(var<u1>)
0x4fdd2  leave.s  loc_4FDDE
0x4fdd4  ldloc.1
0x4fdd5  brfalse.s loc_4FDDD
0x4fdd7  ldloc.0
0x4fdd8  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x4fddd  endfinally
0x4fdde  ldarg.0
0x4fddf  ldfld    bool Microsoft.ReportingServices.Library.ServiceController::m_startThreadExitStarted
0x4fde4  brfalse.s loc_4FDE7
0x4fde6  ret
0x4fde7  ldarg.0
0x4fde8  ldfld    bool Microsoft.ReportingServices.Library.ServiceController::m_startThreadExitStarted
0x4fded  brfalse.s loc_4FDF0
0x4fdef  ret
0x4fdf0  ldarg.0
0x4fdf1  ldfld    object Microsoft.ReportingServices.Library.ServiceController::m_timersSync
0x4fdf6  stloc.0
0x4fdf7  ldc.i4.0
0x4fdf8  stloc.1
0x4fdf9  ldloc.0
0x4fdfa  ldloca.s 1
0x4fdfc  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x4fe01  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningRequestsScavenger::.ctor()
0x4fe06  stloc.3
0x4fe07  ldarg.0
0x4fe08  ldloc.3
0x4fe09  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4fe0e  call     instance bool Microsoft.ReportingServices.Library.ServiceController::FoundTimer(class [mscorlib]System.Type timerType)
0x4fe13  brtrue.s loc_4FE36
0x4fe15  ldloc.3
0x4fe16  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4fe1b  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_RunningRequestsScavengerCycle()
0x4fe20  ldstr    aRunningRequest// "Running Requests Scavenger"
0x4fe25  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase::Start(int32, string)
0x4fe2a  ldarg.0
0x4fe2b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase> Microsoft.ReportingServices.Library.ServiceController::m_timers
0x4fe30  ldloc.3
0x4fe31  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase>::Add(var<u1>)
0x4fe36  ldarg.0
0x4fe37  ldfld    bool Microsoft.ReportingServices.Library.ServiceController::m_startThreadExitStarted
0x4fe3c  brfalse.s loc_4FE43
0x4fe3e  leave    loc_4FFC4
0x4fe43  newobj   instance void Microsoft.ReportingServices.Library.RunningJobDbTimer::.ctor()
0x4fe48  stloc.s  4
0x4fe4a  ldarg.0
0x4fe4b  ldloc.s  4
0x4fe4d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4fe52  call     instance bool Microsoft.ReportingServices.Library.ServiceController::FoundTimer(class [mscorlib]System.Type timerType)
0x4fe57  brtrue.s loc_4FE7C
0x4fe59  ldloc.s  4
0x4fe5b  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4fe60  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_RunningRequestsDBCycle()
0x4fe65  ldstr    aRunningRequest_0// "Running Requests DB"
0x4fe6a  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase::Start(int32, string)
0x4fe6f  ldarg.0
0x4fe70  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase> Microsoft.ReportingServices.Library.ServiceController::m_timers
0x4fe75  ldloc.s  4
0x4fe77  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase>::Add(var<u1>)
0x4fe7c  ldarg.0
0x4fe7d  ldfld    bool Microsoft.ReportingServices.Library.ServiceController::m_startThreadExitStarted
0x4fe82  brfalse.s loc_4FE89
0x4fe84  leave    loc_4FFC4
0x4fe89  newobj   instance void Microsoft.ReportingServices.Library.ExecutionLogEntryExpirer::.ctor()
0x4fe8e  stloc.s  5
0x4fe90  ldarg.0
0x4fe91  ldloc.s  5
0x4fe93  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4fe98  call     instance bool Microsoft.ReportingServices.Library.ServiceController::FoundTimer(class [mscorlib]System.Type timerType)
0x4fe9d  brtrue.s loc_4FEC2
0x4fe9f  ldloc.s  5
0x4fea1  call     int32 Microsoft.ReportingServices.Library.ExecutionLogEntryExpirer::get_SecondsToNextEvent()
0x4fea6  ldc.i4   0x15180
0x4feab  ldstr    aExecutionLogEn// "Execution Log Entry Expiration"
0x4feb0  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase::Start(int32, int32, string)
0x4feb5  ldarg.0
0x4feb6  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase> Microsoft.ReportingServices.Library.ServiceController::m_timers
0x4febb  ldloc.s  5
0x4febd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase>::Add(var<u1>)
0x4fec2  newobj   instance void Microsoft.ReportingServices.Library.DatabaseUsernameSIDRefreshTimer::.ctor()
0x4fec7  stloc.s  6
0x4fec9  ldarg.0
0x4feca  ldloc.s  6
0x4fecc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4fed1  call     instance bool Microsoft.ReportingServices.Library.ServiceController::FoundTimer(class [mscorlib]System.Type timerType)
0x4fed6  brtrue.s loc_4FF0A
0x4fed8  ldloc.s  6
0x4feda  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4fedf  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_UsernameSIDRefreshMinutesParam()
0x4fee4  conv.r8
0x4fee5  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x4feea  stloc.s  8
0x4feec  ldloca.s 8
0x4feee  call     instance int32 [mscorlib]System.TimeSpan::get_Seconds()
0x4fef3  ldstr    aUsernameRefres// "Username refresh based on the SID store"...
0x4fef8  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase::Start(int32, string)
0x4fefd  ldarg.0
0x4fefe  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase> Microsoft.ReportingServices.Library.ServiceController::m_timers
0x4ff03  ldloc.s  6
0x4ff05  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase>::Add(var<u1>)
0x4ff0a  newobj   instance void Microsoft.ReportingServices.Library.UpdatePoliciesTimer::.ctor()
0x4ff0f  stloc.s  7
0x4ff11  ldarg.0
0x4ff12  ldloc.s  6
0x4ff14  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4ff19  call     instance bool Microsoft.ReportingServices.Library.ServiceController::FoundTimer(class [mscorlib]System.Type timerType)
0x4ff1e  brtrue.s loc_4FF43
0x4ff20  ldloc.s  7
0x4ff22  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4ff27  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_UpdatePolicySecondsParam()
0x4ff2c  ldstr    aUpdatePolicies// "Update Policies"
0x4ff31  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase::Start(int32, string)
0x4ff36  ldarg.0
0x4ff37  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase> Microsoft.ReportingServices.Library.ServiceController::m_timers
0x4ff3c  ldloc.s  7
0x4ff3e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase>::Add(var<u1>)
0x4ff43  leave.s  loc_4FF4F
0x4ff45  ldloc.1
0x4ff46  brfalse.s loc_4FF4E
0x4ff48  ldloc.0
0x4ff49  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x4ff4e  endfinally
0x4ff4f  ldarg.0
0x4ff50  ldfld    bool Microsoft.ReportingServices.Library.ServiceController::m_startThreadExitStarted
0x4ff55  brfalse.s loc_4FF58
0x4ff57  ret
0x4ff58  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4ff5d  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x4ff62  ldc.i4.s 0x13
0x4ff64  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Sku::IsFeatureEnabled(string, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures)
0x4ff69  brtrue.s loc_4FFBC
0x4ff6b  ldarg.0
0x4ff6c  ldfld    object Microsoft.ReportingServices.Library.ServiceController::m_timersSync
0x4ff71  stloc.0
0x4ff72  ldc.i4.0
0x4ff73  stloc.1
0x4ff74  ldloc.0
0x4ff75  ldloca.s 1
0x4ff77  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x4ff7c  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.MemoryStatsTimer::.ctor()
0x4ff81  stloc.s  9
0x4ff83  ldarg.0
0x4ff84  ldloc.s  9
0x4ff86  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4ff8b  call     instance bool Microsoft.ReportingServices.Library.ServiceController::FoundTimer(class [mscorlib]System.Type timerType)
0x4ff90  brtrue.s loc_4FFB0
0x4ff92  ldloc.s  9
0x4ff94  call     int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ResourceUtilities::get_UpdateStatsTimerCycle()
0x4ff99  ldstr    aMemoryStatsUpd// "Memory stats update"
0x4ff9e  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase::Start(int32, string)
0x4ffa3  ldarg.0
0x4ffa4  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase> Microsoft.ReportingServices.Library.ServiceController::m_timers
0x4ffa9  ldloc.s  9
0x4ffab  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase>::Add(var<u1>)
0x4ffb0  leave.s  loc_4FFBC
0x4ffb2  ldloc.1
0x4ffb3  brfalse.s loc_4FFBB
0x4ffb5  ldloc.0
0x4ffb6  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x4ffbb  endfinally
0x4ffbc  ldarg.0
0x4ffbd  ldfld    bool Microsoft.ReportingServices.Library.ServiceController::m_startThreadExitStarted
0x4ffc2  pop
0x4ffc3  ret
0x4ffc4  ret
```
