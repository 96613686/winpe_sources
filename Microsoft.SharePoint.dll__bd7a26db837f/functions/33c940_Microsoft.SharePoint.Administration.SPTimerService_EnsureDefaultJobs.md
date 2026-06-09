# Microsoft.SharePoint.Administration.SPTimerService::EnsureDefaultJobs

- ea: `0x33c940`
- end: `0x33d07d`
- name: `Microsoft.SharePoint.Administration.SPTimerService::EnsureDefaultJobs`
- size: `1853`
- prototype: ``
- caller_count: `5`
- callee_count: `48`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x2a3890`
- `0xa6a4f0`
- `0xa6bf90`
- `0xa6cba0`
- `0xa6cd00`

## callees

- `0x1c8850`
- `0x1c89b0`
- `0x1c89e0`
- `0x1c8a20`
- `0x1c91a0`
- `0x1c9d20`
- `0x1c9d50`
- `0x1c9f00`
- `0x1c9f10`
- `0x1ca3b0`
- `0x1ca3c0`
- `0x1ca7c0`
- `0x1cc3c0`
- `0x201990`
- `0x202c80`
- `0x2035a0`
- `0x204990`
- `0x2049c0`
- `0x2095b0`
- `0x20fd00`
- `0x222b20`
- `0x259c60`
- `0x259de0`
- `0x259e80`
- `0x27f100`
- `0x29c2f0`
- `0x2c9270`
- `0x2de7d0`
- `0x2f83c0`
- `0x30f630`
- `0x312f30`
- `0x3164e0`
- `0x3358d0`
- `0x339eb0`
- `0x339ec0`
- `0x339f20`
- `0x33c940`
- `0x33d080`
- `0x33d210`
- `0x37d110`
- `0x472c20`
- `0x584fb0`
- `0x5870d0`
- `0x587100`
- `0x587120`
- `0x6c9890`
- `0x93dab0`
- `0x957470`

## string_xrefs

- `0x33cc45`: `job-app-installation`
- `0x33cc58`: `job-app-installation`
- `0x33d03d`: `job-app-installation`
- `0x33c950`: `job-config-refresh`
- `0x33c969`: `job-config-refresh`
- `0x33c9c3`: `job-config-collection-cache-refresh`
- `0x33c9dc`: `job-config-collection-cache-refresh`
- `0x33ca0e`: `job-config-collection-full-cache-refresh`
- `0x33ca27`: `job-config-collection-full-cache-refresh`
- `0x33caa5`: `job-extensionmap-refresh`
- `0x33cab7`: `job-extensionmap-refresh`
- `0x33cb33`: `job-delete-job-history`
- `0x33cb4e`: `job-delete-job-history`
- `0x33ce99`: `job-config-machine-key-rotation`
- `0x33ceab`: `job-config-machine-key-rotation`
- `0x33cfed`: `Creating the SQLServiceConfigurationCheckTimerJob.`

## pseudocode

```c

