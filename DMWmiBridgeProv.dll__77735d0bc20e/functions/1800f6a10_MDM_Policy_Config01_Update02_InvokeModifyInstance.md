# MDM_Policy_Config01_Update02_InvokeModifyInstance

- ea: `0x1800f6a10`
- end: `0x1800f8323`
- name: `MDM_Policy_Config01_Update02_InvokeModifyInstance`
- size: `6419`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f8330`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x1800f6a10`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1800f6c5e`: `AllowAutoUpdate`
- `0x1800f6c9e`: `AllowAutoWindowsUpdateDownloadOverMeteredNetwork`
- `0x1800f6cde`: `AllowTemporaryEnterpriseFeatureControl`
- `0x1800f6d5e`: `AlwaysAutoRebootAtScheduledTimeMinutes`
- `0x1800f6d9e`: `AllowMUUpdateService`
- `0x1800f6dde`: `AllowNonMicrosoftSignedUpdate`
- `0x1800f6e1e`: `AllowUpdateService`
- `0x1800f6ede`: `AutoRestartDeadlinePeriodInDaysForFeatureUpdates`
- `0x1800f6f9e`: `BranchReadinessLevel`
- `0x1800f6fde`: `ConfigureDeadlineForFeatureUpdates`
- `0x1800f701e`: `ConfigureDeadlineForQualityUpdates`
- `0x1800f705e`: `ConfigureDeadlineGracePeriod`
- `0x1800f709e`: `ConfigureDeadlineGracePeriodForFeatureUpdates`
- `0x1800f70de`: `ConfigureDeadlineNoAutoReboot`
- `0x1800f711e`: `ConfigureFeatureUpdateUninstallPeriod`
- `0x1800f715e`: `DeferFeatureUpdatesPeriodInDays`
- `0x1800f719e`: `DeferQualityUpdatesPeriodInDays`
- `0x1800f71de`: `DeferUpdatePeriod`
- `0x1800f731e`: `DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection`
- `0x1800f739e`: `EngagedRestartDeadlineForFeatureUpdates`
- `0x1800f741e`: `EngagedRestartSnoozeScheduleForFeatureUpdates`
- `0x1800f749e`: `EngagedRestartTransitionScheduleForFeatureUpdates`
- `0x1800f74de`: `ExcludeWUDriversInQualityUpdate`
- `0x1800f759e`: `IgnoreMOUpdateDownloadLimit`
- `0x1800f765e`: `PauseFeatureUpdates`
- `0x1800f769e`: `PauseFeatureUpdatesStartTime`
- `0x1800f76de`: `PauseQualityUpdates`
- `0x1800f771e`: `PauseQualityUpdatesStartTime`
- `0x1800f775e`: `PhoneUpdateRestrictions`
- `0x1800f77de`: `RequireUpdateApproval`
- `0x1800f781e`: `ScheduledInstallDay`
- `0x1800f785e`: `ScheduledInstallEveryWeek`
- `0x1800f789e`: `ScheduledInstallFirstWeek`
- `0x1800f78de`: `ScheduledInstallFourthWeek`
- `0x1800f791e`: `ScheduledInstallSecondWeek`
- `0x1800f795e`: `ScheduledInstallThirdWeek`
- `0x1800f799e`: `ScheduledInstallTime`
- `0x1800f7a9e`: `SetDisablePauseUXAccess`
- `0x1800f7ade`: `SetDisableUXWUAccess`
- `0x1800f7b5e`: `SetPolicyDrivenUpdateSourceForDriverUpdates`
- `0x1800f7b9e`: `SetPolicyDrivenUpdateSourceForFeatureUpdates`
- `0x1800f7bde`: `SetPolicyDrivenUpdateSourceForOtherUpdates`
- `0x1800f7c1e`: `SetPolicyDrivenUpdateSourceForQualityUpdates`
- `0x1800f7c5e`: `SetProxyBehaviorForUpdateDetection`
- `0x1800f7d1e`: `UpdateNotificationLevel`
- `0x1800f7d5e`: `UpdateServiceUrl`
- `0x1800f7d9e`: `UpdateServiceUrlAlternate`
- `0x1800f7e1e`: `MaintenanceWindowUpdateActions`
- `0x1800f6a5b`: `MDM_Policy_Config01_Update02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Update02_InvokeModifyInstance(__int64 a1, __int64 a2)
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
      inserted = CreateRequestHandlerInstance(
                   a1,
                   *(wchar_t **)(a2 + 80),
                   *(const unsigned __int16 **)(a2 + 64),
                   (struct WmiNodeInfo *)&MDM_Policy_Config01_Update02_NodeList,
                   0x5Cu,
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
            (struct WmiNodeInfo *)&MDM_Policy_Config01_Update02_NodeList,
            0x5Cu);
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
          else if ( *(_BYTE *)(a2 + 729) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowEnabled",
                                  (LONG *)(a2 + 728))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 736) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowUpdateActions",
                                  (LONG *)(a2 + 732))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 752) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowStartDate",
                                  (LONG *)(a2 + 744))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 768) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowStartTime",
                                  (LONG *)(a2 + 760))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 780) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowDurationHours",
                                  (LONG *)(a2 + 776))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 788) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowRepeatScheduleOption",
                                  (LONG *)(a2 + 784))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 793) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowWeeklySunday",
                                  (LONG *)(a2 + 792))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 796) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowWeeklyMonday",
                                  (LONG *)(a2 + 795))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 799) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowWeeklyTuesday",
                                  (LONG *)(a2 + 798))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 802) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowWeeklyWednesday",
                                  (LONG *)(a2 + 801))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 805) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowWeeklyThursday",
                                  (LONG *)(a2 + 804))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 808) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowWeeklyFriday",
                                  (LONG *)(a2 + 807))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 811) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowWeeklySaturday",
                                  (LONG *)(a2 + 810))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 820) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowMonthlySchedule",
                                  (LONG *)(a2 + 816))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 828) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowMonthlyMonthBasedDayOfMonth",
                                  (LONG *)(a2 + 824))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 836) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowMonthlyWeekBasedOccurrenceInMonth",
                                  (LONG *)(a2 + 832))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 844) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MaintenanceWindowMonthlyWeekBasedDayOfTheWeek",
                                  (LONG *)(a2 + 840))) != 0 )
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
      word_18035C282,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return inserted;
}

