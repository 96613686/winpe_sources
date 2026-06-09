# MDM_Policy_Result01_Update02_InvokeModifyInstance

- ea: `0x1801ad0e8`
- end: `0x1801ae5bb`
- name: `MDM_Policy_Result01_Update02_InvokeModifyInstance`
- size: `5331`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801ae5d0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x1801ad0e8`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1801ad336`: `AllowAutoUpdate`
- `0x1801ad376`: `AllowAutoWindowsUpdateDownloadOverMeteredNetwork`
- `0x1801ad3b6`: `AllowTemporaryEnterpriseFeatureControl`
- `0x1801ad436`: `AlwaysAutoRebootAtScheduledTimeMinutes`
- `0x1801ad476`: `AllowMUUpdateService`
- `0x1801ad4b6`: `AllowNonMicrosoftSignedUpdate`
- `0x1801ad4f6`: `AllowUpdateService`
- `0x1801ad5b6`: `AutoRestartDeadlinePeriodInDaysForFeatureUpdates`
- `0x1801ad676`: `BranchReadinessLevel`
- `0x1801ad6b6`: `ConfigureDeadlineForFeatureUpdates`
- `0x1801ad6f6`: `ConfigureDeadlineForQualityUpdates`
- `0x1801ad736`: `ConfigureDeadlineGracePeriod`
- `0x1801ad776`: `ConfigureDeadlineGracePeriodForFeatureUpdates`
- `0x1801ad7b6`: `ConfigureDeadlineNoAutoReboot`
- `0x1801ad7f6`: `ConfigureFeatureUpdateUninstallPeriod`
- `0x1801ad836`: `DeferFeatureUpdatesPeriodInDays`
- `0x1801ad876`: `DeferQualityUpdatesPeriodInDays`
- `0x1801ad8b6`: `DeferUpdatePeriod`
- `0x1801ad9f6`: `DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection`
- `0x1801ada76`: `EngagedRestartDeadlineForFeatureUpdates`
- `0x1801adaf6`: `EngagedRestartSnoozeScheduleForFeatureUpdates`
- `0x1801adb76`: `EngagedRestartTransitionScheduleForFeatureUpdates`
- `0x1801adbb6`: `ExcludeWUDriversInQualityUpdate`
- `0x1801adc76`: `IgnoreMOUpdateDownloadLimit`
- `0x1801add36`: `PauseFeatureUpdates`
- `0x1801add76`: `PauseFeatureUpdatesStartTime`
- `0x1801addb6`: `PauseQualityUpdates`
- `0x1801addf6`: `PauseQualityUpdatesStartTime`
- `0x1801ade36`: `PhoneUpdateRestrictions`
- `0x1801adeb6`: `RequireUpdateApproval`
- `0x1801adef6`: `ScheduledInstallDay`
- `0x1801adf36`: `ScheduledInstallEveryWeek`
- `0x1801adf76`: `ScheduledInstallFirstWeek`
- `0x1801adfb6`: `ScheduledInstallFourthWeek`
- `0x1801adff6`: `ScheduledInstallSecondWeek`
- `0x1801ae036`: `ScheduledInstallThirdWeek`
- `0x1801ae076`: `ScheduledInstallTime`
- `0x1801ae176`: `SetDisablePauseUXAccess`
- `0x1801ae1b6`: `SetDisableUXWUAccess`
- `0x1801ae236`: `SetPolicyDrivenUpdateSourceForDriverUpdates`
- `0x1801ae276`: `SetPolicyDrivenUpdateSourceForFeatureUpdates`
- `0x1801ae2b6`: `SetPolicyDrivenUpdateSourceForOtherUpdates`
- `0x1801ae2f6`: `SetPolicyDrivenUpdateSourceForQualityUpdates`
- `0x1801ae336`: `SetProxyBehaviorForUpdateDetection`
- `0x1801ae3f6`: `UpdateNotificationLevel`
- `0x1801ae436`: `UpdateServiceUrl`
- `0x1801ae476`: `UpdateServiceUrlAlternate`
- `0x1801ad133`: `MDM_Policy_Result01_Update02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Result01_Update02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  wil *v5; // rcx
  unsigned int inserted; // edi
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
      inserted = CreateRequestHandlerInstance(
                   a1,
                   *(wchar_t **)(a2 + 80),
                   *(const unsigned __int16 **)(a2 + 64),
                   (struct WmiNodeInfo *)&MDM_Policy_Result01_Update02_NodeList,
                   0x4Bu,
                   3,
                   &v11);
      if ( !inserted )
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
            && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ActiveHoursEnd", (LONG *)(a2 + 96))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 108) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ActiveHoursMaxRange", (LONG *)(a2 + 104))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 116) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ActiveHoursStart", (LONG *)(a2 + 112))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 124) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowAutoUpdate", (LONG *)(a2 + 120))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 132) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowAutoWindowsUpdateDownloadOverMeteredNetwork",
                                  (LONG *)(a2 + 128))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 140) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowTemporaryEnterpriseFeatureControl",
                                  (LONG *)(a2 + 136))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 148) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowOptionalContent", (LONG *)(a2 + 144))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 156) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AlwaysAutoRebootAtScheduledTimeMinutes",
                                  (LONG *)(a2 + 152))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 164) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowMUUpdateService", (LONG *)(a2 + 160))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 172) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowNonMicrosoftSignedUpdate",
                                  (LONG *)(a2 + 168))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 180) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowUpdateService", (LONG *)(a2 + 176))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 188) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AutomaticMaintenanceWakeUp",
                                  (LONG *)(a2 + 184))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 196) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AutoRestartDeadlinePeriodInDays",
                                  (LONG *)(a2 + 192))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 204) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AutoRestartDeadlinePeriodInDaysForFeatureUpdates",
                                  (LONG *)(a2 + 200))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 212) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AutoRestartNotificationSchedule",
                                  (LONG *)(a2 + 208))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 220) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AutoRestartRequiredNotificationDismissal",
                                  (LONG *)(a2 + 216))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 228) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"BranchReadinessLevel", (LONG *)(a2 + 224))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 236) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureDeadlineForFeatureUpdates",
                                  (LONG *)(a2 + 232))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 244) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureDeadlineForQualityUpdates",
                                  (LONG *)(a2 + 240))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 252) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureDeadlineGracePeriod",
                                  (LONG *)(a2 + 248))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 260) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureDeadlineGracePeriodForFeatureUpdates",
                                  (LONG *)(a2 + 256))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 268) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureDeadlineNoAutoReboot",
                                  (LONG *)(a2 + 264))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 276) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureFeatureUpdateUninstallPeriod",
                                  (LONG *)(a2 + 272))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 284) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DeferFeatureUpdatesPeriodInDays",
                                  (LONG *)(a2 + 280))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 292) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DeferQualityUpdatesPeriodInDays",
                                  (LONG *)(a2 + 288))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 300) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"DeferUpdatePeriod", (LONG *)(a2 + 296))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 308) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"DeferUpgradePeriod", (LONG *)(a2 + 304))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 316) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"DetectionFrequency", (LONG *)(a2 + 312))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 324) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"DisableDualScan", (LONG *)(a2 + 320))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 332) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DisableWUfBSafeguards",
                                  (LONG *)(a2 + 328))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 340) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection",
                                  (LONG *)(a2 + 336))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 348) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EngagedRestartDeadline",
                                  (LONG *)(a2 + 344))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 356) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EngagedRestartDeadlineForFeatureUpdates",
                                  (LONG *)(a2 + 352))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 364) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EngagedRestartSnoozeSchedule",
                                  (LONG *)(a2 + 360))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 372) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EngagedRestartSnoozeScheduleForFeatureUpdates",
                                  (LONG *)(a2 + 368))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 380) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EngagedRestartTransitionSchedule",
                                  (LONG *)(a2 + 376))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 388) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EngagedRestartTransitionScheduleForFeatureUpdates",
                                  (LONG *)(a2 + 384))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 396) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ExcludeWUDriversInQualityUpdate",
                                  (LONG *)(a2 + 392))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 404) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"FillEmptyContentUrls", (LONG *)(a2 + 400))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 412) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"IgnoreMOAppDownloadLimit",
                                  (LONG *)(a2 + 408))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 420) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"IgnoreMOUpdateDownloadLimit",
                                  (LONG *)(a2 + 416))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 428) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ManagePreviewBuilds", (LONG *)(a2 + 424))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 436) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"PauseDeferrals", (LONG *)(a2 + 432))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 444) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"PauseFeatureUpdates", (LONG *)(a2 + 440))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 456) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PauseFeatureUpdatesStartTime",
                                  (LONG *)(a2 + 448))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 468) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"PauseQualityUpdates", (LONG *)(a2 + 464))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 480) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PauseQualityUpdatesStartTime",
                                  (LONG *)(a2 + 472))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 492) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PhoneUpdateRestrictions",
                                  (LONG *)(a2 + 488))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 500) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"RequireDeferUpgrade", (LONG *)(a2 + 496))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 508) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"RequireUpdateApproval",
                                  (LONG *)(a2 + 504))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 516) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ScheduledInstallDay", (LONG *)(a2 + 512))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 524) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduledInstallEveryWeek",
                                  (LONG *)(a2 + 520))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 532) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduledInstallFirstWeek",
                                  (LONG *)(a2 + 528))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 540) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduledInstallFourthWeek",
                                  (LONG *)(a2 + 536))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 548) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduledInstallSecondWeek",
                                  (LONG *)(a2 + 544))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 556) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduledInstallThirdWeek",
                                  (LONG *)(a2 + 552))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 564) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ScheduledInstallTime", (LONG *)(a2 + 560))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 572) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduleImminentRestartWarning",
                                  (LONG *)(a2 + 568))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 580) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduleRestartWarning",
                                  (LONG *)(a2 + 576))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 588) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetAutoRestartNotificationDisable",
                                  (LONG *)(a2 + 584))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 596) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetDisablePauseUXAccess",
                                  (LONG *)(a2 + 592))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 604) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"SetDisableUXWUAccess", (LONG *)(a2 + 600))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 612) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"SetEDURestart", (LONG *)(a2 + 608))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 620) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetPolicyDrivenUpdateSourceForDriverUpdates",
                                  (LONG *)(a2 + 616))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 628) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetPolicyDrivenUpdateSourceForFeatureUpdates",
                                  (LONG *)(a2 + 624))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 636) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetPolicyDrivenUpdateSourceForOtherUpdates",
                                  (LONG *)(a2 + 632))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 644) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetPolicyDrivenUpdateSourceForQualityUpdates",
                                  (LONG *)(a2 + 640))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 652) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetProxyBehaviorForUpdateDetection",
                                  (LONG *)(a2 + 648))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 664) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ProductVersion", (LONG *)(a2 + 656))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 680) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"TargetReleaseVersion", (LONG *)(a2 + 672))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 692) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UpdateNotificationLevel",
                                  (LONG *)(a2 + 688))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 704) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"UpdateServiceUrl", (LONG *)(a2 + 696))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 720) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UpdateServiceUrlAlternate",
                                  (LONG *)(a2 + 712))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else
          {
            inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 16LL))(v7);
            if ( inserted )
            {
              v5 = v11;
              if ( v11 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
            }
            else
            {
              inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 8LL))(v7);
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
          inserted = 1;
        }
      }
    }
    catch ( const exception *v13 )
    {
      v9 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v13[0] + 8LL))(v13[0]);
      TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v12, v9);
      LODWORD(v11) = 1;
      inserted = 1;
    }
    catch ( ... )
    {
      v10 = wil::ResultFromCaughtException(v5);
      TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v12, v10);
      LODWORD(v11) = 1;
      inserted = 1;
    }
  }
  else
  {
    inserted = 4;
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
  return inserted;
}

```

