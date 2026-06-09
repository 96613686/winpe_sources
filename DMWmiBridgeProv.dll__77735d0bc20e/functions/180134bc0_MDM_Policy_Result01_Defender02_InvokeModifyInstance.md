# MDM_Policy_Result01_Defender02_InvokeModifyInstance

- ea: `0x180134bc0`
- end: `0x1801358d3`
- name: `MDM_Policy_Result01_Defender02_InvokeModifyInstance`
- size: `3347`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801358e0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x180134bc0`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x180134f4e`: `AllowOnAccessProtection`
- `0x18013504e`: `AllowUserUIAccess`
- `0x18013520e`: `ControlledFolderAccessAllowedApplications`
- `0x18013524e`: `ControlledFolderAccessProtectedFolders`
- `0x18013534e`: `EnableControlledFolderAccess`
- `0x18013540e`: `ExcludedExtensions`
- `0x18013544e`: `ExcludedPaths`
- `0x18013564e`: `SecurityIntelligenceLocation`
- `0x18013568e`: `SignatureUpdateFallbackOrder`
- `0x1801356ce`: `SignatureUpdateFileSharesSources`
- `0x18013570e`: `SignatureUpdateInterval`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Defender02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
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
    inserted = CreateRequestHandlerInstance(
                 a1,
                 *(wchar_t **)(a2 + 80),
                 *(const unsigned __int16 **)(a2 + 64),
                 (struct WmiNodeInfo *)&MDM_Policy_Result01_Defender02_NodeList,
                 0x2Cu,
                 3,
                 &v8);
    if ( !inserted )
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
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowArchiveScanning", (LONG *)(a2 + 96))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 108) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowBehaviorMonitoring",
                                (LONG *)(a2 + 104))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 116) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowCloudProtection", (LONG *)(a2 + 112))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 124) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowEmailScanning", (LONG *)(a2 + 120))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 132) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowFullScanOnMappedNetworkDrives",
                                (LONG *)(a2 + 128))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 140) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowFullScanRemovableDriveScanning",
                                (LONG *)(a2 + 136))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 148) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowIntrusionPreventionSystem",
                                (LONG *)(a2 + 144))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 156) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowIOAVProtection", (LONG *)(a2 + 152))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 164) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowOnAccessProtection",
                                (LONG *)(a2 + 160))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 172) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowRealtimeMonitoring",
                                (LONG *)(a2 + 168))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 180) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowScanningNetworkFiles",
                                (LONG *)(a2 + 176))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 188) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowScriptScanning", (LONG *)(a2 + 184))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 196) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowUserUIAccess", (LONG *)(a2 + 192))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 208) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AttackSurfaceReductionOnlyExclusions",
                                (LONG *)(a2 + 200))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 224) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AttackSurfaceReductionRules",
                                (LONG *)(a2 + 216))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 236) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AvgCPULoadFactor", (LONG *)(a2 + 232))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 244) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"CheckForSignaturesBeforeRunningScan",
                                (LONG *)(a2 + 240))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 252) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CloudBlockLevel", (LONG *)(a2 + 248))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 260) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CloudExtendedTimeout", (LONG *)(a2 + 256))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 272) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ControlledFolderAccessAllowedApplications",
                                (LONG *)(a2 + 264))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 288) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ControlledFolderAccessProtectedFolders",
                                (LONG *)(a2 + 280))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 300) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DaysToRetainCleanedMalware",
                                (LONG *)(a2 + 296))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 308) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableCatchupFullScan", (LONG *)(a2 + 304))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 316) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DisableCatchupQuickScan",
                                (LONG *)(a2 + 312))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 324) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableControlledFolderAccess",
                                (LONG *)(a2 + 320))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 332) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableLowCPUPriority", (LONG *)(a2 + 328))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 340) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableNetworkProtection",
                                (LONG *)(a2 + 336))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 352) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedExtensions", (LONG *)(a2 + 344))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 368) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedPaths", (LONG *)(a2 + 360))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 384) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedProcesses", (LONG *)(a2 + 376))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 396) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PUAProtection", (LONG *)(a2 + 392))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 404) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RealTimeScanDirection", (LONG *)(a2 + 400))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 412) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScanParameter", (LONG *)(a2 + 408))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 420) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleQuickScanTime", (LONG *)(a2 + 416))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 428) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleScanDay", (LONG *)(a2 + 424))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 436) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleScanTime", (LONG *)(a2 + 432))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 448) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SecurityIntelligenceLocation",
                                (LONG *)(a2 + 440))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 464) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SignatureUpdateFallbackOrder",
                                (LONG *)(a2 + 456))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 480) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SignatureUpdateFileSharesSources",
                                (LONG *)(a2 + 472))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 492) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SignatureUpdateInterval",
                                (LONG *)(a2 + 488))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 500) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SubmitSamplesConsent", (LONG *)(a2 + 496))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 512) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ThreatSeverityDefaultAction",
                                (LONG *)(a2 + 504))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else
        {
          inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
          if ( inserted )
          {
            if ( v8 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
          }
          else
          {
            inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
        inserted = 1;
      }
    }
  }
  else
  {
    inserted = 4;
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
  return inserted;
}

