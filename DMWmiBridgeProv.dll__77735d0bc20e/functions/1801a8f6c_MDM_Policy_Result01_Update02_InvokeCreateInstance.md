# MDM_Policy_Result01_Update02_InvokeCreateInstance

- ea: `0x1801a8f6c`
- end: `0x1801aa50b`
- name: `MDM_Policy_Result01_Update02_InvokeCreateInstance`
- size: `5535`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801a8e70`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1801a8f6c`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1801a91ec`: `AllowAutoUpdate`
- `0x1801a922c`: `AllowAutoWindowsUpdateDownloadOverMeteredNetwork`
- `0x1801a926c`: `AllowTemporaryEnterpriseFeatureControl`
- `0x1801a92ec`: `AlwaysAutoRebootAtScheduledTimeMinutes`
- `0x1801a932c`: `AllowMUUpdateService`
- `0x1801a936c`: `AllowNonMicrosoftSignedUpdate`
- `0x1801a93ac`: `AllowUpdateService`
- `0x1801a946c`: `AutoRestartDeadlinePeriodInDaysForFeatureUpdates`
- `0x1801a952c`: `BranchReadinessLevel`
- `0x1801a956c`: `ConfigureDeadlineForFeatureUpdates`
- `0x1801a95ac`: `ConfigureDeadlineForQualityUpdates`
- `0x1801a95ec`: `ConfigureDeadlineGracePeriod`
- `0x1801a962c`: `ConfigureDeadlineGracePeriodForFeatureUpdates`
- `0x1801a966c`: `ConfigureDeadlineNoAutoReboot`
- `0x1801a96ac`: `ConfigureFeatureUpdateUninstallPeriod`
- `0x1801a96ec`: `DeferFeatureUpdatesPeriodInDays`
- `0x1801a972c`: `DeferQualityUpdatesPeriodInDays`
- `0x1801a976c`: `DeferUpdatePeriod`
- `0x1801a98ac`: `DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection`
- `0x1801a992c`: `EngagedRestartDeadlineForFeatureUpdates`
- `0x1801a99ac`: `EngagedRestartSnoozeScheduleForFeatureUpdates`
- `0x1801a9a2c`: `EngagedRestartTransitionScheduleForFeatureUpdates`
- `0x1801a9a6c`: `ExcludeWUDriversInQualityUpdate`
- `0x1801a9b2c`: `IgnoreMOUpdateDownloadLimit`
- `0x1801a9bec`: `PauseFeatureUpdates`
- `0x1801a9c2c`: `PauseFeatureUpdatesStartTime`
- `0x1801a9c6c`: `PauseQualityUpdates`
- `0x1801a9cac`: `PauseQualityUpdatesStartTime`
- `0x1801a9cec`: `PhoneUpdateRestrictions`
- `0x1801a9d6c`: `RequireUpdateApproval`
- `0x1801a9dac`: `ScheduledInstallDay`
- `0x1801a9dec`: `ScheduledInstallEveryWeek`
- `0x1801a9e2c`: `ScheduledInstallFirstWeek`
- `0x1801a9e6c`: `ScheduledInstallFourthWeek`
- `0x1801a9eac`: `ScheduledInstallSecondWeek`
- `0x1801a9eec`: `ScheduledInstallThirdWeek`
- `0x1801a9f2c`: `ScheduledInstallTime`
- `0x1801aa02c`: `SetDisablePauseUXAccess`
- `0x1801aa06c`: `SetDisableUXWUAccess`
- `0x1801aa0ec`: `SetPolicyDrivenUpdateSourceForDriverUpdates`
- `0x1801aa12c`: `SetPolicyDrivenUpdateSourceForFeatureUpdates`
- `0x1801aa16c`: `SetPolicyDrivenUpdateSourceForOtherUpdates`
- `0x1801aa1ac`: `SetPolicyDrivenUpdateSourceForQualityUpdates`
- `0x1801aa1ec`: `SetProxyBehaviorForUpdateDetection`
- `0x1801aa2ac`: `UpdateNotificationLevel`
- `0x1801aa2ec`: `UpdateServiceUrl`
- `0x1801aa32c`: `UpdateServiceUrlAlternate`
- `0x1801a9095`: `CreateInstanceStart`
- `0x1801aa472`: `CreateInstanceEnd`
- `0x1801a8fdc`: `MDM_Policy_Result01_Update02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Result01_Update02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-378h] BYREF
  char v9; // [rsp+48h] [rbp-370h]
  _QWORD v10[5]; // [rsp+50h] [rbp-368h] BYREF
  char v11; // [rsp+78h] [rbp-340h]
  int v12; // [rsp+80h] [rbp-338h] BYREF
  char v13; // [rsp+84h] [rbp-334h]
  _BYTE v14[16]; // [rsp+88h] [rbp-330h] BYREF
  _DWORD v15[6]; // [rsp+98h] [rbp-320h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-308h] BYREF

  memset_0(&instance, 0, 0x2D8u);
  v12 = 0;
  v13 = 0;
  v10[0] = &TelemetryEventWriter::`vftable';
  v10[1] = &v12;
  v10[2] = "MDM_Policy_Result01_Update02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_18033F9A8,
      v14,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    inserted = 4;
    goto LABEL_321;
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
               (struct WmiNodeInfo *)&MDM_Policy_Result01_Update02_NodeList,
               0x4Bu,
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
      goto LABEL_321;
    }
    WmiRequestHandler::SetRequestMIInstance(v8, a2, (struct WmiNodeInfo *)&MDM_Policy_Result01_Update02_NodeList, 0x4Bu);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ActiveHoursEnd", (LONG *)a2[1].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
LABEL_316:
        (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        goto LABEL_321;
      }
    }
    if ( BYTE4(a2[1].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ActiveHoursMaxRange", (LONG *)&a2[1].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[1].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ActiveHoursStart", (LONG *)&a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAutoUpdate", (LONG *)&a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[2].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowOptionalContent", (LONG *)&a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowMUUpdateService", (LONG *)a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[2].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowUpdateService", (LONG *)&a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AutomaticMaintenanceWakeUp", (LONG *)&a2[2].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AutoRestartDeadlinePeriodInDays", (LONG *)&a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[3].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"BranchReadinessLevel", (LONG *)a2[3].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[4].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureDeadlineNoAutoReboot", (LONG *)&a2[4].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[4].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DeferQualityUpdatesPeriodInDays", (LONG *)a2[4].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[4].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DeferUpdatePeriod", (LONG *)&a2[4].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[4].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DeferUpgradePeriod", (LONG *)&a2[4].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DetectionFrequency", (LONG *)&a2[4].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[5].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableDualScan", (LONG *)&a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableWUfBSafeguards", (LONG *)&a2[5].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[5].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EngagedRestartDeadline", (LONG *)&a2[5].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[6].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"FillEmptyContentUrls", (LONG *)&a2[6].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[6].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"IgnoreMOAppDownloadLimit", (LONG *)&a2[6].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[6].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"IgnoreMOUpdateDownloadLimit", (LONG *)a2[6].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[6].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ManagePreviewBuilds", (LONG *)&a2[6].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[6].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseDeferrals", (LONG *)&a2[6].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[6].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseFeatureUpdates", (LONG *)&a2[6].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( LOBYTE(a2[7].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseFeatureUpdatesStartTime", (LONG *)&a2[7]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[7].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseQualityUpdates", (LONG *)&a2[7].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( LOBYTE(a2[7].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseQualityUpdatesStartTime", (LONG *)&a2[7].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[7].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PhoneUpdateRestrictions", (LONG *)&a2[7].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[7].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RequireDeferUpgrade", (LONG *)&a2[7].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[7].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RequireUpdateApproval", (LONG *)&a2[7].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[8].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallDay", (LONG *)&a2[8]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[8].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallEveryWeek", (LONG *)&a2[8].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[8].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallFirstWeek", (LONG *)&a2[8].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[8].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallFourthWeek", (LONG *)&a2[8].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[8].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallSecondWeek", (LONG *)a2[8].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[8].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallThirdWeek", (LONG *)&a2[8].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[8].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallTime", (LONG *)&a2[8].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[9].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleRestartWarning", (LONG *)&a2[9]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[9].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDisablePauseUXAccess", (LONG *)&a2[9].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[9].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDisableUXWUAccess", (LONG *)&a2[9].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[9].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetEDURestart", (LONG *)a2[9].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
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
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( LOBYTE(a2[10].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProductVersion", (LONG *)&a2[10].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( LOBYTE(a2[10].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"TargetReleaseVersion", (LONG *)a2[10].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[10].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UpdateNotificationLevel", (LONG *)&a2[10].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( LOBYTE(a2[11].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UpdateServiceUrl", (LONG *)&a2[10].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( LOBYTE(a2[11].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UpdateServiceUrlAlternate", (LONG *)&a2[11].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_321;
      goto LABEL_316;
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_321;
      goto LABEL_316;
    }
    inserted = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Update02_rtti, &instance);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_321;
      goto LABEL_316;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v8 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_321:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "CreateInstanceEnd", inserted);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_1803601EB,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return inserted;
}

```

