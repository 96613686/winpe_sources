# MDM_Policy_Config01_Update02_InvokeCreateInstance

- ea: `0x1800f1bac`
- end: `0x1800f358b`
- name: `MDM_Policy_Config01_Update02_InvokeCreateInstance`
- size: `6623`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f1ab0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800f1bac`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1800f1e2c`: `AllowAutoUpdate`
- `0x1800f1e6c`: `AllowAutoWindowsUpdateDownloadOverMeteredNetwork`
- `0x1800f1eac`: `AllowTemporaryEnterpriseFeatureControl`
- `0x1800f1f2c`: `AlwaysAutoRebootAtScheduledTimeMinutes`
- `0x1800f1f6c`: `AllowMUUpdateService`
- `0x1800f1fac`: `AllowNonMicrosoftSignedUpdate`
- `0x1800f1fec`: `AllowUpdateService`
- `0x1800f20ac`: `AutoRestartDeadlinePeriodInDaysForFeatureUpdates`
- `0x1800f216c`: `BranchReadinessLevel`
- `0x1800f21ac`: `ConfigureDeadlineForFeatureUpdates`
- `0x1800f21ec`: `ConfigureDeadlineForQualityUpdates`
- `0x1800f222c`: `ConfigureDeadlineGracePeriod`
- `0x1800f226c`: `ConfigureDeadlineGracePeriodForFeatureUpdates`
- `0x1800f22ac`: `ConfigureDeadlineNoAutoReboot`
- `0x1800f22ec`: `ConfigureFeatureUpdateUninstallPeriod`
- `0x1800f232c`: `DeferFeatureUpdatesPeriodInDays`
- `0x1800f236c`: `DeferQualityUpdatesPeriodInDays`
- `0x1800f23ac`: `DeferUpdatePeriod`
- `0x1800f24ec`: `DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection`
- `0x1800f256c`: `EngagedRestartDeadlineForFeatureUpdates`
- `0x1800f25ec`: `EngagedRestartSnoozeScheduleForFeatureUpdates`
- `0x1800f266c`: `EngagedRestartTransitionScheduleForFeatureUpdates`
- `0x1800f26ac`: `ExcludeWUDriversInQualityUpdate`
- `0x1800f276c`: `IgnoreMOUpdateDownloadLimit`
- `0x1800f282c`: `PauseFeatureUpdates`
- `0x1800f286c`: `PauseFeatureUpdatesStartTime`
- `0x1800f28ac`: `PauseQualityUpdates`
- `0x1800f28ec`: `PauseQualityUpdatesStartTime`
- `0x1800f292c`: `PhoneUpdateRestrictions`
- `0x1800f29ac`: `RequireUpdateApproval`
- `0x1800f29ec`: `ScheduledInstallDay`
- `0x1800f2a2c`: `ScheduledInstallEveryWeek`
- `0x1800f2a6c`: `ScheduledInstallFirstWeek`
- `0x1800f2aac`: `ScheduledInstallFourthWeek`
- `0x1800f2aec`: `ScheduledInstallSecondWeek`
- `0x1800f2b2c`: `ScheduledInstallThirdWeek`
- `0x1800f2b6c`: `ScheduledInstallTime`
- `0x1800f2c6c`: `SetDisablePauseUXAccess`
- `0x1800f2cac`: `SetDisableUXWUAccess`
- `0x1800f2d2c`: `SetPolicyDrivenUpdateSourceForDriverUpdates`
- `0x1800f2d6c`: `SetPolicyDrivenUpdateSourceForFeatureUpdates`
- `0x1800f2dac`: `SetPolicyDrivenUpdateSourceForOtherUpdates`
- `0x1800f2dec`: `SetPolicyDrivenUpdateSourceForQualityUpdates`
- `0x1800f2e2c`: `SetProxyBehaviorForUpdateDetection`
- `0x1800f2eec`: `UpdateNotificationLevel`
- `0x1800f2f2c`: `UpdateServiceUrl`
- `0x1800f2f6c`: `UpdateServiceUrlAlternate`
- `0x1800f2fec`: `MaintenanceWindowUpdateActions`
- `0x1800f1cd5`: `CreateInstanceStart`
- `0x1800f34f2`: `CreateInstanceEnd`
- `0x1800f1c1c`: `MDM_Policy_Config01_Update02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Update02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-3E8h] BYREF
  char v9; // [rsp+48h] [rbp-3E0h]
  _QWORD v10[5]; // [rsp+50h] [rbp-3D8h] BYREF
  char v11; // [rsp+78h] [rbp-3B0h]
  int v12; // [rsp+80h] [rbp-3A8h] BYREF
  char v13; // [rsp+84h] [rbp-3A4h]
  _BYTE v14[16]; // [rsp+88h] [rbp-3A0h] BYREF
  _DWORD v15[6]; // [rsp+98h] [rbp-390h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-378h] BYREF

  memset_0(&instance, 0, 0x350u);
  v12 = 0;
  v13 = 0;
  v10[0] = &TelemetryEventWriter::`vftable';
  v10[1] = &v12;
  v10[2] = "MDM_Policy_Config01_Update02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_180347CA7,
      v14,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    inserted = 4;
    goto LABEL_389;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v10,
    "CreateInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v8 = 0;
  inserted = CreateRequestHandlerInstance(
               (__int64)self,
               (wchar_t *)a2[1].serverName,
               (const unsigned __int16 *)a2[1].ft,
               (struct WmiNodeInfo *)&MDM_Policy_Config01_Update02_NodeList,
               0x5Cu,
               4,
               &v8);
  if ( !inserted )
  {
    v10[4] = &v8;
    v11 = 1;
    v6 = v8;
    if ( !v8 )
    {
      inserted = 1;
      goto LABEL_389;
    }
    WmiRequestHandler::SetRequestMIInstance(v8, a2, (struct WmiNodeInfo *)&MDM_Policy_Config01_Update02_NodeList, 0x5Cu);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ActiveHoursEnd", (LONG *)a2[1].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
LABEL_384:
        (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        goto LABEL_389;
      }
    }
    if ( BYTE4(a2[1].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ActiveHoursMaxRange", (LONG *)&a2[1].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[1].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ActiveHoursStart", (LONG *)&a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAutoUpdate", (LONG *)&a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[2].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AllowAutoWindowsUpdateDownloadOverMeteredNetwork",
                   (LONG *)&a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AllowTemporaryEnterpriseFeatureControl",
                   (LONG *)&a2[2].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[2].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowOptionalContent", (LONG *)&a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AlwaysAutoRebootAtScheduledTimeMinutes",
                   (LONG *)&a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowMUUpdateService", (LONG *)a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AllowNonMicrosoftSignedUpdate",
                   (LONG *)&a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[2].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowUpdateService", (LONG *)&a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AutomaticMaintenanceWakeUp", (LONG *)&a2[2].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AutoRestartDeadlinePeriodInDays", (LONG *)&a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[3].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AutoRestartDeadlinePeriodInDaysForFeatureUpdates",
                   (LONG *)&a2[3].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[3].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AutoRestartNotificationSchedule",
                   (LONG *)&a2[3].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[3].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AutoRestartRequiredNotificationDismissal",
                   (LONG *)&a2[3].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[3].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"BranchReadinessLevel", (LONG *)a2[3].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[3].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureDeadlineForFeatureUpdates",
                   (LONG *)&a2[3].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[3].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureDeadlineForQualityUpdates",
                   (LONG *)&a2[3].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[3].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureDeadlineGracePeriod",
                   (LONG *)&a2[3].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureDeadlineGracePeriodForFeatureUpdates",
                   (LONG *)&a2[4]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[4].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureDeadlineNoAutoReboot", (LONG *)&a2[4].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[4].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureFeatureUpdateUninstallPeriod",
                   (LONG *)&a2[4].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[4].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DeferFeatureUpdatesPeriodInDays",
                   (LONG *)&a2[4].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[4].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DeferQualityUpdatesPeriodInDays", (LONG *)a2[4].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[4].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DeferUpdatePeriod", (LONG *)&a2[4].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[4].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DeferUpgradePeriod", (LONG *)&a2[4].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DetectionFrequency", (LONG *)&a2[4].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[5].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableDualScan", (LONG *)&a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableWUfBSafeguards", (LONG *)&a2[5].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[5].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection",
                   (LONG *)&a2[5].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[5].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EngagedRestartDeadline", (LONG *)&a2[5].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[5].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"EngagedRestartDeadlineForFeatureUpdates",
                   (LONG *)a2[5].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[5].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"EngagedRestartSnoozeSchedule",
                   (LONG *)&a2[5].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[5].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"EngagedRestartSnoozeScheduleForFeatureUpdates",
                   (LONG *)&a2[5].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[5].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"EngagedRestartTransitionSchedule",
                   (LONG *)&a2[5].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[6].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"EngagedRestartTransitionScheduleForFeatureUpdates",
                   (LONG *)&a2[6]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[6].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ExcludeWUDriversInQualityUpdate",
                   (LONG *)&a2[6].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[6].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"FillEmptyContentUrls", (LONG *)&a2[6].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[6].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"IgnoreMOAppDownloadLimit", (LONG *)&a2[6].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[6].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"IgnoreMOUpdateDownloadLimit", (LONG *)a2[6].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[6].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ManagePreviewBuilds", (LONG *)&a2[6].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[6].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseDeferrals", (LONG *)&a2[6].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[6].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseFeatureUpdates", (LONG *)&a2[6].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[7].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseFeatureUpdatesStartTime", (LONG *)&a2[7]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[7].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseQualityUpdates", (LONG *)&a2[7].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[7].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseQualityUpdatesStartTime", (LONG *)&a2[7].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[7].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PhoneUpdateRestrictions", (LONG *)&a2[7].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[7].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RequireDeferUpgrade", (LONG *)&a2[7].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[7].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RequireUpdateApproval", (LONG *)&a2[7].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallDay", (LONG *)&a2[8]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallEveryWeek", (LONG *)&a2[8].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallFirstWeek", (LONG *)&a2[8].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallFourthWeek", (LONG *)&a2[8].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallSecondWeek", (LONG *)a2[8].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallThirdWeek", (LONG *)&a2[8].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallTime", (LONG *)&a2[8].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ScheduleImminentRestartWarning",
                   (LONG *)&a2[8].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[9].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleRestartWarning", (LONG *)&a2[9]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[9].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"SetAutoRestartNotificationDisable",
                   (LONG *)&a2[9].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[9].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDisablePauseUXAccess", (LONG *)&a2[9].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[9].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDisableUXWUAccess", (LONG *)&a2[9].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[9].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetEDURestart", (LONG *)a2[9].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[9].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"SetPolicyDrivenUpdateSourceForDriverUpdates",
                   (LONG *)&a2[9].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[9].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"SetPolicyDrivenUpdateSourceForFeatureUpdates",
                   (LONG *)&a2[9].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[9].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"SetPolicyDrivenUpdateSourceForOtherUpdates",
                   (LONG *)&a2[9].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[10].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"SetPolicyDrivenUpdateSourceForQualityUpdates",
                   (LONG *)&a2[10]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[10].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"SetProxyBehaviorForUpdateDetection",
                   (LONG *)&a2[10].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[10].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProductVersion", (LONG *)&a2[10].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[10].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"TargetReleaseVersion", (LONG *)a2[10].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[10].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UpdateNotificationLevel", (LONG *)&a2[10].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[11].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UpdateServiceUrl", (LONG *)&a2[10].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[11].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UpdateServiceUrlAlternate", (LONG *)&a2[11].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE1(a2[11].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"MaintenanceWindowEnabled", (LONG *)&a2[11].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[11].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MaintenanceWindowUpdateActions",
                   (LONG *)&a2[11].nameSpace + 1);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[11].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"MaintenanceWindowStartDate", (LONG *)&a2[11].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[12].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"MaintenanceWindowStartTime", (LONG *)&a2[11].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[12].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MaintenanceWindowDurationHours",
                   (LONG *)&a2[12].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[12].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MaintenanceWindowRepeatScheduleOption",
                   (LONG *)&a2[12].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE1(a2[12].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MaintenanceWindowWeeklySunday",
                   (LONG *)&a2[12].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[12].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MaintenanceWindowWeeklyMonday",
                   (LONG *)((char *)&a2[12].nameSpace + 3));
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( HIBYTE(a2[12].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MaintenanceWindowWeeklyTuesday",
                   (LONG *)((char *)&a2[12].nameSpace + 6));
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE2(a2[12].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MaintenanceWindowWeeklyWednesday",
                   (LONG *)((char *)a2[12].reserved + 1));
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE5(a2[12].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MaintenanceWindowWeeklyThursday",
                   (LONG *)a2[12].reserved + 1);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[12].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MaintenanceWindowWeeklyFriday",
                   (LONG *)((char *)a2[12].reserved + 7));
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE3(a2[12].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MaintenanceWindowWeeklySaturday",
                   (LONG *)((char *)&a2[12].reserved[1] + 2));
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[12].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MaintenanceWindowMonthlySchedule",
                   (LONG *)&a2[12].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[12].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MaintenanceWindowMonthlyMonthBasedDayOfMonth",
                   (LONG *)&a2[12].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[13].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MaintenanceWindowMonthlyWeekBasedOccurrenceInMonth",
                   (LONG *)&a2[13]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[13].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MaintenanceWindowMonthlyWeekBasedDayOfTheWeek",
                   (LONG *)&a2[13].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_389;
      goto LABEL_384;
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_389;
      goto LABEL_384;
    }
    inserted = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Update02_rtti, &instance);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_389;
      goto LABEL_384;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v8 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_389:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "CreateInstanceEnd", inserted);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_180354A8F,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return inserted;
}

