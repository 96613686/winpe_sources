# MDM_Policy_Config01_Defender02_InvokeCreateInstance

- ea: `0x18007a1bc`
- end: `0x18007af9c`
- name: `MDM_Policy_Config01_Defender02_InvokeCreateInstance`
- size: `3552`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007a100`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18007a1bc`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x18007a57c`: `AllowOnAccessProtection`
- `0x18007a67c`: `AllowUserUIAccess`
- `0x18007a83c`: `ControlledFolderAccessAllowedApplications`
- `0x18007a87c`: `ControlledFolderAccessProtectedFolders`
- `0x18007a97c`: `EnableControlledFolderAccess`
- `0x18007aa3c`: `ExcludedExtensions`
- `0x18007aa7c`: `ExcludedPaths`
- `0x18007ac7c`: `SecurityIntelligenceLocation`
- `0x18007acbc`: `SignatureUpdateFallbackOrder`
- `0x18007acfc`: `SignatureUpdateFileSharesSources`
- `0x18007ad3c`: `SignatureUpdateInterval`
- `0x18007a2e5`: `CreateInstanceStart`
- `0x18007af02`: `CreateInstanceEnd`
- `0x18007a22c`: `MDM_Policy_Config01_Defender02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Defender02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
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
  v10[2] = "MDM_Policy_Config01_Defender02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &unk_18035D878,
      v14,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    inserted = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_197;
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
                             &MDM_Policy_Config01_Defender02_NodeList,
                             44,
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
      goto LABEL_197;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v8,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_Defender02_NodeList,
      0x2Cu);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowArchiveScanning", a2[1].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
LABEL_192:
        (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        goto LABEL_197;
      }
    }
    if ( BYTE4(a2[1].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowBehaviorMonitoring", &a2[1].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[1].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowCloudProtection", &a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowEmailScanning", &a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFullScanOnMappedNetworkDrives", &a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFullScanRemovableDriveScanning", &a2[2].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowIntrusionPreventionSystem", &a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowIOAVProtection", &a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowOnAccessProtection", a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowRealtimeMonitoring", &a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowScanningNetworkFiles", &a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowScriptScanning", &a2[2].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowUserUIAccess", &a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[3].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AttackSurfaceReductionOnlyExclusions", &a2[3].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[3].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AttackSurfaceReductionRules", &a2[3].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[3].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AvgCPULoadFactor", &a2[3].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[3].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CheckForSignaturesBeforeRunningScan", &a2[3].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[3].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CloudBlockLevel", &a2[3].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CloudExtendedTimeout", &a2[4]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[4].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ControlledFolderAccessAllowedApplications",
                   &a2[4].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[4].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ControlledFolderAccessProtectedFolders",
                   &a2[4].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[4].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DaysToRetainCleanedMalware", &a2[4].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[4].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableCatchupFullScan", &a2[4].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableCatchupQuickScan", &a2[4].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[5].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableControlledFolderAccess", &a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableLowCPUPriority", &a2[5].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[5].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableNetworkProtection", &a2[5].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[5].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedExtensions", &a2[5].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[5].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedPaths", &a2[5].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[6].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedProcesses", &a2[5].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[6].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PUAProtection", &a2[6].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[6].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RealTimeScanDirection", &a2[6].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[6].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScanParameter", &a2[6].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[6].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleQuickScanTime", a2[6].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[6].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleScanDay", &a2[6].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[6].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleScanTime", &a2[6].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[7].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SecurityIntelligenceLocation", &a2[6].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[7].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SignatureUpdateFallbackOrder", &a2[7].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[7].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SignatureUpdateFileSharesSources", &a2[7].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[7].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SignatureUpdateInterval", &a2[7].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[7].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SubmitSamplesConsent", &a2[7].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[8].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ThreatSeverityDefaultAction", &a2[7].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_197;
      goto LABEL_192;
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_197;
      goto LABEL_192;
    }
    inserted = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Defender02_rtti, &instance);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_197;
      goto LABEL_192;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v8 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_197:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "CreateInstanceEnd", inserted);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180361559,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18007a1bc  mov     [rsp+arg_10], rsi
