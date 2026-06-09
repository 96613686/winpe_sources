# MDM_Policy_Config01_Defender02_InvokeModifyInstance

- ea: `0x18007ce1c`
- end: `0x18007db30`
- name: `MDM_Policy_Config01_Defender02_InvokeModifyInstance`
- size: `3348`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007db40`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x18007ce1c`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x18007d1aa`: `AllowOnAccessProtection`
- `0x18007d2aa`: `AllowUserUIAccess`
- `0x18007d46a`: `ControlledFolderAccessAllowedApplications`
- `0x18007d4aa`: `ControlledFolderAccessProtectedFolders`
- `0x18007d5aa`: `EnableControlledFolderAccess`
- `0x18007d66a`: `ExcludedExtensions`
- `0x18007d6aa`: `ExcludedPaths`
- `0x18007d8aa`: `SecurityIntelligenceLocation`
- `0x18007d8ea`: `SignatureUpdateFallbackOrder`
- `0x18007d92a`: `SignatureUpdateFileSharesSources`
- `0x18007d96a`: `SignatureUpdateInterval`
- `0x18007ce67`: `MDM_Policy_Config01_Defender02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Defender02_InvokeModifyInstance(__int64 a1, __int64 a2)
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
  v12[2] = "MDM_Policy_Config01_Defender02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v4 = v18;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18034E095,
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
                                 &MDM_Policy_Config01_Defender02_NodeList,
                                 44,
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
            (struct WmiNodeInfo *)&MDM_Policy_Config01_Defender02_NodeList,
            0x2Cu);
          if ( *(_BYTE *)(a2 + 100) == 1
            && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowArchiveScanning", (void *)(a2 + 96))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 108) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowBehaviorMonitoring",
                                  (void *)(a2 + 104))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 116) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowCloudProtection", (void *)(a2 + 112))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 124) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowEmailScanning", (void *)(a2 + 120))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 132) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowFullScanOnMappedNetworkDrives",
                                  (void *)(a2 + 128))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 140) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowFullScanRemovableDriveScanning",
                                  (void *)(a2 + 136))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 148) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowIntrusionPreventionSystem",
                                  (void *)(a2 + 144))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 156) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowIOAVProtection", (void *)(a2 + 152))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 164) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowOnAccessProtection",
                                  (void *)(a2 + 160))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 172) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowRealtimeMonitoring",
                                  (void *)(a2 + 168))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 180) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowScanningNetworkFiles",
                                  (void *)(a2 + 176))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 188) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowScriptScanning", (void *)(a2 + 184))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 196) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowUserUIAccess", (void *)(a2 + 192))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 208) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AttackSurfaceReductionOnlyExclusions",
                                  (void *)(a2 + 200))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 224) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AttackSurfaceReductionRules",
                                  (void *)(a2 + 216))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 236) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AvgCPULoadFactor", (void *)(a2 + 232))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 244) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"CheckForSignaturesBeforeRunningScan",
                                  (void *)(a2 + 240))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 252) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"CloudBlockLevel", (void *)(a2 + 248))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 260) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"CloudExtendedTimeout", (void *)(a2 + 256))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 272) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ControlledFolderAccessAllowedApplications",
                                  (void *)(a2 + 264))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 288) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ControlledFolderAccessProtectedFolders",
                                  (void *)(a2 + 280))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 300) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DaysToRetainCleanedMalware",
                                  (void *)(a2 + 296))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 308) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DisableCatchupFullScan",
                                  (void *)(a2 + 304))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 316) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DisableCatchupQuickScan",
                                  (void *)(a2 + 312))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 324) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnableControlledFolderAccess",
                                  (void *)(a2 + 320))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 332) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"EnableLowCPUPriority", (void *)(a2 + 328))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 340) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnableNetworkProtection",
                                  (void *)(a2 + 336))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 352) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ExcludedExtensions", (void *)(a2 + 344))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 368) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ExcludedPaths", (void *)(a2 + 360))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 384) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ExcludedProcesses", (void *)(a2 + 376))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 396) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"PUAProtection", (void *)(a2 + 392))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 404) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"RealTimeScanDirection",
                                  (void *)(a2 + 400))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 412) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ScanParameter", (void *)(a2 + 408))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 420) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduleQuickScanTime",
                                  (void *)(a2 + 416))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 428) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ScheduleScanDay", (void *)(a2 + 424))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 436) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ScheduleScanTime", (void *)(a2 + 432))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 448) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SecurityIntelligenceLocation",
                                  (void *)(a2 + 440))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 464) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SignatureUpdateFallbackOrder",
                                  (void *)(a2 + 456))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 480) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SignatureUpdateFileSharesSources",
                                  (void *)(a2 + 472))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 492) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SignatureUpdateInterval",
                                  (void *)(a2 + 488))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 500) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"SubmitSamplesConsent", (void *)(a2 + 496))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 512) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ThreatSeverityDefaultAction",
                                  (void *)(a2 + 504))) != MI_RESULT_OK )
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
      byte_18034A165,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18007ce1c  mov     r11, rsp
