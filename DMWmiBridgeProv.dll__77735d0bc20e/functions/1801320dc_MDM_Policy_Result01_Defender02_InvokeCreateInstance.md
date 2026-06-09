# MDM_Policy_Result01_Defender02_InvokeCreateInstance

- ea: `0x1801320dc`
- end: `0x180132ebb`
- name: `MDM_Policy_Result01_Defender02_InvokeCreateInstance`
- size: `3551`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180131fe0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1801320dc`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x18013249c`: `AllowOnAccessProtection`
- `0x18013259c`: `AllowUserUIAccess`
- `0x18013275c`: `ControlledFolderAccessAllowedApplications`
- `0x18013279c`: `ControlledFolderAccessProtectedFolders`
- `0x18013289c`: `EnableControlledFolderAccess`
- `0x18013295c`: `ExcludedExtensions`
- `0x18013299c`: `ExcludedPaths`
- `0x180132b9c`: `SecurityIntelligenceLocation`
- `0x180132bdc`: `SignatureUpdateFallbackOrder`
- `0x180132c1c`: `SignatureUpdateFileSharesSources`
- `0x180132c5c`: `SignatureUpdateInterval`
- `0x180132205`: `CreateInstanceStart`
- `0x180132e22`: `CreateInstanceEnd`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Defender02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
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
    inserted = CreateRequestHandlerInstance(
                 (__int64)self,
                 (wchar_t *)a2[1].serverName,
                 (const unsigned __int16 *)a2[1].ft,
                 (struct WmiNodeInfo *)&MDM_Policy_Result01_Defender02_NodeList,
                 0x2Cu,
                 4,
                 &v8);
    if ( !inserted )
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
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowArchiveScanning", (LONG *)a2[1].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowBehaviorMonitoring",
                                (LONG *)&a2[1].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowCloudProtection",
                                (LONG *)&a2[1].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowEmailScanning",
                                (LONG *)&a2[1].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowFullScanOnMappedNetworkDrives",
                                (LONG *)&a2[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowFullScanRemovableDriveScanning",
                                (LONG *)&a2[2].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowIntrusionPreventionSystem",
                                (LONG *)&a2[2].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowIOAVProtection",
                                (LONG *)&a2[2].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowOnAccessProtection",
                                (LONG *)a2[2].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowRealtimeMonitoring",
                                (LONG *)&a2[2].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowScanningNetworkFiles",
                                (LONG *)&a2[2].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowScriptScanning",
                                (LONG *)&a2[2].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowUserUIAccess", (LONG *)&a2[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[3].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AttackSurfaceReductionOnlyExclusions",
                                (LONG *)&a2[3].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[3].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AttackSurfaceReductionRules",
                                (LONG *)&a2[3].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AvgCPULoadFactor",
                                (LONG *)&a2[3].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"CheckForSignaturesBeforeRunningScan",
                                (LONG *)&a2[3].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"CloudBlockLevel",
                                (LONG *)&a2[3].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CloudExtendedTimeout", (LONG *)&a2[4])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ControlledFolderAccessAllowedApplications",
                                (LONG *)&a2[4].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ControlledFolderAccessProtectedFolders",
                                (LONG *)&a2[4].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DaysToRetainCleanedMalware",
                                (LONG *)&a2[4].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DisableCatchupFullScan",
                                (LONG *)&a2[4].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DisableCatchupQuickScan",
                                (LONG *)&a2[4].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableControlledFolderAccess",
                                (LONG *)&a2[5])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableLowCPUPriority",
                                (LONG *)&a2[5].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableNetworkProtection",
                                (LONG *)&a2[5].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ExcludedExtensions",
                                (LONG *)&a2[5].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ExcludedPaths", (LONG *)&a2[5].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ExcludedProcesses",
                                (LONG *)&a2[5].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PUAProtection", (LONG *)&a2[6].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"RealTimeScanDirection",
                                (LONG *)&a2[6].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ScanParameter", (LONG *)&a2[6].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ScheduleQuickScanTime",
                                (LONG *)a2[6].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ScheduleScanDay",
                                (LONG *)&a2[6].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ScheduleScanTime",
                                (LONG *)&a2[6].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SecurityIntelligenceLocation",
                                (LONG *)&a2[6].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SignatureUpdateFallbackOrder",
                                (LONG *)&a2[7].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SignatureUpdateFileSharesSources",
                                (LONG *)&a2[7].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SignatureUpdateInterval",
                                (LONG *)&a2[7].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SubmitSamplesConsent",
                                (LONG *)&a2[7].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ThreatSeverityDefaultAction",
                                (LONG *)&a2[7].reserved[3])) != 0 )
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
        inserted = 1;
      }
    }
  }
  else
  {
    inserted = 4;
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
  return inserted;
}

