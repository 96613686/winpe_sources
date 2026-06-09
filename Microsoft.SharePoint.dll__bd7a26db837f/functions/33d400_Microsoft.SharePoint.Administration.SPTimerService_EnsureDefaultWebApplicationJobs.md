# Microsoft.SharePoint.Administration.SPTimerService::EnsureDefaultWebApplicationJobs

- ea: `0x33d400`
- end: `0x33f756`
- name: `Microsoft.SharePoint.Administration.SPTimerService::EnsureDefaultWebApplicationJobs`
- size: `9046`
- prototype: ``
- caller_count: `3`
- callee_count: `86`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x3227f0`
- `0x32a520`
- `0xa781c0`

## callees

- `0x1b7de0`
- `0x1c8850`
- `0x1c89b0`
- `0x1c89e0`
- `0x1c8a20`
- `0x1c8e40`
- `0x1c91a0`
- `0x1c9d10`
- `0x1c9d20`
- `0x1c9d50`
- `0x1c9f10`
- `0x1ca7c0`
- `0x1cafd0`
- `0x1caff0`
- `0x1cb050`
- `0x202440`
- `0x209050`
- `0x20a610`
- `0x20bfa0`
- `0x20c2d0`
- `0x20ee40`
- `0x20f480`
- `0x20fb80`
- `0x21f930`
- `0x222b20`
- `0x230950`
- `0x230df0`
- `0x231400`
- `0x2356c0`
- `0x236540`
- `0x236c60`
- `0x23ede0`
- `0x23eec0`
- `0x280560`
- `0x283ea0`
- `0x28f040`
- `0x29d020`
- `0x29d250`
- `0x2b2620`
- `0x2badb0`
- `0x2c95d0`
- `0x2cc000`
- `0x2cc7f0`
- `0x2cc8b0`
- `0x301050`
- `0x311dc0`
- `0x31ba80`
- `0x320600`
- `0x333c90`
- `0x3343a0`

## string_xrefs

- `0x33e6e2`: `job-quota-cachereset`
- `0x33e6f4`: `job-quota-cachereset`
- `0x33d46b`: `job-dead-site-delete`
- `0x33d47d`: `job-dead-site-delete`
- `0x33d8ba`: `job-repair-thickets`
- `0x33d8cc`: `job-repair-thickets`
- `0x33d910`: `job-repair-thickets`
- `0x33d991`: `job-repair-site`
- `0x33d9a3`: `job-repair-site`
- `0x33db12`: `job-compression-scanfull`
- `0x33db24`: `job-compression-scanfull`
- `0x33dc34`: `job-solution-resource-usage-update`
- `0x33dc46`: `job-solution-resource-usage-update`
- `0x33dd9f`: `job-delete-upgrade-eval-sites`
- `0x33ddb1`: `job-delete-upgrade-eval-sites`
- `0x33e130`: `job-deferred-acl-application`
- `0x33e142`: `job-deferred-acl-application`
- `0x33e227`: `Only create the GetManifest Timer Job in DataCenter and not in any configs. This is to reduce traffic to the Manifest Service.`
- `0x33e27c`: `job-get-manifests`
- `0x33e28e`: `job-get-manifests`
- `0x33e2b4`: `job-get-manifests`
- `0x33e2c6`: `job-get-manifests`
- `0x33e3c5`: `job-app-install-queue`
- `0x33e3d7`: `job-app-install-queue`
- `0x33e57f`: `job-create-upgrade-eval-sites`
- `0x33e591`: `job-create-upgrade-eval-sites`
- `0x33e7fe`: `AccessServicesGeoDrTimerJob`
- `0x33e803`: `Microsoft.Office.Access.Services.SPO.Timers.AccessServicesGeoDrTimerJob, Microsoft.Office.Access.Services.SPO, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33e84f`: `AccessServicesDatabaseServerCapacityUpdateTimerJob`
- `0x33e854`: `Microsoft.Office.Access.Services.SPO.Timers.AccessServicesDatabaseServerCapacityUpdateTimerJob, Microsoft.Office.Access.Services.SPO, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33e8a0`: `AccessServicesDatabaseStorageCleanupTimerJob`
- `0x33e8a5`: `Microsoft.Office.Access.Services.SPO.Timers.AccessServicesDatabaseStorageCleanupTimerJob, Microsoft.Office.Access.Services.SPO, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33e8e7`: `AccessServicesColdStorageTimerJob`
- `0x33e8ec`: `Microsoft.Office.Access.Services.SPO.Timers.AccessServicesColdStorageTimerJob, Microsoft.Office.Access.Services.SPO, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33e92e`: `AccessServicesAppDetailsTimerJob`
- `0x33e933`: `Microsoft.Office.Access.Services.SPO.Timers.AccessServicesAppDetailsTimerJob, Microsoft.Office.Access.Services.SPO, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33e975`: `AccessServicesOrphanAppDetectionTimerJob`
- `0x33e97a`: `Microsoft.Office.Access.Services.SPO.Timers.AccessServicesOrphanAppDetectionTimerJob, Microsoft.Office.Access.Services.SPO, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33e9b2`: `AccessServicesPackageAppTimerJob`
- `0x33e9b7`: `Microsoft.Office.Access.Services.SPO.Timers.AccessServicesPackageAppTimerJob, Microsoft.Office.Access.Services.SPO, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33e9f9`: `AccessServicesDatabaseCreationTimerJob`
- `0x33e9fe`: `Microsoft.Office.Access.Services.SPO.Timers.AccessServicesDatabaseCreationTimerJob, Microsoft.Office.Access.Services.SPO, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33ea4a`: `RefreshCachedGridManagerItems`
- `0x33ea4f`: `Microsoft.Online.SharePoint.Common.GridManagerSyncTimerJob, Microsoft.Online.SharePoint, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33ea9e`: `Microsoft.Online.SharePoint.Common.CdnHealthJobDefinition, Microsoft.Online.SharePoint, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33eaf3`: `Microsoft.Office.Server.ImportProfileProperties.SPImportProfilePropertiesJobDefinition, Microsoft.Office.Server.ImportProfileProperties, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33eb2f`: `AccessServicesTenantAppMoveTimerJob`
- `0x33eb34`: `Microsoft.Office.Access.Services.SPO.Timers.AccessServicesTenantAppMoveTimerJob, Microsoft.Office.Access.Services.SPO, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33eb6c`: `AccessServicesTenantMoveTimerJob`
- `0x33eb71`: `Microsoft.Office.Access.Services.SPO.Timers.AccessServicesTenantMoveTimerJob, Microsoft.Office.Access.Services.SPO, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33eba9`: `AccessServicesTenantMoveCleanupStorageTimerJob`
- `0x33ebae`: `Microsoft.Office.Access.Services.SPO.Timers.AccessServicesTenantMoveCleanupStorageTimerJob, Microsoft.Office.Access.Services.SPO, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33ebf0`: `AccessServicesTenantAppMoveWorkitemUpdateTimerJob`
- `0x33ebf5`: `Microsoft.Office.Access.Services.SPO.Timers.AccessServicesTenantAppMoveWorkitemUpdateTimerJob, Microsoft.Office.Access.Services.SPO, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33ec41`: `AccessServicesTenantMoveTelemetryTimerJob`
- `0x33ec46`: `Microsoft.Office.Access.Services.SPO.Timers.AccessServicesTenantMoveTelemetryTimerJob, Microsoft.Office.Access.Services.SPO, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33ec91`: `Microsoft.Online.SharePoint.Common.SharePoint.timerjobs.SPContentDatabaseAutoSplitTimer, Microsoft.Online.SharePoint.Common, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33ecdb`: `job-spsearch-datacleanup`
- `0x33ecea`: `Microsoft.Online.SharePoint.Common.SharePoint.timerjobs.SPSearchDataCleanupJobDefinition, Microsoft.Online.SharePoint.Common, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33ed34`: `job-spsearch-completenesscheck`
- `0x33ed43`: `Microsoft.Online.SharePoint.Common.SharePoint.timerjobs.SPSearchCompletenessCheckJobDefinition, Microsoft.Online.SharePoint.Common, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33ed9c`: `Microsoft.Online.SharePoint.Common.SharePoint.timerjobs.SPSearchDetectFastChangingDocumentsJobDefinition, Microsoft.Online.SharePoint.Common, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33ede6`: `Microsoft.Online.SharePoint.Sync.SyncToADTimerJob, Microsoft.Online.SharePoint.SyncTimerJob, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33ee2b`: `CreateSyncToADTimerJobs`
- `0x33ee89`: `job-AkamaiDnsUpdateTimerJob`
- `0x33ee90`: `Microsoft.Online.SharePoint.Failover.DnsUpdateTimerJob, Microsoft.Online.SharePoint.Failover.DnsUpdateTimerJob, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33eef1`: `Microsoft.Office.CompliancePolicy.SharePoint.Internal.SPDarMaintenanceJobDefinition, Microsoft.Office.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33ef5d`: `Microsoft.Office.CompliancePolicy.SharePoint.Internal.DarProcessingMuxJobDefinition, Microsoft.Office.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33efd2`: `Microsoft.Office.CompliancePolicy.SharePoint.Internal.HiPriPolicyProcessingMuxJobDefinition, Microsoft.Office.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f047`: `Microsoft.Office.CompliancePolicy.SharePoint.Internal.ExpirationProcessingMuxJobDefinition, Microsoft.Office.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f0ab`: `Microsoft.Office.RecordsManagement.Internal.HoldSnapshotJobDefinition, Microsoft.Office.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f0ec`: `Microsoft.Office.RecordsManagement.Internal.HoldValidationJobDefinition, Microsoft.Office.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f128`: `UpdateListRetentionJob`
- `0x33f12d`: `Microsoft.Office.CompliancePolicy.SharePoint.Internal.UpdateListRetentionJobDefinition, Microsoft.Office.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f16e`: `Microsoft.Office.CompliancePolicy.SharePoint.Internal.GlobalHoldStampingJobDefinition, Microsoft.Office.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f1af`: `Microsoft.Office.CompliancePolicy.SharePoint.Internal.PolicyEventPurgingJobDefinition, Microsoft.Office.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f1f5`: `job-untag-deletedcompliancetags`
- `0x33f207`: `job-untag-deletedcompliancetags`
- `0x33f23d`: `Microsoft.Office.Server.UserProfiles.PersonalSiteQuotaRefreshJob, Microsoft.Office.Server.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f2d7`: `Microsoft.Online.SharePoint.TenantWorkflowService, Microsoft.Online.SharePoint.Onboarding, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f2ed`: `Failed to get job service type "Microsoft.Online.SharePoint.TenantWorkflowService"`
- `0x33f2fa`: `CreateWorkflowJob`
- `0x33f312`: `Failed to get service method "Microsoft.Online.SharePoint.TenantWorkflowService.CreateWorkflowJob"`
- `0x33f327`: `Microsoft.Online.SharePoint.TenantPostProvWorkflowService, Microsoft.Online.SharePoint.Onboarding, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f33d`: `Failed to get job service type "Microsoft.Online.SharePoint.TenantPostProvWorkflowService"`
- `0x33f34a`: `CreatePostProvWorkflowJob`
- `0x33f362`: `Failed to get service method "Microsoft.Online.SharePoint.TenantPostProvWorkflowService.CreatePostProvWorkflowJob"`
- `0x33f377`: `job-VerifyTenantConfiguredRoutingState`
- `0x33f386`: `Microsoft.Online.SharePoint.Common.VerifyTenantConfiguredRoutingStateJob, Microsoft.Online.SharePoint.Common, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f3d0`: `job-ConfigureTenantRoutingState`
- `0x33f3df`: `Microsoft.Online.SharePoint.Common.ConfigureTenantRoutingStateJob, Microsoft.Online.SharePoint.Common, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f434`: `Microsoft.Office.CompliancePolicy.SharePoint.Internal.UnifiedPolicyFileSyncJobDefinition, Microsoft.Office.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f475`: `Microsoft.Office.CompliancePolicy.SharePoint.Internal.UnifiedPolicyFileSyncUrgentJobDefinition, Microsoft.Office.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f4ca`: `Microsoft.Office.RecordsManagement.Internal.SCInsightsTimerJob, Microsoft.Office.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f51a`: `ScheduledPrecannedInsightsQueries`
- `0x33f51f`: `Microsoft.Office.RecordsManagement.Internal.ScheduledPrecannedInsightsQueries, Microsoft.Office.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f56f`: `ScheduledComplianceTagActionInsightsJob`
- `0x33f574`: `Microsoft.Office.RecordsManagement.Internal.ScheduledComplianceTagActionInsightsJob, Microsoft.Office.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f5c4`: `ScheduledRetentionInsightsJob`
- `0x33f5c9`: `Microsoft.Office.RecordsManagement.Internal.ScheduledRetentionInsightsJob, Microsoft.Office.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`
- `0x33f60f`: `AccessServicesExportToSharePointListTimerJob`
- `0x33f614`: `Microsoft.Office.Access.Services.Timers.AccessServicesExportToSharePointListTimerJob, Microsoft.Office.Access.Services.Moss, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c`

## pseudocode

```c

