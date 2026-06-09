# MDM_Policy_Config01_Defender02_InvokeModifyInstance

- ea: `0x18007d510`
- end: `0x18007e223`
- name: `MDM_Policy_Config01_Defender02_InvokeModifyInstance`
- size: `3347`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007e230`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x18007d510`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x18007d89e`: `AllowOnAccessProtection`
- `0x18007d99e`: `AllowUserUIAccess`
- `0x18007db5e`: `ControlledFolderAccessAllowedApplications`
- `0x18007db9e`: `ControlledFolderAccessProtectedFolders`
- `0x18007dc9e`: `EnableControlledFolderAccess`
- `0x18007dd5e`: `ExcludedExtensions`
- `0x18007dd9e`: `ExcludedPaths`
- `0x18007df9e`: `SecurityIntelligenceLocation`
- `0x18007dfde`: `SignatureUpdateFallbackOrder`
- `0x18007e01e`: `SignatureUpdateFileSharesSources`
- `0x18007e05e`: `SignatureUpdateInterval`
- `0x18007d55b`: `MDM_Policy_Config01_Defender02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Defender02_InvokeModifyInstance(__int64 a1, __int64 a2)
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
      inserted = CreateRequestHandlerInstance(
                   a1,
                   *(wchar_t **)(a2 + 80),
                   *(const unsigned __int16 **)(a2 + 64),
                   (struct WmiNodeInfo *)&MDM_Policy_Config01_Defender02_NodeList,
                   0x2Cu,
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
            (struct WmiNodeInfo *)&MDM_Policy_Config01_Defender02_NodeList,
            0x2Cu);
          if ( *(_BYTE *)(a2 + 100) == 1
            && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowArchiveScanning", (LONG *)(a2 + 96))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 108) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowBehaviorMonitoring",
                                  (LONG *)(a2 + 104))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 116) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowCloudProtection", (LONG *)(a2 + 112))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 124) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowEmailScanning", (LONG *)(a2 + 120))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 132) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowFullScanOnMappedNetworkDrives",
                                  (LONG *)(a2 + 128))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 140) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowFullScanRemovableDriveScanning",
                                  (LONG *)(a2 + 136))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 148) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowIntrusionPreventionSystem",
                                  (LONG *)(a2 + 144))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 156) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowIOAVProtection", (LONG *)(a2 + 152))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 164) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowOnAccessProtection",
                                  (LONG *)(a2 + 160))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 172) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowRealtimeMonitoring",
                                  (LONG *)(a2 + 168))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 180) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowScanningNetworkFiles",
                                  (LONG *)(a2 + 176))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 188) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowScriptScanning", (LONG *)(a2 + 184))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 196) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowUserUIAccess", (LONG *)(a2 + 192))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 208) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AttackSurfaceReductionOnlyExclusions",
                                  (LONG *)(a2 + 200))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 224) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AttackSurfaceReductionRules",
                                  (LONG *)(a2 + 216))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 236) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AvgCPULoadFactor", (LONG *)(a2 + 232))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 244) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"CheckForSignaturesBeforeRunningScan",
                                  (LONG *)(a2 + 240))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 252) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"CloudBlockLevel", (LONG *)(a2 + 248))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 260) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"CloudExtendedTimeout", (LONG *)(a2 + 256))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 272) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ControlledFolderAccessAllowedApplications",
                                  (LONG *)(a2 + 264))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 288) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ControlledFolderAccessProtectedFolders",
                                  (LONG *)(a2 + 280))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 300) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DaysToRetainCleanedMalware",
                                  (LONG *)(a2 + 296))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 308) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DisableCatchupFullScan",
                                  (LONG *)(a2 + 304))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 316) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DisableCatchupQuickScan",
                                  (LONG *)(a2 + 312))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 324) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnableControlledFolderAccess",
                                  (LONG *)(a2 + 320))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 332) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"EnableLowCPUPriority", (LONG *)(a2 + 328))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 340) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnableNetworkProtection",
                                  (LONG *)(a2 + 336))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 352) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ExcludedExtensions", (LONG *)(a2 + 344))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 368) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ExcludedPaths", (LONG *)(a2 + 360))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 384) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ExcludedProcesses", (LONG *)(a2 + 376))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 396) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"PUAProtection", (LONG *)(a2 + 392))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 404) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"RealTimeScanDirection",
                                  (LONG *)(a2 + 400))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 412) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ScanParameter", (LONG *)(a2 + 408))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 420) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ScheduleQuickScanTime",
                                  (LONG *)(a2 + 416))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 428) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ScheduleScanDay", (LONG *)(a2 + 424))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 436) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ScheduleScanTime", (LONG *)(a2 + 432))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 448) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SecurityIntelligenceLocation",
                                  (LONG *)(a2 + 440))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 464) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SignatureUpdateFallbackOrder",
                                  (LONG *)(a2 + 456))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 480) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SignatureUpdateFileSharesSources",
                                  (LONG *)(a2 + 472))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 492) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SignatureUpdateInterval",
                                  (LONG *)(a2 + 488))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 500) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"SubmitSamplesConsent", (LONG *)(a2 + 496))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 512) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ThreatSeverityDefaultAction",
                                  (LONG *)(a2 + 504))) != 0 )
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
      byte_18034A165,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return inserted;
}