0x18007a1c1  mov     [rsp+arg_18], rdi
0x18007a1c6  push    r12
0x18007a1c8  push    r14
0x18007a1ca  push    r15
0x18007a1cc  sub     rsp, 2D0h
0x18007a1d3  mov     rax, cs:__security_cookie
0x18007a1da  xor     rax, rsp
0x18007a1dd  mov     [rsp+2E8h+var_28], rax
0x18007a1e5  mov     rsi, rdx
0x18007a1e8  mov     r15, rcx
0x18007a1eb  xor     edx, edx; Val
0x18007a1ed  mov     r8d, 208h; Size
0x18007a1f3  lea     rcx, [rsp+2E8h+instance]; void *
0x18007a1fb  call    memset_0
0x18007a200  mov     [rsp+2E8h+var_268], 0
0x18007a20b  mov     [rsp+2E8h+var_264], 0
0x18007a213  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18007a21a  mov     [rsp+2E8h+var_298], rax
0x18007a21f  lea     rax, [rsp+2E8h+var_268]
0x18007a227  mov     [rsp+2E8h+var_290], rax
0x18007a22c  lea     rax, aMdmPolicyConfi_40; "MDM_Policy_Config01_Defender02"
0x18007a233  mov     [rsp+2E8h+var_288], rax
0x18007a238  lea     rcx, [rsp+2E8h+var_268]
0x18007a240  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007a245  mov     eax, cs:dword_180380B68
0x18007a24b  cmp     eax, 5
0x18007a24e  jbe     short loc_18007A2C4
0x18007a250  mov     rdx, 200000000000h
0x18007a25a  lea     rcx, dword_180380B68
0x18007a261  call    _tlgKeywordOn
0x18007a266  test    al, al
0x18007a268  jz      short loc_18007A2C4
0x18007a26a  cmp     [rsp+2E8h+var_264], 0
0x18007a272  jz      short loc_18007A2A6
0x18007a274  cmp     [rsp+2E8h+var_250], 0
0x18007a27c  jnz     short loc_18007A29C
0x18007a27e  cmp     [rsp+2E8h+var_24C], 0
0x18007a286  jnz     short loc_18007A29C
0x18007a288  cmp     [rsp+2E8h+var_248], 0
0x18007a290  jnz     short loc_18007A29C
0x18007a292  cmp     [rsp+2E8h+var_244], 0
0x18007a29a  jz      short loc_18007A2A6
0x18007a29c  lea     r9, [rsp+2E8h+var_250]
0x18007a2a4  jmp     short loc_18007A2A9
0x18007a2a6  xor     r9d, r9d
0x18007a2a9  lea     r8, [rsp+2E8h+var_260]
0x18007a2b1  lea     rdx, unk_18035D878
0x18007a2b8  lea     rcx, dword_180380B68
0x18007a2bf  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007a2c4  cmp     byte ptr [rsi+48h], 0
0x18007a2c8  jz      loc_18007AEFA
0x18007a2ce  mov     [rsp+2E8h+var_2A0], 0
0x18007a2d3  cmp     byte ptr [rsi+58h], 0
0x18007a2d7  jz      loc_18007AEFA
0x18007a2dd  mov     r9, [rsi+40h]; unsigned __int16 *
0x18007a2e1  mov     r8, [rsi+50h]; unsigned __int16 *
0x18007a2e5  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x18007a2ec  lea     rcx, [rsp+2E8h+var_298]; this
0x18007a2f1  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18007a2f6  nop
0x18007a2f7  mov     [rsp+2E8h+var_2A8], 0
0x18007a300  lea     rax, [rsp+2E8h+var_2A8]
0x18007a305  mov     [rsp+2E8h+var_2B8], rax
0x18007a30a  mov     [rsp+2E8h+var_2C0], 4
0x18007a312  mov     [rsp+2E8h+var_2C8], 2Ch ; ','
0x18007a31a  lea     r9, ?MDM_Policy_Config01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Defender02_NodeList
0x18007a321  mov     r8, [rsi+40h]
0x18007a325  mov     rdx, [rsi+50h]
0x18007a329  mov     rcx, r15
0x18007a32c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18007a331  mov     edi, eax
0x18007a333  test    eax, eax
0x18007a335  jz      short loc_18007A33C
0x18007a337  jmp     loc_18007AEFF
0x18007a33c  lea     rax, [rsp+2E8h+var_2A8]
0x18007a341  mov     [rsp+2E8h+var_278], rax
0x18007a346  mov     r12d, 1
0x18007a34c  mov     [rsp+2E8h+var_270], r12b
0x18007a351  mov     r14, [rsp+2E8h+var_2A8]
0x18007a356  test    r14, r14
0x18007a359  jnz     short loc_18007A363
0x18007a35b  mov     edi, r12d
0x18007a35e  jmp     loc_18007AEFF
0x18007a363  mov     r9d, 2Ch ; ','; unsigned int
0x18007a369  lea     r8, ?MDM_Policy_Config01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18007a370  mov     rdx, rsi; struct _MI_Instance *
0x18007a373  mov     rcx, r14; this
0x18007a376  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18007a37b  lea     r8, [rsi+60h]; void *
0x18007a37f  cmp     [r8+4], r12b
0x18007a383  jnz     short loc_18007A3B8
0x18007a385  lea     rdx, aAllowarchivesc; "AllowArchiveScanning"
0x18007a38c  mov     rcx, r14; this
0x18007a38f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007a394  mov     edi, eax
0x18007a396  test    eax, eax
0x18007a398  jz      short loc_18007A3B8
0x18007a39a  mov     rcx, [rsp+2E8h+var_2A8]
0x18007a39f  test    rcx, rcx
0x18007a3a2  jz      short loc_18007A3B3
0x18007a3a4  mov     rax, [rcx]
0x18007a3a7  mov     edx, r12d
0x18007a3aa  mov     rax, [rax]
0x18007a3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a3b2  nop
0x18007a3b3  jmp     loc_18007AEFF
0x18007a3b8  lea     r8, [rsi+68h]; void *
0x18007a3bc  cmp     [r8+4], r12b
0x18007a3c0  jnz     short loc_18007A3F5
0x18007a3c2  lea     rdx, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x18007a3c9  mov     rcx, r14; this
0x18007a3cc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007a3d1  mov     edi, eax
0x18007a3d3  test    eax, eax
0x18007a3d5  jz      short loc_18007A3F5
0x18007a3d7  mov     rcx, [rsp+2E8h+var_2A8]
0x18007a3dc  test    rcx, rcx
0x18007a3df  jz      short loc_18007A3F0
0x18007a3e1  mov     rax, [rcx]
0x18007a3e4  mov     edx, r12d
0x18007a3e7  mov     rax, [rax]
0x18007a3ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a3ef  nop
0x18007a3f0  jmp     loc_18007AEFF
0x18007a3f5  lea     r8, [rsi+70h]; void *
0x18007a3f9  cmp     [r8+4], r12b
0x18007a3fd  jnz     short loc_18007A432
0x18007a3ff  lea     rdx, aAllowcloudprot; "AllowCloudProtection"
0x18007a406  mov     rcx, r14; this
0x18007a409  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007a40e  mov     edi, eax
0x18007a410  test    eax, eax
0x18007a412  jz      short loc_18007A432
0x18007a414  mov     rcx, [rsp+2E8h+var_2A8]
0x18007a419  test    rcx, rcx
0x18007a41c  jz      short loc_18007A42D
0x18007a41e  mov     rax, [rcx]
0x18007a421  mov     edx, r12d
0x18007a424  mov     rax, [rax]
0x18007a427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a42c  nop
0x18007a42d  jmp     loc_18007AEFF
0x18007a432  lea     r8, [rsi+78h]; void *
0x18007a436  cmp     [r8+4], r12b
0x18007a43a  jnz     short loc_18007A46F
0x18007a43c  lea     rdx, aAllowemailscan; "AllowEmailScanning"
0x18007a443  mov     rcx, r14; this
0x18007a446  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007a44b  mov     edi, eax
0x18007a44d  test    eax, eax
0x18007a44f  jz      short loc_18007A46F
0x18007a451  mov     rcx, [rsp+2E8h+var_2A8]
0x18007a456  test    rcx, rcx
0x18007a459  jz      short loc_18007A46A
0x18007a45b  mov     rax, [rcx]
0x18007a45e  mov     edx, r12d
0x18007a461  mov     rax, [rax]
0x18007a464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a469  nop
0x18007a46a  jmp     loc_18007AEFF
0x18007a46f  lea     r8, [rsi+80h]; void *
0x18007a476  cmp     [r8+4], r12b
0x18007a47a  jnz     short loc_18007A4AF
0x18007a47c  lea     rdx, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x18007a483  mov     rcx, r14; this
0x18007a486  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007a48b  mov     edi, eax
0x18007a48d  test    eax, eax
0x18007a48f  jz      short loc_18007A4AF
0x18007a491  mov     rcx, [rsp+2E8h+var_2A8]
0x18007a496  test    rcx, rcx
0x18007a499  jz      short loc_18007A4AA
0x18007a49b  mov     rax, [rcx]
0x18007a49e  mov     edx, r12d
0x18007a4a1  mov     rax, [rax]
0x18007a4a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a4a9  nop
0x18007a4aa  jmp     loc_18007AEFF
0x18007a4af  lea     r8, [rsi+88h]; void *
0x18007a4b6  cmp     [r8+4], r12b
0x18007a4ba  jnz     short loc_18007A4EF
0x18007a4bc  lea     rdx, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x18007a4c3  mov     rcx, r14; this
0x18007a4c6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007a4cb  mov     edi, eax
0x18007a4cd  test    eax, eax
0x18007a4cf  jz      short loc_18007A4EF
0x18007a4d1  mov     rcx, [rsp+2E8h+var_2A8]
0x18007a4d6  test    rcx, rcx
0x18007a4d9  jz      short loc_18007A4EA
0x18007a4db  mov     rax, [rcx]
0x18007a4de  mov     edx, r12d
0x18007a4e1  mov     rax, [rax]
0x18007a4e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a4e9  nop
0x18007a4ea  jmp     loc_18007AEFF
0x18007a4ef  lea     r8, [rsi+90h]; void *
0x18007a4f6  cmp     [r8+4], r12b
0x18007a4fa  jnz     short loc_18007A52F
0x18007a4fc  lea     rdx, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x18007a503  mov     rcx, r14; this
0x18007a506  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007a50b  mov     edi, eax
0x18007a50d  test    eax, eax
0x18007a50f  jz      short loc_18007A52F
0x18007a511  mov     rcx, [rsp+2E8h+var_2A8]
0x18007a516  test    rcx, rcx
0x18007a519  jz      short loc_18007A52A
0x18007a51b  mov     rax, [rcx]
0x18007a51e  mov     edx, r12d
0x18007a521  mov     rax, [rax]
0x18007a524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a529  nop
0x18007a52a  jmp     loc_18007AEFF
0x18007a52f  lea     r8, [rsi+98h]; void *
0x18007a536  cmp     [r8+4], r12b
0x18007a53a  jnz     short loc_18007A56F
0x18007a53c  lea     rdx, aAllowioavprote; "AllowIOAVProtection"
0x18007a543  mov     rcx, r14; this
0x18007a546  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007a54b  mov     edi, eax
0x18007a54d  test    eax, eax
0x18007a54f  jz      short loc_18007A56F
0x18007a551  mov     rcx, [rsp+2E8h+var_2A8]
0x18007a556  test    rcx, rcx
0x18007a559  jz      short loc_18007A56A
0x18007a55b  mov     rax, [rcx]
0x18007a55e  mov     edx, r12d
0x18007a561  mov     rax, [rax]
0x18007a564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a569  nop
0x18007a56a  jmp     loc_18007AEFF
0x18007a56f  lea     r8, [rsi+0A0h]; void *
0x18007a576  cmp     [r8+4], r12b
0x18007a57a  jnz     short loc_18007A5AF
0x18007a57c  lea     rdx, aAllowonaccessp; "AllowOnAccessProtection"
0x18007a583  mov     rcx, r14; this
0x18007a586  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007a58b  mov     edi, eax
0x18007a58d  test    eax, eax
0x18007a58f  jz      short loc_18007A5AF
0x18007a591  mov     rcx, [rsp+2E8h+var_2A8]
0x18007a596  test    rcx, rcx
0x18007a599  jz      short loc_18007A5AA
0x18007a59b  mov     rax, [rcx]
0x18007a59e  mov     edx, r12d
0x18007a5a1  mov     rax, [rax]
0x18007a5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a5a9  nop
0x18007a5aa  jmp     loc_18007AEFF
0x18007a5af  lea     r8, [rsi+0A8h]; void *
0x18007a5b6  cmp     [r8+4], r12b
0x18007a5ba  jnz     short loc_18007A5EF
0x18007a5bc  lea     rdx, aAllowrealtimem; "AllowRealtimeMonitoring"
0x18007a5c3  mov     rcx, r14; this
0x18007a5c6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007a5cb  mov     edi, eax
0x18007a5cd  test    eax, eax
0x18007a5cf  jz      short loc_18007A5EF
0x18007a5d1  mov     rcx, [rsp+2E8h+var_2A8]
0x18007a5d6  test    rcx, rcx
0x18007a5d9  jz      short loc_18007A5EA
0x18007a5db  mov     rax, [rcx]
0x18007a5de  mov     edx, r12d
0x18007a5e1  mov     rax, [rax]
0x18007a5e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a5e9  nop
0x18007a5ea  jmp     loc_18007AEFF
0x18007a5ef  lea     r8, [rsi+0B0h]; void *
0x18007a5f6  cmp     [r8+4], r12b
0x18007a5fa  jnz     short loc_18007A62F
0x18007a5fc  lea     rdx, aAllowscanningn; "AllowScanningNetworkFiles"
0x18007a603  mov     rcx, r14; this
0x18007a606  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007a60b  mov     edi, eax
0x18007a60d  test    eax, eax
0x18007a60f  jz      short loc_18007A62F
0x18007a611  mov     rcx, [rsp+2E8h+var_2A8]
0x18007a616  test    rcx, rcx
0x18007a619  jz      short loc_18007A62A
0x18007a61b  mov     rax, [rcx]
0x18007a61e  mov     edx, r12d
0x18007a621  mov     rax, [rax]
0x18007a624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a629  nop
0x18007a62a  jmp     loc_18007AEFF
0x18007a62f  lea     r8, [rsi+0B8h]; void *
0x18007a636  cmp     [r8+4], r12b
0x18007a63a  jnz     short loc_18007A66F
0x18007a63c  lea     rdx, aAllowscriptsca; "AllowScriptScanning"
0x18007a643  mov     rcx, r14; this
0x18007a646  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007a64b  mov     edi, eax
0x18007a64d  test    eax, eax
0x18007a64f  jz      short loc_18007A66F
0x18007a651  mov     rcx, [rsp+2E8h+var_2A8]
0x18007a656  test    rcx, rcx
0x18007a659  jz      short loc_18007A66A
0x18007a65b  mov     rax, [rcx]
  ... truncated ...
```