```

## disassembly

```asm
0x33c940  ldarg.0
0x33c941  call     instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x33c946  ldtoken  Microsoft.SharePoint.Administration.SPConfigurationRefreshJobDefinition
0x33c94b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33c950  ldstr    aJobConfigRefre// "job-config-refresh"
0x33c955  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33c95a  isinst   Microsoft.SharePoint.Administration.SPConfigurationRefreshJobDefinition
0x33c95f  stloc.0
0x33c960  ldloc.0
0x33c961  ldnull
0x33c962  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33c967  brfalse.s loc_33C995
0x33c969  ldstr    aJobConfigRefre// "job-config-refresh"
0x33c96e  ldarg.0
0x33c96f  newobj   instance void Microsoft.SharePoint.Administration.SPConfigurationRefreshJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPTimerService service)
0x33c974  stloc.0
0x33c975  ldloc.0
0x33c976  ldstr    aEvery15Seconds// "every 15 seconds"
0x33c97b  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33c980  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33c985  ldloc.0
0x33c986  ldc.i4.s 0xA
0x33c988  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Flags(int32 value)
0x33c98d  ldloc.0
0x33c98e  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33c993  br.s     loc_33C9B3
0x33c995  ldloc.0
0x33c996  callvirt instance int32 Microsoft.SharePoint.Administration.SPJobDefinition::get_Flags()
0x33c99b  ldc.i4.8
0x33c99c  and
0x33c99d  brtrue.s loc_33C9B3
0x33c99f  ldloc.0
0x33c9a0  dup
0x33c9a1  callvirt instance int32 Microsoft.SharePoint.Administration.SPJobDefinition::get_Flags()
0x33c9a6  ldc.i4.8
0x33c9a7  or
0x33c9a8  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Flags(int32 value)
0x33c9ad  ldloc.0
0x33c9ae  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33c9b3  ldarg.0
0x33c9b4  call     instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x33c9b9  ldtoken  Microsoft.SharePoint.Administration.SPConfigurationCollectionCacheRefreshJobDefinition
0x33c9be  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33c9c3  ldstr    aJobConfigColle// "job-config-collection-cache-refresh"
0x33c9c8  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33c9cd  isinst   Microsoft.SharePoint.Administration.SPConfigurationCollectionCacheRefreshJobDefinition
0x33c9d2  stloc.1
0x33c9d3  ldloc.1
0x33c9d4  ldnull
0x33c9d5  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33c9da  brfalse.s loc_33C9FE
0x33c9dc  ldstr    aJobConfigColle// "job-config-collection-cache-refresh"
0x33c9e1  ldarg.0
0x33c9e2  newobj   instance void Microsoft.SharePoint.Administration.SPConfigurationCollectionCacheRefreshJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPTimerService service)
0x33c9e7  stloc.1
0x33c9e8  ldloc.1
0x33c9e9  ldstr    aHourlyBetween0// "hourly between 0 and 59"
0x33c9ee  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33c9f3  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33c9f8  ldloc.1
0x33c9f9  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33c9fe  ldarg.0
0x33c9ff  call     instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x33ca04  ldtoken  Microsoft.SharePoint.Administration.SPConfigurationCollectionFullCacheRefreshJobDefinition
0x33ca09  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33ca0e  ldstr    aJobConfigColle_0// "job-config-collection-full-cache-refres"...
0x33ca13  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33ca18  isinst   Microsoft.SharePoint.Administration.SPConfigurationCollectionFullCacheRefreshJobDefinition
0x33ca1d  stloc.2
0x33ca1e  ldloc.2
0x33ca1f  ldnull
0x33ca20  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33ca25  brfalse.s loc_33CA4B
0x33ca27  ldstr    aJobConfigColle_0// "job-config-collection-full-cache-refres"...
0x33ca2c  ldarg.0
0x33ca2d  newobj   instance void Microsoft.SharePoint.Administration.SPConfigurationCollectionFullCacheRefreshJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPTimerService service)
0x33ca32  stloc.2
0x33ca33  ldloc.2
0x33ca34  ldstr    aDailyBetween22_0// "daily between 22:00 and 02:00"
0x33ca39  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33ca3e  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33ca43  ldloc.2
0x33ca44  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33ca49  br.s     loc_33CA51
0x33ca4b  ldloc.2
0x33ca4c  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::RefreshScheduleOverride()
0x33ca51  ldarg.0
0x33ca52  call     instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x33ca57  ldtoken  Microsoft.SharePoint.Administration.SPSiteLookupRefreshJobDefinition
0x33ca5c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33ca61  ldstr    aJobSitelookupR// "job-sitelookup-refresh"
0x33ca66  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33ca6b  ldnull
0x33ca6c  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33ca71  brfalse.s loc_33CA95
0x33ca73  ldstr    aJobSitelookupR// "job-sitelookup-refresh"
0x33ca78  ldarg.0
0x33ca79  newobj   instance void Microsoft.SharePoint.Administration.SPSiteLookupRefreshJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPTimerService service)
0x33ca7e  stloc.3
0x33ca7f  ldloc.3
0x33ca80  ldstr    aEvery10Minutes// "every 10 minutes"
0x33ca85  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33ca8a  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33ca8f  ldloc.3
0x33ca90  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33ca95  ldarg.0
0x33ca96  call     instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x33ca9b  ldtoken  Microsoft.SharePoint.Administration.SPExtensionMapRefreshJobDefinition
0x33caa0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33caa5  ldstr    aJobExtensionma// "job-extensionmap-refresh"
0x33caaa  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33caaf  ldnull
0x33cab0  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33cab5  brfalse.s loc_33CADC
0x33cab7  ldstr    aJobExtensionma// "job-extensionmap-refresh"
0x33cabc  ldarg.0
0x33cabd  newobj   instance void Microsoft.SharePoint.Administration.SPExtensionMapRefreshJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPTimerService service)
0x33cac2  stloc.s  4
0x33cac4  ldloc.s  4
0x33cac6  ldstr    aEvery10Minutes// "every 10 minutes"
0x33cacb  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33cad0  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33cad5  ldloc.s  4
0x33cad7  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33cadc  ldarg.0
0x33cadd  call     instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x33cae2  ldtoken  Microsoft.SharePoint.Administration.SPSqmTimerJobDefinition
0x33cae7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33caec  ldstr    aJobCeipDatacol// "job-ceip-datacollection"
0x33caf1  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33caf6  ldnull
0x33caf7  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33cafc  brfalse.s loc_33CB23
0x33cafe  ldstr    aJobCeipDatacol// "job-ceip-datacollection"
0x33cb03  ldarg.0
0x33cb04  newobj   instance void Microsoft.SharePoint.Administration.SPSqmTimerJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPService service)
0x33cb09  stloc.s  5
0x33cb0b  ldloc.s  5
0x33cb0d  ldstr    aDailyBetween04// "daily between 04:31:00 and 04:33:00"
0x33cb12  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33cb17  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33cb1c  ldloc.s  5
0x33cb1e  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33cb23  ldarg.0
0x33cb24  call     instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x33cb29  ldtoken  Microsoft.SharePoint.Administration.SPDeleteJobHistoryJobDefinition
0x33cb2e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33cb33  ldstr    aJobDeleteJobHi// "job-delete-job-history"
0x33cb38  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33cb3d  isinst   Microsoft.SharePoint.Administration.SPDeleteJobHistoryJobDefinition
0x33cb42  stloc.s  6
0x33cb44  ldloc.s  6
0x33cb46  ldnull
0x33cb47  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33cb4c  brfalse.s loc_33CB98
0x33cb4e  ldstr    aJobDeleteJobHi// "job-delete-job-history"
0x33cb53  ldarg.0
0x33cb54  newobj   instance void Microsoft.SharePoint.Administration.SPDeleteJobHistoryJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPService service)
0x33cb59  stloc.s  6
0x33cb5b  call     bool Microsoft.SharePoint.SPGlobal::get_IsSPO()
0x33cb60  brfalse.s loc_33CB75
0x33cb62  ldloc.s  6
0x33cb64  ldstr    aHourlyBetween0// "hourly between 0 and 59"
0x33cb69  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33cb6e  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33cb73  br.s     loc_33CB8F
0x33cb75  ldloc.s  6
0x33cb77  ldc.i4.0
0x33cb78  conv.i8
0x33cb79  callvirt instance void Microsoft.SharePoint.Administration.SPDeleteJobHistoryJobDefinition::set_TableRowCountThreshold(int64 value)
0x33cb7e  ldloc.s  6
0x33cb80  ldstr    aDailyBetween04_0// "daily between 04:41:00 and 04:43:00"
0x33cb85  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33cb8a  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33cb8f  ldloc.s  6
0x33cb91  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33cb96  br.s     loc_33CBEE
0x33cb98  call     bool Microsoft.SharePoint.SPGlobal::get_IsSPO()
0x33cb9d  brfalse.s loc_33CBCB
0x33cb9f  ldloc.s  6
0x33cba1  callvirt instance class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.Administration.SPJobDefinition::get_Schedule()
0x33cba6  ldstr    aHourlyBetween0// "hourly between 0 and 59"
0x33cbab  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33cbb0  beq.s    loc_33CBCB
0x33cbb2  ldloc.s  6
0x33cbb4  ldstr    aHourlyBetween0// "hourly between 0 and 59"
0x33cbb9  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33cbbe  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33cbc3  ldloc.s  6
0x33cbc5  ldc.i4.1
0x33cbc6  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update(bool ensure)
0x33cbcb  call     bool Microsoft.SharePoint.SPGlobal::get_IsSPO()
0x33cbd0  brtrue.s loc_33CBEE
0x33cbd2  ldloc.s  6
0x33cbd4  callvirt instance int64 Microsoft.SharePoint.Administration.SPDeleteJobHistoryJobDefinition::get_TableRowCountThreshold()
0x33cbd9  ldc.i4.0
0x33cbda  conv.i8
0x33cbdb  ble.s    loc_33CBEE
0x33cbdd  ldloc.s  6
0x33cbdf  ldc.i4.0
0x33cbe0  conv.i8
0x33cbe1  callvirt instance void Microsoft.SharePoint.Administration.SPDeleteJobHistoryJobDefinition::set_TableRowCountThreshold(int64 value)
0x33cbe6  ldloc.s  6
0x33cbe8  ldc.i4.1
0x33cbe9  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update(bool ensure)
0x33cbee  ldarg.0
0x33cbef  call     instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x33cbf4  ldtoken  Microsoft.SharePoint.Administration.SPPasswordManagementJobDefinition
0x33cbf9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33cbfe  ldstr    aJobPasswordMan// "job-password-management"
0x33cc03  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33cc08  ldnull
0x33cc09  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33cc0e  brfalse.s loc_33CC35
0x33cc10  ldstr    aJobPasswordMan// "job-password-management"
0x33cc15  ldarg.0
0x33cc16  newobj   instance void Microsoft.SharePoint.Administration.SPPasswordManagementJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPService service)
0x33cc1b  stloc.s  7
0x33cc1d  ldloc.s  7
0x33cc1f  ldstr    aDailyBetween00_1// "daily between 00:31:00 and 00:33:00"
0x33cc24  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33cc29  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33cc2e  ldloc.s  7
0x33cc30  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33cc35  ldarg.0
0x33cc36  call     instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x33cc3b  ldtoken  Microsoft.SharePoint.Administration.SPAppInstallationJobDefinition
0x33cc40  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33cc45  ldstr    aJobAppInstalla// "job-app-installation"
0x33cc4a  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33cc4f  ldnull
0x33cc50  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33cc55  brfalse.s loc_33CC7C
0x33cc57  ldarg.0
0x33cc58  ldstr    aJobAppInstalla// "job-app-installation"
0x33cc5d  newobj   instance void Microsoft.SharePoint.Administration.SPAppInstallationJobDefinition::.ctor(class Microsoft.SharePoint.Administration.SPService parentService, string jobName)
0x33cc62  stloc.s  8
0x33cc64  ldloc.s  8
0x33cc66  ldstr    aEvery5Minutes// "every 5 minutes"
0x33cc6b  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33cc70  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33cc75  ldloc.s  8
0x33cc77  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33cc7c  ldarg.0
0x33cc7d  call     instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x33cc82  ldtoken  Microsoft.SharePoint.Administration.SPAppStatisticsProviderJobDefinition
0x33cc87  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33cc8c  call     string Microsoft.SharePoint.Administration.SPAppStatisticsProviderJobDefinition::get_DefaultName()
0x33cc91  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33cc96  ldnull
0x33cc97  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33cc9c  brfalse.s loc_33CCAD
0x33cc9e  ldarg.0
0x33cc9f  newobj   instance void Microsoft.SharePoint.Administration.SPAppStatisticsProviderJobDefinition::.ctor(class Microsoft.SharePoint.Administration.SPService service)
0x33cca4  stloc.s  9
0x33cca6  ldloc.s  9
0x33cca8  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33ccad  ldarg.0
0x33ccae  call     instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x33ccb3  ldtoken  Microsoft.SharePoint.Administration.SPAutoHostedAppInstanceCounterJobDefinition
0x33ccb8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33ccbd  ldstr    aJobAutohostedA// "job-autohosted-appinstance-counter"
0x33ccc2  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33ccc7  ldnull
0x33ccc8  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33cccd  brfalse.s loc_33CCF4
0x33cccf  ldarg.0
0x33ccd0  ldstr    aJobAutohostedA// "job-autohosted-appinstance-counter"
0x33ccd5  newobj   instance void Microsoft.SharePoint.Administration.SPAutoHostedAppInstanceCounterJobDefinition::.ctor(class Microsoft.SharePoint.Administration.SPService parentService, string jobName)
0x33ccda  stloc.s  0xA
0x33ccdc  ldloc.s  0xA
0x33ccde  ldstr    aWeeklyAtSun050// "weekly at sun 05:00:00"
0x33cce3  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33cce8  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33cced  ldloc.s  0xA
0x33ccef  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33ccf4  ldarg.0
0x33ccf5  call     instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x33ccfa  ldtoken  Microsoft.SharePoint.Administration.SPProductVersionJobDefinition
0x33ccff  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33cd04  ldsfld   string Microsoft.SharePoint.Administration.SPProductVersionJobDefinition::RegularName
0x33cd09  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33cd0e  ldnull
0x33cd0f  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33cd14  brfalse.s loc_33CD2A
0x33cd16  ldarg.0
0x33cd17  call     instance class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPPersistedObject::get_Farm()
0x33cd1c  newobj   instance void Microsoft.SharePoint.Administration.SPProductVersionJobDefinition::.ctor(class Microsoft.SharePoint.Administration.SPFarm farm)
0x33cd21  stloc.s  0xB
0x33cd23  ldloc.s  0xB
0x33cd25  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33cd2a  ldarg.0
0x33cd2b  call     instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x33cd30  ldtoken  Microsoft.SharePoint.Administration.SPTimerRecycleJobDefinition
0x33cd35  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33cd3a  ldstr    aJobTimerRecycl// "job-timer-recycle"
0x33cd3f  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33cd44  isinst   Microsoft.SharePoint.Administration.SPTimerRecycleJobDefinition
0x33cd49  stloc.s  0xC
0x33cd4b  ldloc.s  0xC
  ... truncated ...
```