```

## disassembly

```asm
0x18007d510  mov     r11, rsp
0x18007d513  mov     [r11+18h], rsi
0x18007d517  push    rdi
0x18007d518  push    r14
0x18007d51a  push    r15
0x18007d51c  sub     rsp, 0B0h
0x18007d523  mov     rax, cs:__security_cookie
0x18007d52a  xor     rax, rsp
0x18007d52d  mov     [rsp+0C8h+var_28], rax
0x18007d535  mov     rsi, rdx
0x18007d538  mov     rdi, rcx
0x18007d53b  mov     [rsp+0C8h+var_50], 0
0x18007d543  mov     [rsp+0C8h+var_4C], 0
0x18007d548  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18007d54f  mov     [r11-80h], rax
0x18007d553  lea     rax, [r11-50h]
0x18007d557  mov     [r11-78h], rax
0x18007d55b  lea     rax, aMdmPolicyConfi_40; "MDM_Policy_Config01_Defender02"
0x18007d562  mov     [r11-70h], rax
0x18007d566  lea     rcx, [r11-50h]
0x18007d56a  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007d56f  mov     eax, cs:dword_180380B68
0x18007d575  cmp     eax, 5
0x18007d578  jbe     short loc_18007D5EB
0x18007d57a  mov     rdx, 200000000000h
0x18007d584  lea     rcx, dword_180380B68
0x18007d58b  call    _tlgKeywordOn
0x18007d590  test    al, al
0x18007d592  jz      short loc_18007D5EB
0x18007d594  cmp     [rsp+0C8h+var_4C], 0
0x18007d599  jz      short loc_18007D5CD
0x18007d59b  cmp     [rsp+0C8h+var_38], 0
0x18007d5a3  jnz     short loc_18007D5C3
0x18007d5a5  cmp     [rsp+0C8h+var_34], 0
0x18007d5ad  jnz     short loc_18007D5C3
0x18007d5af  cmp     [rsp+0C8h+var_30], 0
0x18007d5b7  jnz     short loc_18007D5C3
0x18007d5b9  cmp     [rsp+0C8h+var_2C], 0
0x18007d5c1  jz      short loc_18007D5CD
0x18007d5c3  lea     r9, [rsp+0C8h+var_38]
0x18007d5cb  jmp     short loc_18007D5D0
0x18007d5cd  xor     r9d, r9d
0x18007d5d0  lea     r8, [rsp+0C8h+var_48]
0x18007d5d8  lea     rdx, byte_18034E095
0x18007d5df  lea     rcx, dword_180380B68
0x18007d5e6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007d5eb  cmp     byte ptr [rsi+48h], 0
0x18007d5ef  jz      loc_18007E18D
0x18007d5f5  cmp     byte ptr [rsi+58h], 0
0x18007d5f9  jz      loc_18007E18D
0x18007d5ff  mov     r9, [rsi+40h]; unsigned __int16 *
0x18007d603  mov     r8, [rsi+50h]; unsigned __int16 *
0x18007d607  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x18007d60e  lea     rcx, [rsp+0C8h+var_80]; this
0x18007d613  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18007d618  nop
0x18007d619  mov     [rsp+0C8h+var_88], 0
0x18007d622  lea     rax, [rsp+0C8h+var_88]
0x18007d627  mov     [rsp+0C8h+var_98], rax
0x18007d62c  mov     [rsp+0C8h+var_A0], 3
0x18007d634  mov     [rsp+0C8h+var_A8], 2Ch ; ','
0x18007d63c  lea     r9, ?MDM_Policy_Config01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Defender02_NodeList
0x18007d643  mov     r8, [rsi+40h]
0x18007d647  mov     rdx, [rsi+50h]
0x18007d64b  mov     rcx, rdi
0x18007d64e  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18007d653  mov     edi, eax
0x18007d655  test    eax, eax
0x18007d657  jz      short loc_18007D65E
0x18007d659  jmp     loc_18007E192
0x18007d65e  lea     rax, [rsp+0C8h+var_88]
0x18007d663  mov     [rsp+0C8h+var_60], rax
0x18007d668  mov     r15d, 1
0x18007d66e  mov     [rsp+0C8h+var_58], r15b
0x18007d673  mov     r14, [rsp+0C8h+var_88]
0x18007d678  test    r14, r14
0x18007d67b  jnz     short loc_18007D685
0x18007d67d  mov     edi, r15d
0x18007d680  jmp     loc_18007E192
0x18007d685  mov     r9d, 2Ch ; ','; unsigned int
0x18007d68b  lea     r8, ?MDM_Policy_Config01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18007d692  mov     rdx, rsi; struct _MI_Instance *
0x18007d695  mov     rcx, r14; this
0x18007d698  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18007d69d  lea     r8, [rsi+60h]; void *
0x18007d6a1  cmp     [r8+4], r15b
0x18007d6a5  jnz     short loc_18007D6DA
0x18007d6a7  lea     rdx, aAllowarchivesc; "AllowArchiveScanning"
0x18007d6ae  mov     rcx, r14; this
0x18007d6b1  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d6b6  mov     edi, eax
0x18007d6b8  test    eax, eax
0x18007d6ba  jz      short loc_18007D6DA
0x18007d6bc  mov     rcx, [rsp+0C8h+var_88]
0x18007d6c1  test    rcx, rcx
0x18007d6c4  jz      short loc_18007D6D5
0x18007d6c6  mov     rax, [rcx]
0x18007d6c9  mov     edx, r15d
0x18007d6cc  mov     rax, [rax]
0x18007d6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d6d4  nop
0x18007d6d5  jmp     loc_18007E192
0x18007d6da  lea     r8, [rsi+68h]; void *
0x18007d6de  cmp     [r8+4], r15b
0x18007d6e2  jnz     short loc_18007D717
0x18007d6e4  lea     rdx, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x18007d6eb  mov     rcx, r14; this
0x18007d6ee  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d6f3  mov     edi, eax
0x18007d6f5  test    eax, eax
0x18007d6f7  jz      short loc_18007D717
0x18007d6f9  mov     rcx, [rsp+0C8h+var_88]
0x18007d6fe  test    rcx, rcx
0x18007d701  jz      short loc_18007D712
0x18007d703  mov     rax, [rcx]
0x18007d706  mov     edx, r15d
0x18007d709  mov     rax, [rax]
0x18007d70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d711  nop
0x18007d712  jmp     loc_18007E192
0x18007d717  lea     r8, [rsi+70h]; void *
0x18007d71b  cmp     [r8+4], r15b
0x18007d71f  jnz     short loc_18007D754
0x18007d721  lea     rdx, aAllowcloudprot; "AllowCloudProtection"
0x18007d728  mov     rcx, r14; this
0x18007d72b  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d730  mov     edi, eax
0x18007d732  test    eax, eax
0x18007d734  jz      short loc_18007D754
0x18007d736  mov     rcx, [rsp+0C8h+var_88]
0x18007d73b  test    rcx, rcx
0x18007d73e  jz      short loc_18007D74F
0x18007d740  mov     rax, [rcx]
0x18007d743  mov     edx, r15d
0x18007d746  mov     rax, [rax]
0x18007d749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d74e  nop
0x18007d74f  jmp     loc_18007E192
0x18007d754  lea     r8, [rsi+78h]; void *
0x18007d758  cmp     [r8+4], r15b
0x18007d75c  jnz     short loc_18007D791
0x18007d75e  lea     rdx, aAllowemailscan; "AllowEmailScanning"
0x18007d765  mov     rcx, r14; this
0x18007d768  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d76d  mov     edi, eax
0x18007d76f  test    eax, eax
0x18007d771  jz      short loc_18007D791
0x18007d773  mov     rcx, [rsp+0C8h+var_88]
0x18007d778  test    rcx, rcx
0x18007d77b  jz      short loc_18007D78C
0x18007d77d  mov     rax, [rcx]
0x18007d780  mov     edx, r15d
0x18007d783  mov     rax, [rax]
0x18007d786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d78b  nop
0x18007d78c  jmp     loc_18007E192
0x18007d791  lea     r8, [rsi+80h]; void *
0x18007d798  cmp     [r8+4], r15b
0x18007d79c  jnz     short loc_18007D7D1
0x18007d79e  lea     rdx, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x18007d7a5  mov     rcx, r14; this
0x18007d7a8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d7ad  mov     edi, eax
0x18007d7af  test    eax, eax
0x18007d7b1  jz      short loc_18007D7D1
0x18007d7b3  mov     rcx, [rsp+0C8h+var_88]
0x18007d7b8  test    rcx, rcx
0x18007d7bb  jz      short loc_18007D7CC
0x18007d7bd  mov     rax, [rcx]
0x18007d7c0  mov     edx, r15d
0x18007d7c3  mov     rax, [rax]
0x18007d7c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d7cb  nop
0x18007d7cc  jmp     loc_18007E192
0x18007d7d1  lea     r8, [rsi+88h]; void *
0x18007d7d8  cmp     [r8+4], r15b
0x18007d7dc  jnz     short loc_18007D811
0x18007d7de  lea     rdx, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x18007d7e5  mov     rcx, r14; this
0x18007d7e8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d7ed  mov     edi, eax
0x18007d7ef  test    eax, eax
0x18007d7f1  jz      short loc_18007D811
0x18007d7f3  mov     rcx, [rsp+0C8h+var_88]
0x18007d7f8  test    rcx, rcx
0x18007d7fb  jz      short loc_18007D80C
0x18007d7fd  mov     rax, [rcx]
0x18007d800  mov     edx, r15d
0x18007d803  mov     rax, [rax]
0x18007d806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d80b  nop
0x18007d80c  jmp     loc_18007E192
0x18007d811  lea     r8, [rsi+90h]; void *
0x18007d818  cmp     [r8+4], r15b
0x18007d81c  jnz     short loc_18007D851
0x18007d81e  lea     rdx, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x18007d825  mov     rcx, r14; this
0x18007d828  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d82d  mov     edi, eax
0x18007d82f  test    eax, eax
0x18007d831  jz      short loc_18007D851
0x18007d833  mov     rcx, [rsp+0C8h+var_88]
0x18007d838  test    rcx, rcx
0x18007d83b  jz      short loc_18007D84C
0x18007d83d  mov     rax, [rcx]
0x18007d840  mov     edx, r15d
0x18007d843  mov     rax, [rax]
0x18007d846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d84b  nop
0x18007d84c  jmp     loc_18007E192
0x18007d851  lea     r8, [rsi+98h]; void *
0x18007d858  cmp     [r8+4], r15b
0x18007d85c  jnz     short loc_18007D891
0x18007d85e  lea     rdx, aAllowioavprote; "AllowIOAVProtection"
0x18007d865  mov     rcx, r14; this
0x18007d868  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d86d  mov     edi, eax
0x18007d86f  test    eax, eax
0x18007d871  jz      short loc_18007D891
0x18007d873  mov     rcx, [rsp+0C8h+var_88]
0x18007d878  test    rcx, rcx
0x18007d87b  jz      short loc_18007D88C
0x18007d87d  mov     rax, [rcx]
0x18007d880  mov     edx, r15d
0x18007d883  mov     rax, [rax]
0x18007d886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d88b  nop
0x18007d88c  jmp     loc_18007E192
0x18007d891  lea     r8, [rsi+0A0h]; void *
0x18007d898  cmp     [r8+4], r15b
0x18007d89c  jnz     short loc_18007D8D1
0x18007d89e  lea     rdx, aAllowonaccessp; "AllowOnAccessProtection"
0x18007d8a5  mov     rcx, r14; this
0x18007d8a8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d8ad  mov     edi, eax
0x18007d8af  test    eax, eax
0x18007d8b1  jz      short loc_18007D8D1
0x18007d8b3  mov     rcx, [rsp+0C8h+var_88]
0x18007d8b8  test    rcx, rcx
0x18007d8bb  jz      short loc_18007D8CC
0x18007d8bd  mov     rax, [rcx]
0x18007d8c0  mov     edx, r15d
0x18007d8c3  mov     rax, [rax]
0x18007d8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d8cb  nop
0x18007d8cc  jmp     loc_18007E192
0x18007d8d1  lea     r8, [rsi+0A8h]; void *
0x18007d8d8  cmp     [r8+4], r15b
0x18007d8dc  jnz     short loc_18007D911
0x18007d8de  lea     rdx, aAllowrealtimem; "AllowRealtimeMonitoring"
0x18007d8e5  mov     rcx, r14; this
0x18007d8e8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d8ed  mov     edi, eax
0x18007d8ef  test    eax, eax
0x18007d8f1  jz      short loc_18007D911
0x18007d8f3  mov     rcx, [rsp+0C8h+var_88]
0x18007d8f8  test    rcx, rcx
0x18007d8fb  jz      short loc_18007D90C
0x18007d8fd  mov     rax, [rcx]
0x18007d900  mov     edx, r15d
0x18007d903  mov     rax, [rax]
0x18007d906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d90b  nop
0x18007d90c  jmp     loc_18007E192
0x18007d911  lea     r8, [rsi+0B0h]; void *
0x18007d918  cmp     [r8+4], r15b
0x18007d91c  jnz     short loc_18007D951
0x18007d91e  lea     rdx, aAllowscanningn; "AllowScanningNetworkFiles"
0x18007d925  mov     rcx, r14; this
0x18007d928  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d92d  mov     edi, eax
0x18007d92f  test    eax, eax
0x18007d931  jz      short loc_18007D951
0x18007d933  mov     rcx, [rsp+0C8h+var_88]
0x18007d938  test    rcx, rcx
0x18007d93b  jz      short loc_18007D94C
0x18007d93d  mov     rax, [rcx]
0x18007d940  mov     edx, r15d
0x18007d943  mov     rax, [rax]
0x18007d946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d94b  nop
0x18007d94c  jmp     loc_18007E192
0x18007d951  lea     r8, [rsi+0B8h]; void *
0x18007d958  cmp     [r8+4], r15b
0x18007d95c  jnz     short loc_18007D991
0x18007d95e  lea     rdx, aAllowscriptsca; "AllowScriptScanning"
0x18007d965  mov     rcx, r14; this
0x18007d968  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007d96d  mov     edi, eax
0x18007d96f  test    eax, eax
0x18007d971  jz      short loc_18007D991
0x18007d973  mov     rcx, [rsp+0C8h+var_88]
0x18007d978  test    rcx, rcx
0x18007d97b  jz      short loc_18007D98C
0x18007d97d  mov     rax, [rcx]
0x18007d980  mov     edx, r15d
0x18007d983  mov     rax, [rax]
0x18007d986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d98b  nop
0x18007d98c  jmp     loc_18007E192
  ... truncated ...
```