```

## disassembly

```asm
0x1801320dc  mov     [rsp+arg_10], rsi
0x1801320e1  mov     [rsp+arg_18], rdi
0x1801320e6  push    r12
0x1801320e8  push    r14
0x1801320ea  push    r15
0x1801320ec  sub     rsp, 2D0h
0x1801320f3  mov     rax, cs:__security_cookie
0x1801320fa  xor     rax, rsp
0x1801320fd  mov     [rsp+2E8h+var_28], rax
0x180132105  mov     rsi, rdx
0x180132108  mov     r15, rcx
0x18013210b  xor     edx, edx; Val
0x18013210d  mov     r8d, 208h; Size
0x180132113  lea     rcx, [rsp+2E8h+instance]; void *
0x18013211b  call    memset_0
0x180132120  mov     [rsp+2E8h+var_268], 0
0x18013212b  mov     [rsp+2E8h+var_264], 0
0x180132133  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18013213a  mov     [rsp+2E8h+var_298], rax
0x18013213f  lea     rax, [rsp+2E8h+var_268]
0x180132147  mov     [rsp+2E8h+var_290], rax
0x18013214c  lea     rax, aMdmPolicyResul_181; "MDM_Policy_Result01_Defender02"
0x180132153  mov     [rsp+2E8h+var_288], rax
0x180132158  lea     rcx, [rsp+2E8h+var_268]
0x180132160  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180132165  mov     eax, cs:dword_180380B68
0x18013216b  cmp     eax, 5
0x18013216e  jbe     short loc_1801321E4
0x180132170  mov     rdx, 200000000000h
0x18013217a  lea     rcx, dword_180380B68
0x180132181  call    _tlgKeywordOn
0x180132186  test    al, al
0x180132188  jz      short loc_1801321E4
0x18013218a  cmp     [rsp+2E8h+var_264], 0
0x180132192  jz      short loc_1801321C6
0x180132194  cmp     [rsp+2E8h+var_250], 0
0x18013219c  jnz     short loc_1801321BC
0x18013219e  cmp     [rsp+2E8h+var_24C], 0
0x1801321a6  jnz     short loc_1801321BC
0x1801321a8  cmp     [rsp+2E8h+var_248], 0
0x1801321b0  jnz     short loc_1801321BC
0x1801321b2  cmp     [rsp+2E8h+var_244], 0
0x1801321ba  jz      short loc_1801321C6
0x1801321bc  lea     r9, [rsp+2E8h+var_250]
0x1801321c4  jmp     short loc_1801321C9
0x1801321c6  xor     r9d, r9d
0x1801321c9  lea     r8, [rsp+2E8h+var_260]
0x1801321d1  lea     rdx, byte_1803617F7
0x1801321d8  lea     rcx, dword_180380B68
0x1801321df  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801321e4  cmp     byte ptr [rsi+48h], 0
0x1801321e8  jz      loc_180132E1A
0x1801321ee  mov     [rsp+2E8h+var_2A0], 0
0x1801321f3  cmp     byte ptr [rsi+58h], 0
0x1801321f7  jz      loc_180132E1A
0x1801321fd  mov     r9, [rsi+40h]; unsigned __int16 *
0x180132201  mov     r8, [rsi+50h]; unsigned __int16 *
0x180132205  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x18013220c  lea     rcx, [rsp+2E8h+var_298]; this
0x180132211  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180132216  nop
0x180132217  mov     [rsp+2E8h+var_2A8], 0
0x180132220  lea     rax, [rsp+2E8h+var_2A8]
0x180132225  mov     [rsp+2E8h+var_2B8], rax
0x18013222a  mov     [rsp+2E8h+var_2C0], 4
0x180132232  mov     [rsp+2E8h+var_2C8], 2Ch ; ','
0x18013223a  lea     r9, ?MDM_Policy_Result01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Defender02_NodeList
0x180132241  mov     r8, [rsi+40h]
0x180132245  mov     rdx, [rsi+50h]
0x180132249  mov     rcx, r15
0x18013224c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180132251  mov     edi, eax
0x180132253  test    eax, eax
0x180132255  jz      short loc_18013225C
0x180132257  jmp     loc_180132E1F
0x18013225c  lea     rax, [rsp+2E8h+var_2A8]
0x180132261  mov     [rsp+2E8h+var_278], rax
0x180132266  mov     r12d, 1
0x18013226c  mov     [rsp+2E8h+var_270], r12b
0x180132271  mov     r14, [rsp+2E8h+var_2A8]
0x180132276  test    r14, r14
0x180132279  jnz     short loc_180132283
0x18013227b  mov     edi, r12d
0x18013227e  jmp     loc_180132E1F
0x180132283  mov     r9d, 2Ch ; ','; unsigned int
0x180132289  lea     r8, ?MDM_Policy_Result01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180132290  mov     rdx, rsi; struct _MI_Instance *
0x180132293  mov     rcx, r14; this
0x180132296  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18013229b  lea     r8, [rsi+60h]; void *
0x18013229f  cmp     [r8+4], r12b
0x1801322a3  jnz     short loc_1801322D8
0x1801322a5  lea     rdx, aAllowarchivesc; "AllowArchiveScanning"
0x1801322ac  mov     rcx, r14; this
0x1801322af  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801322b4  mov     edi, eax
0x1801322b6  test    eax, eax
0x1801322b8  jz      short loc_1801322D8
0x1801322ba  mov     rcx, [rsp+2E8h+var_2A8]
0x1801322bf  test    rcx, rcx
0x1801322c2  jz      short loc_1801322D3
0x1801322c4  mov     rax, [rcx]
0x1801322c7  mov     edx, r12d
0x1801322ca  mov     rax, [rax]
0x1801322cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801322d2  nop
0x1801322d3  jmp     loc_180132E1F
0x1801322d8  lea     r8, [rsi+68h]; void *
0x1801322dc  cmp     [r8+4], r12b
0x1801322e0  jnz     short loc_180132315
0x1801322e2  lea     rdx, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x1801322e9  mov     rcx, r14; this
0x1801322ec  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801322f1  mov     edi, eax
0x1801322f3  test    eax, eax
0x1801322f5  jz      short loc_180132315
0x1801322f7  mov     rcx, [rsp+2E8h+var_2A8]
0x1801322fc  test    rcx, rcx
0x1801322ff  jz      short loc_180132310
0x180132301  mov     rax, [rcx]
0x180132304  mov     edx, r12d
0x180132307  mov     rax, [rax]
0x18013230a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013230f  nop
0x180132310  jmp     loc_180132E1F
0x180132315  lea     r8, [rsi+70h]; void *
0x180132319  cmp     [r8+4], r12b
0x18013231d  jnz     short loc_180132352
0x18013231f  lea     rdx, aAllowcloudprot; "AllowCloudProtection"
0x180132326  mov     rcx, r14; this
0x180132329  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18013232e  mov     edi, eax
0x180132330  test    eax, eax
0x180132332  jz      short loc_180132352
0x180132334  mov     rcx, [rsp+2E8h+var_2A8]
0x180132339  test    rcx, rcx
0x18013233c  jz      short loc_18013234D
0x18013233e  mov     rax, [rcx]
0x180132341  mov     edx, r12d
0x180132344  mov     rax, [rax]
0x180132347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013234c  nop
0x18013234d  jmp     loc_180132E1F
0x180132352  lea     r8, [rsi+78h]; void *
0x180132356  cmp     [r8+4], r12b
0x18013235a  jnz     short loc_18013238F
0x18013235c  lea     rdx, aAllowemailscan; "AllowEmailScanning"
0x180132363  mov     rcx, r14; this
0x180132366  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18013236b  mov     edi, eax
0x18013236d  test    eax, eax
0x18013236f  jz      short loc_18013238F
0x180132371  mov     rcx, [rsp+2E8h+var_2A8]
0x180132376  test    rcx, rcx
0x180132379  jz      short loc_18013238A
0x18013237b  mov     rax, [rcx]
0x18013237e  mov     edx, r12d
0x180132381  mov     rax, [rax]
0x180132384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132389  nop
0x18013238a  jmp     loc_180132E1F
0x18013238f  lea     r8, [rsi+80h]; void *
0x180132396  cmp     [r8+4], r12b
0x18013239a  jnz     short loc_1801323CF
0x18013239c  lea     rdx, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x1801323a3  mov     rcx, r14; this
0x1801323a6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801323ab  mov     edi, eax
0x1801323ad  test    eax, eax
0x1801323af  jz      short loc_1801323CF
0x1801323b1  mov     rcx, [rsp+2E8h+var_2A8]
0x1801323b6  test    rcx, rcx
0x1801323b9  jz      short loc_1801323CA
0x1801323bb  mov     rax, [rcx]
0x1801323be  mov     edx, r12d
0x1801323c1  mov     rax, [rax]
0x1801323c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801323c9  nop
0x1801323ca  jmp     loc_180132E1F
0x1801323cf  lea     r8, [rsi+88h]; void *
0x1801323d6  cmp     [r8+4], r12b
0x1801323da  jnz     short loc_18013240F
0x1801323dc  lea     rdx, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x1801323e3  mov     rcx, r14; this
0x1801323e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801323eb  mov     edi, eax
0x1801323ed  test    eax, eax
0x1801323ef  jz      short loc_18013240F
0x1801323f1  mov     rcx, [rsp+2E8h+var_2A8]
0x1801323f6  test    rcx, rcx
0x1801323f9  jz      short loc_18013240A
0x1801323fb  mov     rax, [rcx]
0x1801323fe  mov     edx, r12d
0x180132401  mov     rax, [rax]
0x180132404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132409  nop
0x18013240a  jmp     loc_180132E1F
0x18013240f  lea     r8, [rsi+90h]; void *
0x180132416  cmp     [r8+4], r12b
0x18013241a  jnz     short loc_18013244F
0x18013241c  lea     rdx, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x180132423  mov     rcx, r14; this
0x180132426  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18013242b  mov     edi, eax
0x18013242d  test    eax, eax
0x18013242f  jz      short loc_18013244F
0x180132431  mov     rcx, [rsp+2E8h+var_2A8]
0x180132436  test    rcx, rcx
0x180132439  jz      short loc_18013244A
0x18013243b  mov     rax, [rcx]
0x18013243e  mov     edx, r12d
0x180132441  mov     rax, [rax]
0x180132444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132449  nop
0x18013244a  jmp     loc_180132E1F
0x18013244f  lea     r8, [rsi+98h]; void *
0x180132456  cmp     [r8+4], r12b
0x18013245a  jnz     short loc_18013248F
0x18013245c  lea     rdx, aAllowioavprote; "AllowIOAVProtection"
0x180132463  mov     rcx, r14; this
0x180132466  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18013246b  mov     edi, eax
0x18013246d  test    eax, eax
0x18013246f  jz      short loc_18013248F
0x180132471  mov     rcx, [rsp+2E8h+var_2A8]
0x180132476  test    rcx, rcx
0x180132479  jz      short loc_18013248A
0x18013247b  mov     rax, [rcx]
0x18013247e  mov     edx, r12d
0x180132481  mov     rax, [rax]
0x180132484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132489  nop
0x18013248a  jmp     loc_180132E1F
0x18013248f  lea     r8, [rsi+0A0h]; void *
0x180132496  cmp     [r8+4], r12b
0x18013249a  jnz     short loc_1801324CF
0x18013249c  lea     rdx, aAllowonaccessp; "AllowOnAccessProtection"
0x1801324a3  mov     rcx, r14; this
0x1801324a6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801324ab  mov     edi, eax
0x1801324ad  test    eax, eax
0x1801324af  jz      short loc_1801324CF
0x1801324b1  mov     rcx, [rsp+2E8h+var_2A8]
0x1801324b6  test    rcx, rcx
0x1801324b9  jz      short loc_1801324CA
0x1801324bb  mov     rax, [rcx]
0x1801324be  mov     edx, r12d
0x1801324c1  mov     rax, [rax]
0x1801324c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801324c9  nop
0x1801324ca  jmp     loc_180132E1F
0x1801324cf  lea     r8, [rsi+0A8h]; void *
0x1801324d6  cmp     [r8+4], r12b
0x1801324da  jnz     short loc_18013250F
0x1801324dc  lea     rdx, aAllowrealtimem; "AllowRealtimeMonitoring"
0x1801324e3  mov     rcx, r14; this
0x1801324e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801324eb  mov     edi, eax
0x1801324ed  test    eax, eax
0x1801324ef  jz      short loc_18013250F
0x1801324f1  mov     rcx, [rsp+2E8h+var_2A8]
0x1801324f6  test    rcx, rcx
0x1801324f9  jz      short loc_18013250A
0x1801324fb  mov     rax, [rcx]
0x1801324fe  mov     edx, r12d
0x180132501  mov     rax, [rax]
0x180132504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132509  nop
0x18013250a  jmp     loc_180132E1F
0x18013250f  lea     r8, [rsi+0B0h]; void *
0x180132516  cmp     [r8+4], r12b
0x18013251a  jnz     short loc_18013254F
0x18013251c  lea     rdx, aAllowscanningn; "AllowScanningNetworkFiles"
0x180132523  mov     rcx, r14; this
0x180132526  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18013252b  mov     edi, eax
0x18013252d  test    eax, eax
0x18013252f  jz      short loc_18013254F
0x180132531  mov     rcx, [rsp+2E8h+var_2A8]
0x180132536  test    rcx, rcx
0x180132539  jz      short loc_18013254A
0x18013253b  mov     rax, [rcx]
0x18013253e  mov     edx, r12d
0x180132541  mov     rax, [rax]
0x180132544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132549  nop
0x18013254a  jmp     loc_180132E1F
0x18013254f  lea     r8, [rsi+0B8h]; void *
0x180132556  cmp     [r8+4], r12b
0x18013255a  jnz     short loc_18013258F
0x18013255c  lea     rdx, aAllowscriptsca; "AllowScriptScanning"
0x180132563  mov     rcx, r14; this
0x180132566  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18013256b  mov     edi, eax
0x18013256d  test    eax, eax
0x18013256f  jz      short loc_18013258F
0x180132571  mov     rcx, [rsp+2E8h+var_2A8]
0x180132576  test    rcx, rcx
0x180132579  jz      short loc_18013258A
0x18013257b  mov     rax, [rcx]
  ... truncated ...
```
