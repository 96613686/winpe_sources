# MDM_Policy_Config01_Defender02_InvokeCreateInstance

- ea: `0x18007aa2c`
- end: `0x18007b80b`
- name: `MDM_Policy_Config01_Defender02_InvokeCreateInstance`
- size: `3551`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007a930`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18007aa2c`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x18007adec`: `AllowOnAccessProtection`
- `0x18007aeec`: `AllowUserUIAccess`
- `0x18007b0ac`: `ControlledFolderAccessAllowedApplications`
- `0x18007b0ec`: `ControlledFolderAccessProtectedFolders`
- `0x18007b1ec`: `EnableControlledFolderAccess`
- `0x18007b2ac`: `ExcludedExtensions`
- `0x18007b2ec`: `ExcludedPaths`
- `0x18007b4ec`: `SecurityIntelligenceLocation`
- `0x18007b52c`: `SignatureUpdateFallbackOrder`
- `0x18007b56c`: `SignatureUpdateFileSharesSources`
- `0x18007b5ac`: `SignatureUpdateInterval`
- `0x18007ab55`: `CreateInstanceStart`
- `0x18007b772`: `CreateInstanceEnd`
- `0x18007aa9c`: `MDM_Policy_Config01_Defender02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Defender02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
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
    inserted = 4;
    goto LABEL_197;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v10,
    "CreateInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v8 = 0;
  inserted = CreateRequestHandlerInstance(
               (__int64)self,
               (wchar_t *)a2[1].serverName,
               (const unsigned __int16 *)a2[1].ft,
               (struct WmiNodeInfo *)&MDM_Policy_Config01_Defender02_NodeList,
               0x2Cu,
               4,
               &v8);
  if ( !inserted )
  {
    v10[4] = &v8;
    v11 = 1;
    v6 = v8;
    if ( !v8 )
    {
      inserted = 1;
      goto LABEL_197;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v8,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_Defender02_NodeList,
      0x2Cu);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowArchiveScanning", (LONG *)a2[1].reserved);
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
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowBehaviorMonitoring", (LONG *)&a2[1].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[1].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowCloudProtection", (LONG *)&a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowEmailScanning", (LONG *)&a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFullScanOnMappedNetworkDrives", (LONG *)&a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AllowFullScanRemovableDriveScanning",
                   (LONG *)&a2[2].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AllowIntrusionPreventionSystem",
                   (LONG *)&a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowIOAVProtection", (LONG *)&a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowOnAccessProtection", (LONG *)a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowRealtimeMonitoring", (LONG *)&a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowScanningNetworkFiles", (LONG *)&a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowScriptScanning", (LONG *)&a2[2].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowUserUIAccess", (LONG *)&a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[3].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AttackSurfaceReductionOnlyExclusions",
                   (LONG *)&a2[3].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[3].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AttackSurfaceReductionRules", (LONG *)&a2[3].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[3].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AvgCPULoadFactor", (LONG *)&a2[3].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[3].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"CheckForSignaturesBeforeRunningScan",
                   (LONG *)&a2[3].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[3].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CloudBlockLevel", (LONG *)&a2[3].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CloudExtendedTimeout", (LONG *)&a2[4]);
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
                   (LONG *)&a2[4].classDecl);
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
                   (LONG *)&a2[4].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[4].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DaysToRetainCleanedMalware", (LONG *)&a2[4].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[4].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableCatchupFullScan", (LONG *)&a2[4].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableCatchupQuickScan", (LONG *)&a2[4].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[5].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableControlledFolderAccess", (LONG *)&a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableLowCPUPriority", (LONG *)&a2[5].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[5].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableNetworkProtection", (LONG *)&a2[5].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[5].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedExtensions", (LONG *)&a2[5].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[5].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedPaths", (LONG *)&a2[5].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[6].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedProcesses", (LONG *)&a2[5].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[6].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PUAProtection", (LONG *)&a2[6].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[6].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RealTimeScanDirection", (LONG *)&a2[6].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[6].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScanParameter", (LONG *)&a2[6].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[6].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleQuickScanTime", (LONG *)a2[6].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[6].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleScanDay", (LONG *)&a2[6].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[6].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScheduleScanTime", (LONG *)&a2[6].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[7].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"SecurityIntelligenceLocation",
                   (LONG *)&a2[6].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[7].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SignatureUpdateFallbackOrder", (LONG *)&a2[7].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[7].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"SignatureUpdateFileSharesSources",
                   (LONG *)&a2[7].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[7].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SignatureUpdateInterval", (LONG *)&a2[7].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( BYTE4(a2[7].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SubmitSamplesConsent", (LONG *)&a2[7].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    if ( LOBYTE(a2[8].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ThreatSeverityDefaultAction", (LONG *)&a2[7].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_197;
        goto LABEL_192;
      }
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_197;
      goto LABEL_192;
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
  return inserted;
}

