# MDM_Policy_Config01_Update02_InvokeCreateInstance

- ea: `0x1800f13dc`
- end: `0x1800f2dbc`
- name: `MDM_Policy_Config01_Update02_InvokeCreateInstance`
- size: `6624`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f1320`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800f13dc`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1800f165c`: `AllowAutoUpdate`
- `0x1800f169c`: `AllowAutoWindowsUpdateDownloadOverMeteredNetwork`
- `0x1800f16dc`: `AllowTemporaryEnterpriseFeatureControl`
- `0x1800f175c`: `AlwaysAutoRebootAtScheduledTimeMinutes`
- `0x1800f179c`: `AllowMUUpdateService`
- `0x1800f17dc`: `AllowNonMicrosoftSignedUpdate`
- `0x1800f181c`: `AllowUpdateService`
- `0x1800f18dc`: `AutoRestartDeadlinePeriodInDaysForFeatureUpdates`
- `0x1800f199c`: `BranchReadinessLevel`
- `0x1800f19dc`: `ConfigureDeadlineForFeatureUpdates`
- `0x1800f1a1c`: `ConfigureDeadlineForQualityUpdates`
- `0x1800f1a5c`: `ConfigureDeadlineGracePeriod`
- `0x1800f1a9c`: `ConfigureDeadlineGracePeriodForFeatureUpdates`
- `0x1800f1adc`: `ConfigureDeadlineNoAutoReboot`
- `0x1800f1b1c`: `ConfigureFeatureUpdateUninstallPeriod`
- `0x1800f1b5c`: `DeferFeatureUpdatesPeriodInDays`
- `0x1800f1b9c`: `DeferQualityUpdatesPeriodInDays`
- `0x1800f1bdc`: `DeferUpdatePeriod`
- `0x1800f1d1c`: `DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection`
- `0x1800f1d9c`: `EngagedRestartDeadlineForFeatureUpdates`
- `0x1800f1e1c`: `EngagedRestartSnoozeScheduleForFeatureUpdates`
- `0x1800f1e9c`: `EngagedRestartTransitionScheduleForFeatureUpdates`
- `0x1800f1edc`: `ExcludeWUDriversInQualityUpdate`
- `0x1800f1f9c`: `IgnoreMOUpdateDownloadLimit`
- `0x1800f205c`: `PauseFeatureUpdates`
- `0x1800f209c`: `PauseFeatureUpdatesStartTime`
- `0x1800f20dc`: `PauseQualityUpdates`
- `0x1800f211c`: `PauseQualityUpdatesStartTime`
- `0x1800f215c`: `PhoneUpdateRestrictions`
- `0x1800f21dc`: `RequireUpdateApproval`
- `0x1800f221c`: `ScheduledInstallDay`
- `0x1800f225c`: `ScheduledInstallEveryWeek`
- `0x1800f229c`: `ScheduledInstallFirstWeek`
- `0x1800f22dc`: `ScheduledInstallFourthWeek`
- `0x1800f231c`: `ScheduledInstallSecondWeek`
- `0x1800f235c`: `ScheduledInstallThirdWeek`
- `0x1800f239c`: `ScheduledInstallTime`
- `0x1800f249c`: `SetDisablePauseUXAccess`
- `0x1800f24dc`: `SetDisableUXWUAccess`
- `0x1800f255c`: `SetPolicyDrivenUpdateSourceForDriverUpdates`
- `0x1800f259c`: `SetPolicyDrivenUpdateSourceForFeatureUpdates`
- `0x1800f25dc`: `SetPolicyDrivenUpdateSourceForOtherUpdates`
- `0x1800f261c`: `SetPolicyDrivenUpdateSourceForQualityUpdates`
- `0x1800f265c`: `SetProxyBehaviorForUpdateDetection`
- `0x1800f271c`: `UpdateNotificationLevel`
- `0x1800f275c`: `UpdateServiceUrl`
- `0x1800f279c`: `UpdateServiceUrlAlternate`
- `0x1800f281c`: `MaintenanceWindowUpdateActions`
- `0x1800f1505`: `CreateInstanceStart`
- `0x1800f2d22`: `CreateInstanceEnd`
- `0x1800f144c`: `MDM_Policy_Config01_Update02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Update02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
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
    inserted = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_389;
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
                             &MDM_Policy_Config01_Update02_NodeList,
                             92,
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
      goto LABEL_389;
    }
    WmiRequestHandler::SetRequestMIInstance(v8, a2, (struct WmiNodeInfo *)&MDM_Policy_Config01_Update02_NodeList, 0x5Cu);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ActiveHoursEnd", a2[1].reserved);
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
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ActiveHoursMaxRange", &a2[1].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[1].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ActiveHoursStart", &a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAutoUpdate", &a2[1].reserved[3]);
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
                   &a2[2]);
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
                   &a2[2].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[2].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowOptionalContent", &a2[2].serverName);
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
                   &a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowMUUpdateService", a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowNonMicrosoftSignedUpdate", &a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[2].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowUpdateService", &a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AutomaticMaintenanceWakeUp", &a2[2].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AutoRestartDeadlinePeriodInDays", &a2[3]);
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
                   &a2[3].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[3].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AutoRestartNotificationSchedule", &a2[3].serverName);
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
                   &a2[3].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[3].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"BranchReadinessLevel", a2[3].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[3].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureDeadlineForFeatureUpdates", &a2[3].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[3].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureDeadlineForQualityUpdates", &a2[3].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[3].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureDeadlineGracePeriod", &a2[3].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureDeadlineGracePeriodForFeatureUpdates", &a2[4]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[4].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureDeadlineNoAutoReboot", &a2[4].classDecl);
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
                   &a2[4].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[4].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DeferFeatureUpdatesPeriodInDays", &a2[4].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[4].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DeferQualityUpdatesPeriodInDays", a2[4].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[4].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DeferUpdatePeriod", &a2[4].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[4].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DeferUpgradePeriod", &a2[4].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DetectionFrequency", &a2[4].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[5].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableDualScan", &a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableWUfBSafeguards", &a2[5].classDecl);
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
                   &a2[5].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[5].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EngagedRestartDeadline", &a2[5].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[5].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EngagedRestartDeadlineForFeatureUpdates", a2[5].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[5].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EngagedRestartSnoozeSchedule", &a2[5].reserved[1]);
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
                   &a2[5].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[5].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EngagedRestartTransitionSchedule", &a2[5].reserved[3]);
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
                   &a2[6]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[6].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludeWUDriversInQualityUpdate", &a2[6].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[6].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"FillEmptyContentUrls", &a2[6].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[6].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"IgnoreMOAppDownloadLimit", &a2[6].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[6].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"IgnoreMOUpdateDownloadLimit", a2[6].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[6].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ManagePreviewBuilds", &a2[6].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[6].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseDeferrals", &a2[6].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[6].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseFeatureUpdates", &a2[6].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[7].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseFeatureUpdatesStartTime", &a2[7]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[7].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseQualityUpdates", &a2[7].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[7].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PauseQualityUpdatesStartTime", &a2[7].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[7].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PhoneUpdateRestrictions", &a2[7].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[7].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RequireDeferUpgrade", &a2[7].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[7].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RequireUpdateApproval", &a2[7].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallDay", &a2[8]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallEveryWeek", &a2[8].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallFirstWeek", &a2[8].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallFourthWeek", &a2[8].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallSecondWeek", a2[8].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallThirdWeek", &a2[8].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduledInstallTime", &a2[8].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[8].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleImminentRestartWarning", &a2[8].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[9].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleRestartWarning", &a2[9]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[9].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetAutoRestartNotificationDisable", &a2[9].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[9].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDisablePauseUXAccess", &a2[9].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[9].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDisableUXWUAccess", &a2[9].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[9].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetEDURestart", a2[9].reserved);
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
                   &a2[9].reserved[1]);
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
                   &a2[9].reserved[2]);
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
                   &a2[9].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[10].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetPolicyDrivenUpdateSourceForQualityUpdates", &a2[10]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[10].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetProxyBehaviorForUpdateDetection", &a2[10].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[10].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProductVersion", &a2[10].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[10].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"TargetReleaseVersion", a2[10].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[10].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UpdateNotificationLevel", &a2[10].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[11].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UpdateServiceUrl", &a2[10].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[11].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UpdateServiceUrlAlternate", &a2[11].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE1(a2[11].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"MaintenanceWindowEnabled", &a2[11].nameSpace);
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
                   (char *)&a2[11].nameSpace + 4);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[11].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"MaintenanceWindowStartDate", &a2[11].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( LOBYTE(a2[12].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"MaintenanceWindowStartTime", &a2[11].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[12].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"MaintenanceWindowDurationHours", &a2[12].classDecl);
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
                   &a2[12].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE1(a2[12].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"MaintenanceWindowWeeklySunday", &a2[12].nameSpace);
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
                   (char *)&a2[12].nameSpace + 3);
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
                   (char *)&a2[12].nameSpace + 6);
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
                   (char *)a2[12].reserved + 1);
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
                   (char *)a2[12].reserved + 4);
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
                   (char *)a2[12].reserved + 7);
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
                   (char *)&a2[12].reserved[1] + 2);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    if ( BYTE4(a2[12].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"MaintenanceWindowMonthlySchedule", &a2[12].reserved[2]);
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
                   &a2[12].reserved[3]);
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
                   &a2[13]);
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
                   &a2[13].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_389;
        goto LABEL_384;
      }
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_389;
      goto LABEL_384;
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800f13dc  mov     [rsp+arg_10], rsi
0x1800f13e1  mov     [rsp+arg_18], rdi
0x1800f13e6  push    r12
0x1800f13e8  push    r14
0x1800f13ea  push    r15
0x1800f13ec  sub     rsp, 410h
0x1800f13f3  mov     rax, cs:__security_cookie
0x1800f13fa  xor     rax, rsp
0x1800f13fd  mov     [rsp+428h+var_28], rax
0x1800f1405  mov     rsi, rdx
0x1800f1408  mov     r15, rcx
0x1800f140b  xor     edx, edx; Val
0x1800f140d  mov     r8d, 350h; Size
0x1800f1413  lea     rcx, [rsp+428h+instance]; void *
0x1800f141b  call    memset_0
0x1800f1420  mov     [rsp+428h+var_3A8], 0
0x1800f142b  mov     [rsp+428h+var_3A4], 0
0x1800f1433  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800f143a  mov     [rsp+428h+var_3D8], rax
0x1800f143f  lea     rax, [rsp+428h+var_3A8]
0x1800f1447  mov     [rsp+428h+var_3D0], rax
0x1800f144c  lea     rax, aMdmPolicyConfi_91; "MDM_Policy_Config01_Update02"
0x1800f1453  mov     [rsp+428h+var_3C8], rax
0x1800f1458  lea     rcx, [rsp+428h+var_3A8]
0x1800f1460  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800f1465  mov     eax, cs:dword_180380B68
0x1800f146b  cmp     eax, 5
0x1800f146e  jbe     short loc_1800F14E4
0x1800f1470  mov     rdx, 200000000000h
0x1800f147a  lea     rcx, dword_180380B68
0x1800f1481  call    _tlgKeywordOn
0x1800f1486  test    al, al
0x1800f1488  jz      short loc_1800F14E4
0x1800f148a  cmp     [rsp+428h+var_3A4], 0
0x1800f1492  jz      short loc_1800F14C6
0x1800f1494  cmp     [rsp+428h+var_390], 0
0x1800f149c  jnz     short loc_1800F14BC
0x1800f149e  cmp     [rsp+428h+var_38C], 0
0x1800f14a6  jnz     short loc_1800F14BC
0x1800f14a8  cmp     [rsp+428h+var_388], 0
0x1800f14b0  jnz     short loc_1800F14BC
0x1800f14b2  cmp     [rsp+428h+var_384], 0
0x1800f14ba  jz      short loc_1800F14C6
0x1800f14bc  lea     r9, [rsp+428h+var_390]
0x1800f14c4  jmp     short loc_1800F14C9
0x1800f14c6  xor     r9d, r9d
0x1800f14c9  lea     r8, [rsp+428h+var_3A0]
0x1800f14d1  lea     rdx, byte_180347CA7
0x1800f14d8  lea     rcx, dword_180380B68
0x1800f14df  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800f14e4  cmp     byte ptr [rsi+48h], 0
0x1800f14e8  jz      loc_1800F2D1A
0x1800f14ee  mov     [rsp+428h+var_3E0], 0
0x1800f14f3  cmp     byte ptr [rsi+58h], 0
0x1800f14f7  jz      loc_1800F2D1A
0x1800f14fd  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800f1501  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800f1505  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1800f150c  lea     rcx, [rsp+428h+var_3D8]; this
0x1800f1511  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800f1516  nop
0x1800f1517  mov     [rsp+428h+var_3E8], 0
0x1800f1520  lea     rax, [rsp+428h+var_3E8]
0x1800f1525  mov     [rsp+428h+var_3F8], rax
0x1800f152a  mov     [rsp+428h+var_400], 4
0x1800f1532  mov     [rsp+428h+var_408], 5Ch ; '\'
0x1800f153a  lea     r9, ?MDM_Policy_Config01_Update02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Update02_NodeList
0x1800f1541  mov     r8, [rsi+40h]
0x1800f1545  mov     rdx, [rsi+50h]
0x1800f1549  mov     rcx, r15
0x1800f154c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800f1551  mov     edi, eax
0x1800f1553  test    eax, eax
0x1800f1555  jz      short loc_1800F155C
0x1800f1557  jmp     loc_1800F2D1F
0x1800f155c  lea     rax, [rsp+428h+var_3E8]
0x1800f1561  mov     [rsp+428h+var_3B8], rax
0x1800f1566  mov     r12d, 1
0x1800f156c  mov     [rsp+428h+var_3B0], r12b
0x1800f1571  mov     r14, [rsp+428h+var_3E8]
0x1800f1576  test    r14, r14
0x1800f1579  jnz     short loc_1800F1583
0x1800f157b  mov     edi, r12d
0x1800f157e  jmp     loc_1800F2D1F
0x1800f1583  mov     r9d, 5Ch ; '\'; unsigned int
0x1800f1589  lea     r8, ?MDM_Policy_Config01_Update02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800f1590  mov     rdx, rsi; struct _MI_Instance *
0x1800f1593  mov     rcx, r14; this
0x1800f1596  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800f159b  lea     r8, [rsi+60h]; void *
0x1800f159f  cmp     [r8+4], r12b
0x1800f15a3  jnz     short loc_1800F15D8
0x1800f15a5  lea     rdx, aActivehoursend; "ActiveHoursEnd"
0x1800f15ac  mov     rcx, r14; this
0x1800f15af  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f15b4  mov     edi, eax
0x1800f15b6  test    eax, eax
0x1800f15b8  jz      short loc_1800F15D8
0x1800f15ba  mov     rcx, [rsp+428h+var_3E8]
0x1800f15bf  test    rcx, rcx
0x1800f15c2  jz      short loc_1800F15D3
0x1800f15c4  mov     rax, [rcx]
0x1800f15c7  mov     edx, r12d
0x1800f15ca  mov     rax, [rax]
0x1800f15cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f15d2  nop
0x1800f15d3  jmp     loc_1800F2D1F
0x1800f15d8  lea     r8, [rsi+68h]; void *
0x1800f15dc  cmp     [r8+4], r12b
0x1800f15e0  jnz     short loc_1800F1615
0x1800f15e2  lea     rdx, aActivehoursmax; "ActiveHoursMaxRange"
0x1800f15e9  mov     rcx, r14; this
0x1800f15ec  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f15f1  mov     edi, eax
0x1800f15f3  test    eax, eax
0x1800f15f5  jz      short loc_1800F1615
0x1800f15f7  mov     rcx, [rsp+428h+var_3E8]
0x1800f15fc  test    rcx, rcx
0x1800f15ff  jz      short loc_1800F1610
0x1800f1601  mov     rax, [rcx]
0x1800f1604  mov     edx, r12d
0x1800f1607  mov     rax, [rax]
0x1800f160a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f160f  nop
0x1800f1610  jmp     loc_1800F2D1F
0x1800f1615  lea     r8, [rsi+70h]; void *
0x1800f1619  cmp     [r8+4], r12b
0x1800f161d  jnz     short loc_1800F1652
0x1800f161f  lea     rdx, aActivehourssta; "ActiveHoursStart"
0x1800f1626  mov     rcx, r14; this
0x1800f1629  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f162e  mov     edi, eax
0x1800f1630  test    eax, eax
0x1800f1632  jz      short loc_1800F1652
0x1800f1634  mov     rcx, [rsp+428h+var_3E8]
0x1800f1639  test    rcx, rcx
0x1800f163c  jz      short loc_1800F164D
0x1800f163e  mov     rax, [rcx]
0x1800f1641  mov     edx, r12d
0x1800f1644  mov     rax, [rax]
0x1800f1647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f164c  nop
0x1800f164d  jmp     loc_1800F2D1F
0x1800f1652  lea     r8, [rsi+78h]; void *
0x1800f1656  cmp     [r8+4], r12b
0x1800f165a  jnz     short loc_1800F168F
0x1800f165c  lea     rdx, aAllowautoupdat; "AllowAutoUpdate"
0x1800f1663  mov     rcx, r14; this
0x1800f1666  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f166b  mov     edi, eax
0x1800f166d  test    eax, eax
0x1800f166f  jz      short loc_1800F168F
0x1800f1671  mov     rcx, [rsp+428h+var_3E8]
0x1800f1676  test    rcx, rcx
0x1800f1679  jz      short loc_1800F168A
0x1800f167b  mov     rax, [rcx]
0x1800f167e  mov     edx, r12d
0x1800f1681  mov     rax, [rax]
0x1800f1684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1689  nop
0x1800f168a  jmp     loc_1800F2D1F
0x1800f168f  lea     r8, [rsi+80h]; void *
0x1800f1696  cmp     [r8+4], r12b
0x1800f169a  jnz     short loc_1800F16CF
0x1800f169c  lea     rdx, aAllowautowindo; "AllowAutoWindowsUpdateDownloadOverMeter"...
0x1800f16a3  mov     rcx, r14; this
0x1800f16a6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f16ab  mov     edi, eax
0x1800f16ad  test    eax, eax
0x1800f16af  jz      short loc_1800F16CF
0x1800f16b1  mov     rcx, [rsp+428h+var_3E8]
0x1800f16b6  test    rcx, rcx
0x1800f16b9  jz      short loc_1800F16CA
0x1800f16bb  mov     rax, [rcx]
0x1800f16be  mov     edx, r12d
0x1800f16c1  mov     rax, [rax]
0x1800f16c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f16c9  nop
0x1800f16ca  jmp     loc_1800F2D1F
0x1800f16cf  lea     r8, [rsi+88h]; void *
0x1800f16d6  cmp     [r8+4], r12b
0x1800f16da  jnz     short loc_1800F170F
0x1800f16dc  lea     rdx, aAllowtemporary; "AllowTemporaryEnterpriseFeatureControl"
0x1800f16e3  mov     rcx, r14; this
0x1800f16e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f16eb  mov     edi, eax
0x1800f16ed  test    eax, eax
0x1800f16ef  jz      short loc_1800F170F
0x1800f16f1  mov     rcx, [rsp+428h+var_3E8]
0x1800f16f6  test    rcx, rcx
0x1800f16f9  jz      short loc_1800F170A
0x1800f16fb  mov     rax, [rcx]
0x1800f16fe  mov     edx, r12d
0x1800f1701  mov     rax, [rax]
0x1800f1704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1709  nop
0x1800f170a  jmp     loc_1800F2D1F
0x1800f170f  lea     r8, [rsi+90h]; void *
0x1800f1716  cmp     [r8+4], r12b
0x1800f171a  jnz     short loc_1800F174F
0x1800f171c  lea     rdx, aAllowoptionalc; "AllowOptionalContent"
0x1800f1723  mov     rcx, r14; this
0x1800f1726  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f172b  mov     edi, eax
0x1800f172d  test    eax, eax
0x1800f172f  jz      short loc_1800F174F
0x1800f1731  mov     rcx, [rsp+428h+var_3E8]
0x1800f1736  test    rcx, rcx
0x1800f1739  jz      short loc_1800F174A
0x1800f173b  mov     rax, [rcx]
0x1800f173e  mov     edx, r12d
0x1800f1741  mov     rax, [rax]
0x1800f1744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1749  nop
0x1800f174a  jmp     loc_1800F2D1F
0x1800f174f  lea     r8, [rsi+98h]; void *
0x1800f1756  cmp     [r8+4], r12b
0x1800f175a  jnz     short loc_1800F178F
0x1800f175c  lea     rdx, aAlwaysautorebo; "AlwaysAutoRebootAtScheduledTimeMinutes"
0x1800f1763  mov     rcx, r14; this
0x1800f1766  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f176b  mov     edi, eax
0x1800f176d  test    eax, eax
0x1800f176f  jz      short loc_1800F178F
0x1800f1771  mov     rcx, [rsp+428h+var_3E8]
0x1800f1776  test    rcx, rcx
0x1800f1779  jz      short loc_1800F178A
0x1800f177b  mov     rax, [rcx]
0x1800f177e  mov     edx, r12d
0x1800f1781  mov     rax, [rax]
0x1800f1784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1789  nop
0x1800f178a  jmp     loc_1800F2D1F
0x1800f178f  lea     r8, [rsi+0A0h]; void *
0x1800f1796  cmp     [r8+4], r12b
0x1800f179a  jnz     short loc_1800F17CF
0x1800f179c  lea     rdx, aAllowmuupdates; "AllowMUUpdateService"
0x1800f17a3  mov     rcx, r14; this
0x1800f17a6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f17ab  mov     edi, eax
0x1800f17ad  test    eax, eax
0x1800f17af  jz      short loc_1800F17CF
0x1800f17b1  mov     rcx, [rsp+428h+var_3E8]
0x1800f17b6  test    rcx, rcx
0x1800f17b9  jz      short loc_1800F17CA
0x1800f17bb  mov     rax, [rcx]
0x1800f17be  mov     edx, r12d
0x1800f17c1  mov     rax, [rax]
0x1800f17c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f17c9  nop
0x1800f17ca  jmp     loc_1800F2D1F
0x1800f17cf  lea     r8, [rsi+0A8h]; void *
0x1800f17d6  cmp     [r8+4], r12b
0x1800f17da  jnz     short loc_1800F180F
0x1800f17dc  lea     rdx, aAllownonmicros; "AllowNonMicrosoftSignedUpdate"
0x1800f17e3  mov     rcx, r14; this
0x1800f17e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f17eb  mov     edi, eax
0x1800f17ed  test    eax, eax
0x1800f17ef  jz      short loc_1800F180F
0x1800f17f1  mov     rcx, [rsp+428h+var_3E8]
0x1800f17f6  test    rcx, rcx
0x1800f17f9  jz      short loc_1800F180A
0x1800f17fb  mov     rax, [rcx]
0x1800f17fe  mov     edx, r12d
0x1800f1801  mov     rax, [rax]
0x1800f1804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1809  nop
0x1800f180a  jmp     loc_1800F2D1F
0x1800f180f  lea     r8, [rsi+0B0h]; void *
0x1800f1816  cmp     [r8+4], r12b
0x1800f181a  jnz     short loc_1800F184F
0x1800f181c  lea     rdx, aAllowupdateser; "AllowUpdateService"
0x1800f1823  mov     rcx, r14; this
0x1800f1826  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f182b  mov     edi, eax
0x1800f182d  test    eax, eax
0x1800f182f  jz      short loc_1800F184F
0x1800f1831  mov     rcx, [rsp+428h+var_3E8]
0x1800f1836  test    rcx, rcx
0x1800f1839  jz      short loc_1800F184A
0x1800f183b  mov     rax, [rcx]
0x1800f183e  mov     edx, r12d
0x1800f1841  mov     rax, [rax]
0x1800f1844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1849  nop
0x1800f184a  jmp     loc_1800F2D1F
0x1800f184f  lea     r8, [rsi+0B8h]; void *
0x1800f1856  cmp     [r8+4], r12b
0x1800f185a  jnz     short loc_1800F188F
0x1800f185c  lea     rdx, aAutomaticmaint; "AutomaticMaintenanceWakeUp"
0x1800f1863  mov     rcx, r14; this
0x1800f1866  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f186b  mov     edi, eax
0x1800f186d  test    eax, eax
0x1800f186f  jz      short loc_1800F188F
0x1800f1871  mov     rcx, [rsp+428h+var_3E8]
0x1800f1876  test    rcx, rcx
0x1800f1879  jz      short loc_1800F188A
0x1800f187b  mov     rax, [rcx]
  ... truncated ...
```
