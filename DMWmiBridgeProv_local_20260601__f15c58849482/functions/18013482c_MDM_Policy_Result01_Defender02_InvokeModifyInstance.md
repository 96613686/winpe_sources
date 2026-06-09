# MDM_Policy_Result01_Defender02_InvokeModifyInstance

- ea: `0x18013482c`
- end: `0x180135540`
- name: `MDM_Policy_Result01_Defender02_InvokeModifyInstance`
- size: `3348`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180135550`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x18013482c`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x180134bba`: `AllowOnAccessProtection`
- `0x180134cba`: `AllowUserUIAccess`
- `0x180134e7a`: `ControlledFolderAccessAllowedApplications`
- `0x180134eba`: `ControlledFolderAccessProtectedFolders`
- `0x180134fba`: `EnableControlledFolderAccess`
- `0x18013507a`: `ExcludedExtensions`
- `0x1801350ba`: `ExcludedPaths`
- `0x1801352ba`: `SecurityIntelligenceLocation`
- `0x1801352fa`: `SignatureUpdateFallbackOrder`
- `0x18013533a`: `SignatureUpdateFileSharesSources`
- `0x18013537a`: `SignatureUpdateInterval`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Defender02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-88h] BYREF
  _QWORD v9[5]; // [rsp+48h] [rbp-80h] BYREF
  char v10; // [rsp+70h] [rbp-58h]
  int v11; // [rsp+78h] [rbp-50h] BYREF
  char v12; // [rsp+7Ch] [rbp-4Ch]
  _BYTE v13[16]; // [rsp+80h] [rbp-48h] BYREF
  _DWORD v14[4]; // [rsp+90h] [rbp-38h] BYREF

  v11 = 0;
  v12 = 0;
  v9[0] = &TelemetryEventWriter::`vftable';
  v9[1] = &v11;
  v9[2] = "MDM_Policy_Result01_Defender02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v11);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v12 && (v14[0] || v14[1] || v14[2] || v14[3]) )
      v4 = v14;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_18033ED2C,
      v13,
      v4);
  }
  if ( *(_BYTE *)(a2 + 72) && *(_BYTE *)(a2 + 88) )
  {
    TelemetryEventWriter::WriteStart(
      (TelemetryEventWriter *)v9,
      "ModifyInstanceStart",
      *(const unsigned __int16 **)(a2 + 80),
      *(const unsigned __int16 **)(a2 + 64));
    v8 = 0;
    inserted = (unsigned int)CreateRequestHandlerInstance(
                               a1,
                               *(_QWORD *)(a2 + 80),
                               *(_QWORD *)(a2 + 64),
                               &MDM_Policy_Result01_Defender02_NodeList,
                               44,
                               3,
                               &v8);
    if ( inserted == MI_RESULT_OK )
    {
      v9[4] = &v8;
      v10 = 1;
      v6 = v8;
      if ( v8 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v8,
          (const struct _MI_Instance *)a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_Defender02_NodeList,
          0x2Cu);
        if ( *(_BYTE *)(a2 + 100) == 1
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowArchiveScanning", (void *)(a2 + 96))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 108) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowBehaviorMonitoring",
                                (void *)(a2 + 104))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 116) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowCloudProtection", (void *)(a2 + 112))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 124) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowEmailScanning", (void *)(a2 + 120))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 132) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowFullScanOnMappedNetworkDrives",
                                (void *)(a2 + 128))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 140) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowFullScanRemovableDriveScanning",
                                (void *)(a2 + 136))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 148) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowIntrusionPreventionSystem",
                                (void *)(a2 + 144))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 156) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowIOAVProtection", (void *)(a2 + 152))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 164) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowOnAccessProtection",
                                (void *)(a2 + 160))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 172) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowRealtimeMonitoring",
                                (void *)(a2 + 168))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 180) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowScanningNetworkFiles",
                                (void *)(a2 + 176))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 188) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowScriptScanning", (void *)(a2 + 184))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 196) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowUserUIAccess", (void *)(a2 + 192))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 208) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AttackSurfaceReductionOnlyExclusions",
                                (void *)(a2 + 200))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 224) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AttackSurfaceReductionRules",
                                (void *)(a2 + 216))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 236) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AvgCPULoadFactor", (void *)(a2 + 232))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 244) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"CheckForSignaturesBeforeRunningScan",
                                (void *)(a2 + 240))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 252) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CloudBlockLevel", (void *)(a2 + 248))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 260) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CloudExtendedTimeout", (void *)(a2 + 256))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 272) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ControlledFolderAccessAllowedApplications",
                                (void *)(a2 + 264))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 288) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ControlledFolderAccessProtectedFolders",
                                (void *)(a2 + 280))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 300) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DaysToRetainCleanedMalware",
                                (void *)(a2 + 296))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 308) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableCatchupFullScan", (void *)(a2 + 304))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 316) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DisableCatchupQuickScan",
                                (void *)(a2 + 312))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 324) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableControlledFolderAccess",
                                (void *)(a2 + 320))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 332) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableLowCPUPriority", (void *)(a2 + 328))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 340) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableNetworkProtection",
                                (void *)(a2 + 336))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 352) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedExtensions", (void *)(a2 + 344))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 368) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedPaths", (void *)(a2 + 360))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 384) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedProcesses", (void *)(a2 + 376))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 396) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PUAProtection", (void *)(a2 + 392))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 404) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RealTimeScanDirection", (void *)(a2 + 400))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 412) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScanParameter", (void *)(a2 + 408))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 420) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleQuickScanTime", (void *)(a2 + 416))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 428) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleScanDay", (void *)(a2 + 424))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 436) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleScanTime", (void *)(a2 + 432))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 448) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SecurityIntelligenceLocation",
                                (void *)(a2 + 440))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 464) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SignatureUpdateFallbackOrder",
                                (void *)(a2 + 456))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 480) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SignatureUpdateFileSharesSources",
                                (void *)(a2 + 472))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 492) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SignatureUpdateInterval",
                                (void *)(a2 + 488))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 500) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SubmitSamplesConsent", (void *)(a2 + 496))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 512) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ThreatSeverityDefaultAction",
                                (void *)(a2 + 504))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else
        {
          inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
          if ( inserted )
          {
            if ( v8 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
          }
          else
          {
            inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
            if ( inserted )
            {
              if ( v8 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
            }
            else if ( v8 )
            {
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
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
  else
  {
    inserted = MI_RESULT_INVALID_PARAMETER;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v9, "ModifyInstanceEnd", inserted);
  v11 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_18036CCC4,
      v13,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v11);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18013482c  mov     r11, rsp
0x18013482f  mov     [r11+18h], rsi
0x180134833  push    rdi
0x180134834  push    r14
0x180134836  push    r15
0x180134838  sub     rsp, 0B0h
0x18013483f  mov     rax, cs:__security_cookie
0x180134846  xor     rax, rsp
0x180134849  mov     [rsp+0C8h+var_28], rax
0x180134851  mov     rsi, rdx
0x180134854  mov     rdi, rcx
0x180134857  mov     [rsp+0C8h+var_50], 0
0x18013485f  mov     [rsp+0C8h+var_4C], 0
0x180134864  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18013486b  mov     [r11-80h], rax
0x18013486f  lea     rax, [r11-50h]
0x180134873  mov     [r11-78h], rax
0x180134877  lea     rax, aMdmPolicyResul_181; "MDM_Policy_Result01_Defender02"
0x18013487e  mov     [r11-70h], rax
0x180134882  lea     rcx, [r11-50h]
0x180134886  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18013488b  mov     eax, cs:dword_180380B68
0x180134891  cmp     eax, 5
0x180134894  jbe     short loc_180134907
0x180134896  mov     rdx, 200000000000h
0x1801348a0  lea     rcx, dword_180380B68
0x1801348a7  call    _tlgKeywordOn
0x1801348ac  test    al, al
0x1801348ae  jz      short loc_180134907
0x1801348b0  cmp     [rsp+0C8h+var_4C], 0
0x1801348b5  jz      short loc_1801348E9
0x1801348b7  cmp     [rsp+0C8h+var_38], 0
0x1801348bf  jnz     short loc_1801348DF
0x1801348c1  cmp     [rsp+0C8h+var_34], 0
0x1801348c9  jnz     short loc_1801348DF
0x1801348cb  cmp     [rsp+0C8h+var_30], 0
0x1801348d3  jnz     short loc_1801348DF
0x1801348d5  cmp     [rsp+0C8h+var_2C], 0
0x1801348dd  jz      short loc_1801348E9
0x1801348df  lea     r9, [rsp+0C8h+var_38]
0x1801348e7  jmp     short loc_1801348EC
0x1801348e9  xor     r9d, r9d
0x1801348ec  lea     r8, [rsp+0C8h+var_48]
0x1801348f4  lea     rdx, dword_18033ED2C
0x1801348fb  lea     rcx, dword_180380B68
0x180134902  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180134907  cmp     byte ptr [rsi+48h], 0
0x18013490b  jz      loc_1801354A9
0x180134911  cmp     byte ptr [rsi+58h], 0
0x180134915  jz      loc_1801354A9
0x18013491b  mov     r9, [rsi+40h]; unsigned __int16 *
0x18013491f  mov     r8, [rsi+50h]; unsigned __int16 *
0x180134923  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x18013492a  lea     rcx, [rsp+0C8h+var_80]; this
0x18013492f  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180134934  nop
0x180134935  mov     [rsp+0C8h+var_88], 0
0x18013493e  lea     rax, [rsp+0C8h+var_88]
0x180134943  mov     [rsp+0C8h+var_98], rax
0x180134948  mov     [rsp+0C8h+var_A0], 3
0x180134950  mov     [rsp+0C8h+var_A8], 2Ch ; ','
0x180134958  lea     r9, ?MDM_Policy_Result01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Defender02_NodeList
0x18013495f  mov     r8, [rsi+40h]
0x180134963  mov     rdx, [rsi+50h]
0x180134967  mov     rcx, rdi
0x18013496a  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18013496f  mov     edi, eax
0x180134971  test    eax, eax
0x180134973  jz      short loc_18013497A
0x180134975  jmp     loc_1801354AE
0x18013497a  lea     rax, [rsp+0C8h+var_88]
0x18013497f  mov     [rsp+0C8h+var_60], rax
0x180134984  mov     r15d, 1
0x18013498a  mov     [rsp+0C8h+var_58], r15b
0x18013498f  mov     r14, [rsp+0C8h+var_88]
0x180134994  test    r14, r14
0x180134997  jnz     short loc_1801349A1
0x180134999  mov     edi, r15d
0x18013499c  jmp     loc_1801354AE
0x1801349a1  mov     r9d, 2Ch ; ','; unsigned int
0x1801349a7  lea     r8, ?MDM_Policy_Result01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801349ae  mov     rdx, rsi; struct _MI_Instance *
0x1801349b1  mov     rcx, r14; this
0x1801349b4  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801349b9  lea     r8, [rsi+60h]; void *
0x1801349bd  cmp     [r8+4], r15b
0x1801349c1  jnz     short loc_1801349F6
0x1801349c3  lea     rdx, aAllowarchivesc; "AllowArchiveScanning"
0x1801349ca  mov     rcx, r14; this
0x1801349cd  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801349d2  mov     edi, eax
0x1801349d4  test    eax, eax
0x1801349d6  jz      short loc_1801349F6
0x1801349d8  mov     rcx, [rsp+0C8h+var_88]
0x1801349dd  test    rcx, rcx
0x1801349e0  jz      short loc_1801349F1
0x1801349e2  mov     rax, [rcx]
0x1801349e5  mov     edx, r15d
0x1801349e8  mov     rax, [rax]
0x1801349eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801349f0  nop
0x1801349f1  jmp     loc_1801354AE
0x1801349f6  lea     r8, [rsi+68h]; void *
0x1801349fa  cmp     [r8+4], r15b
0x1801349fe  jnz     short loc_180134A33
0x180134a00  lea     rdx, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x180134a07  mov     rcx, r14; this
0x180134a0a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134a0f  mov     edi, eax
0x180134a11  test    eax, eax
0x180134a13  jz      short loc_180134A33
0x180134a15  mov     rcx, [rsp+0C8h+var_88]
0x180134a1a  test    rcx, rcx
0x180134a1d  jz      short loc_180134A2E
0x180134a1f  mov     rax, [rcx]
0x180134a22  mov     edx, r15d
0x180134a25  mov     rax, [rax]
0x180134a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134a2d  nop
0x180134a2e  jmp     loc_1801354AE
0x180134a33  lea     r8, [rsi+70h]; void *
0x180134a37  cmp     [r8+4], r15b
0x180134a3b  jnz     short loc_180134A70
0x180134a3d  lea     rdx, aAllowcloudprot; "AllowCloudProtection"
0x180134a44  mov     rcx, r14; this
0x180134a47  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134a4c  mov     edi, eax
0x180134a4e  test    eax, eax
0x180134a50  jz      short loc_180134A70
0x180134a52  mov     rcx, [rsp+0C8h+var_88]
0x180134a57  test    rcx, rcx
0x180134a5a  jz      short loc_180134A6B
0x180134a5c  mov     rax, [rcx]
0x180134a5f  mov     edx, r15d
0x180134a62  mov     rax, [rax]
0x180134a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134a6a  nop
0x180134a6b  jmp     loc_1801354AE
0x180134a70  lea     r8, [rsi+78h]; void *
0x180134a74  cmp     [r8+4], r15b
0x180134a78  jnz     short loc_180134AAD
0x180134a7a  lea     rdx, aAllowemailscan; "AllowEmailScanning"
0x180134a81  mov     rcx, r14; this
0x180134a84  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134a89  mov     edi, eax
0x180134a8b  test    eax, eax
0x180134a8d  jz      short loc_180134AAD
0x180134a8f  mov     rcx, [rsp+0C8h+var_88]
0x180134a94  test    rcx, rcx
0x180134a97  jz      short loc_180134AA8
0x180134a99  mov     rax, [rcx]
0x180134a9c  mov     edx, r15d
0x180134a9f  mov     rax, [rax]
0x180134aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134aa7  nop
0x180134aa8  jmp     loc_1801354AE
0x180134aad  lea     r8, [rsi+80h]; void *
0x180134ab4  cmp     [r8+4], r15b
0x180134ab8  jnz     short loc_180134AED
0x180134aba  lea     rdx, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x180134ac1  mov     rcx, r14; this
0x180134ac4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134ac9  mov     edi, eax
0x180134acb  test    eax, eax
0x180134acd  jz      short loc_180134AED
0x180134acf  mov     rcx, [rsp+0C8h+var_88]
0x180134ad4  test    rcx, rcx
0x180134ad7  jz      short loc_180134AE8
0x180134ad9  mov     rax, [rcx]
0x180134adc  mov     edx, r15d
0x180134adf  mov     rax, [rax]
0x180134ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134ae7  nop
0x180134ae8  jmp     loc_1801354AE
0x180134aed  lea     r8, [rsi+88h]; void *
0x180134af4  cmp     [r8+4], r15b
0x180134af8  jnz     short loc_180134B2D
0x180134afa  lea     rdx, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x180134b01  mov     rcx, r14; this
0x180134b04  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134b09  mov     edi, eax
0x180134b0b  test    eax, eax
0x180134b0d  jz      short loc_180134B2D
0x180134b0f  mov     rcx, [rsp+0C8h+var_88]
0x180134b14  test    rcx, rcx
0x180134b17  jz      short loc_180134B28
0x180134b19  mov     rax, [rcx]
0x180134b1c  mov     edx, r15d
0x180134b1f  mov     rax, [rax]
0x180134b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134b27  nop
0x180134b28  jmp     loc_1801354AE
0x180134b2d  lea     r8, [rsi+90h]; void *
0x180134b34  cmp     [r8+4], r15b
0x180134b38  jnz     short loc_180134B6D
0x180134b3a  lea     rdx, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x180134b41  mov     rcx, r14; this
0x180134b44  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134b49  mov     edi, eax
0x180134b4b  test    eax, eax
0x180134b4d  jz      short loc_180134B6D
0x180134b4f  mov     rcx, [rsp+0C8h+var_88]
0x180134b54  test    rcx, rcx
0x180134b57  jz      short loc_180134B68
0x180134b59  mov     rax, [rcx]
0x180134b5c  mov     edx, r15d
0x180134b5f  mov     rax, [rax]
0x180134b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134b67  nop
0x180134b68  jmp     loc_1801354AE
0x180134b6d  lea     r8, [rsi+98h]; void *
0x180134b74  cmp     [r8+4], r15b
0x180134b78  jnz     short loc_180134BAD
0x180134b7a  lea     rdx, aAllowioavprote; "AllowIOAVProtection"
0x180134b81  mov     rcx, r14; this
0x180134b84  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134b89  mov     edi, eax
0x180134b8b  test    eax, eax
0x180134b8d  jz      short loc_180134BAD
0x180134b8f  mov     rcx, [rsp+0C8h+var_88]
0x180134b94  test    rcx, rcx
0x180134b97  jz      short loc_180134BA8
0x180134b99  mov     rax, [rcx]
0x180134b9c  mov     edx, r15d
0x180134b9f  mov     rax, [rax]
0x180134ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134ba7  nop
0x180134ba8  jmp     loc_1801354AE
0x180134bad  lea     r8, [rsi+0A0h]; void *
0x180134bb4  cmp     [r8+4], r15b
0x180134bb8  jnz     short loc_180134BED
0x180134bba  lea     rdx, aAllowonaccessp; "AllowOnAccessProtection"
0x180134bc1  mov     rcx, r14; this
0x180134bc4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134bc9  mov     edi, eax
0x180134bcb  test    eax, eax
0x180134bcd  jz      short loc_180134BED
0x180134bcf  mov     rcx, [rsp+0C8h+var_88]
0x180134bd4  test    rcx, rcx
0x180134bd7  jz      short loc_180134BE8
0x180134bd9  mov     rax, [rcx]
0x180134bdc  mov     edx, r15d
0x180134bdf  mov     rax, [rax]
0x180134be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134be7  nop
0x180134be8  jmp     loc_1801354AE
0x180134bed  lea     r8, [rsi+0A8h]; void *
0x180134bf4  cmp     [r8+4], r15b
0x180134bf8  jnz     short loc_180134C2D
0x180134bfa  lea     rdx, aAllowrealtimem; "AllowRealtimeMonitoring"
0x180134c01  mov     rcx, r14; this
0x180134c04  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134c09  mov     edi, eax
0x180134c0b  test    eax, eax
0x180134c0d  jz      short loc_180134C2D
0x180134c0f  mov     rcx, [rsp+0C8h+var_88]
0x180134c14  test    rcx, rcx
0x180134c17  jz      short loc_180134C28
0x180134c19  mov     rax, [rcx]
0x180134c1c  mov     edx, r15d
0x180134c1f  mov     rax, [rax]
0x180134c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134c27  nop
0x180134c28  jmp     loc_1801354AE
0x180134c2d  lea     r8, [rsi+0B0h]; void *
0x180134c34  cmp     [r8+4], r15b
0x180134c38  jnz     short loc_180134C6D
0x180134c3a  lea     rdx, aAllowscanningn; "AllowScanningNetworkFiles"
0x180134c41  mov     rcx, r14; this
0x180134c44  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134c49  mov     edi, eax
0x180134c4b  test    eax, eax
0x180134c4d  jz      short loc_180134C6D
0x180134c4f  mov     rcx, [rsp+0C8h+var_88]
0x180134c54  test    rcx, rcx
0x180134c57  jz      short loc_180134C68
0x180134c59  mov     rax, [rcx]
0x180134c5c  mov     edx, r15d
0x180134c5f  mov     rax, [rax]
0x180134c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134c67  nop
0x180134c68  jmp     loc_1801354AE
0x180134c6d  lea     r8, [rsi+0B8h]; void *
0x180134c74  cmp     [r8+4], r15b
0x180134c78  jnz     short loc_180134CAD
0x180134c7a  lea     rdx, aAllowscriptsca; "AllowScriptScanning"
0x180134c81  mov     rcx, r14; this
0x180134c84  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134c89  mov     edi, eax
0x180134c8b  test    eax, eax
0x180134c8d  jz      short loc_180134CAD
0x180134c8f  mov     rcx, [rsp+0C8h+var_88]
0x180134c94  test    rcx, rcx
0x180134c97  jz      short loc_180134CA8
0x180134c99  mov     rax, [rcx]
0x180134c9c  mov     edx, r15d
0x180134c9f  mov     rax, [rax]
0x180134ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134ca7  nop
0x180134ca8  jmp     loc_1801354AE
  ... truncated ...
```