## disassembly

```asm
0x1801a8f6c  mov     [rsp+arg_10], rsi
0x1801a8f71  mov     [rsp+arg_18], rdi
0x1801a8f76  push    r12
0x1801a8f78  push    r14
0x1801a8f7a  push    r15
0x1801a8f7c  sub     rsp, 3A0h
0x1801a8f83  mov     rax, cs:__security_cookie
0x1801a8f8a  xor     rax, rsp
0x1801a8f8d  mov     [rsp+3B8h+var_28], rax
0x1801a8f95  mov     rsi, rdx
0x1801a8f98  mov     r15, rcx
0x1801a8f9b  xor     edx, edx; Val
0x1801a8f9d  mov     r8d, 2D8h; Size
0x1801a8fa3  lea     rcx, [rsp+3B8h+instance]; void *
0x1801a8fab  call    memset_0
0x1801a8fb0  mov     [rsp+3B8h+var_338], 0
0x1801a8fbb  mov     [rsp+3B8h+var_334], 0
0x1801a8fc3  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801a8fca  mov     [rsp+3B8h+var_368], rax
0x1801a8fcf  lea     rax, [rsp+3B8h+var_338]
0x1801a8fd7  mov     [rsp+3B8h+var_360], rax
0x1801a8fdc  lea     rax, aMdmPolicyResul_174; "MDM_Policy_Result01_Update02"
0x1801a8fe3  mov     [rsp+3B8h+var_358], rax
0x1801a8fe8  lea     rcx, [rsp+3B8h+var_338]
0x1801a8ff0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801a8ff5  mov     eax, cs:dword_180380B68
0x1801a8ffb  cmp     eax, 5
0x1801a8ffe  jbe     short loc_1801A9074
0x1801a9000  mov     rdx, 200000000000h
0x1801a900a  lea     rcx, dword_180380B68
0x1801a9011  call    _tlgKeywordOn
0x1801a9016  test    al, al
0x1801a9018  jz      short loc_1801A9074
0x1801a901a  cmp     [rsp+3B8h+var_334], 0
0x1801a9022  jz      short loc_1801A9056
0x1801a9024  cmp     [rsp+3B8h+var_320], 0
0x1801a902c  jnz     short loc_1801A904C
0x1801a902e  cmp     [rsp+3B8h+var_31C], 0
0x1801a9036  jnz     short loc_1801A904C
0x1801a9038  cmp     [rsp+3B8h+var_318], 0
0x1801a9040  jnz     short loc_1801A904C
0x1801a9042  cmp     [rsp+3B8h+var_314], 0
0x1801a904a  jz      short loc_1801A9056
0x1801a904c  lea     r9, [rsp+3B8h+var_320]
0x1801a9054  jmp     short loc_1801A9059
0x1801a9056  xor     r9d, r9d
0x1801a9059  lea     r8, [rsp+3B8h+var_330]
0x1801a9061  lea     rdx, qword_18033F9A8
0x1801a9068  lea     rcx, dword_180380B68
0x1801a906f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801a9074  cmp     byte ptr [rsi+48h], 0
0x1801a9078  jz      loc_1801AA46A
0x1801a907e  mov     [rsp+3B8h+var_370], 0
0x1801a9083  cmp     byte ptr [rsi+58h], 0
0x1801a9087  jz      loc_1801AA46A
0x1801a908d  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801a9091  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801a9095  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1801a909c  lea     rcx, [rsp+3B8h+var_368]; this
0x1801a90a1  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801a90a6  nop
0x1801a90a7  mov     [rsp+3B8h+var_378], 0
0x1801a90b0  lea     rax, [rsp+3B8h+var_378]
0x1801a90b5  mov     [rsp+3B8h+var_388], rax
0x1801a90ba  mov     [rsp+3B8h+var_390], 4
0x1801a90c2  mov     [rsp+3B8h+var_398], 4Bh ; 'K'
0x1801a90ca  lea     r9, ?MDM_Policy_Result01_Update02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Update02_NodeList
0x1801a90d1  mov     r8, [rsi+40h]
0x1801a90d5  mov     rdx, [rsi+50h]
0x1801a90d9  mov     rcx, r15
0x1801a90dc  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801a90e1  mov     edi, eax
0x1801a90e3  test    eax, eax
0x1801a90e5  jz      short loc_1801A90EC
0x1801a90e7  jmp     loc_1801AA46F
0x1801a90ec  lea     rax, [rsp+3B8h+var_378]
0x1801a90f1  mov     [rsp+3B8h+var_348], rax
0x1801a90f6  mov     r12d, 1
0x1801a90fc  mov     [rsp+3B8h+var_340], r12b
0x1801a9101  mov     r14, [rsp+3B8h+var_378]
0x1801a9106  test    r14, r14
0x1801a9109  jnz     short loc_1801A9113
0x1801a910b  mov     edi, r12d
0x1801a910e  jmp     loc_1801AA46F
0x1801a9113  mov     r9d, 4Bh ; 'K'; unsigned int
0x1801a9119  lea     r8, ?MDM_Policy_Result01_Update02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801a9120  mov     rdx, rsi; struct _MI_Instance *
0x1801a9123  mov     rcx, r14; this
0x1801a9126  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801a912b  lea     r8, [rsi+60h]; void *
0x1801a912f  cmp     [r8+4], r12b
0x1801a9133  jnz     short loc_1801A9168
0x1801a9135  lea     rdx, aActivehoursend; "ActiveHoursEnd"
0x1801a913c  mov     rcx, r14; this
0x1801a913f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a9144  mov     edi, eax
0x1801a9146  test    eax, eax
0x1801a9148  jz      short loc_1801A9168
0x1801a914a  mov     rcx, [rsp+3B8h+var_378]
0x1801a914f  test    rcx, rcx
0x1801a9152  jz      short loc_1801A9163
0x1801a9154  mov     rax, [rcx]
0x1801a9157  mov     edx, r12d
0x1801a915a  mov     rax, [rax]
0x1801a915d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9162  nop
0x1801a9163  jmp     loc_1801AA46F
0x1801a9168  lea     r8, [rsi+68h]; void *
0x1801a916c  cmp     [r8+4], r12b
0x1801a9170  jnz     short loc_1801A91A5
0x1801a9172  lea     rdx, aActivehoursmax; "ActiveHoursMaxRange"
0x1801a9179  mov     rcx, r14; this
0x1801a917c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a9181  mov     edi, eax
0x1801a9183  test    eax, eax
0x1801a9185  jz      short loc_1801A91A5
0x1801a9187  mov     rcx, [rsp+3B8h+var_378]
0x1801a918c  test    rcx, rcx
0x1801a918f  jz      short loc_1801A91A0
0x1801a9191  mov     rax, [rcx]
0x1801a9194  mov     edx, r12d
0x1801a9197  mov     rax, [rax]
0x1801a919a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a919f  nop
0x1801a91a0  jmp     loc_1801AA46F
0x1801a91a5  lea     r8, [rsi+70h]; void *
0x1801a91a9  cmp     [r8+4], r12b
0x1801a91ad  jnz     short loc_1801A91E2
0x1801a91af  lea     rdx, aActivehourssta; "ActiveHoursStart"
0x1801a91b6  mov     rcx, r14; this
0x1801a91b9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a91be  mov     edi, eax
0x1801a91c0  test    eax, eax
0x1801a91c2  jz      short loc_1801A91E2
0x1801a91c4  mov     rcx, [rsp+3B8h+var_378]
0x1801a91c9  test    rcx, rcx
0x1801a91cc  jz      short loc_1801A91DD
0x1801a91ce  mov     rax, [rcx]
0x1801a91d1  mov     edx, r12d
0x1801a91d4  mov     rax, [rax]
0x1801a91d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a91dc  nop
0x1801a91dd  jmp     loc_1801AA46F
0x1801a91e2  lea     r8, [rsi+78h]; void *
0x1801a91e6  cmp     [r8+4], r12b
0x1801a91ea  jnz     short loc_1801A921F
0x1801a91ec  lea     rdx, aAllowautoupdat; "AllowAutoUpdate"
0x1801a91f3  mov     rcx, r14; this
0x1801a91f6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a91fb  mov     edi, eax
0x1801a91fd  test    eax, eax
0x1801a91ff  jz      short loc_1801A921F
0x1801a9201  mov     rcx, [rsp+3B8h+var_378]
0x1801a9206  test    rcx, rcx
0x1801a9209  jz      short loc_1801A921A
0x1801a920b  mov     rax, [rcx]
0x1801a920e  mov     edx, r12d
0x1801a9211  mov     rax, [rax]
0x1801a9214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9219  nop
0x1801a921a  jmp     loc_1801AA46F
0x1801a921f  lea     r8, [rsi+80h]; void *
0x1801a9226  cmp     [r8+4], r12b
0x1801a922a  jnz     short loc_1801A925F
0x1801a922c  lea     rdx, aAllowautowindo; "AllowAutoWindowsUpdateDownloadOverMeter"...
0x1801a9233  mov     rcx, r14; this
0x1801a9236  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a923b  mov     edi, eax
0x1801a923d  test    eax, eax
0x1801a923f  jz      short loc_1801A925F
0x1801a9241  mov     rcx, [rsp+3B8h+var_378]
0x1801a9246  test    rcx, rcx
0x1801a9249  jz      short loc_1801A925A
0x1801a924b  mov     rax, [rcx]
0x1801a924e  mov     edx, r12d
0x1801a9251  mov     rax, [rax]
0x1801a9254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9259  nop
0x1801a925a  jmp     loc_1801AA46F
0x1801a925f  lea     r8, [rsi+88h]; void *
0x1801a9266  cmp     [r8+4], r12b
0x1801a926a  jnz     short loc_1801A929F
0x1801a926c  lea     rdx, aAllowtemporary; "AllowTemporaryEnterpriseFeatureControl"
0x1801a9273  mov     rcx, r14; this
0x1801a9276  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a927b  mov     edi, eax
0x1801a927d  test    eax, eax
0x1801a927f  jz      short loc_1801A929F
0x1801a9281  mov     rcx, [rsp+3B8h+var_378]
0x1801a9286  test    rcx, rcx
0x1801a9289  jz      short loc_1801A929A
0x1801a928b  mov     rax, [rcx]
0x1801a928e  mov     edx, r12d
0x1801a9291  mov     rax, [rax]
0x1801a9294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9299  nop
0x1801a929a  jmp     loc_1801AA46F
0x1801a929f  lea     r8, [rsi+90h]; void *
0x1801a92a6  cmp     [r8+4], r12b
0x1801a92aa  jnz     short loc_1801A92DF
0x1801a92ac  lea     rdx, aAllowoptionalc; "AllowOptionalContent"
0x1801a92b3  mov     rcx, r14; this
0x1801a92b6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a92bb  mov     edi, eax
0x1801a92bd  test    eax, eax
0x1801a92bf  jz      short loc_1801A92DF
0x1801a92c1  mov     rcx, [rsp+3B8h+var_378]
0x1801a92c6  test    rcx, rcx
0x1801a92c9  jz      short loc_1801A92DA
0x1801a92cb  mov     rax, [rcx]
0x1801a92ce  mov     edx, r12d
0x1801a92d1  mov     rax, [rax]
0x1801a92d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a92d9  nop
0x1801a92da  jmp     loc_1801AA46F
0x1801a92df  lea     r8, [rsi+98h]; void *
0x1801a92e6  cmp     [r8+4], r12b
0x1801a92ea  jnz     short loc_1801A931F
0x1801a92ec  lea     rdx, aAlwaysautorebo; "AlwaysAutoRebootAtScheduledTimeMinutes"
0x1801a92f3  mov     rcx, r14; this
0x1801a92f6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a92fb  mov     edi, eax
0x1801a92fd  test    eax, eax
0x1801a92ff  jz      short loc_1801A931F
0x1801a9301  mov     rcx, [rsp+3B8h+var_378]
0x1801a9306  test    rcx, rcx
0x1801a9309  jz      short loc_1801A931A
0x1801a930b  mov     rax, [rcx]
0x1801a930e  mov     edx, r12d
0x1801a9311  mov     rax, [rax]
0x1801a9314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9319  nop
0x1801a931a  jmp     loc_1801AA46F
0x1801a931f  lea     r8, [rsi+0A0h]; void *
0x1801a9326  cmp     [r8+4], r12b
0x1801a932a  jnz     short loc_1801A935F
0x1801a932c  lea     rdx, aAllowmuupdates; "AllowMUUpdateService"
0x1801a9333  mov     rcx, r14; this
0x1801a9336  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a933b  mov     edi, eax
0x1801a933d  test    eax, eax
0x1801a933f  jz      short loc_1801A935F
0x1801a9341  mov     rcx, [rsp+3B8h+var_378]
0x1801a9346  test    rcx, rcx
0x1801a9349  jz      short loc_1801A935A
0x1801a934b  mov     rax, [rcx]
0x1801a934e  mov     edx, r12d
0x1801a9351  mov     rax, [rax]
0x1801a9354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9359  nop
0x1801a935a  jmp     loc_1801AA46F
0x1801a935f  lea     r8, [rsi+0A8h]; void *
0x1801a9366  cmp     [r8+4], r12b
0x1801a936a  jnz     short loc_1801A939F
0x1801a936c  lea     rdx, aAllownonmicros; "AllowNonMicrosoftSignedUpdate"
0x1801a9373  mov     rcx, r14; this
0x1801a9376  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a937b  mov     edi, eax
0x1801a937d  test    eax, eax
0x1801a937f  jz      short loc_1801A939F
0x1801a9381  mov     rcx, [rsp+3B8h+var_378]
0x1801a9386  test    rcx, rcx
0x1801a9389  jz      short loc_1801A939A
0x1801a938b  mov     rax, [rcx]
0x1801a938e  mov     edx, r12d
0x1801a9391  mov     rax, [rax]
0x1801a9394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9399  nop
0x1801a939a  jmp     loc_1801AA46F
0x1801a939f  lea     r8, [rsi+0B0h]; void *
0x1801a93a6  cmp     [r8+4], r12b
0x1801a93aa  jnz     short loc_1801A93DF
0x1801a93ac  lea     rdx, aAllowupdateser; "AllowUpdateService"
0x1801a93b3  mov     rcx, r14; this
0x1801a93b6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a93bb  mov     edi, eax
0x1801a93bd  test    eax, eax
0x1801a93bf  jz      short loc_1801A93DF
0x1801a93c1  mov     rcx, [rsp+3B8h+var_378]
0x1801a93c6  test    rcx, rcx
0x1801a93c9  jz      short loc_1801A93DA
0x1801a93cb  mov     rax, [rcx]
0x1801a93ce  mov     edx, r12d
0x1801a93d1  mov     rax, [rax]
0x1801a93d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a93d9  nop
0x1801a93da  jmp     loc_1801AA46F
0x1801a93df  lea     r8, [rsi+0B8h]; void *
0x1801a93e6  cmp     [r8+4], r12b
0x1801a93ea  jnz     short loc_1801A941F
0x1801a93ec  lea     rdx, aAutomaticmaint; "AutomaticMaintenanceWakeUp"
0x1801a93f3  mov     rcx, r14; this
0x1801a93f6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a93fb  mov     edi, eax
0x1801a93fd  test    eax, eax
0x1801a93ff  jz      short loc_1801A941F
0x1801a9401  mov     rcx, [rsp+3B8h+var_378]
0x1801a9406  test    rcx, rcx
0x1801a9409  jz      short loc_1801A941A
0x1801a940b  mov     rax, [rcx]
  ... truncated ...
```