```

## disassembly

```asm
0x33d400  ldarg.0
0x33d401  ldnull
0x33d402  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d407  brfalse.s loc_33D414
0x33d409  ldstr    aWebapplication_8// "webApplication"
0x33d40e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x33d413  throw
0x33d414  ldarg.0
0x33d415  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d41a  ldtoken  Microsoft.SharePoint.Administration.SPImmediateAlertsJobDefinition
0x33d41f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d424  ldstr    aJobImmediateAl// "job-immediate-alerts"
0x33d429  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d42e  ldnull
0x33d42f  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d434  brfalse.s loc_33D45B
0x33d436  ldstr    aJobImmediateAl// "job-immediate-alerts"
0x33d43b  ldarg.0
0x33d43c  newobj   instance void Microsoft.SharePoint.Administration.SPImmediateAlertsJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPWebApplication webApplication)
0x33d441  stloc.0
0x33d442  ldstr    aEvery1MinutesB// "every 1 minutes between 0 and 59"
0x33d447  stloc.1
0x33d448  ldloc.0
0x33d449  ldloc.1
0x33d44a  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33d44f  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33d454  ldloc.0
0x33d455  ldc.i4.1
0x33d456  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update(bool ensure)
0x33d45b  ldarg.0
0x33d45c  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d461  ldtoken  Microsoft.SharePoint.Administration.SPDeadSiteDeleteJobDefinition
0x33d466  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d46b  ldstr    aJobDeadSiteDel// "job-dead-site-delete"
0x33d470  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d475  ldnull
0x33d476  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d47b  brfalse.s loc_33D4A6
0x33d47d  ldstr    aJobDeadSiteDel// "job-dead-site-delete"
0x33d482  ldarg.0
0x33d483  newobj   instance void Microsoft.SharePoint.Administration.SPDeadSiteDeleteJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPWebApplication webApplication)
0x33d488  stloc.2
0x33d489  ldloc.2
0x33d48a  ldstr    aWeeklyAtSat210// "weekly at sat 21:00:00"
0x33d48f  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33d494  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33d499  ldloc.2
0x33d49a  ldc.i4.1
0x33d49b  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_IsDisabled(bool value)
0x33d4a0  ldloc.2
0x33d4a1  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33d4a6  ldarg.0
0x33d4a7  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d4ac  ldtoken  Microsoft.SharePoint.Administration.SPDiskQuotaWarningJobDefinition
0x33d4b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d4b6  ldstr    aJobDiskquotaWa// "job-diskquota-warning"
0x33d4bb  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d4c0  ldnull
0x33d4c1  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d4c6  brfalse.s loc_33D4EA
0x33d4c8  ldstr    aJobDiskquotaWa// "job-diskquota-warning"
0x33d4cd  ldarg.0
0x33d4ce  newobj   instance void Microsoft.SharePoint.Administration.SPDiskQuotaWarningJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPWebApplication webApplication)
0x33d4d3  stloc.3
0x33d4d4  ldloc.3
0x33d4d5  ldstr    aWeeklyAtSat220// "weekly at sat 22:00:00"
0x33d4da  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33d4df  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33d4e4  ldloc.3
0x33d4e5  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33d4ea  ldarg.0
0x33d4eb  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d4f0  ldtoken  Microsoft.SharePoint.Administration.SPChangeLogJobDefinition
0x33d4f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d4fa  ldstr    aJobChangeLogEx// "job-change-log-expiration"
0x33d4ff  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d504  ldnull
0x33d505  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d50a  brfalse.s loc_33D533
0x33d50c  ldstr    aJobChangeLogEx// "job-change-log-expiration"
0x33d511  ldarg.0
0x33d512  newobj   instance void Microsoft.SharePoint.Administration.SPChangeLogJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPWebApplication webApplication)
0x33d517  stloc.s  4
0x33d519  ldloc.s  4
0x33d51b  ldstr    aDailyBetween22_1// "daily between 22:00:00 and 06:00:00"
0x33d520  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33d525  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33d52a  ldloc.s  4
0x33d52c  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33d531  br.s     loc_33D565
0x33d533  ldarg.0
0x33d534  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d539  ldtoken  Microsoft.SharePoint.Administration.SPChangeLogJobDefinition
0x33d53e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d543  ldstr    aJobChangeLogEx// "job-change-log-expiration"
0x33d548  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d54d  isinst   Microsoft.SharePoint.Administration.SPChangeLogJobDefinition
0x33d552  stloc.s  5
0x33d554  ldloc.s  5
0x33d556  ldnull
0x33d557  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d55c  brfalse.s loc_33D565
0x33d55e  ldloc.s  5
0x33d560  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::RefreshScheduleOverride()
0x33d565  ldarg.0
0x33d566  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d56b  ldtoken  Microsoft.SharePoint.Administration.SPRecycleBinCleanupJobDefinition
0x33d570  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d575  ldstr    aJobRecycleBinC// "job-recycle-bin-cleanup"
0x33d57a  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d57f  ldnull
0x33d580  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d585  brfalse.s loc_33D5AE
0x33d587  ldstr    aJobRecycleBinC// "job-recycle-bin-cleanup"
0x33d58c  ldarg.0
0x33d58d  newobj   instance void Microsoft.SharePoint.Administration.SPRecycleBinCleanupJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPWebApplication webApplication)
0x33d592  stloc.s  6
0x33d594  ldloc.s  6
0x33d596  ldstr    aDailyAt000000// "daily at 00:00:00"
0x33d59b  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33d5a0  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33d5a5  ldloc.s  6
0x33d5a7  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33d5ac  br.s     loc_33D5E0
0x33d5ae  ldarg.0
0x33d5af  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d5b4  ldtoken  Microsoft.SharePoint.Administration.SPRecycleBinCleanupJobDefinition
0x33d5b9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d5be  ldstr    aJobRecycleBinC// "job-recycle-bin-cleanup"
0x33d5c3  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d5c8  isinst   Microsoft.SharePoint.Administration.SPRecycleBinCleanupJobDefinition
0x33d5cd  stloc.s  7
0x33d5cf  ldloc.s  7
0x33d5d1  ldnull
0x33d5d2  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d5d7  brfalse.s loc_33D5E0
0x33d5d9  ldloc.s  7
0x33d5db  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::RefreshScheduleOverride()
0x33d5e0  ldarg.0
0x33d5e1  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d5e6  ldtoken  Microsoft.SharePoint.Administration.SPActivitiesAutoCleanJobDefinition
0x33d5eb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d5f0  ldstr    aJobActivitiesA// "job-activities-autoclean"
0x33d5f5  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d5fa  ldnull
0x33d5fb  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d600  brfalse.s loc_33D627
0x33d602  ldstr    aJobActivitiesA// "job-activities-autoclean"
0x33d607  ldarg.0
0x33d608  newobj   instance void Microsoft.SharePoint.Administration.SPActivitiesAutoCleanJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPWebApplication webApplication)
0x33d60d  stloc.s  8
0x33d60f  ldloc.s  8
0x33d611  ldstr    aWeeklyAtSat050// "weekly at sat 05:00:00"
0x33d616  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33d61b  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33d620  ldloc.s  8
0x33d622  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33d627  ldarg.0
0x33d628  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d62d  ldtoken  Microsoft.SharePoint.Administration.SPWorkflowAutoCleanJobDefinition
0x33d632  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d637  ldstr    aJobWorkflowAut// "job-workflow-autoclean"
0x33d63c  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d641  ldnull
0x33d642  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d647  brfalse.s loc_33D66E
0x33d649  ldstr    aJobWorkflowAut// "job-workflow-autoclean"
0x33d64e  ldarg.0
0x33d64f  newobj   instance void Microsoft.SharePoint.Administration.SPWorkflowAutoCleanJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPWebApplication webApplication)
0x33d654  stloc.s  9
0x33d656  ldloc.s  9
0x33d658  ldstr    aDailyBetween22_1// "daily between 22:00:00 and 06:00:00"
0x33d65d  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33d662  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33d667  ldloc.s  9
0x33d669  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33d66e  ldarg.0
0x33d66f  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d674  ldtoken  Microsoft.SharePoint.Administration.SPWorkflowFailOverJobDefinition
0x33d679  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d67e  ldstr    aJobWorkflowFai// "job-workflow-failover"
0x33d683  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d688  ldnull
0x33d689  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d68e  brfalse.s loc_33D6B5
0x33d690  ldstr    aJobWorkflowFai// "job-workflow-failover"
0x33d695  ldarg.0
0x33d696  newobj   instance void Microsoft.SharePoint.Administration.SPWorkflowFailOverJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPWebApplication webApplication)
0x33d69b  stloc.s  0xA
0x33d69d  ldloc.s  0xA
0x33d69f  ldstr    aEvery15Minutes_0// "every 15 minutes between 0 and 59"
0x33d6a4  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33d6a9  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33d6ae  ldloc.s  0xA
0x33d6b0  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33d6b5  ldarg.0
0x33d6b6  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d6bb  ldtoken  Microsoft.SharePoint.Administration.SPWorkflowJobDefinition
0x33d6c0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d6c5  ldstr    aJobWorkflow// "job-workflow"
0x33d6ca  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d6cf  ldnull
0x33d6d0  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d6d5  brfalse.s loc_33D6FF
0x33d6d7  ldarg.0
0x33d6d8  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d6dd  ldtoken  Microsoft.SharePoint.Administration.SPWorkflowJobDefinition
0x33d6e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d6e7  ldstr    aJobWorkflow// "job-workflow"
0x33d6ec  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d6f1  castclass Microsoft.SharePoint.Administration.SPJobDefinition
0x33d6f6  stloc.s  0xB
0x33d6f8  ldloc.s  0xB
0x33d6fa  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Delete()
0x33d6ff  ldarg.0
0x33d700  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d705  ldtoken  Microsoft.SharePoint.Administration.SPSiteInfoJobDefinition
0x33d70a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d70f  ldstr    aJobSiteinfo// "job-siteinfo"
0x33d714  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d719  ldnull
0x33d71a  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d71f  brfalse.s loc_33D746
0x33d721  ldstr    aJobSiteinfo// "job-siteinfo"
0x33d726  ldarg.0
0x33d727  newobj   instance void Microsoft.SharePoint.Administration.SPSiteInfoJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPWebApplication webApplication)
0x33d72c  stloc.s  0xC
0x33d72e  ldloc.s  0xC
0x33d730  ldstr    aDailyBetween22_1// "daily between 22:00:00 and 06:00:00"
0x33d735  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33d73a  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33d73f  ldloc.s  0xC
0x33d741  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33d746  ldarg.0
0x33d747  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d74c  ldtoken  Microsoft.SharePoint.Administration.SPWebInfoJobDefinition
0x33d751  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d756  ldstr    aJobWebinfo// "job-webinfo"
0x33d75b  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d760  ldnull
0x33d761  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d766  brfalse.s loc_33D78D
0x33d768  ldstr    aJobWebinfo// "job-webinfo"
0x33d76d  ldarg.0
0x33d76e  newobj   instance void Microsoft.SharePoint.Administration.SPWebInfoJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPWebApplication webApplication)
0x33d773  stloc.s  0xD
0x33d775  ldloc.s  0xD
0x33d777  ldstr    aDailyBetween22_1// "daily between 22:00:00 and 06:00:00"
0x33d77c  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33d781  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33d786  ldloc.s  0xD
0x33d788  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33d78d  ldarg.0
0x33d78e  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d793  ldtoken  Microsoft.SharePoint.Administration.SPSiteDeletionJobDefinition
0x33d798  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d79d  ldstr    aJobSiteDeletio// "job-site-deletion"
0x33d7a2  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d7a7  ldnull
0x33d7a8  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d7ad  brfalse.s loc_33D7D4
0x33d7af  ldstr    aJobSiteDeletio// "job-site-deletion"
0x33d7b4  ldarg.0
0x33d7b5  newobj   instance void Microsoft.SharePoint.Administration.SPSiteDeletionJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPWebApplication webApplication)
0x33d7ba  stloc.s  0xE
0x33d7bc  ldloc.s  0xE
0x33d7be  ldstr    aHourlyBetween0// "hourly between 0 and 59"
0x33d7c3  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33d7c8  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33d7cd  ldloc.s  0xE
0x33d7cf  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33d7d4  ldarg.0
0x33d7d5  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d7da  ldtoken  Microsoft.SharePoint.Administration.SPFixSiteStorageMetricsJobDefinition
0x33d7df  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d7e4  ldstr    aJobFixSiteStor// "job-fix-site-storage-metrics"
0x33d7e9  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
0x33d7ee  ldnull
0x33d7ef  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x33d7f4  brfalse.s loc_33D825
0x33d7f6  ldstr    aJobFixSiteStor// "job-fix-site-storage-metrics"
0x33d7fb  ldarg.0
0x33d7fc  newobj   instance void Microsoft.SharePoint.Administration.SPFixSiteStorageMetricsJobDefinition::.ctor(string name, class Microsoft.SharePoint.Administration.SPWebApplication webApplication)
0x33d801  stloc.s  0xF
0x33d803  ldloc.s  0xF
0x33d805  ldstr    aHourlyBetween0// "hourly between 0 and 59"
0x33d80a  call     class Microsoft.SharePoint.SPSchedule Microsoft.SharePoint.SPSchedule::FromString(string recurrenceValue)
0x33d80f  callvirt instance void Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class Microsoft.SharePoint.SPSchedule value)
0x33d814  ldloc.s  0xF
0x33d816  ldc.i4.s 0x19
0x33d818  conv.i8
0x33d819  callvirt instance void Microsoft.SharePoint.Administration.SPContentDatabaseJobDefinition::set_FetchLimit(int64 value)
0x33d81e  ldloc.s  0xF
0x33d820  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x33d825  ldarg.0
0x33d826  callvirt instance class Microsoft.SharePoint.Administration.SPJobDefinitionCollection Microsoft.SharePoint.Administration.SPWebApplication::get_JobDefinitions()
0x33d82b  ldtoken  Microsoft.SharePoint.Administration.SPRecalculateThicketsJobDefinition
0x33d830  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33d835  ldstr    aJobRecalcThick// "job-recalc-thickets"
0x33d83a  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPJobDefinition>::GetValue(class [mscorlib]System.Type, string)
  ... truncated ...
```
