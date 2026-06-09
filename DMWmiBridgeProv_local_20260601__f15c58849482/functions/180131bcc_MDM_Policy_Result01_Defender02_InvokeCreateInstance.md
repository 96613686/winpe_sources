# MDM_Policy_Result01_Defender02_InvokeCreateInstance

- ea: `0x180131bcc`
- end: `0x1801329ac`
- name: `MDM_Policy_Result01_Defender02_InvokeCreateInstance`
- size: `3552`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180131b10`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x180131bcc`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x180131f8c`: `AllowOnAccessProtection`
- `0x18013208c`: `AllowUserUIAccess`
- `0x18013224c`: `ControlledFolderAccessAllowedApplications`
- `0x18013228c`: `ControlledFolderAccessProtectedFolders`
- `0x18013238c`: `EnableControlledFolderAccess`
- `0x18013244c`: `ExcludedExtensions`
- `0x18013248c`: `ExcludedPaths`
- `0x18013268c`: `SecurityIntelligenceLocation`
- `0x1801326cc`: `SignatureUpdateFallbackOrder`
- `0x18013270c`: `SignatureUpdateFileSharesSources`
- `0x18013274c`: `SignatureUpdateInterval`
- `0x180131cf5`: `CreateInstanceStart`
- `0x180132912`: `CreateInstanceEnd`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Defender02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-2A8h] BYREF
  char v9; // [rsp+48h] [rbp-2A0h]
  _QWORD v10[5]; // [rsp+50h] [rbp-298h] BYREF
  char v11; // [rsp+78h] [rbp-270h]
  int v12; // [rsp+80h] [rbp-268h] BYREF
  char v13; // [rsp+84h] [rbp-264h]
  _BYTE v14[16]; // [rsp+88h] [rbp-260h] BYREF
  _DWORD v15[6]; // [rsp+98h] [rbp-250h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-238h] BYREF

  memset_0(&instance, 0, 0x208u);
  v12 = 0;
  v13 = 0;
  v10[0] = &TelemetryEventWriter::`vftable';
  v10[1] = &v12;
  v10[2] = "MDM_Policy_Result01_Defender02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_1803617F7,
      v14,
      v4);
  }
  if ( LOBYTE(a2[1].classDecl) && (v9 = 0, LOBYTE(a2[1].nameSpace)) )
  {
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
                               &MDM_Policy_Result01_Defender02_NodeList,
                               44,
                               4,
                               &v8);
    if ( inserted == MI_RESULT_OK )
    {
      v10[4] = &v8;
      v11 = 1;
      v6 = v8;
      if ( v8 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v8,
          a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_Defender02_NodeList,
          0x2Cu);
        if ( BYTE4(a2[1].reserved[0]) == 1
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowArchiveScanning", a2[1].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowBehaviorMonitoring",
                                &a2[1].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowCloudProtection", &a2[1].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowEmailScanning", &a2[1].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFullScanOnMappedNetworkDrives", &a2[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowFullScanRemovableDriveScanning",
                                &a2[2].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowIntrusionPreventionSystem",
                                &a2[2].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowIOAVProtection", &a2[2].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowOnAccessProtection", a2[2].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowRealtimeMonitoring",
                                &a2[2].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowScanningNetworkFiles",
                                &a2[2].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowScriptScanning", &a2[2].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowUserUIAccess", &a2[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[3].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AttackSurfaceReductionOnlyExclusions",
                                &a2[3].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[3].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AttackSurfaceReductionRules",
                                &a2[3].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AvgCPULoadFactor", &a2[3].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"CheckForSignaturesBeforeRunningScan",
                                &a2[3].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CloudBlockLevel", &a2[3].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CloudExtendedTimeout", &a2[4])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ControlledFolderAccessAllowedApplications",
                                &a2[4].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ControlledFolderAccessProtectedFolders",
                                &a2[4].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DaysToRetainCleanedMalware",
                                &a2[4].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableCatchupFullScan", &a2[4].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DisableCatchupQuickScan",
                                &a2[4].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableControlledFolderAccess", &a2[5])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableLowCPUPriority", &a2[5].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableNetworkProtection", &a2[5].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedExtensions", &a2[5].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedPaths", &a2[5].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedProcesses", &a2[5].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PUAProtection", &a2[6].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RealTimeScanDirection", &a2[6].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScanParameter", &a2[6].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleQuickScanTime", a2[6].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleScanDay", &a2[6].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleScanTime", &a2[6].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SecurityIntelligenceLocation",
                                &a2[6].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SignatureUpdateFallbackOrder",
                                &a2[7].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SignatureUpdateFileSharesSources",
                                &a2[7].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SignatureUpdateInterval",
                                &a2[7].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SubmitSamplesConsent", &a2[7].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ThreatSeverityDefaultAction",
                                &a2[7].reserved[3])) != MI_RESULT_OK )
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
            else
            {
              inserted = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Defender02_rtti, &instance);
              if ( inserted )
              {
                if ( v8 )
                  (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
              }
              else
              {
                v9 = 1;
                MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
                MI_Instance_Destruct((MI_Instance *)self);
                if ( v8 )
                  (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
                MI_Instance_Destruct(&instance);
              }
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
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "CreateInstanceEnd", inserted);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_180357BDF,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180131bcc  mov     [rsp+arg_10], rsi
0x180131bd1  mov     [rsp+arg_18], rdi
0x180131bd6  push    r12
0x180131bd8  push    r14
0x180131bda  push    r15
0x180131bdc  sub     rsp, 2D0h
0x180131be3  mov     rax, cs:__security_cookie
0x180131bea  xor     rax, rsp
0x180131bed  mov     [rsp+2E8h+var_28], rax
0x180131bf5  mov     rsi, rdx
0x180131bf8  mov     r15, rcx
0x180131bfb  xor     edx, edx; Val
0x180131bfd  mov     r8d, 208h; Size
0x180131c03  lea     rcx, [rsp+2E8h+instance]; void *
0x180131c0b  call    memset_0
0x180131c10  mov     [rsp+2E8h+var_268], 0
0x180131c1b  mov     [rsp+2E8h+var_264], 0
0x180131c23  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180131c2a  mov     [rsp+2E8h+var_298], rax
0x180131c2f  lea     rax, [rsp+2E8h+var_268]
0x180131c37  mov     [rsp+2E8h+var_290], rax
0x180131c3c  lea     rax, aMdmPolicyResul_181; "MDM_Policy_Result01_Defender02"
0x180131c43  mov     [rsp+2E8h+var_288], rax
0x180131c48  lea     rcx, [rsp+2E8h+var_268]
0x180131c50  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180131c55  mov     eax, cs:dword_180380B68
0x180131c5b  cmp     eax, 5
0x180131c5e  jbe     short loc_180131CD4
0x180131c60  mov     rdx, 200000000000h
0x180131c6a  lea     rcx, dword_180380B68
0x180131c71  call    _tlgKeywordOn
0x180131c76  test    al, al
0x180131c78  jz      short loc_180131CD4
0x180131c7a  cmp     [rsp+2E8h+var_264], 0
0x180131c82  jz      short loc_180131CB6
0x180131c84  cmp     [rsp+2E8h+var_250], 0
0x180131c8c  jnz     short loc_180131CAC
0x180131c8e  cmp     [rsp+2E8h+var_24C], 0
0x180131c96  jnz     short loc_180131CAC
0x180131c98  cmp     [rsp+2E8h+var_248], 0
0x180131ca0  jnz     short loc_180131CAC
0x180131ca2  cmp     [rsp+2E8h+var_244], 0
0x180131caa  jz      short loc_180131CB6
0x180131cac  lea     r9, [rsp+2E8h+var_250]
0x180131cb4  jmp     short loc_180131CB9
0x180131cb6  xor     r9d, r9d
0x180131cb9  lea     r8, [rsp+2E8h+var_260]
0x180131cc1  lea     rdx, byte_1803617F7
0x180131cc8  lea     rcx, dword_180380B68
0x180131ccf  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180131cd4  cmp     byte ptr [rsi+48h], 0
0x180131cd8  jz      loc_18013290A
0x180131cde  mov     [rsp+2E8h+var_2A0], 0
0x180131ce3  cmp     byte ptr [rsi+58h], 0
0x180131ce7  jz      loc_18013290A
0x180131ced  mov     r9, [rsi+40h]; unsigned __int16 *
0x180131cf1  mov     r8, [rsi+50h]; unsigned __int16 *
0x180131cf5  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x180131cfc  lea     rcx, [rsp+2E8h+var_298]; this
0x180131d01  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180131d06  nop
0x180131d07  mov     [rsp+2E8h+var_2A8], 0
0x180131d10  lea     rax, [rsp+2E8h+var_2A8]
0x180131d15  mov     [rsp+2E8h+var_2B8], rax
0x180131d1a  mov     [rsp+2E8h+var_2C0], 4
0x180131d22  mov     [rsp+2E8h+var_2C8], 2Ch ; ','
0x180131d2a  lea     r9, ?MDM_Policy_Result01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Defender02_NodeList
0x180131d31  mov     r8, [rsi+40h]
0x180131d35  mov     rdx, [rsi+50h]
0x180131d39  mov     rcx, r15
0x180131d3c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180131d41  mov     edi, eax
0x180131d43  test    eax, eax
0x180131d45  jz      short loc_180131D4C
0x180131d47  jmp     loc_18013290F
0x180131d4c  lea     rax, [rsp+2E8h+var_2A8]
0x180131d51  mov     [rsp+2E8h+var_278], rax
0x180131d56  mov     r12d, 1
0x180131d5c  mov     [rsp+2E8h+var_270], r12b
0x180131d61  mov     r14, [rsp+2E8h+var_2A8]
0x180131d66  test    r14, r14
0x180131d69  jnz     short loc_180131D73
0x180131d6b  mov     edi, r12d
0x180131d6e  jmp     loc_18013290F
0x180131d73  mov     r9d, 2Ch ; ','; unsigned int
0x180131d79  lea     r8, ?MDM_Policy_Result01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180131d80  mov     rdx, rsi; struct _MI_Instance *
0x180131d83  mov     rcx, r14; this
0x180131d86  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180131d8b  lea     r8, [rsi+60h]; void *
0x180131d8f  cmp     [r8+4], r12b
0x180131d93  jnz     short loc_180131DC8
0x180131d95  lea     rdx, aAllowarchivesc; "AllowArchiveScanning"
0x180131d9c  mov     rcx, r14; this
0x180131d9f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180131da4  mov     edi, eax
0x180131da6  test    eax, eax
0x180131da8  jz      short loc_180131DC8
0x180131daa  mov     rcx, [rsp+2E8h+var_2A8]
0x180131daf  test    rcx, rcx
0x180131db2  jz      short loc_180131DC3
0x180131db4  mov     rax, [rcx]
0x180131db7  mov     edx, r12d
0x180131dba  mov     rax, [rax]
0x180131dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131dc2  nop
0x180131dc3  jmp     loc_18013290F
0x180131dc8  lea     r8, [rsi+68h]; void *
0x180131dcc  cmp     [r8+4], r12b
0x180131dd0  jnz     short loc_180131E05
0x180131dd2  lea     rdx, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x180131dd9  mov     rcx, r14; this
0x180131ddc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180131de1  mov     edi, eax
0x180131de3  test    eax, eax
0x180131de5  jz      short loc_180131E05
0x180131de7  mov     rcx, [rsp+2E8h+var_2A8]
0x180131dec  test    rcx, rcx
0x180131def  jz      short loc_180131E00
0x180131df1  mov     rax, [rcx]
0x180131df4  mov     edx, r12d
0x180131df7  mov     rax, [rax]
0x180131dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131dff  nop
0x180131e00  jmp     loc_18013290F
0x180131e05  lea     r8, [rsi+70h]; void *
0x180131e09  cmp     [r8+4], r12b
0x180131e0d  jnz     short loc_180131E42
0x180131e0f  lea     rdx, aAllowcloudprot; "AllowCloudProtection"
0x180131e16  mov     rcx, r14; this
0x180131e19  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180131e1e  mov     edi, eax
0x180131e20  test    eax, eax
0x180131e22  jz      short loc_180131E42
0x180131e24  mov     rcx, [rsp+2E8h+var_2A8]
0x180131e29  test    rcx, rcx
0x180131e2c  jz      short loc_180131E3D
0x180131e2e  mov     rax, [rcx]
0x180131e31  mov     edx, r12d
0x180131e34  mov     rax, [rax]
0x180131e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131e3c  nop
0x180131e3d  jmp     loc_18013290F
0x180131e42  lea     r8, [rsi+78h]; void *
0x180131e46  cmp     [r8+4], r12b
0x180131e4a  jnz     short loc_180131E7F
0x180131e4c  lea     rdx, aAllowemailscan; "AllowEmailScanning"
0x180131e53  mov     rcx, r14; this
0x180131e56  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180131e5b  mov     edi, eax
0x180131e5d  test    eax, eax
0x180131e5f  jz      short loc_180131E7F
0x180131e61  mov     rcx, [rsp+2E8h+var_2A8]
0x180131e66  test    rcx, rcx
0x180131e69  jz      short loc_180131E7A
0x180131e6b  mov     rax, [rcx]
0x180131e6e  mov     edx, r12d
0x180131e71  mov     rax, [rax]
0x180131e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131e79  nop
0x180131e7a  jmp     loc_18013290F
0x180131e7f  lea     r8, [rsi+80h]; void *
0x180131e86  cmp     [r8+4], r12b
0x180131e8a  jnz     short loc_180131EBF
0x180131e8c  lea     rdx, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x180131e93  mov     rcx, r14; this
0x180131e96  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180131e9b  mov     edi, eax
0x180131e9d  test    eax, eax
0x180131e9f  jz      short loc_180131EBF
0x180131ea1  mov     rcx, [rsp+2E8h+var_2A8]
0x180131ea6  test    rcx, rcx
0x180131ea9  jz      short loc_180131EBA
0x180131eab  mov     rax, [rcx]
0x180131eae  mov     edx, r12d
0x180131eb1  mov     rax, [rax]
0x180131eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131eb9  nop
0x180131eba  jmp     loc_18013290F
0x180131ebf  lea     r8, [rsi+88h]; void *
0x180131ec6  cmp     [r8+4], r12b
0x180131eca  jnz     short loc_180131EFF
0x180131ecc  lea     rdx, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x180131ed3  mov     rcx, r14; this
0x180131ed6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180131edb  mov     edi, eax
0x180131edd  test    eax, eax
0x180131edf  jz      short loc_180131EFF
0x180131ee1  mov     rcx, [rsp+2E8h+var_2A8]
0x180131ee6  test    rcx, rcx
0x180131ee9  jz      short loc_180131EFA
0x180131eeb  mov     rax, [rcx]
0x180131eee  mov     edx, r12d
0x180131ef1  mov     rax, [rax]
0x180131ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131ef9  nop
0x180131efa  jmp     loc_18013290F
0x180131eff  lea     r8, [rsi+90h]; void *
0x180131f06  cmp     [r8+4], r12b
0x180131f0a  jnz     short loc_180131F3F
0x180131f0c  lea     rdx, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x180131f13  mov     rcx, r14; this
0x180131f16  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180131f1b  mov     edi, eax
0x180131f1d  test    eax, eax
0x180131f1f  jz      short loc_180131F3F
0x180131f21  mov     rcx, [rsp+2E8h+var_2A8]
0x180131f26  test    rcx, rcx
0x180131f29  jz      short loc_180131F3A
0x180131f2b  mov     rax, [rcx]
0x180131f2e  mov     edx, r12d
0x180131f31  mov     rax, [rax]
0x180131f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131f39  nop
0x180131f3a  jmp     loc_18013290F
0x180131f3f  lea     r8, [rsi+98h]; void *
0x180131f46  cmp     [r8+4], r12b
0x180131f4a  jnz     short loc_180131F7F
0x180131f4c  lea     rdx, aAllowioavprote; "AllowIOAVProtection"
0x180131f53  mov     rcx, r14; this
0x180131f56  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180131f5b  mov     edi, eax
0x180131f5d  test    eax, eax
0x180131f5f  jz      short loc_180131F7F
0x180131f61  mov     rcx, [rsp+2E8h+var_2A8]
0x180131f66  test    rcx, rcx
0x180131f69  jz      short loc_180131F7A
0x180131f6b  mov     rax, [rcx]
0x180131f6e  mov     edx, r12d
0x180131f71  mov     rax, [rax]
0x180131f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131f79  nop
0x180131f7a  jmp     loc_18013290F
0x180131f7f  lea     r8, [rsi+0A0h]; void *
0x180131f86  cmp     [r8+4], r12b
0x180131f8a  jnz     short loc_180131FBF
0x180131f8c  lea     rdx, aAllowonaccessp; "AllowOnAccessProtection"
0x180131f93  mov     rcx, r14; this
0x180131f96  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180131f9b  mov     edi, eax
0x180131f9d  test    eax, eax
0x180131f9f  jz      short loc_180131FBF
0x180131fa1  mov     rcx, [rsp+2E8h+var_2A8]
0x180131fa6  test    rcx, rcx
0x180131fa9  jz      short loc_180131FBA
0x180131fab  mov     rax, [rcx]
0x180131fae  mov     edx, r12d
0x180131fb1  mov     rax, [rax]
0x180131fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131fb9  nop
0x180131fba  jmp     loc_18013290F
0x180131fbf  lea     r8, [rsi+0A8h]; void *
0x180131fc6  cmp     [r8+4], r12b
0x180131fca  jnz     short loc_180131FFF
0x180131fcc  lea     rdx, aAllowrealtimem; "AllowRealtimeMonitoring"
0x180131fd3  mov     rcx, r14; this
0x180131fd6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180131fdb  mov     edi, eax
0x180131fdd  test    eax, eax
0x180131fdf  jz      short loc_180131FFF
0x180131fe1  mov     rcx, [rsp+2E8h+var_2A8]
0x180131fe6  test    rcx, rcx
0x180131fe9  jz      short loc_180131FFA
0x180131feb  mov     rax, [rcx]
0x180131fee  mov     edx, r12d
0x180131ff1  mov     rax, [rax]
0x180131ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131ff9  nop
0x180131ffa  jmp     loc_18013290F
0x180131fff  lea     r8, [rsi+0B0h]; void *
0x180132006  cmp     [r8+4], r12b
0x18013200a  jnz     short loc_18013203F
0x18013200c  lea     rdx, aAllowscanningn; "AllowScanningNetworkFiles"
0x180132013  mov     rcx, r14; this
0x180132016  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18013201b  mov     edi, eax
0x18013201d  test    eax, eax
0x18013201f  jz      short loc_18013203F
0x180132021  mov     rcx, [rsp+2E8h+var_2A8]
0x180132026  test    rcx, rcx
0x180132029  jz      short loc_18013203A
0x18013202b  mov     rax, [rcx]
0x18013202e  mov     edx, r12d
0x180132031  mov     rax, [rax]
0x180132034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132039  nop
0x18013203a  jmp     loc_18013290F
0x18013203f  lea     r8, [rsi+0B8h]; void *
0x180132046  cmp     [r8+4], r12b
0x18013204a  jnz     short loc_18013207F
0x18013204c  lea     rdx, aAllowscriptsca; "AllowScriptScanning"
0x180132053  mov     rcx, r14; this
0x180132056  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18013205b  mov     edi, eax
0x18013205d  test    eax, eax
0x18013205f  jz      short loc_18013207F
0x180132061  mov     rcx, [rsp+2E8h+var_2A8]
0x180132066  test    rcx, rcx
0x180132069  jz      short loc_18013207A
0x18013206b  mov     rax, [rcx]
  ... truncated ...
```