0x18007ce1f  mov     [r11+18h], rsi
0x18007ce23  push    rdi
0x18007ce24  push    r14
0x18007ce26  push    r15
0x18007ce28  sub     rsp, 0B0h
0x18007ce2f  mov     rax, cs:__security_cookie
0x18007ce36  xor     rax, rsp
0x18007ce39  mov     [rsp+0C8h+var_28], rax
0x18007ce41  mov     rsi, rdx
0x18007ce44  mov     rdi, rcx
0x18007ce47  mov     [rsp+0C8h+var_50], 0
0x18007ce4f  mov     [rsp+0C8h+var_4C], 0
0x18007ce54  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18007ce5b  mov     [r11-80h], rax
0x18007ce5f  lea     rax, [r11-50h]
0x18007ce63  mov     [r11-78h], rax
0x18007ce67  lea     rax, aMdmPolicyConfi_40; "MDM_Policy_Config01_Defender02"
0x18007ce6e  mov     [r11-70h], rax
0x18007ce72  lea     rcx, [r11-50h]
0x18007ce76  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007ce7b  mov     eax, cs:dword_180380B68
0x18007ce81  cmp     eax, 5
0x18007ce84  jbe     short loc_18007CEF7
0x18007ce86  mov     rdx, 200000000000h
0x18007ce90  lea     rcx, dword_180380B68
0x18007ce97  call    _tlgKeywordOn
0x18007ce9c  test    al, al
0x18007ce9e  jz      short loc_18007CEF7
0x18007cea0  cmp     [rsp+0C8h+var_4C], 0
0x18007cea5  jz      short loc_18007CED9
0x18007cea7  cmp     [rsp+0C8h+var_38], 0
0x18007ceaf  jnz     short loc_18007CECF
0x18007ceb1  cmp     [rsp+0C8h+var_34], 0
0x18007ceb9  jnz     short loc_18007CECF
0x18007cebb  cmp     [rsp+0C8h+var_30], 0
0x18007cec3  jnz     short loc_18007CECF
0x18007cec5  cmp     [rsp+0C8h+var_2C], 0
0x18007cecd  jz      short loc_18007CED9
0x18007cecf  lea     r9, [rsp+0C8h+var_38]
0x18007ced7  jmp     short loc_18007CEDC
0x18007ced9  xor     r9d, r9d
0x18007cedc  lea     r8, [rsp+0C8h+var_48]
0x18007cee4  lea     rdx, byte_18034E095
0x18007ceeb  lea     rcx, dword_180380B68
0x18007cef2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007cef7  cmp     byte ptr [rsi+48h], 0
0x18007cefb  jz      loc_18007DA99
0x18007cf01  cmp     byte ptr [rsi+58h], 0
0x18007cf05  jz      loc_18007DA99
0x18007cf0b  mov     r9, [rsi+40h]; unsigned __int16 *
0x18007cf0f  mov     r8, [rsi+50h]; unsigned __int16 *
0x18007cf13  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x18007cf1a  lea     rcx, [rsp+0C8h+var_80]; this
0x18007cf1f  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18007cf24  nop
0x18007cf25  mov     [rsp+0C8h+var_88], 0
0x18007cf2e  lea     rax, [rsp+0C8h+var_88]
0x18007cf33  mov     [rsp+0C8h+var_98], rax
0x18007cf38  mov     [rsp+0C8h+var_A0], 3
0x18007cf40  mov     [rsp+0C8h+var_A8], 2Ch ; ','
0x18007cf48  lea     r9, ?MDM_Policy_Config01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Defender02_NodeList
0x18007cf4f  mov     r8, [rsi+40h]
0x18007cf53  mov     rdx, [rsi+50h]
0x18007cf57  mov     rcx, rdi
0x18007cf5a  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18007cf5f  mov     edi, eax
0x18007cf61  test    eax, eax
0x18007cf63  jz      short loc_18007CF6A
0x18007cf65  jmp     loc_18007DA9E
0x18007cf6a  lea     rax, [rsp+0C8h+var_88]
0x18007cf6f  mov     [rsp+0C8h+var_60], rax
0x18007cf74  mov     r15d, 1
0x18007cf7a  mov     [rsp+0C8h+var_58], r15b
0x18007cf7f  mov     r14, [rsp+0C8h+var_88]
0x18007cf84  test    r14, r14
0x18007cf87  jnz     short loc_18007CF91
0x18007cf89  mov     edi, r15d
0x18007cf8c  jmp     loc_18007DA9E
0x18007cf91  mov     r9d, 2Ch ; ','; unsigned int
0x18007cf97  lea     r8, ?MDM_Policy_Config01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18007cf9e  mov     rdx, rsi; struct _MI_Instance *
0x18007cfa1  mov     rcx, r14; this
0x18007cfa4  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18007cfa9  lea     r8, [rsi+60h]; void *
0x18007cfad  cmp     [r8+4], r15b
0x18007cfb1  jnz     short loc_18007CFE6
0x18007cfb3  lea     rdx, aAllowarchivesc; "AllowArchiveScanning"
0x18007cfba  mov     rcx, r14; this
0x18007cfbd  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007cfc2  mov     edi, eax
0x18007cfc4  test    eax, eax
0x18007cfc6  jz      short loc_18007CFE6
0x18007cfc8  mov     rcx, [rsp+0C8h+var_88]
0x18007cfcd  test    rcx, rcx
0x18007cfd0  jz      short loc_18007CFE1
0x18007cfd2  mov     rax, [rcx]
0x18007cfd5  mov     edx, r15d
0x18007cfd8  mov     rax, [rax]
0x18007cfdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cfe0  nop
0x18007cfe1  jmp     loc_18007DA9E
0x18007cfe6  lea     r8, [rsi+68h]; void *
0x18007cfea  cmp     [r8+4], r15b
0x18007cfee  jnz     short loc_18007D023
0x18007cff0  lea     rdx, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x18007cff7  mov     rcx, r14; this
0x18007cffa  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007cfff  mov     edi, eax
0x18007d001  test    eax, eax
0x18007d003  jz      short loc_18007D023
0x18007d005  mov     rcx, [rsp+0C8h+var_88]
0x18007d00a  test    rcx, rcx
0x18007d00d  jz      short loc_18007D01E
0x18007d00f  mov     rax, [rcx]
0x18007d012  mov     edx, r15d
0x18007d015  mov     rax, [rax]
0x18007d018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d01d  nop
0x18007d01e  jmp     loc_18007DA9E
0x18007d023  lea     r8, [rsi+70h]; void *
0x18007d027  cmp     [r8+4], r15b
0x18007d02b  jnz     short loc_18007D060
0x18007d02d  lea     rdx, aAllowcloudprot; "AllowCloudProtection"
0x18007d034  mov     rcx, r14; this
0x18007d037  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d03c  mov     edi, eax
0x18007d03e  test    eax, eax
0x18007d040  jz      short loc_18007D060
0x18007d042  mov     rcx, [rsp+0C8h+var_88]
0x18007d047  test    rcx, rcx
0x18007d04a  jz      short loc_18007D05B
0x18007d04c  mov     rax, [rcx]
0x18007d04f  mov     edx, r15d
0x18007d052  mov     rax, [rax]
0x18007d055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d05a  nop
0x18007d05b  jmp     loc_18007DA9E
0x18007d060  lea     r8, [rsi+78h]; void *
0x18007d064  cmp     [r8+4], r15b
0x18007d068  jnz     short loc_18007D09D
0x18007d06a  lea     rdx, aAllowemailscan; "AllowEmailScanning"
0x18007d071  mov     rcx, r14; this
0x18007d074  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d079  mov     edi, eax
0x18007d07b  test    eax, eax
0x18007d07d  jz      short loc_18007D09D
0x18007d07f  mov     rcx, [rsp+0C8h+var_88]
0x18007d084  test    rcx, rcx
0x18007d087  jz      short loc_18007D098
0x18007d089  mov     rax, [rcx]
0x18007d08c  mov     edx, r15d
0x18007d08f  mov     rax, [rax]
0x18007d092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d097  nop
0x18007d098  jmp     loc_18007DA9E
0x18007d09d  lea     r8, [rsi+80h]; void *
0x18007d0a4  cmp     [r8+4], r15b
0x18007d0a8  jnz     short loc_18007D0DD
0x18007d0aa  lea     rdx, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x18007d0b1  mov     rcx, r14; this
0x18007d0b4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d0b9  mov     edi, eax
0x18007d0bb  test    eax, eax
0x18007d0bd  jz      short loc_18007D0DD
0x18007d0bf  mov     rcx, [rsp+0C8h+var_88]
0x18007d0c4  test    rcx, rcx
0x18007d0c7  jz      short loc_18007D0D8
0x18007d0c9  mov     rax, [rcx]
0x18007d0cc  mov     edx, r15d
0x18007d0cf  mov     rax, [rax]
0x18007d0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d0d7  nop
0x18007d0d8  jmp     loc_18007DA9E
0x18007d0dd  lea     r8, [rsi+88h]; void *
0x18007d0e4  cmp     [r8+4], r15b
0x18007d0e8  jnz     short loc_18007D11D
0x18007d0ea  lea     rdx, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x18007d0f1  mov     rcx, r14; this
0x18007d0f4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d0f9  mov     edi, eax
0x18007d0fb  test    eax, eax
0x18007d0fd  jz      short loc_18007D11D
0x18007d0ff  mov     rcx, [rsp+0C8h+var_88]
0x18007d104  test    rcx, rcx
0x18007d107  jz      short loc_18007D118
0x18007d109  mov     rax, [rcx]
0x18007d10c  mov     edx, r15d
0x18007d10f  mov     rax, [rax]
0x18007d112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d117  nop
0x18007d118  jmp     loc_18007DA9E
0x18007d11d  lea     r8, [rsi+90h]; void *
0x18007d124  cmp     [r8+4], r15b
0x18007d128  jnz     short loc_18007D15D
0x18007d12a  lea     rdx, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x18007d131  mov     rcx, r14; this
0x18007d134  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d139  mov     edi, eax
0x18007d13b  test    eax, eax
0x18007d13d  jz      short loc_18007D15D
0x18007d13f  mov     rcx, [rsp+0C8h+var_88]
0x18007d144  test    rcx, rcx
0x18007d147  jz      short loc_18007D158
0x18007d149  mov     rax, [rcx]
0x18007d14c  mov     edx, r15d
0x18007d14f  mov     rax, [rax]
0x18007d152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d157  nop
0x18007d158  jmp     loc_18007DA9E
0x18007d15d  lea     r8, [rsi+98h]; void *
0x18007d164  cmp     [r8+4], r15b
0x18007d168  jnz     short loc_18007D19D
0x18007d16a  lea     rdx, aAllowioavprote; "AllowIOAVProtection"
0x18007d171  mov     rcx, r14; this
0x18007d174  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d179  mov     edi, eax
0x18007d17b  test    eax, eax
0x18007d17d  jz      short loc_18007D19D
0x18007d17f  mov     rcx, [rsp+0C8h+var_88]
0x18007d184  test    rcx, rcx
0x18007d187  jz      short loc_18007D198
0x18007d189  mov     rax, [rcx]
0x18007d18c  mov     edx, r15d
0x18007d18f  mov     rax, [rax]
0x18007d192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d197  nop
0x18007d198  jmp     loc_18007DA9E
0x18007d19d  lea     r8, [rsi+0A0h]; void *
0x18007d1a4  cmp     [r8+4], r15b
0x18007d1a8  jnz     short loc_18007D1DD
0x18007d1aa  lea     rdx, aAllowonaccessp; "AllowOnAccessProtection"
0x18007d1b1  mov     rcx, r14; this
0x18007d1b4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d1b9  mov     edi, eax
0x18007d1bb  test    eax, eax
0x18007d1bd  jz      short loc_18007D1DD
0x18007d1bf  mov     rcx, [rsp+0C8h+var_88]
0x18007d1c4  test    rcx, rcx
0x18007d1c7  jz      short loc_18007D1D8
0x18007d1c9  mov     rax, [rcx]
0x18007d1cc  mov     edx, r15d
0x18007d1cf  mov     rax, [rax]
0x18007d1d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d1d7  nop
0x18007d1d8  jmp     loc_18007DA9E
0x18007d1dd  lea     r8, [rsi+0A8h]; void *
0x18007d1e4  cmp     [r8+4], r15b
0x18007d1e8  jnz     short loc_18007D21D
0x18007d1ea  lea     rdx, aAllowrealtimem; "AllowRealtimeMonitoring"
0x18007d1f1  mov     rcx, r14; this
0x18007d1f4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d1f9  mov     edi, eax
0x18007d1fb  test    eax, eax
0x18007d1fd  jz      short loc_18007D21D
0x18007d1ff  mov     rcx, [rsp+0C8h+var_88]
0x18007d204  test    rcx, rcx
0x18007d207  jz      short loc_18007D218
0x18007d209  mov     rax, [rcx]
0x18007d20c  mov     edx, r15d
0x18007d20f  mov     rax, [rax]
0x18007d212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d217  nop
0x18007d218  jmp     loc_18007DA9E
0x18007d21d  lea     r8, [rsi+0B0h]; void *
0x18007d224  cmp     [r8+4], r15b
0x18007d228  jnz     short loc_18007D25D
0x18007d22a  lea     rdx, aAllowscanningn; "AllowScanningNetworkFiles"
0x18007d231  mov     rcx, r14; this
0x18007d234  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d239  mov     edi, eax
0x18007d23b  test    eax, eax
0x18007d23d  jz      short loc_18007D25D
0x18007d23f  mov     rcx, [rsp+0C8h+var_88]
0x18007d244  test    rcx, rcx
0x18007d247  jz      short loc_18007D258
0x18007d249  mov     rax, [rcx]
0x18007d24c  mov     edx, r15d
0x18007d24f  mov     rax, [rax]
0x18007d252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d257  nop
0x18007d258  jmp     loc_18007DA9E
0x18007d25d  lea     r8, [rsi+0B8h]; void *
0x18007d264  cmp     [r8+4], r15b
0x18007d268  jnz     short loc_18007D29D
0x18007d26a  lea     rdx, aAllowscriptsca; "AllowScriptScanning"
0x18007d271  mov     rcx, r14; this
0x18007d274  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d279  mov     edi, eax
0x18007d27b  test    eax, eax
0x18007d27d  jz      short loc_18007D29D
0x18007d27f  mov     rcx, [rsp+0C8h+var_88]
0x18007d284  test    rcx, rcx
0x18007d287  jz      short loc_18007D298
0x18007d289  mov     rax, [rcx]
0x18007d28c  mov     edx, r15d
0x18007d28f  mov     rax, [rax]
0x18007d292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d297  nop
0x18007d298  jmp     loc_18007DA9E
  ... truncated ...
```