## disassembly

```asm
0x1801ad0e8  mov     r11, rsp
0x1801ad0eb  mov     [r11+18h], rsi
0x1801ad0ef  push    rdi
0x1801ad0f0  push    r14
0x1801ad0f2  push    r15
0x1801ad0f4  sub     rsp, 0B0h
0x1801ad0fb  mov     rax, cs:__security_cookie
0x1801ad102  xor     rax, rsp
0x1801ad105  mov     [rsp+0C8h+var_28], rax
0x1801ad10d  mov     rsi, rdx
0x1801ad110  mov     rdi, rcx
0x1801ad113  mov     [rsp+0C8h+var_50], 0
0x1801ad11b  mov     [rsp+0C8h+var_4C], 0
0x1801ad120  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801ad127  mov     [r11-80h], rax
0x1801ad12b  lea     rax, [r11-50h]
0x1801ad12f  mov     [r11-78h], rax
0x1801ad133  lea     rax, aMdmPolicyResul_174; "MDM_Policy_Result01_Update02"
0x1801ad13a  mov     [r11-70h], rax
0x1801ad13e  lea     rcx, [r11-50h]
0x1801ad142  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801ad147  mov     eax, cs:dword_180380B68
0x1801ad14d  cmp     eax, 5
0x1801ad150  jbe     short loc_1801AD1C3
0x1801ad152  mov     rdx, 200000000000h
0x1801ad15c  lea     rcx, dword_180380B68
0x1801ad163  call    _tlgKeywordOn
0x1801ad168  test    al, al
0x1801ad16a  jz      short loc_1801AD1C3
0x1801ad16c  cmp     [rsp+0C8h+var_4C], 0
0x1801ad171  jz      short loc_1801AD1A5
0x1801ad173  cmp     [rsp+0C8h+var_38], 0
0x1801ad17b  jnz     short loc_1801AD19B
0x1801ad17d  cmp     [rsp+0C8h+var_34], 0
0x1801ad185  jnz     short loc_1801AD19B
0x1801ad187  cmp     [rsp+0C8h+var_30], 0
0x1801ad18f  jnz     short loc_1801AD19B
0x1801ad191  cmp     [rsp+0C8h+var_2C], 0
0x1801ad199  jz      short loc_1801AD1A5
0x1801ad19b  lea     r9, [rsp+0C8h+var_38]
0x1801ad1a3  jmp     short loc_1801AD1A8
0x1801ad1a5  xor     r9d, r9d
0x1801ad1a8  lea     r8, [rsp+0C8h+var_48]
0x1801ad1b0  lea     rdx, byte_18033CBD1
0x1801ad1b7  lea     rcx, dword_180380B68
0x1801ad1be  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801ad1c3  cmp     byte ptr [rsi+48h], 0
0x1801ad1c7  jz      loc_1801AE525
0x1801ad1cd  cmp     byte ptr [rsi+58h], 0
0x1801ad1d1  jz      loc_1801AE525
0x1801ad1d7  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801ad1db  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801ad1df  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1801ad1e6  lea     rcx, [rsp+0C8h+var_80]; this
0x1801ad1eb  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801ad1f0  nop
0x1801ad1f1  mov     [rsp+0C8h+var_88], 0
0x1801ad1fa  lea     rax, [rsp+0C8h+var_88]
0x1801ad1ff  mov     [rsp+0C8h+var_98], rax
0x1801ad204  mov     [rsp+0C8h+var_A0], 3
0x1801ad20c  mov     [rsp+0C8h+var_A8], 4Bh ; 'K'
0x1801ad214  lea     r9, ?MDM_Policy_Result01_Update02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Update02_NodeList
0x1801ad21b  mov     r8, [rsi+40h]
0x1801ad21f  mov     rdx, [rsi+50h]
0x1801ad223  mov     rcx, rdi
0x1801ad226  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801ad22b  mov     edi, eax
0x1801ad22d  test    eax, eax
0x1801ad22f  jz      short loc_1801AD236
0x1801ad231  jmp     loc_1801AE52A
0x1801ad236  lea     rax, [rsp+0C8h+var_88]
0x1801ad23b  mov     [rsp+0C8h+var_60], rax
0x1801ad240  mov     r15d, 1
0x1801ad246  mov     [rsp+0C8h+var_58], r15b
0x1801ad24b  mov     r14, [rsp+0C8h+var_88]
0x1801ad250  test    r14, r14
0x1801ad253  jnz     short loc_1801AD25D
0x1801ad255  mov     edi, r15d
0x1801ad258  jmp     loc_1801AE52A
0x1801ad25d  mov     r9d, 4Bh ; 'K'; unsigned int
0x1801ad263  lea     r8, ?MDM_Policy_Result01_Update02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801ad26a  mov     rdx, rsi; struct _MI_Instance *
0x1801ad26d  mov     rcx, r14; this
0x1801ad270  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801ad275  lea     r8, [rsi+60h]; void *
0x1801ad279  cmp     [r8+4], r15b
0x1801ad27d  jnz     short loc_1801AD2B2
0x1801ad27f  lea     rdx, aActivehoursend; "ActiveHoursEnd"
0x1801ad286  mov     rcx, r14; this
0x1801ad289  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad28e  mov     edi, eax
0x1801ad290  test    eax, eax
0x1801ad292  jz      short loc_1801AD2B2
0x1801ad294  mov     rcx, [rsp+0C8h+var_88]
0x1801ad299  test    rcx, rcx
0x1801ad29c  jz      short loc_1801AD2AD
0x1801ad29e  mov     rax, [rcx]
0x1801ad2a1  mov     edx, r15d
0x1801ad2a4  mov     rax, [rax]
0x1801ad2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad2ac  nop
0x1801ad2ad  jmp     loc_1801AE52A
0x1801ad2b2  lea     r8, [rsi+68h]; void *
0x1801ad2b6  cmp     [r8+4], r15b
0x1801ad2ba  jnz     short loc_1801AD2EF
0x1801ad2bc  lea     rdx, aActivehoursmax; "ActiveHoursMaxRange"
0x1801ad2c3  mov     rcx, r14; this
0x1801ad2c6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad2cb  mov     edi, eax
0x1801ad2cd  test    eax, eax
0x1801ad2cf  jz      short loc_1801AD2EF
0x1801ad2d1  mov     rcx, [rsp+0C8h+var_88]
0x1801ad2d6  test    rcx, rcx
0x1801ad2d9  jz      short loc_1801AD2EA
0x1801ad2db  mov     rax, [rcx]
0x1801ad2de  mov     edx, r15d
0x1801ad2e1  mov     rax, [rax]
0x1801ad2e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad2e9  nop
0x1801ad2ea  jmp     loc_1801AE52A
0x1801ad2ef  lea     r8, [rsi+70h]; void *
0x1801ad2f3  cmp     [r8+4], r15b
0x1801ad2f7  jnz     short loc_1801AD32C
0x1801ad2f9  lea     rdx, aActivehourssta; "ActiveHoursStart"
0x1801ad300  mov     rcx, r14; this
0x1801ad303  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad308  mov     edi, eax
0x1801ad30a  test    eax, eax
0x1801ad30c  jz      short loc_1801AD32C
0x1801ad30e  mov     rcx, [rsp+0C8h+var_88]
0x1801ad313  test    rcx, rcx
0x1801ad316  jz      short loc_1801AD327
0x1801ad318  mov     rax, [rcx]
0x1801ad31b  mov     edx, r15d
0x1801ad31e  mov     rax, [rax]
0x1801ad321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad326  nop
0x1801ad327  jmp     loc_1801AE52A
0x1801ad32c  lea     r8, [rsi+78h]; void *
0x1801ad330  cmp     [r8+4], r15b
0x1801ad334  jnz     short loc_1801AD369
0x1801ad336  lea     rdx, aAllowautoupdat; "AllowAutoUpdate"
0x1801ad33d  mov     rcx, r14; this
0x1801ad340  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad345  mov     edi, eax
0x1801ad347  test    eax, eax
0x1801ad349  jz      short loc_1801AD369
0x1801ad34b  mov     rcx, [rsp+0C8h+var_88]
0x1801ad350  test    rcx, rcx
0x1801ad353  jz      short loc_1801AD364
0x1801ad355  mov     rax, [rcx]
0x1801ad358  mov     edx, r15d
0x1801ad35b  mov     rax, [rax]
0x1801ad35e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad363  nop
0x1801ad364  jmp     loc_1801AE52A
0x1801ad369  lea     r8, [rsi+80h]; void *
0x1801ad370  cmp     [r8+4], r15b
0x1801ad374  jnz     short loc_1801AD3A9
0x1801ad376  lea     rdx, aAllowautowindo; "AllowAutoWindowsUpdateDownloadOverMeter"...
0x1801ad37d  mov     rcx, r14; this
0x1801ad380  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad385  mov     edi, eax
0x1801ad387  test    eax, eax
0x1801ad389  jz      short loc_1801AD3A9
0x1801ad38b  mov     rcx, [rsp+0C8h+var_88]
0x1801ad390  test    rcx, rcx
0x1801ad393  jz      short loc_1801AD3A4
0x1801ad395  mov     rax, [rcx]
0x1801ad398  mov     edx, r15d
0x1801ad39b  mov     rax, [rax]
0x1801ad39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad3a3  nop
0x1801ad3a4  jmp     loc_1801AE52A
0x1801ad3a9  lea     r8, [rsi+88h]; void *
0x1801ad3b0  cmp     [r8+4], r15b
0x1801ad3b4  jnz     short loc_1801AD3E9
0x1801ad3b6  lea     rdx, aAllowtemporary; "AllowTemporaryEnterpriseFeatureControl"
0x1801ad3bd  mov     rcx, r14; this
0x1801ad3c0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad3c5  mov     edi, eax
0x1801ad3c7  test    eax, eax
0x1801ad3c9  jz      short loc_1801AD3E9
0x1801ad3cb  mov     rcx, [rsp+0C8h+var_88]
0x1801ad3d0  test    rcx, rcx
0x1801ad3d3  jz      short loc_1801AD3E4
0x1801ad3d5  mov     rax, [rcx]
0x1801ad3d8  mov     edx, r15d
0x1801ad3db  mov     rax, [rax]
0x1801ad3de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad3e3  nop
0x1801ad3e4  jmp     loc_1801AE52A
0x1801ad3e9  lea     r8, [rsi+90h]; void *
0x1801ad3f0  cmp     [r8+4], r15b
0x1801ad3f4  jnz     short loc_1801AD429
0x1801ad3f6  lea     rdx, aAllowoptionalc; "AllowOptionalContent"
0x1801ad3fd  mov     rcx, r14; this
0x1801ad400  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad405  mov     edi, eax
0x1801ad407  test    eax, eax
0x1801ad409  jz      short loc_1801AD429
0x1801ad40b  mov     rcx, [rsp+0C8h+var_88]
0x1801ad410  test    rcx, rcx
0x1801ad413  jz      short loc_1801AD424
0x1801ad415  mov     rax, [rcx]
0x1801ad418  mov     edx, r15d
0x1801ad41b  mov     rax, [rax]
0x1801ad41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad423  nop
0x1801ad424  jmp     loc_1801AE52A
0x1801ad429  lea     r8, [rsi+98h]; void *
0x1801ad430  cmp     [r8+4], r15b
0x1801ad434  jnz     short loc_1801AD469
0x1801ad436  lea     rdx, aAlwaysautorebo; "AlwaysAutoRebootAtScheduledTimeMinutes"
0x1801ad43d  mov     rcx, r14; this
0x1801ad440  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad445  mov     edi, eax
0x1801ad447  test    eax, eax
0x1801ad449  jz      short loc_1801AD469
0x1801ad44b  mov     rcx, [rsp+0C8h+var_88]
0x1801ad450  test    rcx, rcx
0x1801ad453  jz      short loc_1801AD464
0x1801ad455  mov     rax, [rcx]
0x1801ad458  mov     edx, r15d
0x1801ad45b  mov     rax, [rax]
0x1801ad45e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad463  nop
0x1801ad464  jmp     loc_1801AE52A
0x1801ad469  lea     r8, [rsi+0A0h]; void *
0x1801ad470  cmp     [r8+4], r15b
0x1801ad474  jnz     short loc_1801AD4A9
0x1801ad476  lea     rdx, aAllowmuupdates; "AllowMUUpdateService"
0x1801ad47d  mov     rcx, r14; this
0x1801ad480  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad485  mov     edi, eax
0x1801ad487  test    eax, eax
0x1801ad489  jz      short loc_1801AD4A9
0x1801ad48b  mov     rcx, [rsp+0C8h+var_88]
0x1801ad490  test    rcx, rcx
0x1801ad493  jz      short loc_1801AD4A4
0x1801ad495  mov     rax, [rcx]
0x1801ad498  mov     edx, r15d
0x1801ad49b  mov     rax, [rax]
0x1801ad49e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad4a3  nop
0x1801ad4a4  jmp     loc_1801AE52A
0x1801ad4a9  lea     r8, [rsi+0A8h]; void *
0x1801ad4b0  cmp     [r8+4], r15b
0x1801ad4b4  jnz     short loc_1801AD4E9
0x1801ad4b6  lea     rdx, aAllownonmicros; "AllowNonMicrosoftSignedUpdate"
0x1801ad4bd  mov     rcx, r14; this
0x1801ad4c0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad4c5  mov     edi, eax
0x1801ad4c7  test    eax, eax
0x1801ad4c9  jz      short loc_1801AD4E9
0x1801ad4cb  mov     rcx, [rsp+0C8h+var_88]
0x1801ad4d0  test    rcx, rcx
0x1801ad4d3  jz      short loc_1801AD4E4
0x1801ad4d5  mov     rax, [rcx]
0x1801ad4d8  mov     edx, r15d
0x1801ad4db  mov     rax, [rax]
0x1801ad4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad4e3  nop
0x1801ad4e4  jmp     loc_1801AE52A
0x1801ad4e9  lea     r8, [rsi+0B0h]; void *
0x1801ad4f0  cmp     [r8+4], r15b
0x1801ad4f4  jnz     short loc_1801AD529
0x1801ad4f6  lea     rdx, aAllowupdateser; "AllowUpdateService"
0x1801ad4fd  mov     rcx, r14; this
0x1801ad500  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad505  mov     edi, eax
0x1801ad507  test    eax, eax
0x1801ad509  jz      short loc_1801AD529
0x1801ad50b  mov     rcx, [rsp+0C8h+var_88]
0x1801ad510  test    rcx, rcx
0x1801ad513  jz      short loc_1801AD524
0x1801ad515  mov     rax, [rcx]
0x1801ad518  mov     edx, r15d
0x1801ad51b  mov     rax, [rax]
0x1801ad51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad523  nop
0x1801ad524  jmp     loc_1801AE52A
0x1801ad529  lea     r8, [rsi+0B8h]; void *
0x1801ad530  cmp     [r8+4], r15b
0x1801ad534  jnz     short loc_1801AD569
0x1801ad536  lea     rdx, aAutomaticmaint; "AutomaticMaintenanceWakeUp"
0x1801ad53d  mov     rcx, r14; this
0x1801ad540  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801ad545  mov     edi, eax
0x1801ad547  test    eax, eax
0x1801ad549  jz      short loc_1801AD569
0x1801ad54b  mov     rcx, [rsp+0C8h+var_88]
0x1801ad550  test    rcx, rcx
0x1801ad553  jz      short loc_1801AD564
0x1801ad555  mov     rax, [rcx]
0x1801ad558  mov     edx, r15d
0x1801ad55b  mov     rax, [rax]
0x1801ad55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad563  nop
0x1801ad564  jmp     loc_1801AE52A
  ... truncated ...
```