```

## disassembly

```asm
0x1800f6a10  mov     r11, rsp
0x1800f6a13  mov     [r11+18h], rsi
0x1800f6a17  push    rdi
0x1800f6a18  push    r14
0x1800f6a1a  push    r15
0x1800f6a1c  sub     rsp, 0B0h
0x1800f6a23  mov     rax, cs:__security_cookie
0x1800f6a2a  xor     rax, rsp
0x1800f6a2d  mov     [rsp+0C8h+var_28], rax
0x1800f6a35  mov     rsi, rdx
0x1800f6a38  mov     rdi, rcx
0x1800f6a3b  mov     [rsp+0C8h+var_50], 0
0x1800f6a43  mov     [rsp+0C8h+var_4C], 0
0x1800f6a48  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800f6a4f  mov     [r11-80h], rax
0x1800f6a53  lea     rax, [r11-50h]
0x1800f6a57  mov     [r11-78h], rax
0x1800f6a5b  lea     rax, aMdmPolicyConfi_91; "MDM_Policy_Config01_Update02"
0x1800f6a62  mov     [r11-70h], rax
0x1800f6a66  lea     rcx, [r11-50h]
0x1800f6a6a  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800f6a6f  mov     eax, cs:dword_180380B68
0x1800f6a75  cmp     eax, 5
0x1800f6a78  jbe     short loc_1800F6AEB
0x1800f6a7a  mov     rdx, 200000000000h
0x1800f6a84  lea     rcx, dword_180380B68
0x1800f6a8b  call    _tlgKeywordOn
0x1800f6a90  test    al, al
0x1800f6a92  jz      short loc_1800F6AEB
0x1800f6a94  cmp     [rsp+0C8h+var_4C], 0
0x1800f6a99  jz      short loc_1800F6ACD
0x1800f6a9b  cmp     [rsp+0C8h+var_38], 0
0x1800f6aa3  jnz     short loc_1800F6AC3
0x1800f6aa5  cmp     [rsp+0C8h+var_34], 0
0x1800f6aad  jnz     short loc_1800F6AC3
0x1800f6aaf  cmp     [rsp+0C8h+var_30], 0
0x1800f6ab7  jnz     short loc_1800F6AC3
0x1800f6ab9  cmp     [rsp+0C8h+var_2C], 0
0x1800f6ac1  jz      short loc_1800F6ACD
0x1800f6ac3  lea     r9, [rsp+0C8h+var_38]
0x1800f6acb  jmp     short loc_1800F6AD0
0x1800f6acd  xor     r9d, r9d
0x1800f6ad0  lea     r8, [rsp+0C8h+var_48]
0x1800f6ad8  lea     rdx, byte_180368659
0x1800f6adf  lea     rcx, dword_180380B68
0x1800f6ae6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800f6aeb  cmp     byte ptr [rsi+48h], 0
0x1800f6aef  jz      loc_1800F828D
0x1800f6af5  cmp     byte ptr [rsi+58h], 0
0x1800f6af9  jz      loc_1800F828D
0x1800f6aff  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800f6b03  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800f6b07  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1800f6b0e  lea     rcx, [rsp+0C8h+var_80]; this
0x1800f6b13  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800f6b18  nop
0x1800f6b19  mov     [rsp+0C8h+var_88], 0
0x1800f6b22  lea     rax, [rsp+0C8h+var_88]
0x1800f6b27  mov     [rsp+0C8h+var_98], rax
0x1800f6b2c  mov     [rsp+0C8h+var_A0], 3
0x1800f6b34  mov     [rsp+0C8h+var_A8], 5Ch ; '\'
0x1800f6b3c  lea     r9, ?MDM_Policy_Config01_Update02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Update02_NodeList
0x1800f6b43  mov     r8, [rsi+40h]
0x1800f6b47  mov     rdx, [rsi+50h]
0x1800f6b4b  mov     rcx, rdi
0x1800f6b4e  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800f6b53  mov     edi, eax
0x1800f6b55  test    eax, eax
0x1800f6b57  jz      short loc_1800F6B5E
0x1800f6b59  jmp     loc_1800F8292
0x1800f6b5e  lea     rax, [rsp+0C8h+var_88]
0x1800f6b63  mov     [rsp+0C8h+var_60], rax
0x1800f6b68  mov     r15d, 1
0x1800f6b6e  mov     [rsp+0C8h+var_58], r15b
0x1800f6b73  mov     r14, [rsp+0C8h+var_88]
0x1800f6b78  test    r14, r14
0x1800f6b7b  jnz     short loc_1800F6B85
0x1800f6b7d  mov     edi, r15d
0x1800f6b80  jmp     loc_1800F8292
0x1800f6b85  mov     r9d, 5Ch ; '\'; unsigned int
0x1800f6b8b  lea     r8, ?MDM_Policy_Config01_Update02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800f6b92  mov     rdx, rsi; struct _MI_Instance *
0x1800f6b95  mov     rcx, r14; this
0x1800f6b98  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800f6b9d  lea     r8, [rsi+60h]; void *
0x1800f6ba1  cmp     [r8+4], r15b
0x1800f6ba5  jnz     short loc_1800F6BDA
0x1800f6ba7  lea     rdx, aActivehoursend; "ActiveHoursEnd"
0x1800f6bae  mov     rcx, r14; this
0x1800f6bb1  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6bb6  mov     edi, eax
0x1800f6bb8  test    eax, eax
0x1800f6bba  jz      short loc_1800F6BDA
0x1800f6bbc  mov     rcx, [rsp+0C8h+var_88]
0x1800f6bc1  test    rcx, rcx
0x1800f6bc4  jz      short loc_1800F6BD5
0x1800f6bc6  mov     rax, [rcx]
0x1800f6bc9  mov     edx, r15d
0x1800f6bcc  mov     rax, [rax]
0x1800f6bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6bd4  nop
0x1800f6bd5  jmp     loc_1800F8292
0x1800f6bda  lea     r8, [rsi+68h]; void *
0x1800f6bde  cmp     [r8+4], r15b
0x1800f6be2  jnz     short loc_1800F6C17
0x1800f6be4  lea     rdx, aActivehoursmax; "ActiveHoursMaxRange"
0x1800f6beb  mov     rcx, r14; this
0x1800f6bee  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6bf3  mov     edi, eax
0x1800f6bf5  test    eax, eax
0x1800f6bf7  jz      short loc_1800F6C17
0x1800f6bf9  mov     rcx, [rsp+0C8h+var_88]
0x1800f6bfe  test    rcx, rcx
0x1800f6c01  jz      short loc_1800F6C12
0x1800f6c03  mov     rax, [rcx]
0x1800f6c06  mov     edx, r15d
0x1800f6c09  mov     rax, [rax]
0x1800f6c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6c11  nop
0x1800f6c12  jmp     loc_1800F8292
0x1800f6c17  lea     r8, [rsi+70h]; void *
0x1800f6c1b  cmp     [r8+4], r15b
0x1800f6c1f  jnz     short loc_1800F6C54
0x1800f6c21  lea     rdx, aActivehourssta; "ActiveHoursStart"
0x1800f6c28  mov     rcx, r14; this
0x1800f6c2b  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6c30  mov     edi, eax
0x1800f6c32  test    eax, eax
0x1800f6c34  jz      short loc_1800F6C54
0x1800f6c36  mov     rcx, [rsp+0C8h+var_88]
0x1800f6c3b  test    rcx, rcx
0x1800f6c3e  jz      short loc_1800F6C4F
0x1800f6c40  mov     rax, [rcx]
0x1800f6c43  mov     edx, r15d
0x1800f6c46  mov     rax, [rax]
0x1800f6c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6c4e  nop
0x1800f6c4f  jmp     loc_1800F8292
0x1800f6c54  lea     r8, [rsi+78h]; void *
0x1800f6c58  cmp     [r8+4], r15b
0x1800f6c5c  jnz     short loc_1800F6C91
0x1800f6c5e  lea     rdx, aAllowautoupdat; "AllowAutoUpdate"
0x1800f6c65  mov     rcx, r14; this
0x1800f6c68  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6c6d  mov     edi, eax
0x1800f6c6f  test    eax, eax
0x1800f6c71  jz      short loc_1800F6C91
0x1800f6c73  mov     rcx, [rsp+0C8h+var_88]
0x1800f6c78  test    rcx, rcx
0x1800f6c7b  jz      short loc_1800F6C8C
0x1800f6c7d  mov     rax, [rcx]
0x1800f6c80  mov     edx, r15d
0x1800f6c83  mov     rax, [rax]
0x1800f6c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6c8b  nop
0x1800f6c8c  jmp     loc_1800F8292
0x1800f6c91  lea     r8, [rsi+80h]; void *
0x1800f6c98  cmp     [r8+4], r15b
0x1800f6c9c  jnz     short loc_1800F6CD1
0x1800f6c9e  lea     rdx, aAllowautowindo; "AllowAutoWindowsUpdateDownloadOverMeter"...
0x1800f6ca5  mov     rcx, r14; this
0x1800f6ca8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6cad  mov     edi, eax
0x1800f6caf  test    eax, eax
0x1800f6cb1  jz      short loc_1800F6CD1
0x1800f6cb3  mov     rcx, [rsp+0C8h+var_88]
0x1800f6cb8  test    rcx, rcx
0x1800f6cbb  jz      short loc_1800F6CCC
0x1800f6cbd  mov     rax, [rcx]
0x1800f6cc0  mov     edx, r15d
0x1800f6cc3  mov     rax, [rax]
0x1800f6cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6ccb  nop
0x1800f6ccc  jmp     loc_1800F8292
0x1800f6cd1  lea     r8, [rsi+88h]; void *
0x1800f6cd8  cmp     [r8+4], r15b
0x1800f6cdc  jnz     short loc_1800F6D11
0x1800f6cde  lea     rdx, aAllowtemporary; "AllowTemporaryEnterpriseFeatureControl"
0x1800f6ce5  mov     rcx, r14; this
0x1800f6ce8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6ced  mov     edi, eax
0x1800f6cef  test    eax, eax
0x1800f6cf1  jz      short loc_1800F6D11
0x1800f6cf3  mov     rcx, [rsp+0C8h+var_88]
0x1800f6cf8  test    rcx, rcx
0x1800f6cfb  jz      short loc_1800F6D0C
0x1800f6cfd  mov     rax, [rcx]
0x1800f6d00  mov     edx, r15d
0x1800f6d03  mov     rax, [rax]
0x1800f6d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6d0b  nop
0x1800f6d0c  jmp     loc_1800F8292
0x1800f6d11  lea     r8, [rsi+90h]; void *
0x1800f6d18  cmp     [r8+4], r15b
0x1800f6d1c  jnz     short loc_1800F6D51
0x1800f6d1e  lea     rdx, aAllowoptionalc; "AllowOptionalContent"
0x1800f6d25  mov     rcx, r14; this
0x1800f6d28  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6d2d  mov     edi, eax
0x1800f6d2f  test    eax, eax
0x1800f6d31  jz      short loc_1800F6D51
0x1800f6d33  mov     rcx, [rsp+0C8h+var_88]
0x1800f6d38  test    rcx, rcx
0x1800f6d3b  jz      short loc_1800F6D4C
0x1800f6d3d  mov     rax, [rcx]
0x1800f6d40  mov     edx, r15d
0x1800f6d43  mov     rax, [rax]
0x1800f6d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6d4b  nop
0x1800f6d4c  jmp     loc_1800F8292
0x1800f6d51  lea     r8, [rsi+98h]; void *
0x1800f6d58  cmp     [r8+4], r15b
0x1800f6d5c  jnz     short loc_1800F6D91
0x1800f6d5e  lea     rdx, aAlwaysautorebo; "AlwaysAutoRebootAtScheduledTimeMinutes"
0x1800f6d65  mov     rcx, r14; this
0x1800f6d68  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6d6d  mov     edi, eax
0x1800f6d6f  test    eax, eax
0x1800f6d71  jz      short loc_1800F6D91
0x1800f6d73  mov     rcx, [rsp+0C8h+var_88]
0x1800f6d78  test    rcx, rcx
0x1800f6d7b  jz      short loc_1800F6D8C
0x1800f6d7d  mov     rax, [rcx]
0x1800f6d80  mov     edx, r15d
0x1800f6d83  mov     rax, [rax]
0x1800f6d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6d8b  nop
0x1800f6d8c  jmp     loc_1800F8292
0x1800f6d91  lea     r8, [rsi+0A0h]; void *
0x1800f6d98  cmp     [r8+4], r15b
0x1800f6d9c  jnz     short loc_1800F6DD1
0x1800f6d9e  lea     rdx, aAllowmuupdates; "AllowMUUpdateService"
0x1800f6da5  mov     rcx, r14; this
0x1800f6da8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6dad  mov     edi, eax
0x1800f6daf  test    eax, eax
0x1800f6db1  jz      short loc_1800F6DD1
0x1800f6db3  mov     rcx, [rsp+0C8h+var_88]
0x1800f6db8  test    rcx, rcx
0x1800f6dbb  jz      short loc_1800F6DCC
0x1800f6dbd  mov     rax, [rcx]
0x1800f6dc0  mov     edx, r15d
0x1800f6dc3  mov     rax, [rax]
0x1800f6dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6dcb  nop
0x1800f6dcc  jmp     loc_1800F8292
0x1800f6dd1  lea     r8, [rsi+0A8h]; void *
0x1800f6dd8  cmp     [r8+4], r15b
0x1800f6ddc  jnz     short loc_1800F6E11
0x1800f6dde  lea     rdx, aAllownonmicros; "AllowNonMicrosoftSignedUpdate"
0x1800f6de5  mov     rcx, r14; this
0x1800f6de8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6ded  mov     edi, eax
0x1800f6def  test    eax, eax
0x1800f6df1  jz      short loc_1800F6E11
0x1800f6df3  mov     rcx, [rsp+0C8h+var_88]
0x1800f6df8  test    rcx, rcx
0x1800f6dfb  jz      short loc_1800F6E0C
0x1800f6dfd  mov     rax, [rcx]
0x1800f6e00  mov     edx, r15d
0x1800f6e03  mov     rax, [rax]
0x1800f6e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6e0b  nop
0x1800f6e0c  jmp     loc_1800F8292
0x1800f6e11  lea     r8, [rsi+0B0h]; void *
0x1800f6e18  cmp     [r8+4], r15b
0x1800f6e1c  jnz     short loc_1800F6E51
0x1800f6e1e  lea     rdx, aAllowupdateser; "AllowUpdateService"
0x1800f6e25  mov     rcx, r14; this
0x1800f6e28  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6e2d  mov     edi, eax
0x1800f6e2f  test    eax, eax
0x1800f6e31  jz      short loc_1800F6E51
0x1800f6e33  mov     rcx, [rsp+0C8h+var_88]
0x1800f6e38  test    rcx, rcx
0x1800f6e3b  jz      short loc_1800F6E4C
0x1800f6e3d  mov     rax, [rcx]
0x1800f6e40  mov     edx, r15d
0x1800f6e43  mov     rax, [rax]
0x1800f6e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6e4b  nop
0x1800f6e4c  jmp     loc_1800F8292
0x1800f6e51  lea     r8, [rsi+0B8h]; void *
0x1800f6e58  cmp     [r8+4], r15b
0x1800f6e5c  jnz     short loc_1800F6E91
0x1800f6e5e  lea     rdx, aAutomaticmaint; "AutomaticMaintenanceWakeUp"
0x1800f6e65  mov     rcx, r14; this
0x1800f6e68  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f6e6d  mov     edi, eax
0x1800f6e6f  test    eax, eax
0x1800f6e71  jz      short loc_1800F6E91
0x1800f6e73  mov     rcx, [rsp+0C8h+var_88]
0x1800f6e78  test    rcx, rcx
0x1800f6e7b  jz      short loc_1800F6E8C
0x1800f6e7d  mov     rax, [rcx]
0x1800f6e80  mov     edx, r15d
0x1800f6e83  mov     rax, [rax]
0x1800f6e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6e8b  nop
0x1800f6e8c  jmp     loc_1800F8292
  ... truncated ...
```
