# MDM_Policy_Result01_Update02_InvokeModifyInstance

- ea: `0x1801acf94`
- end: `0x1801ae468`
- name: `MDM_Policy_Result01_Update02_InvokeModifyInstance`
- size: `5332`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801ae470`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x1801acf94`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1801ad1e2`: `AllowAutoUpdate`
- `0x1801ad222`: `AllowAutoWindowsUpdateDownloadOverMeteredNetwork`
- `0x1801ad262`: `AllowTemporaryEnterpriseFeatureControl`
- `0x1801ad2e2`: `AlwaysAutoRebootAtScheduledTimeMinutes`
- `0x1801ad322`: `AllowMUUpdateService`
- `0x1801ad362`: `AllowNonMicrosoftSignedUpdate`
- `0x1801ad3a2`: `AllowUpdateService`
- `0x1801ad462`: `AutoRestartDeadlinePeriodInDaysForFeatureUpdates`
- `0x1801ad522`: `BranchReadinessLevel`
- `0x1801ad562`: `ConfigureDeadlineForFeatureUpdates`
- `0x1801ad5a2`: `ConfigureDeadlineForQualityUpdates`
- `0x1801ad5e2`: `ConfigureDeadlineGracePeriod`
- `0x1801ad622`: `ConfigureDeadlineGracePeriodForFeatureUpdates`
- `0x1801ad662`: `ConfigureDeadlineNoAutoReboot`
- `0x1801ad6a2`: `ConfigureFeatureUpdateUninstallPeriod`
- `0x1801ad6e2`: `DeferFeatureUpdatesPeriodInDays`
- `0x1801ad722`: `DeferQualityUpdatesPeriodInDays`
- `0x1801ad762`: `DeferUpdatePeriod`
- `0x1801ad8a2`: `DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection`
- `0x1801ad922`: `EngagedRestartDeadlineForFeatureUpdates`
- `0x1801ad9a2`: `EngagedRestartSnoozeScheduleForFeatureUpdates`
- `0x1801ada22`: `EngagedRestartTransitionScheduleForFeatureUpdates`
- `0x1801ada62`: `ExcludeWUDriversInQualityUpdate`
- `0x1801adb22`: `IgnoreMOUpdateDownloadLimit`
- `0x1801adbe2`: `PauseFeatureUpdates`
- `0x1801adc22`: `PauseFeatureUpdatesStartTime`
- `0x1801adc62`: `PauseQualityUpdates`
- `0x1801adca2`: `PauseQualityUpdatesStartTime`
- `0x1801adce2`: `PhoneUpdateRestrictions`
- `0x1801add62`: `RequireUpdateApproval`
- `0x1801adda2`: `ScheduledInstallDay`
- `0x1801adde2`: `ScheduledInstallEveryWeek`
- `0x1801ade22`: `ScheduledInstallFirstWeek`
- `0x1801ade62`: `ScheduledInstallFourthWeek`
- `0x1801adea2`: `ScheduledInstallSecondWeek`
- `0x1801adee2`: `ScheduledInstallThirdWeek`
- `0x1801adf22`: `ScheduledInstallTime`
- `0x1801ae022`: `SetDisablePauseUXAccess`
- `0x1801ae062`: `SetDisableUXWUAccess`
- `0x1801ae0e2`: `SetPolicyDrivenUpdateSourceForDriverUpdates`
- `0x1801ae122`: `SetPolicyDrivenUpdateSourceForFeatureUpdates`
- `0x1801ae162`: `SetPolicyDrivenUpdateSourceForOtherUpdates`
- `0x1801ae1a2`: `SetPolicyDrivenUpdateSourceForQualityUpdates`
- `0x1801ae1e2`: `SetProxyBehaviorForUpdateDetection`
- `0x1801ae2a2`: `UpdateNotificationLevel`
- `0x1801ae2e2`: `UpdateServiceUrl`
- `0x1801ae322`: `UpdateServiceUrlAlternate`
- `0x1801acfdf`: `MDM_Policy_Result01_Update02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Result01_Update02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  wil *v5; // rcx
  enum _MI_Result inserted; // edi
  WmiRequestHandler *v7; // r14
  const char *v9; // rax
  int v10; // eax
  WmiRequestHandler *v11; // [rsp+40h] [rbp-88h] BYREF
  _QWORD v12[3]; // [rsp+48h] [rbp-80h] BYREF
  const exception *v13[2]; // [rsp+60h] [rbp-68h] BYREF
  char v14; // [rsp+70h] [rbp-58h]
  int v15; // [rsp+78h] [rbp-50h] BYREF
  char v16; // [rsp+7Ch] [rbp-4Ch]
  _BYTE v17[16]; // [rsp+80h] [rbp-48h] BYREF
  _DWORD v18[4]; // [rsp+90h] [rbp-38h] BYREF

  v15 = 0;
  v16 = 0;
  v12[0] = &TelemetryEventWriter::`vftable';
  v12[1] = &v15;
  v12[2] = "MDM_Policy_Result01_Update02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v4 = v18;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18033CBD1,
      v17,
      v4);
  }
  if ( *(_BYTE *)(a2 + 72) && *(_BYTE *)(a2 + 88) )
  {
    TelemetryEventWriter::WriteStart(
      (TelemetryEventWriter *)v12,
      "ModifyInstanceStart",
      *(const unsigned __int16 **)(a2 + 80),
      *(const unsigned __int16 **)(a2 + 64));
    try
    {
      v11 = 0;
      inserted = (unsigned int)CreateRequestHandlerInstance(
                                 a1,
                                 *(_QWORD *)(a2 + 80),
                                 *(_QWORD *)(a2 + 64),
                                 &MDM_Policy_Result01_Update02_NodeList,
                                 75,
                                 3,
                                 &v11);
      if ( inserted == MI_RESULT_OK )
      {
        v13[1] = (const exception *)&v11;
        v14 = 1;
        v7 = v11;
        if ( v11 )
        {
          WmiRequestHandler::SetRequestMIInstance(
            v11,
            (const struct _MI_Instance *)a2,
            (struct WmiNodeInfo *)&MDM_Policy_Result01_Update02_NodeList,
            0x4Bu);
          if ( *(_BYTE *)(a2 + 100) == 1
            && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ActiveHoursEnd", (void *)(a2 + 96))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 108) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ActiveHoursMaxRange", (void *)(a2 + 104))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 116) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ActiveHoursStart", (void *)(a2 + 112))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 124) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowAutoUpdate", (void *)(a2 + 120))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 132) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowAutoWindowsUpdateDownloadOverMeteredNetwork",
                                  (void *)(a2 + 128))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 140) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowTemporaryEnterpriseFeatureControl",
                                  (void *)(a2 + 136))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 148) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowOptionalContent", (void *)(a2 + 144))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 156) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AlwaysAutoRebootAtScheduledTimeMinutes",
                                  (void *)(a2 + 152))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 164) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowMUUpdateService", (void *)(a2 + 160))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 172) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowNonMicrosoftSignedUpdate",
                                  (void *)(a2 + 168))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 180) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowUpdateService", (void *)(a2 + 176))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 188) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AutomaticMaintenanceWakeUp",
                                  (void *)(a2 + 184))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 196) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AutoRestartDeadlinePeriodInDays",
                                  (void *)(a2 + 192))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 204) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AutoRestartDeadlinePeriodInDaysForFeatureUpdates",
                                  (void *)(a2 + 200))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 212) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AutoRestartNotificationSchedule",
                                  (void *)(a2 + 208))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 220) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AutoRestartRequiredNotificationDismissal",
                                  (void *)(a2 + 216))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 228) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"BranchReadinessLevel", (void *)(a2 + 224))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 236) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureDeadlineForFeatureUpdates",
                                  (void *)(a2 + 232))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 244) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureDeadlineForQualityUpdates",
                                  (void *)(a2 + 240))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 252) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureDeadlineGracePeriod",
                                  (void *)(a2 + 248))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 260) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureDeadlineGracePeriodForFeatureUpdates",
                                  (void *)(a2 + 256))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 268) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureDeadlineNoAutoReboot",
                                  (void *)(a2 + 264))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 276) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureFeatureUpdateUninstallPeriod",
                                  (void *)(a2 + 272))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 284) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DeferFeatureUpdatesPeriodInDays",
                                  (void *)(a2 + 280))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 292) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DeferQualityUpdatesPeriodInDays",
                                  (void *)(a2 + 288))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 300) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"DeferUpdatePeriod", (void *)(a2 + 296))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 308) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"DeferUpgradePeriod", (void *)(a2 + 304))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 316) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"DetectionFrequency", (void *)(a2 + 312))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 324) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"DisableDualScan", (void *)(a2 + 320))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 332) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DisableWUfBSafeguards",
                                  (void *)(a2 + 328))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 340) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection",
                                  (void *)(a2 + 336))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 348) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EngagedRestartDeadline",
                                  (void *)(a2 + 344))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 356) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EngagedRestartDeadlineForFeatureUpdates",
                                  (void *)(a2 + 352))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 364) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EngagedRestartSnoozeSchedule",
                                  (void *)(a2 + 360))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 372) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EngagedRestartSnoozeScheduleForFeatureUpdates",
                                  (void *)(a2 + 368))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 380) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EngagedRestartTransitionSchedule",
                                  (void *)(a2 + 376))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 388) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EngagedRestartTransitionScheduleForFeatureUpdates",
                                  (void *)(a2 + 384))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 396) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ExcludeWUDriversInQualityUpdate",
                                  (void *)(a2 + 392))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 404) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"FillEmptyContentUrls", (void *)(a2 + 400))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 412) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"IgnoreMOAppDownloadLimit",
                                  (void *)(a2 + 408))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 420) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"IgnoreMOUpdateDownloadLimit",
                                  (void *)(a2 + 416))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 428) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ManagePreviewBuilds", (void *)(a2 + 424))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 436) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"PauseDeferrals", (void *)(a2 + 432))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 444) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"PauseFeatureUpdates", (void *)(a2 + 440))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 456) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PauseFeatureUpdatesStartTime",
                                  (void *)(a2 + 448))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 468) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"PauseQualityUpdates", (void *)(a2 + 464))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 480) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PauseQualityUpdatesStartTime",
                                  (void *)(a2 + 472))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 492) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PhoneUpdateRestrictions",
                                  (void *)(a2 + 488))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 500) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"RequireDeferUpgrade", (void *)(a2 + 496))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 508) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"RequireUpdateApproval",
                                  (void *)(a2 + 504))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 516) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ScheduledInstallDay", (void *)(a2 + 512))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 524) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduledInstallEveryWeek",
                                  (void *)(a2 + 520))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 532) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduledInstallFirstWeek",
                                  (void *)(a2 + 528))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 540) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduledInstallFourthWeek",
                                  (void *)(a2 + 536))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 548) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduledInstallSecondWeek",
                                  (void *)(a2 + 544))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 556) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduledInstallThirdWeek",
                                  (void *)(a2 + 552))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 564) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ScheduledInstallTime", (void *)(a2 + 560))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 572) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduleImminentRestartWarning",
                                  (void *)(a2 + 568))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 580) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduleRestartWarning",
                                  (void *)(a2 + 576))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 588) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetAutoRestartNotificationDisable",
                                  (void *)(a2 + 584))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 596) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetDisablePauseUXAccess",
                                  (void *)(a2 + 592))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 604) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"SetDisableUXWUAccess", (void *)(a2 + 600))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 612) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"SetEDURestart", (void *)(a2 + 608))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 620) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetPolicyDrivenUpdateSourceForDriverUpdates",
                                  (void *)(a2 + 616))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 628) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetPolicyDrivenUpdateSourceForFeatureUpdates",
                                  (void *)(a2 + 624))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 636) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetPolicyDrivenUpdateSourceForOtherUpdates",
                                  (void *)(a2 + 632))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 644) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetPolicyDrivenUpdateSourceForQualityUpdates",
                                  (void *)(a2 + 640))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 652) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetProxyBehaviorForUpdateDetection",
                                  (void *)(a2 + 648))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 664) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ProductVersion", (void *)(a2 + 656))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 680) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"TargetReleaseVersion", (void *)(a2 + 672))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 692) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UpdateNotificationLevel",
                                  (void *)(a2 + 688))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 704) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"UpdateServiceUrl", (void *)(a2 + 696))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 720) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UpdateServiceUrlAlternate",
                                  (void *)(a2 + 712))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else
          {
            inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 16LL))(v7);
            if ( inserted )
            {
              v5 = v11;
              if ( v11 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
            }
            else
            {
              inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 8LL))(v7);
              v5 = v11;
              if ( inserted )
              {
                if ( v11 )
                  (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
              }
              else if ( v11 )
              {
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
              }
            }
          }
        }
        else
        {
          inserted = MI_RESULT_FAILED;
        }
      }
    }
    catch ( const exception *v13 )
    {
      v9 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v13[0] + 8LL))(v13[0]);
      TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v12, v9);
      LODWORD(v11) = 1;
      inserted = MI_RESULT_FAILED;
    }
    catch ( ... )
    {
      v10 = wil::ResultFromCaughtException(v5);
      TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v12, v10);
      LODWORD(v11) = 1;
      inserted = MI_RESULT_FAILED;
    }
  }
  else
  {
    inserted = MI_RESULT_INVALID_PARAMETER;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v12, "ModifyInstanceEnd", inserted);
  v15 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18033765D,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1801acf94  mov     r11, rsp
0x1801acf97  mov     [r11+18h], rsi
0x1801acf9b  push    rdi
0x1801acf9c  push    r14
0x1801acf9e  push    r15
0x1801acfa0  sub     rsp, 0B0h
0x1801acfa7  mov     rax, cs:__security_cookie
0x1801acfae  xor     rax, rsp
0x1801acfb1  mov     [rsp+0C8h+var_28], rax
0x1801acfb9  mov     rsi, rdx
0x1801acfbc  mov     rdi, rcx
0x1801acfbf  mov     [rsp+0C8h+var_50], 0
0x1801acfc7  mov     [rsp+0C8h+var_4C], 0
0x1801acfcc  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801acfd3  mov     [r11-80h], rax
0x1801acfd7  lea     rax, [r11-50h]
0x1801acfdb  mov     [r11-78h], rax
0x1801acfdf  lea     rax, aMdmPolicyResul_174; "MDM_Policy_Result01_Update02"
0x1801acfe6  mov     [r11-70h], rax
0x1801acfea  lea     rcx, [r11-50h]
0x1801acfee  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801acff3  mov     eax, cs:dword_180380B68
0x1801acff9  cmp     eax, 5
0x1801acffc  jbe     short loc_1801AD06F
0x1801acffe  mov     rdx, 200000000000h
0x1801ad008  lea     rcx, dword_180380B68
0x1801ad00f  call    _tlgKeywordOn
0x1801ad014  test    al, al
0x1801ad016  jz      short loc_1801AD06F
0x1801ad018  cmp     [rsp+0C8h+var_4C], 0
0x1801ad01d  jz      short loc_1801AD051
0x1801ad01f  cmp     [rsp+0C8h+var_38], 0
0x1801ad027  jnz     short loc_1801AD047
0x1801ad029  cmp     [rsp+0C8h+var_34], 0
0x1801ad031  jnz     short loc_1801AD047
0x1801ad033  cmp     [rsp+0C8h+var_30], 0
0x1801ad03b  jnz     short loc_1801AD047
0x1801ad03d  cmp     [rsp+0C8h+var_2C], 0
0x1801ad045  jz      short loc_1801AD051
0x1801ad047  lea     r9, [rsp+0C8h+var_38]
0x1801ad04f  jmp     short loc_1801AD054
0x1801ad051  xor     r9d, r9d
0x1801ad054  lea     r8, [rsp+0C8h+var_48]
0x1801ad05c  lea     rdx, byte_18033CBD1
0x1801ad063  lea     rcx, dword_180380B68
0x1801ad06a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801ad06f  cmp     byte ptr [rsi+48h], 0
0x1801ad073  jz      loc_1801AE3D1
0x1801ad079  cmp     byte ptr [rsi+58h], 0
0x1801ad07d  jz      loc_1801AE3D1
0x1801ad083  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801ad087  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801ad08b  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1801ad092  lea     rcx, [rsp+0C8h+var_80]; this
0x1801ad097  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801ad09c  nop
0x1801ad09d  mov     [rsp+0C8h+var_88], 0
0x1801ad0a6  lea     rax, [rsp+0C8h+var_88]
0x1801ad0ab  mov     [rsp+0C8h+var_98], rax
0x1801ad0b0  mov     [rsp+0C8h+var_A0], 3
0x1801ad0b8  mov     [rsp+0C8h+var_A8], 4Bh ; 'K'
0x1801ad0c0  lea     r9, ?MDM_Policy_Result01_Update02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Update02_NodeList
0x1801ad0c7  mov     r8, [rsi+40h]
0x1801ad0cb  mov     rdx, [rsi+50h]
0x1801ad0cf  mov     rcx, rdi
0x1801ad0d2  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801ad0d7  mov     edi, eax
0x1801ad0d9  test    eax, eax
0x1801ad0db  jz      short loc_1801AD0E2
0x1801ad0dd  jmp     loc_1801AE3D6
0x1801ad0e2  lea     rax, [rsp+0C8h+var_88]
0x1801ad0e7  mov     [rsp+0C8h+var_60], rax
0x1801ad0ec  mov     r15d, 1
0x1801ad0f2  mov     [rsp+0C8h+var_58], r15b
0x1801ad0f7  mov     r14, [rsp+0C8h+var_88]
0x1801ad0fc  test    r14, r14
0x1801ad0ff  jnz     short loc_1801AD109
0x1801ad101  mov     edi, r15d
0x1801ad104  jmp     loc_1801AE3D6
0x1801ad109  mov     r9d, 4Bh ; 'K'; unsigned int
0x1801ad10f  lea     r8, ?MDM_Policy_Result01_Update02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801ad116  mov     rdx, rsi; struct _MI_Instance *
0x1801ad119  mov     rcx, r14; this
0x1801ad11c  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801ad121  lea     r8, [rsi+60h]; void *
0x1801ad125  cmp     [r8+4], r15b
0x1801ad129  jnz     short loc_1801AD15E
0x1801ad12b  lea     rdx, aActivehoursend; "ActiveHoursEnd"
0x1801ad132  mov     rcx, r14; this
0x1801ad135  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad13a  mov     edi, eax
0x1801ad13c  test    eax, eax
0x1801ad13e  jz      short loc_1801AD15E
0x1801ad140  mov     rcx, [rsp+0C8h+var_88]
0x1801ad145  test    rcx, rcx
0x1801ad148  jz      short loc_1801AD159
0x1801ad14a  mov     rax, [rcx]
0x1801ad14d  mov     edx, r15d
0x1801ad150  mov     rax, [rax]
0x1801ad153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad158  nop
0x1801ad159  jmp     loc_1801AE3D6
0x1801ad15e  lea     r8, [rsi+68h]; void *
0x1801ad162  cmp     [r8+4], r15b
0x1801ad166  jnz     short loc_1801AD19B
0x1801ad168  lea     rdx, aActivehoursmax; "ActiveHoursMaxRange"
0x1801ad16f  mov     rcx, r14; this
0x1801ad172  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad177  mov     edi, eax
0x1801ad179  test    eax, eax
0x1801ad17b  jz      short loc_1801AD19B
0x1801ad17d  mov     rcx, [rsp+0C8h+var_88]
0x1801ad182  test    rcx, rcx
0x1801ad185  jz      short loc_1801AD196
0x1801ad187  mov     rax, [rcx]
0x1801ad18a  mov     edx, r15d
0x1801ad18d  mov     rax, [rax]
0x1801ad190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad195  nop
0x1801ad196  jmp     loc_1801AE3D6
0x1801ad19b  lea     r8, [rsi+70h]; void *
0x1801ad19f  cmp     [r8+4], r15b
0x1801ad1a3  jnz     short loc_1801AD1D8
0x1801ad1a5  lea     rdx, aActivehourssta; "ActiveHoursStart"
0x1801ad1ac  mov     rcx, r14; this
0x1801ad1af  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad1b4  mov     edi, eax
0x1801ad1b6  test    eax, eax
0x1801ad1b8  jz      short loc_1801AD1D8
0x1801ad1ba  mov     rcx, [rsp+0C8h+var_88]
0x1801ad1bf  test    rcx, rcx
0x1801ad1c2  jz      short loc_1801AD1D3
0x1801ad1c4  mov     rax, [rcx]
0x1801ad1c7  mov     edx, r15d
0x1801ad1ca  mov     rax, [rax]
0x1801ad1cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad1d2  nop
0x1801ad1d3  jmp     loc_1801AE3D6
0x1801ad1d8  lea     r8, [rsi+78h]; void *
0x1801ad1dc  cmp     [r8+4], r15b
0x1801ad1e0  jnz     short loc_1801AD215
0x1801ad1e2  lea     rdx, aAllowautoupdat; "AllowAutoUpdate"
0x1801ad1e9  mov     rcx, r14; this
0x1801ad1ec  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad1f1  mov     edi, eax
0x1801ad1f3  test    eax, eax
0x1801ad1f5  jz      short loc_1801AD215
0x1801ad1f7  mov     rcx, [rsp+0C8h+var_88]
0x1801ad1fc  test    rcx, rcx
0x1801ad1ff  jz      short loc_1801AD210
0x1801ad201  mov     rax, [rcx]
0x1801ad204  mov     edx, r15d
0x1801ad207  mov     rax, [rax]
0x1801ad20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad20f  nop
0x1801ad210  jmp     loc_1801AE3D6
0x1801ad215  lea     r8, [rsi+80h]; void *
0x1801ad21c  cmp     [r8+4], r15b
0x1801ad220  jnz     short loc_1801AD255
0x1801ad222  lea     rdx, aAllowautowindo; "AllowAutoWindowsUpdateDownloadOverMeter"...
0x1801ad229  mov     rcx, r14; this
0x1801ad22c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad231  mov     edi, eax
0x1801ad233  test    eax, eax
0x1801ad235  jz      short loc_1801AD255
0x1801ad237  mov     rcx, [rsp+0C8h+var_88]
0x1801ad23c  test    rcx, rcx
0x1801ad23f  jz      short loc_1801AD250
0x1801ad241  mov     rax, [rcx]
0x1801ad244  mov     edx, r15d
0x1801ad247  mov     rax, [rax]
0x1801ad24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad24f  nop
0x1801ad250  jmp     loc_1801AE3D6
0x1801ad255  lea     r8, [rsi+88h]; void *
0x1801ad25c  cmp     [r8+4], r15b
0x1801ad260  jnz     short loc_1801AD295
0x1801ad262  lea     rdx, aAllowtemporary; "AllowTemporaryEnterpriseFeatureControl"
0x1801ad269  mov     rcx, r14; this
0x1801ad26c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad271  mov     edi, eax
0x1801ad273  test    eax, eax
0x1801ad275  jz      short loc_1801AD295
0x1801ad277  mov     rcx, [rsp+0C8h+var_88]
0x1801ad27c  test    rcx, rcx
0x1801ad27f  jz      short loc_1801AD290
0x1801ad281  mov     rax, [rcx]
0x1801ad284  mov     edx, r15d
0x1801ad287  mov     rax, [rax]
0x1801ad28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad28f  nop
0x1801ad290  jmp     loc_1801AE3D6
0x1801ad295  lea     r8, [rsi+90h]; void *
0x1801ad29c  cmp     [r8+4], r15b
0x1801ad2a0  jnz     short loc_1801AD2D5
0x1801ad2a2  lea     rdx, aAllowoptionalc; "AllowOptionalContent"
0x1801ad2a9  mov     rcx, r14; this
0x1801ad2ac  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad2b1  mov     edi, eax
0x1801ad2b3  test    eax, eax
0x1801ad2b5  jz      short loc_1801AD2D5
0x1801ad2b7  mov     rcx, [rsp+0C8h+var_88]
0x1801ad2bc  test    rcx, rcx
0x1801ad2bf  jz      short loc_1801AD2D0
0x1801ad2c1  mov     rax, [rcx]
0x1801ad2c4  mov     edx, r15d
0x1801ad2c7  mov     rax, [rax]
0x1801ad2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad2cf  nop
0x1801ad2d0  jmp     loc_1801AE3D6
0x1801ad2d5  lea     r8, [rsi+98h]; void *
0x1801ad2dc  cmp     [r8+4], r15b
0x1801ad2e0  jnz     short loc_1801AD315
0x1801ad2e2  lea     rdx, aAlwaysautorebo; "AlwaysAutoRebootAtScheduledTimeMinutes"
0x1801ad2e9  mov     rcx, r14; this
0x1801ad2ec  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad2f1  mov     edi, eax
0x1801ad2f3  test    eax, eax
0x1801ad2f5  jz      short loc_1801AD315
0x1801ad2f7  mov     rcx, [rsp+0C8h+var_88]
0x1801ad2fc  test    rcx, rcx
0x1801ad2ff  jz      short loc_1801AD310
0x1801ad301  mov     rax, [rcx]
0x1801ad304  mov     edx, r15d
0x1801ad307  mov     rax, [rax]
0x1801ad30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad30f  nop
0x1801ad310  jmp     loc_1801AE3D6
0x1801ad315  lea     r8, [rsi+0A0h]; void *
0x1801ad31c  cmp     [r8+4], r15b
0x1801ad320  jnz     short loc_1801AD355
0x1801ad322  lea     rdx, aAllowmuupdates; "AllowMUUpdateService"
0x1801ad329  mov     rcx, r14; this
0x1801ad32c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad331  mov     edi, eax
0x1801ad333  test    eax, eax
0x1801ad335  jz      short loc_1801AD355
0x1801ad337  mov     rcx, [rsp+0C8h+var_88]
0x1801ad33c  test    rcx, rcx
0x1801ad33f  jz      short loc_1801AD350
0x1801ad341  mov     rax, [rcx]
0x1801ad344  mov     edx, r15d
0x1801ad347  mov     rax, [rax]
0x1801ad34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad34f  nop
0x1801ad350  jmp     loc_1801AE3D6
0x1801ad355  lea     r8, [rsi+0A8h]; void *
0x1801ad35c  cmp     [r8+4], r15b
0x1801ad360  jnz     short loc_1801AD395
0x1801ad362  lea     rdx, aAllownonmicros; "AllowNonMicrosoftSignedUpdate"
0x1801ad369  mov     rcx, r14; this
0x1801ad36c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad371  mov     edi, eax
0x1801ad373  test    eax, eax
0x1801ad375  jz      short loc_1801AD395
0x1801ad377  mov     rcx, [rsp+0C8h+var_88]
0x1801ad37c  test    rcx, rcx
0x1801ad37f  jz      short loc_1801AD390
0x1801ad381  mov     rax, [rcx]
0x1801ad384  mov     edx, r15d
0x1801ad387  mov     rax, [rax]
0x1801ad38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad38f  nop
0x1801ad390  jmp     loc_1801AE3D6
0x1801ad395  lea     r8, [rsi+0B0h]; void *
0x1801ad39c  cmp     [r8+4], r15b
0x1801ad3a0  jnz     short loc_1801AD3D5
0x1801ad3a2  lea     rdx, aAllowupdateser; "AllowUpdateService"
0x1801ad3a9  mov     rcx, r14; this
0x1801ad3ac  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad3b1  mov     edi, eax
0x1801ad3b3  test    eax, eax
0x1801ad3b5  jz      short loc_1801AD3D5
0x1801ad3b7  mov     rcx, [rsp+0C8h+var_88]
0x1801ad3bc  test    rcx, rcx
0x1801ad3bf  jz      short loc_1801AD3D0
0x1801ad3c1  mov     rax, [rcx]
0x1801ad3c4  mov     edx, r15d
0x1801ad3c7  mov     rax, [rax]
0x1801ad3ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad3cf  nop
0x1801ad3d0  jmp     loc_1801AE3D6
0x1801ad3d5  lea     r8, [rsi+0B8h]; void *
0x1801ad3dc  cmp     [r8+4], r15b
0x1801ad3e0  jnz     short loc_1801AD415
0x1801ad3e2  lea     rdx, aAutomaticmaint; "AutomaticMaintenanceWakeUp"
0x1801ad3e9  mov     rcx, r14; this
0x1801ad3ec  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad3f1  mov     edi, eax
0x1801ad3f3  test    eax, eax
0x1801ad3f5  jz      short loc_1801AD415
0x1801ad3f7  mov     rcx, [rsp+0C8h+var_88]
0x1801ad3fc  test    rcx, rcx
0x1801ad3ff  jz      short loc_1801AD410
0x1801ad401  mov     rax, [rcx]
0x1801ad404  mov     edx, r15d
0x1801ad407  mov     rax, [rax]
0x1801ad40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad40f  nop
0x1801ad410  jmp     loc_1801AE3D6
  ... truncated ...
```