```

## disassembly

```asm
0x18007aa2c  mov     [rsp+arg_10], rsi
0x18007aa31  mov     [rsp+arg_18], rdi
0x18007aa36  push    r12
0x18007aa38  push    r14
0x18007aa3a  push    r15
0x18007aa3c  sub     rsp, 2D0h
0x18007aa43  mov     rax, cs:__security_cookie
0x18007aa4a  xor     rax, rsp
0x18007aa4d  mov     [rsp+2E8h+var_28], rax
0x18007aa55  mov     rsi, rdx
0x18007aa58  mov     r15, rcx
0x18007aa5b  xor     edx, edx; Val
0x18007aa5d  mov     r8d, 208h; Size
0x18007aa63  lea     rcx, [rsp+2E8h+instance]; void *
0x18007aa6b  call    memset_0
0x18007aa70  mov     [rsp+2E8h+var_268], 0
0x18007aa7b  mov     [rsp+2E8h+var_264], 0
0x18007aa83  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18007aa8a  mov     [rsp+2E8h+var_298], rax
0x18007aa8f  lea     rax, [rsp+2E8h+var_268]
0x18007aa97  mov     [rsp+2E8h+var_290], rax
0x18007aa9c  lea     rax, aMdmPolicyConfi_40; "MDM_Policy_Config01_Defender02"
0x18007aaa3  mov     [rsp+2E8h+var_288], rax
0x18007aaa8  lea     rcx, [rsp+2E8h+var_268]
0x18007aab0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007aab5  mov     eax, cs:dword_180380B68
0x18007aabb  cmp     eax, 5
0x18007aabe  jbe     short loc_18007AB34
0x18007aac0  mov     rdx, 200000000000h
0x18007aaca  lea     rcx, dword_180380B68
0x18007aad1  call    _tlgKeywordOn
0x18007aad6  test    al, al
0x18007aad8  jz      short loc_18007AB34
0x18007aada  cmp     [rsp+2E8h+var_264], 0
0x18007aae2  jz      short loc_18007AB16
0x18007aae4  cmp     [rsp+2E8h+var_250], 0
0x18007aaec  jnz     short loc_18007AB0C
0x18007aaee  cmp     [rsp+2E8h+var_24C], 0
0x18007aaf6  jnz     short loc_18007AB0C
0x18007aaf8  cmp     [rsp+2E8h+var_248], 0
0x18007ab00  jnz     short loc_18007AB0C
0x18007ab02  cmp     [rsp+2E8h+var_244], 0
0x18007ab0a  jz      short loc_18007AB16
0x18007ab0c  lea     r9, [rsp+2E8h+var_250]
0x18007ab14  jmp     short loc_18007AB19
0x18007ab16  xor     r9d, r9d
0x18007ab19  lea     r8, [rsp+2E8h+var_260]
0x18007ab21  lea     rdx, unk_18035D878
0x18007ab28  lea     rcx, dword_180380B68
0x18007ab2f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007ab34  cmp     byte ptr [rsi+48h], 0
0x18007ab38  jz      loc_18007B76A
0x18007ab3e  mov     [rsp+2E8h+var_2A0], 0
0x18007ab43  cmp     byte ptr [rsi+58h], 0
0x18007ab47  jz      loc_18007B76A
0x18007ab4d  mov     r9, [rsi+40h]; unsigned __int16 *
0x18007ab51  mov     r8, [rsi+50h]; unsigned __int16 *
0x18007ab55  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x18007ab5c  lea     rcx, [rsp+2E8h+var_298]; this
0x18007ab61  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18007ab66  nop
0x18007ab67  mov     [rsp+2E8h+var_2A8], 0
0x18007ab70  lea     rax, [rsp+2E8h+var_2A8]
0x18007ab75  mov     [rsp+2E8h+var_2B8], rax
0x18007ab7a  mov     [rsp+2E8h+var_2C0], 4
0x18007ab82  mov     [rsp+2E8h+var_2C8], 2Ch ; ','
0x18007ab8a  lea     r9, ?MDM_Policy_Config01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Defender02_NodeList
0x18007ab91  mov     r8, [rsi+40h]
0x18007ab95  mov     rdx, [rsi+50h]
0x18007ab99  mov     rcx, r15
0x18007ab9c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18007aba1  mov     edi, eax
0x18007aba3  test    eax, eax
0x18007aba5  jz      short loc_18007ABAC
0x18007aba7  jmp     loc_18007B76F
0x18007abac  lea     rax, [rsp+2E8h+var_2A8]
0x18007abb1  mov     [rsp+2E8h+var_278], rax
0x18007abb6  mov     r12d, 1
0x18007abbc  mov     [rsp+2E8h+var_270], r12b
0x18007abc1  mov     r14, [rsp+2E8h+var_2A8]
0x18007abc6  test    r14, r14
0x18007abc9  jnz     short loc_18007ABD3
0x18007abcb  mov     edi, r12d
0x18007abce  jmp     loc_18007B76F
0x18007abd3  mov     r9d, 2Ch ; ','; unsigned int
0x18007abd9  lea     r8, ?MDM_Policy_Config01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18007abe0  mov     rdx, rsi; struct _MI_Instance *
0x18007abe3  mov     rcx, r14; this
0x18007abe6  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18007abeb  lea     r8, [rsi+60h]; void *
0x18007abef  cmp     [r8+4], r12b
0x18007abf3  jnz     short loc_18007AC28
0x18007abf5  lea     rdx, aAllowarchivesc; "AllowArchiveScanning"
0x18007abfc  mov     rcx, r14; this
0x18007abff  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007ac04  mov     edi, eax
0x18007ac06  test    eax, eax
0x18007ac08  jz      short loc_18007AC28
0x18007ac0a  mov     rcx, [rsp+2E8h+var_2A8]
0x18007ac0f  test    rcx, rcx
0x18007ac12  jz      short loc_18007AC23
0x18007ac14  mov     rax, [rcx]
0x18007ac17  mov     edx, r12d
0x18007ac1a  mov     rax, [rax]
0x18007ac1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ac22  nop
0x18007ac23  jmp     loc_18007B76F
0x18007ac28  lea     r8, [rsi+68h]; void *
0x18007ac2c  cmp     [r8+4], r12b
0x18007ac30  jnz     short loc_18007AC65
0x18007ac32  lea     rdx, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x18007ac39  mov     rcx, r14; this
0x18007ac3c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007ac41  mov     edi, eax
0x18007ac43  test    eax, eax
0x18007ac45  jz      short loc_18007AC65
0x18007ac47  mov     rcx, [rsp+2E8h+var_2A8]
0x18007ac4c  test    rcx, rcx
0x18007ac4f  jz      short loc_18007AC60
0x18007ac51  mov     rax, [rcx]
0x18007ac54  mov     edx, r12d
0x18007ac57  mov     rax, [rax]
0x18007ac5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ac5f  nop
0x18007ac60  jmp     loc_18007B76F
0x18007ac65  lea     r8, [rsi+70h]; void *
0x18007ac69  cmp     [r8+4], r12b
0x18007ac6d  jnz     short loc_18007ACA2
0x18007ac6f  lea     rdx, aAllowcloudprot; "AllowCloudProtection"
0x18007ac76  mov     rcx, r14; this
0x18007ac79  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007ac7e  mov     edi, eax
0x18007ac80  test    eax, eax
0x18007ac82  jz      short loc_18007ACA2
0x18007ac84  mov     rcx, [rsp+2E8h+var_2A8]
0x18007ac89  test    rcx, rcx
0x18007ac8c  jz      short loc_18007AC9D
0x18007ac8e  mov     rax, [rcx]
0x18007ac91  mov     edx, r12d
0x18007ac94  mov     rax, [rax]
0x18007ac97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ac9c  nop
0x18007ac9d  jmp     loc_18007B76F
0x18007aca2  lea     r8, [rsi+78h]; void *
0x18007aca6  cmp     [r8+4], r12b
0x18007acaa  jnz     short loc_18007ACDF
0x18007acac  lea     rdx, aAllowemailscan; "AllowEmailScanning"
0x18007acb3  mov     rcx, r14; this
0x18007acb6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007acbb  mov     edi, eax
0x18007acbd  test    eax, eax
0x18007acbf  jz      short loc_18007ACDF
0x18007acc1  mov     rcx, [rsp+2E8h+var_2A8]
0x18007acc6  test    rcx, rcx
0x18007acc9  jz      short loc_18007ACDA
0x18007accb  mov     rax, [rcx]
0x18007acce  mov     edx, r12d
0x18007acd1  mov     rax, [rax]
0x18007acd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007acd9  nop
0x18007acda  jmp     loc_18007B76F
0x18007acdf  lea     r8, [rsi+80h]; void *
0x18007ace6  cmp     [r8+4], r12b
0x18007acea  jnz     short loc_18007AD1F
0x18007acec  lea     rdx, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x18007acf3  mov     rcx, r14; this
0x18007acf6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007acfb  mov     edi, eax
0x18007acfd  test    eax, eax
0x18007acff  jz      short loc_18007AD1F
0x18007ad01  mov     rcx, [rsp+2E8h+var_2A8]
0x18007ad06  test    rcx, rcx
0x18007ad09  jz      short loc_18007AD1A
0x18007ad0b  mov     rax, [rcx]
0x18007ad0e  mov     edx, r12d
0x18007ad11  mov     rax, [rax]
0x18007ad14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ad19  nop
0x18007ad1a  jmp     loc_18007B76F
0x18007ad1f  lea     r8, [rsi+88h]; void *
0x18007ad26  cmp     [r8+4], r12b
0x18007ad2a  jnz     short loc_18007AD5F
0x18007ad2c  lea     rdx, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x18007ad33  mov     rcx, r14; this
0x18007ad36  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007ad3b  mov     edi, eax
0x18007ad3d  test    eax, eax
0x18007ad3f  jz      short loc_18007AD5F
0x18007ad41  mov     rcx, [rsp+2E8h+var_2A8]
0x18007ad46  test    rcx, rcx
0x18007ad49  jz      short loc_18007AD5A
0x18007ad4b  mov     rax, [rcx]
0x18007ad4e  mov     edx, r12d
0x18007ad51  mov     rax, [rax]
0x18007ad54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ad59  nop
0x18007ad5a  jmp     loc_18007B76F
0x18007ad5f  lea     r8, [rsi+90h]; void *
0x18007ad66  cmp     [r8+4], r12b
0x18007ad6a  jnz     short loc_18007AD9F
0x18007ad6c  lea     rdx, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x18007ad73  mov     rcx, r14; this
0x18007ad76  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007ad7b  mov     edi, eax
0x18007ad7d  test    eax, eax
0x18007ad7f  jz      short loc_18007AD9F
0x18007ad81  mov     rcx, [rsp+2E8h+var_2A8]
0x18007ad86  test    rcx, rcx
0x18007ad89  jz      short loc_18007AD9A
0x18007ad8b  mov     rax, [rcx]
0x18007ad8e  mov     edx, r12d
0x18007ad91  mov     rax, [rax]
0x18007ad94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ad99  nop
0x18007ad9a  jmp     loc_18007B76F
0x18007ad9f  lea     r8, [rsi+98h]; void *
0x18007ada6  cmp     [r8+4], r12b
0x18007adaa  jnz     short loc_18007ADDF
0x18007adac  lea     rdx, aAllowioavprote; "AllowIOAVProtection"
0x18007adb3  mov     rcx, r14; this
0x18007adb6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007adbb  mov     edi, eax
0x18007adbd  test    eax, eax
0x18007adbf  jz      short loc_18007ADDF
0x18007adc1  mov     rcx, [rsp+2E8h+var_2A8]
0x18007adc6  test    rcx, rcx
0x18007adc9  jz      short loc_18007ADDA
0x18007adcb  mov     rax, [rcx]
0x18007adce  mov     edx, r12d
0x18007add1  mov     rax, [rax]
0x18007add4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007add9  nop
0x18007adda  jmp     loc_18007B76F
0x18007addf  lea     r8, [rsi+0A0h]; void *
0x18007ade6  cmp     [r8+4], r12b
0x18007adea  jnz     short loc_18007AE1F
0x18007adec  lea     rdx, aAllowonaccessp; "AllowOnAccessProtection"
0x18007adf3  mov     rcx, r14; this
0x18007adf6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007adfb  mov     edi, eax
0x18007adfd  test    eax, eax
0x18007adff  jz      short loc_18007AE1F
0x18007ae01  mov     rcx, [rsp+2E8h+var_2A8]
0x18007ae06  test    rcx, rcx
0x18007ae09  jz      short loc_18007AE1A
0x18007ae0b  mov     rax, [rcx]
0x18007ae0e  mov     edx, r12d
0x18007ae11  mov     rax, [rax]
0x18007ae14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ae19  nop
0x18007ae1a  jmp     loc_18007B76F
0x18007ae1f  lea     r8, [rsi+0A8h]; void *
0x18007ae26  cmp     [r8+4], r12b
0x18007ae2a  jnz     short loc_18007AE5F
0x18007ae2c  lea     rdx, aAllowrealtimem; "AllowRealtimeMonitoring"
0x18007ae33  mov     rcx, r14; this
0x18007ae36  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007ae3b  mov     edi, eax
0x18007ae3d  test    eax, eax
0x18007ae3f  jz      short loc_18007AE5F
0x18007ae41  mov     rcx, [rsp+2E8h+var_2A8]
0x18007ae46  test    rcx, rcx
0x18007ae49  jz      short loc_18007AE5A
0x18007ae4b  mov     rax, [rcx]
0x18007ae4e  mov     edx, r12d
0x18007ae51  mov     rax, [rax]
0x18007ae54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ae59  nop
0x18007ae5a  jmp     loc_18007B76F
0x18007ae5f  lea     r8, [rsi+0B0h]; void *
0x18007ae66  cmp     [r8+4], r12b
0x18007ae6a  jnz     short loc_18007AE9F
0x18007ae6c  lea     rdx, aAllowscanningn; "AllowScanningNetworkFiles"
0x18007ae73  mov     rcx, r14; this
0x18007ae76  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007ae7b  mov     edi, eax
0x18007ae7d  test    eax, eax
0x18007ae7f  jz      short loc_18007AE9F
0x18007ae81  mov     rcx, [rsp+2E8h+var_2A8]
0x18007ae86  test    rcx, rcx
0x18007ae89  jz      short loc_18007AE9A
0x18007ae8b  mov     rax, [rcx]
0x18007ae8e  mov     edx, r12d
0x18007ae91  mov     rax, [rax]
0x18007ae94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ae99  nop
0x18007ae9a  jmp     loc_18007B76F
0x18007ae9f  lea     r8, [rsi+0B8h]; void *
0x18007aea6  cmp     [r8+4], r12b
0x18007aeaa  jnz     short loc_18007AEDF
0x18007aeac  lea     rdx, aAllowscriptsca; "AllowScriptScanning"
0x18007aeb3  mov     rcx, r14; this
0x18007aeb6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007aebb  mov     edi, eax
0x18007aebd  test    eax, eax
0x18007aebf  jz      short loc_18007AEDF
0x18007aec1  mov     rcx, [rsp+2E8h+var_2A8]
0x18007aec6  test    rcx, rcx
0x18007aec9  jz      short loc_18007AEDA
0x18007aecb  mov     rax, [rcx]
  ... truncated ...
```
