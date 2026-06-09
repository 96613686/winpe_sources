# MDM_Policy_Config01_Update02_InvokeModifyInstance

- ea: `0x1800f65bc`
- end: `0x1800f7ed0`
- name: `MDM_Policy_Config01_Update02_InvokeModifyInstance`
- size: `6420`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f7ee0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x1800f65bc`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1800f680a`: `AllowAutoUpdate`
- `0x1800f684a`: `AllowAutoWindowsUpdateDownloadOverMeteredNetwork`
- `0x1800f688a`: `AllowTemporaryEnterpriseFeatureControl`
- `0x1800f690a`: `AlwaysAutoRebootAtScheduledTimeMinutes`
- `0x1800f694a`: `AllowMUUpdateService`
- `0x1800f698a`: `AllowNonMicrosoftSignedUpdate`
- `0x1800f69ca`: `AllowUpdateService`
- `0x1800f6a8a`: `AutoRestartDeadlinePeriodInDaysForFeatureUpdates`
- `0x1800f6b4a`: `BranchReadinessLevel`
- `0x1800f6b8a`: `ConfigureDeadlineForFeatureUpdates`
- `0x1800f6bca`: `ConfigureDeadlineForQualityUpdates`
- `0x1800f6c0a`: `ConfigureDeadlineGracePeriod`
- `0x1800f6c4a`: `ConfigureDeadlineGracePeriodForFeatureUpdates`
- `0x1800f6c8a`: `ConfigureDeadlineNoAutoReboot`
- `0x1800f6cca`: `ConfigureFeatureUpdateUninstallPeriod`
- `0x1800f6d0a`: `DeferFeatureUpdatesPeriodInDays`
- `0x1800f6d4a`: `DeferQualityUpdatesPeriodInDays`
- `0x1800f6d8a`: `DeferUpdatePeriod`
- `0x1800f6eca`: `DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection`
- `0x1800f6f4a`: `EngagedRestartDeadlineForFeatureUpdates`
- `0x1800f6fca`: `EngagedRestartSnoozeScheduleForFeatureUpdates`
- `0x1800f704a`: `EngagedRestartTransitionScheduleForFeatureUpdates`
- `0x1800f708a`: `ExcludeWUDriversInQualityUpdate`
- `0x1800f714a`: `IgnoreMOUpdateDownloadLimit`
- `0x1800f720a`: `PauseFeatureUpdates`
- `0x1800f724a`: `PauseFeatureUpdatesStartTime`
- `0x1800f728a`: `PauseQualityUpdates`
- `0x1800f72ca`: `PauseQualityUpdatesStartTime`
- `0x1800f730a`: `PhoneUpdateRestrictions`
- `0x1800f738a`: `RequireUpdateApproval`
- `0x1800f73ca`: `ScheduledInstallDay`
- `0x1800f740a`: `ScheduledInstallEveryWeek`
- `0x1800f744a`: `ScheduledInstallFirstWeek`
- `0x1800f748a`: `ScheduledInstallFourthWeek`
- `0x1800f74ca`: `ScheduledInstallSecondWeek`
- `0x1800f750a`: `ScheduledInstallThirdWeek`
- `0x1800f754a`: `ScheduledInstallTime`
- `0x1800f764a`: `SetDisablePauseUXAccess`
- `0x1800f768a`: `SetDisableUXWUAccess`
- `0x1800f770a`: `SetPolicyDrivenUpdateSourceForDriverUpdates`
- `0x1800f774a`: `SetPolicyDrivenUpdateSourceForFeatureUpdates`
- `0x1800f778a`: `SetPolicyDrivenUpdateSourceForOtherUpdates`
- `0x1800f77ca`: `SetPolicyDrivenUpdateSourceForQualityUpdates`
- `0x1800f780a`: `SetProxyBehaviorForUpdateDetection`
- `0x1800f78ca`: `UpdateNotificationLevel`
- `0x1800f790a`: `UpdateServiceUrl`
- `0x1800f794a`: `UpdateServiceUrlAlternate`
- `0x1800f79ca`: `MaintenanceWindowUpdateActions`
- `0x1800f6607`: `MDM_Policy_Config01_Update02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Update02_InvokeModifyInstance(__int64 a1, __int64 a2)
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
  v12[2] = "MDM_Policy_Config01_Update02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v4 = v18;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180368659,
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
                                 &MDM_Policy_Config01_Update02_NodeList,
                                 92,
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
            (struct WmiNodeInfo *)&MDM_Policy_Config01_Update02_NodeList,
            0x5Cu);
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
          else if ( *(_BYTE *)(a2 + 729) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowEnabled",
                                  (void *)(a2 + 728))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 736) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowUpdateActions",
                                  (void *)(a2 + 732))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 752) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowStartDate",
                                  (void *)(a2 + 744))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 768) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowStartTime",
                                  (void *)(a2 + 760))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 780) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowDurationHours",
                                  (void *)(a2 + 776))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 788) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowRepeatScheduleOption",
                                  (void *)(a2 + 784))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 793) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowWeeklySunday",
                                  (void *)(a2 + 792))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 796) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowWeeklyMonday",
                                  (void *)(a2 + 795))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 799) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowWeeklyTuesday",
                                  (void *)(a2 + 798))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 802) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowWeeklyWednesday",
                                  (void *)(a2 + 801))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 805) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowWeeklyThursday",
                                  (void *)(a2 + 804))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 808) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowWeeklyFriday",
                                  (void *)(a2 + 807))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 811) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowWeeklySaturday",
                                  (void *)(a2 + 810))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 820) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowMonthlySchedule",
                                  (void *)(a2 + 816))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 828) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowMonthlyMonthBasedDayOfMonth",
                                  (void *)(a2 + 824))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 836) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowMonthlyWeekBasedOccurrenceInMonth",
                                  (void *)(a2 + 832))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 844) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowMonthlyWeekBasedDayOfTheWeek",
                                  (void *)(a2 + 840))) != MI_RESULT_OK )
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
      word_18035C282,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800f65bc  mov     r11, rsp
0x1800f65bf  mov     [r11+18h], rsi
0x1800f65c3  push    rdi
0x1800f65c4  push    r14
0x1800f65c6  push    r15
0x1800f65c8  sub     rsp, 0B0h
0x1800f65cf  mov     rax, cs:__security_cookie
0x1800f65d6  xor     rax, rsp
0x1800f65d9  mov     [rsp+0C8h+var_28], rax
0x1800f65e1  mov     rsi, rdx
0x1800f65e4  mov     rdi, rcx
0x1800f65e7  mov     [rsp+0C8h+var_50], 0
0x1800f65ef  mov     [rsp+0C8h+var_4C], 0
0x1800f65f4  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800f65fb  mov     [r11-80h], rax
0x1800f65ff  lea     rax, [r11-50h]
0x1800f6603  mov     [r11-78h], rax
0x1800f6607  lea     rax, aMdmPolicyConfi_91; "MDM_Policy_Config01_Update02"
0x1800f660e  mov     [r11-70h], rax
0x1800f6612  lea     rcx, [r11-50h]
0x1800f6616  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800f661b  mov     eax, cs:dword_180380B68
0x1800f6621  cmp     eax, 5
0x1800f6624  jbe     short loc_1800F6697
0x1800f6626  mov     rdx, 200000000000h
0x1800f6630  lea     rcx, dword_180380B68
0x1800f6637  call    _tlgKeywordOn
0x1800f663c  test    al, al
0x1800f663e  jz      short loc_1800F6697
0x1800f6640  cmp     [rsp+0C8h+var_4C], 0
0x1800f6645  jz      short loc_1800F6679
0x1800f6647  cmp     [rsp+0C8h+var_38], 0
0x1800f664f  jnz     short loc_1800F666F
0x1800f6651  cmp     [rsp+0C8h+var_34], 0
0x1800f6659  jnz     short loc_1800F666F
0x1800f665b  cmp     [rsp+0C8h+var_30], 0
0x1800f6663  jnz     short loc_1800F666F
0x1800f6665  cmp     [rsp+0C8h+var_2C], 0
0x1800f666d  jz      short loc_1800F6679
0x1800f666f  lea     r9, [rsp+0C8h+var_38]
0x1800f6677  jmp     short loc_1800F667C
0x1800f6679  xor     r9d, r9d
0x1800f667c  lea     r8, [rsp+0C8h+var_48]
0x1800f6684  lea     rdx, byte_180368659
0x1800f668b  lea     rcx, dword_180380B68
0x1800f6692  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800f6697  cmp     byte ptr [rsi+48h], 0
0x1800f669b  jz      loc_1800F7E39
0x1800f66a1  cmp     byte ptr [rsi+58h], 0
0x1800f66a5  jz      loc_1800F7E39
0x1800f66ab  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800f66af  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800f66b3  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1800f66ba  lea     rcx, [rsp+0C8h+var_80]; this
0x1800f66bf  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800f66c4  nop
0x1800f66c5  mov     [rsp+0C8h+var_88], 0
0x1800f66ce  lea     rax, [rsp+0C8h+var_88]
0x1800f66d3  mov     [rsp+0C8h+var_98], rax
0x1800f66d8  mov     [rsp+0C8h+var_A0], 3
0x1800f66e0  mov     [rsp+0C8h+var_A8], 5Ch ; '\'
0x1800f66e8  lea     r9, ?MDM_Policy_Config01_Update02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Update02_NodeList
0x1800f66ef  mov     r8, [rsi+40h]
0x1800f66f3  mov     rdx, [rsi+50h]
0x1800f66f7  mov     rcx, rdi
0x1800f66fa  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800f66ff  mov     edi, eax
0x1800f6701  test    eax, eax
0x1800f6703  jz      short loc_1800F670A
0x1800f6705  jmp     loc_1800F7E3E
0x1800f670a  lea     rax, [rsp+0C8h+var_88]
0x1800f670f  mov     [rsp+0C8h+var_60], rax
0x1800f6714  mov     r15d, 1
0x1800f671a  mov     [rsp+0C8h+var_58], r15b
0x1800f671f  mov     r14, [rsp+0C8h+var_88]
0x1800f6724  test    r14, r14
0x1800f6727  jnz     short loc_1800F6731
0x1800f6729  mov     edi, r15d
0x1800f672c  jmp     loc_1800F7E3E
0x1800f6731  mov     r9d, 5Ch ; '\'; unsigned int
0x1800f6737  lea     r8, ?MDM_Policy_Config01_Update02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800f673e  mov     rdx, rsi; struct _MI_Instance *
0x1800f6741  mov     rcx, r14; this
0x1800f6744  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800f6749  lea     r8, [rsi+60h]; void *
0x1800f674d  cmp     [r8+4], r15b
0x1800f6751  jnz     short loc_1800F6786
0x1800f6753  lea     rdx, aActivehoursend; "ActiveHoursEnd"
0x1800f675a  mov     rcx, r14; this
0x1800f675d  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6762  mov     edi, eax
0x1800f6764  test    eax, eax
0x1800f6766  jz      short loc_1800F6786
0x1800f6768  mov     rcx, [rsp+0C8h+var_88]
0x1800f676d  test    rcx, rcx
0x1800f6770  jz      short loc_1800F6781
0x1800f6772  mov     rax, [rcx]
0x1800f6775  mov     edx, r15d
0x1800f6778  mov     rax, [rax]
0x1800f677b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6780  nop
0x1800f6781  jmp     loc_1800F7E3E
0x1800f6786  lea     r8, [rsi+68h]; void *
0x1800f678a  cmp     [r8+4], r15b
0x1800f678e  jnz     short loc_1800F67C3
0x1800f6790  lea     rdx, aActivehoursmax; "ActiveHoursMaxRange"
0x1800f6797  mov     rcx, r14; this
0x1800f679a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f679f  mov     edi, eax
0x1800f67a1  test    eax, eax
0x1800f67a3  jz      short loc_1800F67C3
0x1800f67a5  mov     rcx, [rsp+0C8h+var_88]
0x1800f67aa  test    rcx, rcx
0x1800f67ad  jz      short loc_1800F67BE
0x1800f67af  mov     rax, [rcx]
0x1800f67b2  mov     edx, r15d
0x1800f67b5  mov     rax, [rax]
0x1800f67b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f67bd  nop
0x1800f67be  jmp     loc_1800F7E3E
0x1800f67c3  lea     r8, [rsi+70h]; void *
0x1800f67c7  cmp     [r8+4], r15b
0x1800f67cb  jnz     short loc_1800F6800
0x1800f67cd  lea     rdx, aActivehourssta; "ActiveHoursStart"
0x1800f67d4  mov     rcx, r14; this
0x1800f67d7  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f67dc  mov     edi, eax
0x1800f67de  test    eax, eax
0x1800f67e0  jz      short loc_1800F6800
0x1800f67e2  mov     rcx, [rsp+0C8h+var_88]
0x1800f67e7  test    rcx, rcx
0x1800f67ea  jz      short loc_1800F67FB
0x1800f67ec  mov     rax, [rcx]
0x1800f67ef  mov     edx, r15d
0x1800f67f2  mov     rax, [rax]
0x1800f67f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f67fa  nop
0x1800f67fb  jmp     loc_1800F7E3E
0x1800f6800  lea     r8, [rsi+78h]; void *
0x1800f6804  cmp     [r8+4], r15b
0x1800f6808  jnz     short loc_1800F683D
0x1800f680a  lea     rdx, aAllowautoupdat; "AllowAutoUpdate"
0x1800f6811  mov     rcx, r14; this
0x1800f6814  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6819  mov     edi, eax
0x1800f681b  test    eax, eax
0x1800f681d  jz      short loc_1800F683D
0x1800f681f  mov     rcx, [rsp+0C8h+var_88]
0x1800f6824  test    rcx, rcx
0x1800f6827  jz      short loc_1800F6838
0x1800f6829  mov     rax, [rcx]
0x1800f682c  mov     edx, r15d
0x1800f682f  mov     rax, [rax]
0x1800f6832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6837  nop
0x1800f6838  jmp     loc_1800F7E3E
0x1800f683d  lea     r8, [rsi+80h]; void *
0x1800f6844  cmp     [r8+4], r15b
0x1800f6848  jnz     short loc_1800F687D
0x1800f684a  lea     rdx, aAllowautowindo; "AllowAutoWindowsUpdateDownloadOverMeter"...
0x1800f6851  mov     rcx, r14; this
0x1800f6854  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6859  mov     edi, eax
0x1800f685b  test    eax, eax
0x1800f685d  jz      short loc_1800F687D
0x1800f685f  mov     rcx, [rsp+0C8h+var_88]
0x1800f6864  test    rcx, rcx
0x1800f6867  jz      short loc_1800F6878
0x1800f6869  mov     rax, [rcx]
0x1800f686c  mov     edx, r15d
0x1800f686f  mov     rax, [rax]
0x1800f6872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6877  nop
0x1800f6878  jmp     loc_1800F7E3E
0x1800f687d  lea     r8, [rsi+88h]; void *
0x1800f6884  cmp     [r8+4], r15b
0x1800f6888  jnz     short loc_1800F68BD
0x1800f688a  lea     rdx, aAllowtemporary; "AllowTemporaryEnterpriseFeatureControl"
0x1800f6891  mov     rcx, r14; this
0x1800f6894  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6899  mov     edi, eax
0x1800f689b  test    eax, eax
0x1800f689d  jz      short loc_1800F68BD
0x1800f689f  mov     rcx, [rsp+0C8h+var_88]
0x1800f68a4  test    rcx, rcx
0x1800f68a7  jz      short loc_1800F68B8
0x1800f68a9  mov     rax, [rcx]
0x1800f68ac  mov     edx, r15d
0x1800f68af  mov     rax, [rax]
0x1800f68b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f68b7  nop
0x1800f68b8  jmp     loc_1800F7E3E
0x1800f68bd  lea     r8, [rsi+90h]; void *
0x1800f68c4  cmp     [r8+4], r15b
0x1800f68c8  jnz     short loc_1800F68FD
0x1800f68ca  lea     rdx, aAllowoptionalc; "AllowOptionalContent"
0x1800f68d1  mov     rcx, r14; this
0x1800f68d4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f68d9  mov     edi, eax
0x1800f68db  test    eax, eax
0x1800f68dd  jz      short loc_1800F68FD
0x1800f68df  mov     rcx, [rsp+0C8h+var_88]
0x1800f68e4  test    rcx, rcx
0x1800f68e7  jz      short loc_1800F68F8
0x1800f68e9  mov     rax, [rcx]
0x1800f68ec  mov     edx, r15d
0x1800f68ef  mov     rax, [rax]
0x1800f68f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f68f7  nop
0x1800f68f8  jmp     loc_1800F7E3E
0x1800f68fd  lea     r8, [rsi+98h]; void *
0x1800f6904  cmp     [r8+4], r15b
0x1800f6908  jnz     short loc_1800F693D
0x1800f690a  lea     rdx, aAlwaysautorebo; "AlwaysAutoRebootAtScheduledTimeMinutes"
0x1800f6911  mov     rcx, r14; this
0x1800f6914  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6919  mov     edi, eax
0x1800f691b  test    eax, eax
0x1800f691d  jz      short loc_1800F693D
0x1800f691f  mov     rcx, [rsp+0C8h+var_88]
0x1800f6924  test    rcx, rcx
0x1800f6927  jz      short loc_1800F6938
0x1800f6929  mov     rax, [rcx]
0x1800f692c  mov     edx, r15d
0x1800f692f  mov     rax, [rax]
0x1800f6932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6937  nop
0x1800f6938  jmp     loc_1800F7E3E
0x1800f693d  lea     r8, [rsi+0A0h]; void *
0x1800f6944  cmp     [r8+4], r15b
0x1800f6948  jnz     short loc_1800F697D
0x1800f694a  lea     rdx, aAllowmuupdates; "AllowMUUpdateService"
0x1800f6951  mov     rcx, r14; this
0x1800f6954  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6959  mov     edi, eax
0x1800f695b  test    eax, eax
0x1800f695d  jz      short loc_1800F697D
0x1800f695f  mov     rcx, [rsp+0C8h+var_88]
0x1800f6964  test    rcx, rcx
0x1800f6967  jz      short loc_1800F6978
0x1800f6969  mov     rax, [rcx]
0x1800f696c  mov     edx, r15d
0x1800f696f  mov     rax, [rax]
0x1800f6972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6977  nop
0x1800f6978  jmp     loc_1800F7E3E
0x1800f697d  lea     r8, [rsi+0A8h]; void *
0x1800f6984  cmp     [r8+4], r15b
0x1800f6988  jnz     short loc_1800F69BD
0x1800f698a  lea     rdx, aAllownonmicros; "AllowNonMicrosoftSignedUpdate"
0x1800f6991  mov     rcx, r14; this
0x1800f6994  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6999  mov     edi, eax
0x1800f699b  test    eax, eax
0x1800f699d  jz      short loc_1800F69BD
0x1800f699f  mov     rcx, [rsp+0C8h+var_88]
0x1800f69a4  test    rcx, rcx
0x1800f69a7  jz      short loc_1800F69B8
0x1800f69a9  mov     rax, [rcx]
0x1800f69ac  mov     edx, r15d
0x1800f69af  mov     rax, [rax]
0x1800f69b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f69b7  nop
0x1800f69b8  jmp     loc_1800F7E3E
0x1800f69bd  lea     r8, [rsi+0B0h]; void *
0x1800f69c4  cmp     [r8+4], r15b
0x1800f69c8  jnz     short loc_1800F69FD
0x1800f69ca  lea     rdx, aAllowupdateser; "AllowUpdateService"
0x1800f69d1  mov     rcx, r14; this
0x1800f69d4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f69d9  mov     edi, eax
0x1800f69db  test    eax, eax
0x1800f69dd  jz      short loc_1800F69FD
0x1800f69df  mov     rcx, [rsp+0C8h+var_88]
0x1800f69e4  test    rcx, rcx
0x1800f69e7  jz      short loc_1800F69F8
0x1800f69e9  mov     rax, [rcx]
0x1800f69ec  mov     edx, r15d
0x1800f69ef  mov     rax, [rax]
0x1800f69f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f69f7  nop
0x1800f69f8  jmp     loc_1800F7E3E
0x1800f69fd  lea     r8, [rsi+0B8h]; void *
0x1800f6a04  cmp     [r8+4], r15b
0x1800f6a08  jnz     short loc_1800F6A3D
0x1800f6a0a  lea     rdx, aAutomaticmaint; "AutomaticMaintenanceWakeUp"
0x1800f6a11  mov     rcx, r14; this
0x1800f6a14  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6a19  mov     edi, eax
0x1800f6a1b  test    eax, eax
0x1800f6a1d  jz      short loc_1800F6A3D
0x1800f6a1f  mov     rcx, [rsp+0C8h+var_88]
0x1800f6a24  test    rcx, rcx
0x1800f6a27  jz      short loc_1800F6A38
0x1800f6a29  mov     rax, [rcx]
0x1800f6a2c  mov     edx, r15d
0x1800f6a2f  mov     rax, [rax]
0x1800f6a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6a37  nop
0x1800f6a38  jmp     loc_1800F7E3E
  ... truncated ...
```
