# MDM_Policy_Result01_Update02_InvokeCreateInstance

- ea: `0x1801a8aec`
- end: `0x1801aa08c`
- name: `MDM_Policy_Result01_Update02_InvokeCreateInstance`
- size: `5536`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801a8a30`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1801a8aec`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1801a8d6c`: `AllowAutoUpdate`
- `0x1801a8dac`: `AllowAutoWindowsUpdateDownloadOverMeteredNetwork`
- `0x1801a8dec`: `AllowTemporaryEnterpriseFeatureControl`
- `0x1801a8e6c`: `AlwaysAutoRebootAtScheduledTimeMinutes`
- `0x1801a8eac`: `AllowMUUpdateService`
- `0x1801a8eec`: `AllowNonMicrosoftSignedUpdate`
- `0x1801a8f2c`: `AllowUpdateService`
- `0x1801a8fec`: `AutoRestartDeadlinePeriodInDaysForFeatureUpdates`
- `0x1801a90ac`: `BranchReadinessLevel`
- `0x1801a90ec`: `ConfigureDeadlineForFeatureUpdates`
- `0x1801a912c`: `ConfigureDeadlineForQualityUpdates`
- `0x1801a916c`: `ConfigureDeadlineGracePeriod`
- `0x1801a91ac`: `ConfigureDeadlineGracePeriodForFeatureUpdates`
- `0x1801a91ec`: `ConfigureDeadlineNoAutoReboot`
- `0x1801a922c`: `ConfigureFeatureUpdateUninstallPeriod`
- `0x1801a926c`: `DeferFeatureUpdatesPeriodInDays`
- `0x1801a92ac`: `DeferQualityUpdatesPeriodInDays`
- `0x1801a92ec`: `DeferUpdatePeriod`
- `0x1801a942c`: `DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection`
- `0x1801a94ac`: `EngagedRestartDeadlineForFeatureUpdates`
- `0x1801a952c`: `EngagedRestartSnoozeScheduleForFeatureUpdates`
- `0x1801a95ac`: `EngagedRestartTransitionScheduleForFeatureUpdates`
- `0x1801a95ec`: `ExcludeWUDriversInQualityUpdate`
- `0x1801a96ac`: `IgnoreMOUpdateDownloadLimit`
- `0x1801a976c`: `PauseFeatureUpdates`
- `0x1801a97ac`: `PauseFeatureUpdatesStartTime`
- `0x1801a97ec`: `PauseQualityUpdates`
- `0x1801a982c`: `PauseQualityUpdatesStartTime`
- `0x1801a986c`: `PhoneUpdateRestrictions`
- `0x1801a98ec`: `RequireUpdateApproval`
- `0x1801a992c`: `ScheduledInstallDay`
- `0x1801a996c`: `ScheduledInstallEveryWeek`
- `0x1801a99ac`: `ScheduledInstallFirstWeek`
- `0x1801a99ec`: `ScheduledInstallFourthWeek`
- `0x1801a9a2c`: `ScheduledInstallSecondWeek`
- `0x1801a9a6c`: `ScheduledInstallThirdWeek`
- `0x1801a9aac`: `ScheduledInstallTime`
- `0x1801a9bac`: `SetDisablePauseUXAccess`
- `0x1801a9bec`: `SetDisableUXWUAccess`
- `0x1801a9c6c`: `SetPolicyDrivenUpdateSourceForDriverUpdates`
- `0x1801a9cac`: `SetPolicyDrivenUpdateSourceForFeatureUpdates`
- `0x1801a9cec`: `SetPolicyDrivenUpdateSourceForOtherUpdates`
- `0x1801a9d2c`: `SetPolicyDrivenUpdateSourceForQualityUpdates`
- `0x1801a9d6c`: `SetProxyBehaviorForUpdateDetection`
- `0x1801a9e2c`: `UpdateNotificationLevel`
- `0x1801a9e6c`: `UpdateServiceUrl`
- `0x1801a9eac`: `UpdateServiceUrlAlternate`
- `0x1801a8c15`: `CreateInstanceStart`
- `0x1801a9ff2`: `CreateInstanceEnd`
- `0x1801a8b5c`: `MDM_Policy_Result01_Update02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Result01_Update02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
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
    inserted = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_321;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v10,
    "CreateInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v8 = 0;
  inserted = (unsigned int)CreateRequestHandlerInstance(
                             self,
                             a2[1].serverName,
                             a2[1].ft,
                             &MDM_Policy_Result01_Update02_NodeList,
                             75,
                             4,
                             &v8);
  if ( inserted == MI_RESULT_OK )
  {
    v10[4] = &v8;
    v11 = 1;
    v6 = v8;
    if ( !v8 )
    {
      inserted = MI_RESULT_FAILED;
      goto LABEL_321;
    }
    WmiRequestHandler::SetRequestMIInstance(v8, a2, (struct WmiNodeInfo *)&MDM_Policy_Result01_Update02_NodeList, 0x4Bu);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ActiveHoursEnd", a2[1].reserved);
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
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ActiveHoursMaxRange", &a2[1].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[1].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ActiveHoursStart", &a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAutoUpdate", &a2[1].reserved[3]);
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
                   &a2[2]);
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
                   &a2[2].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[2].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowOptionalContent", &a2[2].serverName);
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
                   &a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowMUUpdateService", a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowNonMicrosoftSignedUpdate", &a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[2].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowUpdateService", &a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AutomaticMaintenanceWakeUp", &a2[2].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AutoRestartDeadlinePeriodInDays", &a2[3]);
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
                   &a2[3].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[3].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AutoRestartNotificationSchedule", &a2[3].serverName);
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
                   &a2[3].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[3].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"BranchReadinessLevel", a2[3].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[3].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureDeadlineForFeatureUpdates", &a2[3].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[3].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureDeadlineForQualityUpdates", &a2[3].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[3].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureDeadlineGracePeriod", &a2[3].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureDeadlineGracePeriodForFeatureUpdates", &a2[4]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[4].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureDeadlineNoAutoReboot", &a2[4].classDecl);
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
                   &a2[4].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[4].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DeferFeatureUpdatesPeriodInDays", &a2[4].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[4].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DeferQualityUpdatesPeriodInDays", a2[4].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[4].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DeferUpdatePeriod", &a2[4].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[4].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DeferUpgradePeriod", &a2[4].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DetectionFrequency", &a2[4].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[5].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableDualScan", &a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableWUfBSafeguards", &a2[5].classDecl);
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
                   &a2[5].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[5].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EngagedRestartDeadline", &a2[5].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[5].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EngagedRestartDeadlineForFeatureUpdates", a2[5].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[5].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EngagedRestartSnoozeSchedule", &a2[5].reserved[1]);
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
                   &a2[5].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[5].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EngagedRestartTransitionSchedule", &a2[5].reserved[3]);
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
                   &a2[6]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[6].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludeWUDriversInQualityUpdate", &a2[6].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[6].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"FillEmptyContentUrls", &a2[6].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[6].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"IgnoreMOAppDownloadLimit", &a2[6].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[6].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"IgnoreMOUpdateDownloadLimit", a2[6].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[6].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ManagePreviewBuilds", &a2[6].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[6].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseDeferrals", &a2[6].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[6].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseFeatureUpdates", &a2[6].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( LOBYTE(a2[7].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseFeatureUpdatesStartTime", &a2[7]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[7].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseQualityUpdates", &a2[7].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( LOBYTE(a2[7].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseQualityUpdatesStartTime", &a2[7].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[7].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PhoneUpdateRestrictions", &a2[7].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[7].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RequireDeferUpgrade", &a2[7].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[7].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RequireUpdateApproval", &a2[7].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[8].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallDay", &a2[8]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[8].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallEveryWeek", &a2[8].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[8].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallFirstWeek", &a2[8].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[8].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallFourthWeek", &a2[8].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[8].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallSecondWeek", a2[8].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[8].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallThirdWeek", &a2[8].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[8].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallTime", &a2[8].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[8].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleImminentRestartWarning", &a2[8].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[9].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleRestartWarning", &a2[9]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[9].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetAutoRestartNotificationDisable", &a2[9].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[9].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDisablePauseUXAccess", &a2[9].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[9].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDisableUXWUAccess", &a2[9].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[9].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetEDURestart", a2[9].reserved);
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
                   &a2[9].reserved[1]);
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
                   &a2[9].reserved[2]);
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
                   &a2[9].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[10].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetPolicyDrivenUpdateSourceForQualityUpdates", &a2[10]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[10].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetProxyBehaviorForUpdateDetection", &a2[10].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( LOBYTE(a2[10].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProductVersion", &a2[10].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( LOBYTE(a2[10].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"TargetReleaseVersion", a2[10].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( BYTE4(a2[10].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UpdateNotificationLevel", &a2[10].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( LOBYTE(a2[11].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UpdateServiceUrl", &a2[10].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    if ( LOBYTE(a2[11].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UpdateServiceUrlAlternate", &a2[11].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_321;
        goto LABEL_316;
      }
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_321;
      goto LABEL_316;
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1801a8aec  mov     [rsp+arg_10], rsi
0x1801a8af1  mov     [rsp+arg_18], rdi
0x1801a8af6  push    r12
0x1801a8af8  push    r14
0x1801a8afa  push    r15
0x1801a8afc  sub     rsp, 3A0h
0x1801a8b03  mov     rax, cs:__security_cookie
0x1801a8b0a  xor     rax, rsp
0x1801a8b0d  mov     [rsp+3B8h+var_28], rax
0x1801a8b15  mov     rsi, rdx
0x1801a8b18  mov     r15, rcx
0x1801a8b1b  xor     edx, edx; Val
0x1801a8b1d  mov     r8d, 2D8h; Size
0x1801a8b23  lea     rcx, [rsp+3B8h+instance]; void *
0x1801a8b2b  call    memset_0
0x1801a8b30  mov     [rsp+3B8h+var_338], 0
0x1801a8b3b  mov     [rsp+3B8h+var_334], 0
0x1801a8b43  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801a8b4a  mov     [rsp+3B8h+var_368], rax
0x1801a8b4f  lea     rax, [rsp+3B8h+var_338]
0x1801a8b57  mov     [rsp+3B8h+var_360], rax
0x1801a8b5c  lea     rax, aMdmPolicyResul_174; "MDM_Policy_Result01_Update02"
0x1801a8b63  mov     [rsp+3B8h+var_358], rax
0x1801a8b68  lea     rcx, [rsp+3B8h+var_338]
0x1801a8b70  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801a8b75  mov     eax, cs:dword_180380B68
0x1801a8b7b  cmp     eax, 5
0x1801a8b7e  jbe     short loc_1801A8BF4
0x1801a8b80  mov     rdx, 200000000000h
0x1801a8b8a  lea     rcx, dword_180380B68
0x1801a8b91  call    _tlgKeywordOn
0x1801a8b96  test    al, al
0x1801a8b98  jz      short loc_1801A8BF4
0x1801a8b9a  cmp     [rsp+3B8h+var_334], 0
0x1801a8ba2  jz      short loc_1801A8BD6
0x1801a8ba4  cmp     [rsp+3B8h+var_320], 0
0x1801a8bac  jnz     short loc_1801A8BCC
0x1801a8bae  cmp     [rsp+3B8h+var_31C], 0
0x1801a8bb6  jnz     short loc_1801A8BCC
0x1801a8bb8  cmp     [rsp+3B8h+var_318], 0
0x1801a8bc0  jnz     short loc_1801A8BCC
0x1801a8bc2  cmp     [rsp+3B8h+var_314], 0
0x1801a8bca  jz      short loc_1801A8BD6
0x1801a8bcc  lea     r9, [rsp+3B8h+var_320]
0x1801a8bd4  jmp     short loc_1801A8BD9
0x1801a8bd6  xor     r9d, r9d
0x1801a8bd9  lea     r8, [rsp+3B8h+var_330]
0x1801a8be1  lea     rdx, qword_18033F9A8
0x1801a8be8  lea     rcx, dword_180380B68
0x1801a8bef  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801a8bf4  cmp     byte ptr [rsi+48h], 0
0x1801a8bf8  jz      loc_1801A9FEA
0x1801a8bfe  mov     [rsp+3B8h+var_370], 0
0x1801a8c03  cmp     byte ptr [rsi+58h], 0
0x1801a8c07  jz      loc_1801A9FEA
0x1801a8c0d  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801a8c11  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801a8c15  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1801a8c1c  lea     rcx, [rsp+3B8h+var_368]; this
0x1801a8c21  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801a8c26  nop
0x1801a8c27  mov     [rsp+3B8h+var_378], 0
0x1801a8c30  lea     rax, [rsp+3B8h+var_378]
0x1801a8c35  mov     [rsp+3B8h+var_388], rax
0x1801a8c3a  mov     [rsp+3B8h+var_390], 4
0x1801a8c42  mov     [rsp+3B8h+var_398], 4Bh ; 'K'
0x1801a8c4a  lea     r9, ?MDM_Policy_Result01_Update02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Update02_NodeList
0x1801a8c51  mov     r8, [rsi+40h]
0x1801a8c55  mov     rdx, [rsi+50h]
0x1801a8c59  mov     rcx, r15
0x1801a8c5c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801a8c61  mov     edi, eax
0x1801a8c63  test    eax, eax
0x1801a8c65  jz      short loc_1801A8C6C
0x1801a8c67  jmp     loc_1801A9FEF
0x1801a8c6c  lea     rax, [rsp+3B8h+var_378]
0x1801a8c71  mov     [rsp+3B8h+var_348], rax
0x1801a8c76  mov     r12d, 1
0x1801a8c7c  mov     [rsp+3B8h+var_340], r12b
0x1801a8c81  mov     r14, [rsp+3B8h+var_378]
0x1801a8c86  test    r14, r14
0x1801a8c89  jnz     short loc_1801A8C93
0x1801a8c8b  mov     edi, r12d
0x1801a8c8e  jmp     loc_1801A9FEF
0x1801a8c93  mov     r9d, 4Bh ; 'K'; unsigned int
0x1801a8c99  lea     r8, ?MDM_Policy_Result01_Update02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801a8ca0  mov     rdx, rsi; struct _MI_Instance *
0x1801a8ca3  mov     rcx, r14; this
0x1801a8ca6  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801a8cab  lea     r8, [rsi+60h]; void *
0x1801a8caf  cmp     [r8+4], r12b
0x1801a8cb3  jnz     short loc_1801A8CE8
0x1801a8cb5  lea     rdx, aActivehoursend; "ActiveHoursEnd"
0x1801a8cbc  mov     rcx, r14; this
0x1801a8cbf  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a8cc4  mov     edi, eax
0x1801a8cc6  test    eax, eax
0x1801a8cc8  jz      short loc_1801A8CE8
0x1801a8cca  mov     rcx, [rsp+3B8h+var_378]
0x1801a8ccf  test    rcx, rcx
0x1801a8cd2  jz      short loc_1801A8CE3
0x1801a8cd4  mov     rax, [rcx]
0x1801a8cd7  mov     edx, r12d
0x1801a8cda  mov     rax, [rax]
0x1801a8cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8ce2  nop
0x1801a8ce3  jmp     loc_1801A9FEF
0x1801a8ce8  lea     r8, [rsi+68h]; void *
0x1801a8cec  cmp     [r8+4], r12b
0x1801a8cf0  jnz     short loc_1801A8D25
0x1801a8cf2  lea     rdx, aActivehoursmax; "ActiveHoursMaxRange"
0x1801a8cf9  mov     rcx, r14; this
0x1801a8cfc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a8d01  mov     edi, eax
0x1801a8d03  test    eax, eax
0x1801a8d05  jz      short loc_1801A8D25
0x1801a8d07  mov     rcx, [rsp+3B8h+var_378]
0x1801a8d0c  test    rcx, rcx
0x1801a8d0f  jz      short loc_1801A8D20
0x1801a8d11  mov     rax, [rcx]
0x1801a8d14  mov     edx, r12d
0x1801a8d17  mov     rax, [rax]
0x1801a8d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8d1f  nop
0x1801a8d20  jmp     loc_1801A9FEF
0x1801a8d25  lea     r8, [rsi+70h]; void *
0x1801a8d29  cmp     [r8+4], r12b
0x1801a8d2d  jnz     short loc_1801A8D62
0x1801a8d2f  lea     rdx, aActivehourssta; "ActiveHoursStart"
0x1801a8d36  mov     rcx, r14; this
0x1801a8d39  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a8d3e  mov     edi, eax
0x1801a8d40  test    eax, eax
0x1801a8d42  jz      short loc_1801A8D62
0x1801a8d44  mov     rcx, [rsp+3B8h+var_378]
0x1801a8d49  test    rcx, rcx
0x1801a8d4c  jz      short loc_1801A8D5D
0x1801a8d4e  mov     rax, [rcx]
0x1801a8d51  mov     edx, r12d
0x1801a8d54  mov     rax, [rax]
0x1801a8d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8d5c  nop
0x1801a8d5d  jmp     loc_1801A9FEF
0x1801a8d62  lea     r8, [rsi+78h]; void *
0x1801a8d66  cmp     [r8+4], r12b
0x1801a8d6a  jnz     short loc_1801A8D9F
0x1801a8d6c  lea     rdx, aAllowautoupdat; "AllowAutoUpdate"
0x1801a8d73  mov     rcx, r14; this
0x1801a8d76  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a8d7b  mov     edi, eax
0x1801a8d7d  test    eax, eax
0x1801a8d7f  jz      short loc_1801A8D9F
0x1801a8d81  mov     rcx, [rsp+3B8h+var_378]
0x1801a8d86  test    rcx, rcx
0x1801a8d89  jz      short loc_1801A8D9A
0x1801a8d8b  mov     rax, [rcx]
0x1801a8d8e  mov     edx, r12d
0x1801a8d91  mov     rax, [rax]
0x1801a8d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8d99  nop
0x1801a8d9a  jmp     loc_1801A9FEF
0x1801a8d9f  lea     r8, [rsi+80h]; void *
0x1801a8da6  cmp     [r8+4], r12b
0x1801a8daa  jnz     short loc_1801A8DDF
0x1801a8dac  lea     rdx, aAllowautowindo; "AllowAutoWindowsUpdateDownloadOverMeter"...
0x1801a8db3  mov     rcx, r14; this
0x1801a8db6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a8dbb  mov     edi, eax
0x1801a8dbd  test    eax, eax
0x1801a8dbf  jz      short loc_1801A8DDF
0x1801a8dc1  mov     rcx, [rsp+3B8h+var_378]
0x1801a8dc6  test    rcx, rcx
0x1801a8dc9  jz      short loc_1801A8DDA
0x1801a8dcb  mov     rax, [rcx]
0x1801a8dce  mov     edx, r12d
0x1801a8dd1  mov     rax, [rax]
0x1801a8dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8dd9  nop
0x1801a8dda  jmp     loc_1801A9FEF
0x1801a8ddf  lea     r8, [rsi+88h]; void *
0x1801a8de6  cmp     [r8+4], r12b
0x1801a8dea  jnz     short loc_1801A8E1F
0x1801a8dec  lea     rdx, aAllowtemporary; "AllowTemporaryEnterpriseFeatureControl"
0x1801a8df3  mov     rcx, r14; this
0x1801a8df6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a8dfb  mov     edi, eax
0x1801a8dfd  test    eax, eax
0x1801a8dff  jz      short loc_1801A8E1F
0x1801a8e01  mov     rcx, [rsp+3B8h+var_378]
0x1801a8e06  test    rcx, rcx
0x1801a8e09  jz      short loc_1801A8E1A
0x1801a8e0b  mov     rax, [rcx]
0x1801a8e0e  mov     edx, r12d
0x1801a8e11  mov     rax, [rax]
0x1801a8e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8e19  nop
0x1801a8e1a  jmp     loc_1801A9FEF
0x1801a8e1f  lea     r8, [rsi+90h]; void *
0x1801a8e26  cmp     [r8+4], r12b
0x1801a8e2a  jnz     short loc_1801A8E5F
0x1801a8e2c  lea     rdx, aAllowoptionalc; "AllowOptionalContent"
0x1801a8e33  mov     rcx, r14; this
0x1801a8e36  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a8e3b  mov     edi, eax
0x1801a8e3d  test    eax, eax
0x1801a8e3f  jz      short loc_1801A8E5F
0x1801a8e41  mov     rcx, [rsp+3B8h+var_378]
0x1801a8e46  test    rcx, rcx
0x1801a8e49  jz      short loc_1801A8E5A
0x1801a8e4b  mov     rax, [rcx]
0x1801a8e4e  mov     edx, r12d
0x1801a8e51  mov     rax, [rax]
0x1801a8e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8e59  nop
0x1801a8e5a  jmp     loc_1801A9FEF
0x1801a8e5f  lea     r8, [rsi+98h]; void *
0x1801a8e66  cmp     [r8+4], r12b
0x1801a8e6a  jnz     short loc_1801A8E9F
0x1801a8e6c  lea     rdx, aAlwaysautorebo; "AlwaysAutoRebootAtScheduledTimeMinutes"
0x1801a8e73  mov     rcx, r14; this
0x1801a8e76  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a8e7b  mov     edi, eax
0x1801a8e7d  test    eax, eax
0x1801a8e7f  jz      short loc_1801A8E9F
0x1801a8e81  mov     rcx, [rsp+3B8h+var_378]
0x1801a8e86  test    rcx, rcx
0x1801a8e89  jz      short loc_1801A8E9A
0x1801a8e8b  mov     rax, [rcx]
0x1801a8e8e  mov     edx, r12d
0x1801a8e91  mov     rax, [rax]
0x1801a8e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8e99  nop
0x1801a8e9a  jmp     loc_1801A9FEF
0x1801a8e9f  lea     r8, [rsi+0A0h]; void *
0x1801a8ea6  cmp     [r8+4], r12b
0x1801a8eaa  jnz     short loc_1801A8EDF
0x1801a8eac  lea     rdx, aAllowmuupdates; "AllowMUUpdateService"
0x1801a8eb3  mov     rcx, r14; this
0x1801a8eb6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a8ebb  mov     edi, eax
0x1801a8ebd  test    eax, eax
0x1801a8ebf  jz      short loc_1801A8EDF
0x1801a8ec1  mov     rcx, [rsp+3B8h+var_378]
0x1801a8ec6  test    rcx, rcx
0x1801a8ec9  jz      short loc_1801A8EDA
0x1801a8ecb  mov     rax, [rcx]
0x1801a8ece  mov     edx, r12d
0x1801a8ed1  mov     rax, [rax]
0x1801a8ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8ed9  nop
0x1801a8eda  jmp     loc_1801A9FEF
0x1801a8edf  lea     r8, [rsi+0A8h]; void *
0x1801a8ee6  cmp     [r8+4], r12b
0x1801a8eea  jnz     short loc_1801A8F1F
0x1801a8eec  lea     rdx, aAllownonmicros; "AllowNonMicrosoftSignedUpdate"
0x1801a8ef3  mov     rcx, r14; this
0x1801a8ef6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a8efb  mov     edi, eax
0x1801a8efd  test    eax, eax
0x1801a8eff  jz      short loc_1801A8F1F
0x1801a8f01  mov     rcx, [rsp+3B8h+var_378]
0x1801a8f06  test    rcx, rcx
0x1801a8f09  jz      short loc_1801A8F1A
0x1801a8f0b  mov     rax, [rcx]
0x1801a8f0e  mov     edx, r12d
0x1801a8f11  mov     rax, [rax]
0x1801a8f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8f19  nop
0x1801a8f1a  jmp     loc_1801A9FEF
0x1801a8f1f  lea     r8, [rsi+0B0h]; void *
0x1801a8f26  cmp     [r8+4], r12b
0x1801a8f2a  jnz     short loc_1801A8F5F
0x1801a8f2c  lea     rdx, aAllowupdateser; "AllowUpdateService"
0x1801a8f33  mov     rcx, r14; this
0x1801a8f36  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a8f3b  mov     edi, eax
0x1801a8f3d  test    eax, eax
0x1801a8f3f  jz      short loc_1801A8F5F
0x1801a8f41  mov     rcx, [rsp+3B8h+var_378]
0x1801a8f46  test    rcx, rcx
0x1801a8f49  jz      short loc_1801A8F5A
0x1801a8f4b  mov     rax, [rcx]
0x1801a8f4e  mov     edx, r12d
0x1801a8f51  mov     rax, [rax]
0x1801a8f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8f59  nop
0x1801a8f5a  jmp     loc_1801A9FEF
0x1801a8f5f  lea     r8, [rsi+0B8h]; void *
0x1801a8f66  cmp     [r8+4], r12b
0x1801a8f6a  jnz     short loc_1801A8F9F
0x1801a8f6c  lea     rdx, aAutomaticmaint; "AutomaticMaintenanceWakeUp"
0x1801a8f73  mov     rcx, r14; this
0x1801a8f76  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801a8f7b  mov     edi, eax
0x1801a8f7d  test    eax, eax
0x1801a8f7f  jz      short loc_1801A8F9F
0x1801a8f81  mov     rcx, [rsp+3B8h+var_378]
0x1801a8f86  test    rcx, rcx
0x1801a8f89  jz      short loc_1801A8F9A
0x1801a8f8b  mov     rax, [rcx]
  ... truncated ...
```