```

## disassembly

```asm
0x1800f1bac  mov     [rsp+arg_10], rsi
0x1800f1bb1  mov     [rsp+arg_18], rdi
0x1800f1bb6  push    r12
0x1800f1bb8  push    r14
0x1800f1bba  push    r15
0x1800f1bbc  sub     rsp, 410h
0x1800f1bc3  mov     rax, cs:__security_cookie
0x1800f1bca  xor     rax, rsp
0x1800f1bcd  mov     [rsp+428h+var_28], rax
0x1800f1bd5  mov     rsi, rdx
0x1800f1bd8  mov     r15, rcx
0x1800f1bdb  xor     edx, edx; Val
0x1800f1bdd  mov     r8d, 350h; Size
0x1800f1be3  lea     rcx, [rsp+428h+instance]; void *
0x1800f1beb  call    memset_0
0x1800f1bf0  mov     [rsp+428h+var_3A8], 0
0x1800f1bfb  mov     [rsp+428h+var_3A4], 0
0x1800f1c03  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800f1c0a  mov     [rsp+428h+var_3D8], rax
0x1800f1c0f  lea     rax, [rsp+428h+var_3A8]
0x1800f1c17  mov     [rsp+428h+var_3D0], rax
0x1800f1c1c  lea     rax, aMdmPolicyConfi_91; "MDM_Policy_Config01_Update02"
0x1800f1c23  mov     [rsp+428h+var_3C8], rax
0x1800f1c28  lea     rcx, [rsp+428h+var_3A8]
0x1800f1c30  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800f1c35  mov     eax, cs:dword_180380B68
0x1800f1c3b  cmp     eax, 5
0x1800f1c3e  jbe     short loc_1800F1CB4
0x1800f1c40  mov     rdx, 200000000000h
0x1800f1c4a  lea     rcx, dword_180380B68
0x1800f1c51  call    _tlgKeywordOn
0x1800f1c56  test    al, al
0x1800f1c58  jz      short loc_1800F1CB4
0x1800f1c5a  cmp     [rsp+428h+var_3A4], 0
0x1800f1c62  jz      short loc_1800F1C96
0x1800f1c64  cmp     [rsp+428h+var_390], 0
0x1800f1c6c  jnz     short loc_1800F1C8C
0x1800f1c6e  cmp     [rsp+428h+var_38C], 0
0x1800f1c76  jnz     short loc_1800F1C8C
0x1800f1c78  cmp     [rsp+428h+var_388], 0
0x1800f1c80  jnz     short loc_1800F1C8C
0x1800f1c82  cmp     [rsp+428h+var_384], 0
0x1800f1c8a  jz      short loc_1800F1C96
0x1800f1c8c  lea     r9, [rsp+428h+var_390]
0x1800f1c94  jmp     short loc_1800F1C99
0x1800f1c96  xor     r9d, r9d
0x1800f1c99  lea     r8, [rsp+428h+var_3A0]
0x1800f1ca1  lea     rdx, byte_180347CA7
0x1800f1ca8  lea     rcx, dword_180380B68
0x1800f1caf  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800f1cb4  cmp     byte ptr [rsi+48h], 0
0x1800f1cb8  jz      loc_1800F34EA
0x1800f1cbe  mov     [rsp+428h+var_3E0], 0
0x1800f1cc3  cmp     byte ptr [rsi+58h], 0
0x1800f1cc7  jz      loc_1800F34EA
0x1800f1ccd  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800f1cd1  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800f1cd5  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1800f1cdc  lea     rcx, [rsp+428h+var_3D8]; this
0x1800f1ce1  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800f1ce6  nop
0x1800f1ce7  mov     [rsp+428h+var_3E8], 0
0x1800f1cf0  lea     rax, [rsp+428h+var_3E8]
0x1800f1cf5  mov     [rsp+428h+var_3F8], rax
0x1800f1cfa  mov     [rsp+428h+var_400], 4
0x1800f1d02  mov     [rsp+428h+var_408], 5Ch ; '\'
0x1800f1d0a  lea     r9, ?MDM_Policy_Config01_Update02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Update02_NodeList
0x1800f1d11  mov     r8, [rsi+40h]
0x1800f1d15  mov     rdx, [rsi+50h]
0x1800f1d19  mov     rcx, r15
0x1800f1d1c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800f1d21  mov     edi, eax
0x1800f1d23  test    eax, eax
0x1800f1d25  jz      short loc_1800F1D2C
0x1800f1d27  jmp     loc_1800F34EF
0x1800f1d2c  lea     rax, [rsp+428h+var_3E8]
0x1800f1d31  mov     [rsp+428h+var_3B8], rax
0x1800f1d36  mov     r12d, 1
0x1800f1d3c  mov     [rsp+428h+var_3B0], r12b
0x1800f1d41  mov     r14, [rsp+428h+var_3E8]
0x1800f1d46  test    r14, r14
0x1800f1d49  jnz     short loc_1800F1D53
0x1800f1d4b  mov     edi, r12d
0x1800f1d4e  jmp     loc_1800F34EF
0x1800f1d53  mov     r9d, 5Ch ; '\'; unsigned int
0x1800f1d59  lea     r8, ?MDM_Policy_Config01_Update02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800f1d60  mov     rdx, rsi; struct _MI_Instance *
0x1800f1d63  mov     rcx, r14; this
0x1800f1d66  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800f1d6b  lea     r8, [rsi+60h]; void *
0x1800f1d6f  cmp     [r8+4], r12b
0x1800f1d73  jnz     short loc_1800F1DA8
0x1800f1d75  lea     rdx, aActivehoursend; "ActiveHoursEnd"
0x1800f1d7c  mov     rcx, r14; this
0x1800f1d7f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f1d84  mov     edi, eax
0x1800f1d86  test    eax, eax
0x1800f1d88  jz      short loc_1800F1DA8
0x1800f1d8a  mov     rcx, [rsp+428h+var_3E8]
0x1800f1d8f  test    rcx, rcx
0x1800f1d92  jz      short loc_1800F1DA3
0x1800f1d94  mov     rax, [rcx]
0x1800f1d97  mov     edx, r12d
0x1800f1d9a  mov     rax, [rax]
0x1800f1d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1da2  nop
0x1800f1da3  jmp     loc_1800F34EF
0x1800f1da8  lea     r8, [rsi+68h]; void *
0x1800f1dac  cmp     [r8+4], r12b
0x1800f1db0  jnz     short loc_1800F1DE5
0x1800f1db2  lea     rdx, aActivehoursmax; "ActiveHoursMaxRange"
0x1800f1db9  mov     rcx, r14; this
0x1800f1dbc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f1dc1  mov     edi, eax
0x1800f1dc3  test    eax, eax
0x1800f1dc5  jz      short loc_1800F1DE5
0x1800f1dc7  mov     rcx, [rsp+428h+var_3E8]
0x1800f1dcc  test    rcx, rcx
0x1800f1dcf  jz      short loc_1800F1DE0
0x1800f1dd1  mov     rax, [rcx]
0x1800f1dd4  mov     edx, r12d
0x1800f1dd7  mov     rax, [rax]
0x1800f1dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1ddf  nop
0x1800f1de0  jmp     loc_1800F34EF
0x1800f1de5  lea     r8, [rsi+70h]; void *
0x1800f1de9  cmp     [r8+4], r12b
0x1800f1ded  jnz     short loc_1800F1E22
0x1800f1def  lea     rdx, aActivehourssta; "ActiveHoursStart"
0x1800f1df6  mov     rcx, r14; this
0x1800f1df9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f1dfe  mov     edi, eax
0x1800f1e00  test    eax, eax
0x1800f1e02  jz      short loc_1800F1E22
0x1800f1e04  mov     rcx, [rsp+428h+var_3E8]
0x1800f1e09  test    rcx, rcx
0x1800f1e0c  jz      short loc_1800F1E1D
0x1800f1e0e  mov     rax, [rcx]
0x1800f1e11  mov     edx, r12d
0x1800f1e14  mov     rax, [rax]
0x1800f1e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1e1c  nop
0x1800f1e1d  jmp     loc_1800F34EF
0x1800f1e22  lea     r8, [rsi+78h]; void *
0x1800f1e26  cmp     [r8+4], r12b
0x1800f1e2a  jnz     short loc_1800F1E5F
0x1800f1e2c  lea     rdx, aAllowautoupdat; "AllowAutoUpdate"
0x1800f1e33  mov     rcx, r14; this
0x1800f1e36  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f1e3b  mov     edi, eax
0x1800f1e3d  test    eax, eax
0x1800f1e3f  jz      short loc_1800F1E5F
0x1800f1e41  mov     rcx, [rsp+428h+var_3E8]
0x1800f1e46  test    rcx, rcx
0x1800f1e49  jz      short loc_1800F1E5A
0x1800f1e4b  mov     rax, [rcx]
0x1800f1e4e  mov     edx, r12d
0x1800f1e51  mov     rax, [rax]
0x1800f1e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1e59  nop
0x1800f1e5a  jmp     loc_1800F34EF
0x1800f1e5f  lea     r8, [rsi+80h]; void *
0x1800f1e66  cmp     [r8+4], r12b
0x1800f1e6a  jnz     short loc_1800F1E9F
0x1800f1e6c  lea     rdx, aAllowautowindo; "AllowAutoWindowsUpdateDownloadOverMeter"...
0x1800f1e73  mov     rcx, r14; this
0x1800f1e76  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f1e7b  mov     edi, eax
0x1800f1e7d  test    eax, eax
0x1800f1e7f  jz      short loc_1800F1E9F
0x1800f1e81  mov     rcx, [rsp+428h+var_3E8]
0x1800f1e86  test    rcx, rcx
0x1800f1e89  jz      short loc_1800F1E9A
0x1800f1e8b  mov     rax, [rcx]
0x1800f1e8e  mov     edx, r12d
0x1800f1e91  mov     rax, [rax]
0x1800f1e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1e99  nop
0x1800f1e9a  jmp     loc_1800F34EF
0x1800f1e9f  lea     r8, [rsi+88h]; void *
0x1800f1ea6  cmp     [r8+4], r12b
0x1800f1eaa  jnz     short loc_1800F1EDF
0x1800f1eac  lea     rdx, aAllowtemporary; "AllowTemporaryEnterpriseFeatureControl"
0x1800f1eb3  mov     rcx, r14; this
0x1800f1eb6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f1ebb  mov     edi, eax
0x1800f1ebd  test    eax, eax
0x1800f1ebf  jz      short loc_1800F1EDF
0x1800f1ec1  mov     rcx, [rsp+428h+var_3E8]
0x1800f1ec6  test    rcx, rcx
0x1800f1ec9  jz      short loc_1800F1EDA
0x1800f1ecb  mov     rax, [rcx]
0x1800f1ece  mov     edx, r12d
0x1800f1ed1  mov     rax, [rax]
0x1800f1ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1ed9  nop
0x1800f1eda  jmp     loc_1800F34EF
0x1800f1edf  lea     r8, [rsi+90h]; void *
0x1800f1ee6  cmp     [r8+4], r12b
0x1800f1eea  jnz     short loc_1800F1F1F
0x1800f1eec  lea     rdx, aAllowoptionalc; "AllowOptionalContent"
0x1800f1ef3  mov     rcx, r14; this
0x1800f1ef6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f1efb  mov     edi, eax
0x1800f1efd  test    eax, eax
0x1800f1eff  jz      short loc_1800F1F1F
0x1800f1f01  mov     rcx, [rsp+428h+var_3E8]
0x1800f1f06  test    rcx, rcx
0x1800f1f09  jz      short loc_1800F1F1A
0x1800f1f0b  mov     rax, [rcx]
0x1800f1f0e  mov     edx, r12d
0x1800f1f11  mov     rax, [rax]
0x1800f1f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1f19  nop
0x1800f1f1a  jmp     loc_1800F34EF
0x1800f1f1f  lea     r8, [rsi+98h]; void *
0x1800f1f26  cmp     [r8+4], r12b
0x1800f1f2a  jnz     short loc_1800F1F5F
0x1800f1f2c  lea     rdx, aAlwaysautorebo; "AlwaysAutoRebootAtScheduledTimeMinutes"
0x1800f1f33  mov     rcx, r14; this
0x1800f1f36  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f1f3b  mov     edi, eax
0x1800f1f3d  test    eax, eax
0x1800f1f3f  jz      short loc_1800F1F5F
0x1800f1f41  mov     rcx, [rsp+428h+var_3E8]
0x1800f1f46  test    rcx, rcx
0x1800f1f49  jz      short loc_1800F1F5A
0x1800f1f4b  mov     rax, [rcx]
0x1800f1f4e  mov     edx, r12d
0x1800f1f51  mov     rax, [rax]
0x1800f1f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1f59  nop
0x1800f1f5a  jmp     loc_1800F34EF
0x1800f1f5f  lea     r8, [rsi+0A0h]; void *
0x1800f1f66  cmp     [r8+4], r12b
0x1800f1f6a  jnz     short loc_1800F1F9F
0x1800f1f6c  lea     rdx, aAllowmuupdates; "AllowMUUpdateService"
0x1800f1f73  mov     rcx, r14; this
0x1800f1f76  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f1f7b  mov     edi, eax
0x1800f1f7d  test    eax, eax
0x1800f1f7f  jz      short loc_1800F1F9F
0x1800f1f81  mov     rcx, [rsp+428h+var_3E8]
0x1800f1f86  test    rcx, rcx
0x1800f1f89  jz      short loc_1800F1F9A
0x1800f1f8b  mov     rax, [rcx]
0x1800f1f8e  mov     edx, r12d
0x1800f1f91  mov     rax, [rax]
0x1800f1f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1f99  nop
0x1800f1f9a  jmp     loc_1800F34EF
0x1800f1f9f  lea     r8, [rsi+0A8h]; void *
0x1800f1fa6  cmp     [r8+4], r12b
0x1800f1faa  jnz     short loc_1800F1FDF
0x1800f1fac  lea     rdx, aAllownonmicros; "AllowNonMicrosoftSignedUpdate"
0x1800f1fb3  mov     rcx, r14; this
0x1800f1fb6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f1fbb  mov     edi, eax
0x1800f1fbd  test    eax, eax
0x1800f1fbf  jz      short loc_1800F1FDF
0x1800f1fc1  mov     rcx, [rsp+428h+var_3E8]
0x1800f1fc6  test    rcx, rcx
0x1800f1fc9  jz      short loc_1800F1FDA
0x1800f1fcb  mov     rax, [rcx]
0x1800f1fce  mov     edx, r12d
0x1800f1fd1  mov     rax, [rax]
0x1800f1fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1fd9  nop
0x1800f1fda  jmp     loc_1800F34EF
0x1800f1fdf  lea     r8, [rsi+0B0h]; void *
0x1800f1fe6  cmp     [r8+4], r12b
0x1800f1fea  jnz     short loc_1800F201F
0x1800f1fec  lea     rdx, aAllowupdateser; "AllowUpdateService"
0x1800f1ff3  mov     rcx, r14; this
0x1800f1ff6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f1ffb  mov     edi, eax
0x1800f1ffd  test    eax, eax
0x1800f1fff  jz      short loc_1800F201F
0x1800f2001  mov     rcx, [rsp+428h+var_3E8]
0x1800f2006  test    rcx, rcx
0x1800f2009  jz      short loc_1800F201A
0x1800f200b  mov     rax, [rcx]
0x1800f200e  mov     edx, r12d
0x1800f2011  mov     rax, [rax]
0x1800f2014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2019  nop
0x1800f201a  jmp     loc_1800F34EF
0x1800f201f  lea     r8, [rsi+0B8h]; void *
0x1800f2026  cmp     [r8+4], r12b
0x1800f202a  jnz     short loc_1800F205F
0x1800f202c  lea     rdx, aAutomaticmaint; "AutomaticMaintenanceWakeUp"
0x1800f2033  mov     rcx, r14; this
0x1800f2036  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f203b  mov     edi, eax
0x1800f203d  test    eax, eax
0x1800f203f  jz      short loc_1800F205F
0x1800f2041  mov     rcx, [rsp+428h+var_3E8]
0x1800f2046  test    rcx, rcx
0x1800f2049  jz      short loc_1800F205A
0x1800f204b  mov     rax, [rcx]
  ... truncated ...
```