```

## disassembly

```asm
0x180134bc0  mov     r11, rsp
0x180134bc3  mov     [r11+18h], rsi
0x180134bc7  push    rdi
0x180134bc8  push    r14
0x180134bca  push    r15
0x180134bcc  sub     rsp, 0B0h
0x180134bd3  mov     rax, cs:__security_cookie
0x180134bda  xor     rax, rsp
0x180134bdd  mov     [rsp+0C8h+var_28], rax
0x180134be5  mov     rsi, rdx
0x180134be8  mov     rdi, rcx
0x180134beb  mov     [rsp+0C8h+var_50], 0
0x180134bf3  mov     [rsp+0C8h+var_4C], 0
0x180134bf8  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180134bff  mov     [r11-80h], rax
0x180134c03  lea     rax, [r11-50h]
0x180134c07  mov     [r11-78h], rax
0x180134c0b  lea     rax, aMdmPolicyResul_181; "MDM_Policy_Result01_Defender02"
0x180134c12  mov     [r11-70h], rax
0x180134c16  lea     rcx, [r11-50h]
0x180134c1a  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180134c1f  mov     eax, cs:dword_180380B68
0x180134c25  cmp     eax, 5
0x180134c28  jbe     short loc_180134C9B
0x180134c2a  mov     rdx, 200000000000h
0x180134c34  lea     rcx, dword_180380B68
0x180134c3b  call    _tlgKeywordOn
0x180134c40  test    al, al
0x180134c42  jz      short loc_180134C9B
0x180134c44  cmp     [rsp+0C8h+var_4C], 0
0x180134c49  jz      short loc_180134C7D
0x180134c4b  cmp     [rsp+0C8h+var_38], 0
0x180134c53  jnz     short loc_180134C73
0x180134c55  cmp     [rsp+0C8h+var_34], 0
0x180134c5d  jnz     short loc_180134C73
0x180134c5f  cmp     [rsp+0C8h+var_30], 0
0x180134c67  jnz     short loc_180134C73
0x180134c69  cmp     [rsp+0C8h+var_2C], 0
0x180134c71  jz      short loc_180134C7D
0x180134c73  lea     r9, [rsp+0C8h+var_38]
0x180134c7b  jmp     short loc_180134C80
0x180134c7d  xor     r9d, r9d
0x180134c80  lea     r8, [rsp+0C8h+var_48]
0x180134c88  lea     rdx, dword_18033ED2C
0x180134c8f  lea     rcx, dword_180380B68
0x180134c96  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180134c9b  cmp     byte ptr [rsi+48h], 0
0x180134c9f  jz      loc_18013583D
0x180134ca5  cmp     byte ptr [rsi+58h], 0
0x180134ca9  jz      loc_18013583D
0x180134caf  mov     r9, [rsi+40h]; unsigned __int16 *
0x180134cb3  mov     r8, [rsi+50h]; unsigned __int16 *
0x180134cb7  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x180134cbe  lea     rcx, [rsp+0C8h+var_80]; this
0x180134cc3  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180134cc8  nop
0x180134cc9  mov     [rsp+0C8h+var_88], 0
0x180134cd2  lea     rax, [rsp+0C8h+var_88]
0x180134cd7  mov     [rsp+0C8h+var_98], rax
0x180134cdc  mov     [rsp+0C8h+var_A0], 3
0x180134ce4  mov     [rsp+0C8h+var_A8], 2Ch ; ','
0x180134cec  lea     r9, ?MDM_Policy_Result01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Defender02_NodeList
0x180134cf3  mov     r8, [rsi+40h]
0x180134cf7  mov     rdx, [rsi+50h]
0x180134cfb  mov     rcx, rdi
0x180134cfe  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180134d03  mov     edi, eax
0x180134d05  test    eax, eax
0x180134d07  jz      short loc_180134D0E
0x180134d09  jmp     loc_180135842
0x180134d0e  lea     rax, [rsp+0C8h+var_88]
0x180134d13  mov     [rsp+0C8h+var_60], rax
0x180134d18  mov     r15d, 1
0x180134d1e  mov     [rsp+0C8h+var_58], r15b
0x180134d23  mov     r14, [rsp+0C8h+var_88]
0x180134d28  test    r14, r14
0x180134d2b  jnz     short loc_180134D35
0x180134d2d  mov     edi, r15d
0x180134d30  jmp     loc_180135842
0x180134d35  mov     r9d, 2Ch ; ','; unsigned int
0x180134d3b  lea     r8, ?MDM_Policy_Result01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180134d42  mov     rdx, rsi; struct _MI_Instance *
0x180134d45  mov     rcx, r14; this
0x180134d48  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180134d4d  lea     r8, [rsi+60h]; void *
0x180134d51  cmp     [r8+4], r15b
0x180134d55  jnz     short loc_180134D8A
0x180134d57  lea     rdx, aAllowarchivesc; "AllowArchiveScanning"
0x180134d5e  mov     rcx, r14; this
0x180134d61  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134d66  mov     edi, eax
0x180134d68  test    eax, eax
0x180134d6a  jz      short loc_180134D8A
0x180134d6c  mov     rcx, [rsp+0C8h+var_88]
0x180134d71  test    rcx, rcx
0x180134d74  jz      short loc_180134D85
0x180134d76  mov     rax, [rcx]
0x180134d79  mov     edx, r15d
0x180134d7c  mov     rax, [rax]
0x180134d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134d84  nop
0x180134d85  jmp     loc_180135842
0x180134d8a  lea     r8, [rsi+68h]; void *
0x180134d8e  cmp     [r8+4], r15b
0x180134d92  jnz     short loc_180134DC7
0x180134d94  lea     rdx, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x180134d9b  mov     rcx, r14; this
0x180134d9e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134da3  mov     edi, eax
0x180134da5  test    eax, eax
0x180134da7  jz      short loc_180134DC7
0x180134da9  mov     rcx, [rsp+0C8h+var_88]
0x180134dae  test    rcx, rcx
0x180134db1  jz      short loc_180134DC2
0x180134db3  mov     rax, [rcx]
0x180134db6  mov     edx, r15d
0x180134db9  mov     rax, [rax]
0x180134dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134dc1  nop
0x180134dc2  jmp     loc_180135842
0x180134dc7  lea     r8, [rsi+70h]; void *
0x180134dcb  cmp     [r8+4], r15b
0x180134dcf  jnz     short loc_180134E04
0x180134dd1  lea     rdx, aAllowcloudprot; "AllowCloudProtection"
0x180134dd8  mov     rcx, r14; this
0x180134ddb  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134de0  mov     edi, eax
0x180134de2  test    eax, eax
0x180134de4  jz      short loc_180134E04
0x180134de6  mov     rcx, [rsp+0C8h+var_88]
0x180134deb  test    rcx, rcx
0x180134dee  jz      short loc_180134DFF
0x180134df0  mov     rax, [rcx]
0x180134df3  mov     edx, r15d
0x180134df6  mov     rax, [rax]
0x180134df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134dfe  nop
0x180134dff  jmp     loc_180135842
0x180134e04  lea     r8, [rsi+78h]; void *
0x180134e08  cmp     [r8+4], r15b
0x180134e0c  jnz     short loc_180134E41
0x180134e0e  lea     rdx, aAllowemailscan; "AllowEmailScanning"
0x180134e15  mov     rcx, r14; this
0x180134e18  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134e1d  mov     edi, eax
0x180134e1f  test    eax, eax
0x180134e21  jz      short loc_180134E41
0x180134e23  mov     rcx, [rsp+0C8h+var_88]
0x180134e28  test    rcx, rcx
0x180134e2b  jz      short loc_180134E3C
0x180134e2d  mov     rax, [rcx]
0x180134e30  mov     edx, r15d
0x180134e33  mov     rax, [rax]
0x180134e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134e3b  nop
0x180134e3c  jmp     loc_180135842
0x180134e41  lea     r8, [rsi+80h]; void *
0x180134e48  cmp     [r8+4], r15b
0x180134e4c  jnz     short loc_180134E81
0x180134e4e  lea     rdx, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x180134e55  mov     rcx, r14; this
0x180134e58  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134e5d  mov     edi, eax
0x180134e5f  test    eax, eax
0x180134e61  jz      short loc_180134E81
0x180134e63  mov     rcx, [rsp+0C8h+var_88]
0x180134e68  test    rcx, rcx
0x180134e6b  jz      short loc_180134E7C
0x180134e6d  mov     rax, [rcx]
0x180134e70  mov     edx, r15d
0x180134e73  mov     rax, [rax]
0x180134e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134e7b  nop
0x180134e7c  jmp     loc_180135842
0x180134e81  lea     r8, [rsi+88h]; void *
0x180134e88  cmp     [r8+4], r15b
0x180134e8c  jnz     short loc_180134EC1
0x180134e8e  lea     rdx, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x180134e95  mov     rcx, r14; this
0x180134e98  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134e9d  mov     edi, eax
0x180134e9f  test    eax, eax
0x180134ea1  jz      short loc_180134EC1
0x180134ea3  mov     rcx, [rsp+0C8h+var_88]
0x180134ea8  test    rcx, rcx
0x180134eab  jz      short loc_180134EBC
0x180134ead  mov     rax, [rcx]
0x180134eb0  mov     edx, r15d
0x180134eb3  mov     rax, [rax]
0x180134eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134ebb  nop
0x180134ebc  jmp     loc_180135842
0x180134ec1  lea     r8, [rsi+90h]; void *
0x180134ec8  cmp     [r8+4], r15b
0x180134ecc  jnz     short loc_180134F01
0x180134ece  lea     rdx, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x180134ed5  mov     rcx, r14; this
0x180134ed8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134edd  mov     edi, eax
0x180134edf  test    eax, eax
0x180134ee1  jz      short loc_180134F01
0x180134ee3  mov     rcx, [rsp+0C8h+var_88]
0x180134ee8  test    rcx, rcx
0x180134eeb  jz      short loc_180134EFC
0x180134eed  mov     rax, [rcx]
0x180134ef0  mov     edx, r15d
0x180134ef3  mov     rax, [rax]
0x180134ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134efb  nop
0x180134efc  jmp     loc_180135842
0x180134f01  lea     r8, [rsi+98h]; void *
0x180134f08  cmp     [r8+4], r15b
0x180134f0c  jnz     short loc_180134F41
0x180134f0e  lea     rdx, aAllowioavprote; "AllowIOAVProtection"
0x180134f15  mov     rcx, r14; this
0x180134f18  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134f1d  mov     edi, eax
0x180134f1f  test    eax, eax
0x180134f21  jz      short loc_180134F41
0x180134f23  mov     rcx, [rsp+0C8h+var_88]
0x180134f28  test    rcx, rcx
0x180134f2b  jz      short loc_180134F3C
0x180134f2d  mov     rax, [rcx]
0x180134f30  mov     edx, r15d
0x180134f33  mov     rax, [rax]
0x180134f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134f3b  nop
0x180134f3c  jmp     loc_180135842
0x180134f41  lea     r8, [rsi+0A0h]; void *
0x180134f48  cmp     [r8+4], r15b
0x180134f4c  jnz     short loc_180134F81
0x180134f4e  lea     rdx, aAllowonaccessp; "AllowOnAccessProtection"
0x180134f55  mov     rcx, r14; this
0x180134f58  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134f5d  mov     edi, eax
0x180134f5f  test    eax, eax
0x180134f61  jz      short loc_180134F81
0x180134f63  mov     rcx, [rsp+0C8h+var_88]
0x180134f68  test    rcx, rcx
0x180134f6b  jz      short loc_180134F7C
0x180134f6d  mov     rax, [rcx]
0x180134f70  mov     edx, r15d
0x180134f73  mov     rax, [rax]
0x180134f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134f7b  nop
0x180134f7c  jmp     loc_180135842
0x180134f81  lea     r8, [rsi+0A8h]; void *
0x180134f88  cmp     [r8+4], r15b
0x180134f8c  jnz     short loc_180134FC1
0x180134f8e  lea     rdx, aAllowrealtimem; "AllowRealtimeMonitoring"
0x180134f95  mov     rcx, r14; this
0x180134f98  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134f9d  mov     edi, eax
0x180134f9f  test    eax, eax
0x180134fa1  jz      short loc_180134FC1
0x180134fa3  mov     rcx, [rsp+0C8h+var_88]
0x180134fa8  test    rcx, rcx
0x180134fab  jz      short loc_180134FBC
0x180134fad  mov     rax, [rcx]
0x180134fb0  mov     edx, r15d
0x180134fb3  mov     rax, [rax]
0x180134fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134fbb  nop
0x180134fbc  jmp     loc_180135842
0x180134fc1  lea     r8, [rsi+0B0h]; void *
0x180134fc8  cmp     [r8+4], r15b
0x180134fcc  jnz     short loc_180135001
0x180134fce  lea     rdx, aAllowscanningn; "AllowScanningNetworkFiles"
0x180134fd5  mov     rcx, r14; this
0x180134fd8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180134fdd  mov     edi, eax
0x180134fdf  test    eax, eax
0x180134fe1  jz      short loc_180135001
0x180134fe3  mov     rcx, [rsp+0C8h+var_88]
0x180134fe8  test    rcx, rcx
0x180134feb  jz      short loc_180134FFC
0x180134fed  mov     rax, [rcx]
0x180134ff0  mov     edx, r15d
0x180134ff3  mov     rax, [rax]
0x180134ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134ffb  nop
0x180134ffc  jmp     loc_180135842
0x180135001  lea     r8, [rsi+0B8h]; void *
0x180135008  cmp     [r8+4], r15b
0x18013500c  jnz     short loc_180135041
0x18013500e  lea     rdx, aAllowscriptsca; "AllowScriptScanning"
0x180135015  mov     rcx, r14; this
0x180135018  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18013501d  mov     edi, eax
0x18013501f  test    eax, eax
0x180135021  jz      short loc_180135041
0x180135023  mov     rcx, [rsp+0C8h+var_88]
0x180135028  test    rcx, rcx
0x18013502b  jz      short loc_18013503C
0x18013502d  mov     rax, [rcx]
0x180135030  mov     edx, r15d
0x180135033  mov     rax, [rax]
0x180135036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013503b  nop
0x18013503c  jmp     loc_180135842
  ... truncated ...
```
