# MDM_Policy_Config01_SystemServices02_InvokeCreateInstance

- ea: `0x1800e57ec`
- end: `0x1800e60cb`
- name: `MDM_Policy_Config01_SystemServices02_InvokeCreateInstance`
- size: `2271`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e56f0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800e57ec`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1800e59b5`: `ConfigureComputerBrowserServiceStartupMode`
- `0x1800e59f2`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x1800e5a2f`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x1800e5a6c`: `ConfigureIISAdminServiceStartupMode`
- `0x1800e5aac`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x1800e5aec`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x1800e5b2c`: `ConfigureLxssManagerServiceStartupMode`
- `0x1800e5b6c`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x1800e5bac`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x1800e5bec`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x1800e5c2c`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x1800e5c6c`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x1800e5cac`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x1800e5cec`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x1800e5d2c`: `ConfigureWebManagementServiceStartupMode`
- `0x1800e5d6c`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x1800e5dac`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x1800e5dec`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x1800e5e2c`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x1800e5e6c`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x1800e5eac`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x1800e5eec`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x1800e5915`: `CreateInstanceStart`
- `0x1800e6032`: `CreateInstanceEnd`
- `0x1800e585c`: `MDM_Policy_Config01_SystemServices02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_SystemServices02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-1A8h] BYREF
  char v9; // [rsp+48h] [rbp-1A0h]
  _QWORD v10[5]; // [rsp+50h] [rbp-198h] BYREF
  char v11; // [rsp+78h] [rbp-170h]
  int v12; // [rsp+80h] [rbp-168h] BYREF
  char v13; // [rsp+84h] [rbp-164h]
  _BYTE v14[16]; // [rsp+88h] [rbp-160h] BYREF
  _DWORD v15[6]; // [rsp+98h] [rbp-150h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-138h] BYREF

  memset_0(&instance, 0, 0x110u);
  v12 = 0;
  v13 = 0;
  v10[0] = &TelemetryEventWriter::`vftable';
  v10[1] = &v12;
  v10[2] = "MDM_Policy_Config01_SystemServices02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18035C5D5,
      v14,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    inserted = 4;
    goto LABEL_117;
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
               (struct WmiNodeInfo *)&MDM_Policy_Config01_SystemServices02_NodeList,
               0x18u,
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
      goto LABEL_117;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v8,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_SystemServices02_NodeList,
      0x18u);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureComputerBrowserServiceStartupMode",
                   (LONG *)a2[1].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
LABEL_112:
        (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        goto LABEL_117;
      }
    }
    if ( BYTE4(a2[1].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureHomeGroupListenerServiceStartupMode",
                   (LONG *)&a2[1].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[1].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureHomeGroupProviderServiceStartupMode",
                   (LONG *)&a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureIISAdminServiceStartupMode",
                   (LONG *)&a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[2].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureInfraredMonitorServiceStartupMode",
                   (LONG *)&a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureInternetConnectionSharingServiceStartupMode",
                   (LONG *)&a2[2].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[2].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureLxssManagerServiceStartupMode",
                   (LONG *)&a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureMicrosoftFTPServiceStartupMode",
                   (LONG *)&a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureRemoteProcedureCallLocatorServiceStartupMode",
                   (LONG *)a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureRoutingAndRemoteAccessServiceStartupMode",
                   (LONG *)&a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[2].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureSimpleTCPIPServicesStartupMode",
                   (LONG *)&a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureSpecialAdministrationConsoleHelperServiceStartupMode",
                   (LONG *)&a2[2].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureSSDPDiscoveryServiceStartupMode",
                   (LONG *)&a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[3].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureUPnPDeviceHostServiceStartupMode",
                   (LONG *)&a2[3].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[3].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureWebManagementServiceStartupMode",
                   (LONG *)&a2[3].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[3].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode",
                   (LONG *)&a2[3].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[3].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureWindowsMobileHotspotServiceStartupMode",
                   (LONG *)a2[3].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[3].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureWorldWideWebPublishingServiceStartupMode",
                   (LONG *)&a2[3].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[3].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureXboxAccessoryManagementServiceStartupMode",
                   (LONG *)&a2[3].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[3].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureXboxLiveAuthManagerServiceStartupMode",
                   (LONG *)&a2[3].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureXboxLiveGameSaveServiceStartupMode",
                   (LONG *)&a2[4]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[4].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureXboxLiveNetworkingServiceStartupMode",
                   (LONG *)&a2[4].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_117;
      goto LABEL_112;
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_117;
      goto LABEL_112;
    }
    inserted = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_SystemServices02_rtti, &instance);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_117;
      goto LABEL_112;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v8 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_117:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "CreateInstanceEnd", inserted);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_18036EE14,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return inserted;
}

```

## disassembly

```asm
0x1800e57ec  mov     [rsp+arg_10], rsi
0x1800e57f1  mov     [rsp+arg_18], rdi
0x1800e57f6  push    r12
0x1800e57f8  push    r14
0x1800e57fa  push    r15
0x1800e57fc  sub     rsp, 1D0h
0x1800e5803  mov     rax, cs:__security_cookie
0x1800e580a  xor     rax, rsp
0x1800e580d  mov     [rsp+1E8h+var_28], rax
0x1800e5815  mov     rsi, rdx
0x1800e5818  mov     r15, rcx
0x1800e581b  xor     edx, edx; Val
0x1800e581d  mov     r8d, 110h; Size
0x1800e5823  lea     rcx, [rsp+1E8h+instance]; void *
0x1800e582b  call    memset_0
0x1800e5830  mov     [rsp+1E8h+var_168], 0
0x1800e583b  mov     [rsp+1E8h+var_164], 0
0x1800e5843  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e584a  mov     [rsp+1E8h+var_198], rax
0x1800e584f  lea     rax, [rsp+1E8h+var_168]
0x1800e5857  mov     [rsp+1E8h+var_190], rax
0x1800e585c  lea     rax, aMdmPolicyConfi_72; "MDM_Policy_Config01_SystemServices02"
0x1800e5863  mov     [rsp+1E8h+var_188], rax
0x1800e5868  lea     rcx, [rsp+1E8h+var_168]
0x1800e5870  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e5875  mov     eax, cs:dword_180380B68
0x1800e587b  cmp     eax, 5
0x1800e587e  jbe     short loc_1800E58F4
0x1800e5880  mov     rdx, 200000000000h
0x1800e588a  lea     rcx, dword_180380B68
0x1800e5891  call    _tlgKeywordOn
0x1800e5896  test    al, al
0x1800e5898  jz      short loc_1800E58F4
0x1800e589a  cmp     [rsp+1E8h+var_164], 0
0x1800e58a2  jz      short loc_1800E58D6
0x1800e58a4  cmp     [rsp+1E8h+var_150], 0
0x1800e58ac  jnz     short loc_1800E58CC
0x1800e58ae  cmp     [rsp+1E8h+var_14C], 0
0x1800e58b6  jnz     short loc_1800E58CC
0x1800e58b8  cmp     [rsp+1E8h+var_148], 0
0x1800e58c0  jnz     short loc_1800E58CC
0x1800e58c2  cmp     [rsp+1E8h+var_144], 0
0x1800e58ca  jz      short loc_1800E58D6
0x1800e58cc  lea     r9, [rsp+1E8h+var_150]
0x1800e58d4  jmp     short loc_1800E58D9
0x1800e58d6  xor     r9d, r9d
0x1800e58d9  lea     r8, [rsp+1E8h+var_160]
0x1800e58e1  lea     rdx, byte_18035C5D5
0x1800e58e8  lea     rcx, dword_180380B68
0x1800e58ef  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e58f4  cmp     byte ptr [rsi+48h], 0
0x1800e58f8  jz      loc_1800E602A
0x1800e58fe  mov     [rsp+1E8h+var_1A0], 0
0x1800e5903  cmp     byte ptr [rsi+58h], 0
0x1800e5907  jz      loc_1800E602A
0x1800e590d  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800e5911  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800e5915  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1800e591c  lea     rcx, [rsp+1E8h+var_198]; this
0x1800e5921  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800e5926  nop
0x1800e5927  mov     [rsp+1E8h+var_1A8], 0
0x1800e5930  lea     rax, [rsp+1E8h+var_1A8]
0x1800e5935  mov     [rsp+1E8h+var_1B8], rax
0x1800e593a  mov     [rsp+1E8h+var_1C0], 4
0x1800e5942  mov     [rsp+1E8h+var_1C8], 18h
0x1800e594a  lea     r9, ?MDM_Policy_Config01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_SystemServices02_NodeList
0x1800e5951  mov     r8, [rsi+40h]
0x1800e5955  mov     rdx, [rsi+50h]
0x1800e5959  mov     rcx, r15
0x1800e595c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e5961  mov     edi, eax
0x1800e5963  test    eax, eax
0x1800e5965  jz      short loc_1800E596C
0x1800e5967  jmp     loc_1800E602F
0x1800e596c  lea     rax, [rsp+1E8h+var_1A8]
0x1800e5971  mov     [rsp+1E8h+var_178], rax
0x1800e5976  mov     r12d, 1
0x1800e597c  mov     [rsp+1E8h+var_170], r12b
0x1800e5981  mov     r14, [rsp+1E8h+var_1A8]
0x1800e5986  test    r14, r14
0x1800e5989  jnz     short loc_1800E5993
0x1800e598b  mov     edi, r12d
0x1800e598e  jmp     loc_1800E602F
0x1800e5993  mov     r9d, 18h; unsigned int
0x1800e5999  lea     r8, ?MDM_Policy_Config01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800e59a0  mov     rdx, rsi; struct _MI_Instance *
0x1800e59a3  mov     rcx, r14; this
0x1800e59a6  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800e59ab  lea     r8, [rsi+60h]; void *
0x1800e59af  cmp     [r8+4], r12b
0x1800e59b3  jnz     short loc_1800E59E8
0x1800e59b5  lea     rdx, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x1800e59bc  mov     rcx, r14; this
0x1800e59bf  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e59c4  mov     edi, eax
0x1800e59c6  test    eax, eax
0x1800e59c8  jz      short loc_1800E59E8
0x1800e59ca  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e59cf  test    rcx, rcx
0x1800e59d2  jz      short loc_1800E59E3
0x1800e59d4  mov     rax, [rcx]
0x1800e59d7  mov     edx, r12d
0x1800e59da  mov     rax, [rax]
0x1800e59dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e59e2  nop
0x1800e59e3  jmp     loc_1800E602F
0x1800e59e8  lea     r8, [rsi+68h]; void *
0x1800e59ec  cmp     [r8+4], r12b
0x1800e59f0  jnz     short loc_1800E5A25
0x1800e59f2  lea     rdx, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x1800e59f9  mov     rcx, r14; this
0x1800e59fc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e5a01  mov     edi, eax
0x1800e5a03  test    eax, eax
0x1800e5a05  jz      short loc_1800E5A25
0x1800e5a07  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5a0c  test    rcx, rcx
0x1800e5a0f  jz      short loc_1800E5A20
0x1800e5a11  mov     rax, [rcx]
0x1800e5a14  mov     edx, r12d
0x1800e5a17  mov     rax, [rax]
0x1800e5a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5a1f  nop
0x1800e5a20  jmp     loc_1800E602F
0x1800e5a25  lea     r8, [rsi+70h]; void *
0x1800e5a29  cmp     [r8+4], r12b
0x1800e5a2d  jnz     short loc_1800E5A62
0x1800e5a2f  lea     rdx, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x1800e5a36  mov     rcx, r14; this
0x1800e5a39  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e5a3e  mov     edi, eax
0x1800e5a40  test    eax, eax
0x1800e5a42  jz      short loc_1800E5A62
0x1800e5a44  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5a49  test    rcx, rcx
0x1800e5a4c  jz      short loc_1800E5A5D
0x1800e5a4e  mov     rax, [rcx]
0x1800e5a51  mov     edx, r12d
0x1800e5a54  mov     rax, [rax]
0x1800e5a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5a5c  nop
0x1800e5a5d  jmp     loc_1800E602F
0x1800e5a62  lea     r8, [rsi+78h]; void *
0x1800e5a66  cmp     [r8+4], r12b
0x1800e5a6a  jnz     short loc_1800E5A9F
0x1800e5a6c  lea     rdx, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x1800e5a73  mov     rcx, r14; this
0x1800e5a76  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e5a7b  mov     edi, eax
0x1800e5a7d  test    eax, eax
0x1800e5a7f  jz      short loc_1800E5A9F
0x1800e5a81  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5a86  test    rcx, rcx
0x1800e5a89  jz      short loc_1800E5A9A
0x1800e5a8b  mov     rax, [rcx]
0x1800e5a8e  mov     edx, r12d
0x1800e5a91  mov     rax, [rax]
0x1800e5a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5a99  nop
0x1800e5a9a  jmp     loc_1800E602F
0x1800e5a9f  lea     r8, [rsi+80h]; void *
0x1800e5aa6  cmp     [r8+4], r12b
0x1800e5aaa  jnz     short loc_1800E5ADF
0x1800e5aac  lea     rdx, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x1800e5ab3  mov     rcx, r14; this
0x1800e5ab6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e5abb  mov     edi, eax
0x1800e5abd  test    eax, eax
0x1800e5abf  jz      short loc_1800E5ADF
0x1800e5ac1  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5ac6  test    rcx, rcx
0x1800e5ac9  jz      short loc_1800E5ADA
0x1800e5acb  mov     rax, [rcx]
0x1800e5ace  mov     edx, r12d
0x1800e5ad1  mov     rax, [rax]
0x1800e5ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5ad9  nop
0x1800e5ada  jmp     loc_1800E602F
0x1800e5adf  lea     r8, [rsi+88h]; void *
0x1800e5ae6  cmp     [r8+4], r12b
0x1800e5aea  jnz     short loc_1800E5B1F
0x1800e5aec  lea     rdx, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x1800e5af3  mov     rcx, r14; this
0x1800e5af6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e5afb  mov     edi, eax
0x1800e5afd  test    eax, eax
0x1800e5aff  jz      short loc_1800E5B1F
0x1800e5b01  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5b06  test    rcx, rcx
0x1800e5b09  jz      short loc_1800E5B1A
0x1800e5b0b  mov     rax, [rcx]
0x1800e5b0e  mov     edx, r12d
0x1800e5b11  mov     rax, [rax]
0x1800e5b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5b19  nop
0x1800e5b1a  jmp     loc_1800E602F
0x1800e5b1f  lea     r8, [rsi+90h]; void *
0x1800e5b26  cmp     [r8+4], r12b
0x1800e5b2a  jnz     short loc_1800E5B5F
0x1800e5b2c  lea     rdx, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x1800e5b33  mov     rcx, r14; this
0x1800e5b36  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e5b3b  mov     edi, eax
0x1800e5b3d  test    eax, eax
0x1800e5b3f  jz      short loc_1800E5B5F
0x1800e5b41  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5b46  test    rcx, rcx
0x1800e5b49  jz      short loc_1800E5B5A
0x1800e5b4b  mov     rax, [rcx]
0x1800e5b4e  mov     edx, r12d
0x1800e5b51  mov     rax, [rax]
0x1800e5b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5b59  nop
0x1800e5b5a  jmp     loc_1800E602F
0x1800e5b5f  lea     r8, [rsi+98h]; void *
0x1800e5b66  cmp     [r8+4], r12b
0x1800e5b6a  jnz     short loc_1800E5B9F
0x1800e5b6c  lea     rdx, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x1800e5b73  mov     rcx, r14; this
0x1800e5b76  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e5b7b  mov     edi, eax
0x1800e5b7d  test    eax, eax
0x1800e5b7f  jz      short loc_1800E5B9F
0x1800e5b81  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5b86  test    rcx, rcx
0x1800e5b89  jz      short loc_1800E5B9A
0x1800e5b8b  mov     rax, [rcx]
0x1800e5b8e  mov     edx, r12d
0x1800e5b91  mov     rax, [rax]
0x1800e5b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5b99  nop
0x1800e5b9a  jmp     loc_1800E602F
0x1800e5b9f  lea     r8, [rsi+0A0h]; void *
0x1800e5ba6  cmp     [r8+4], r12b
0x1800e5baa  jnz     short loc_1800E5BDF
0x1800e5bac  lea     rdx, aConfigureremot; "ConfigureRemoteProcedureCallLocatorServ"...
0x1800e5bb3  mov     rcx, r14; this
0x1800e5bb6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e5bbb  mov     edi, eax
0x1800e5bbd  test    eax, eax
0x1800e5bbf  jz      short loc_1800E5BDF
0x1800e5bc1  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5bc6  test    rcx, rcx
0x1800e5bc9  jz      short loc_1800E5BDA
0x1800e5bcb  mov     rax, [rcx]
0x1800e5bce  mov     edx, r12d
0x1800e5bd1  mov     rax, [rax]
0x1800e5bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5bd9  nop
0x1800e5bda  jmp     loc_1800E602F
0x1800e5bdf  lea     r8, [rsi+0A8h]; void *
0x1800e5be6  cmp     [r8+4], r12b
0x1800e5bea  jnz     short loc_1800E5C1F
0x1800e5bec  lea     rdx, aConfigurerouti; "ConfigureRoutingAndRemoteAccessServiceS"...
0x1800e5bf3  mov     rcx, r14; this
0x1800e5bf6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e5bfb  mov     edi, eax
0x1800e5bfd  test    eax, eax
0x1800e5bff  jz      short loc_1800E5C1F
0x1800e5c01  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5c06  test    rcx, rcx
0x1800e5c09  jz      short loc_1800E5C1A
0x1800e5c0b  mov     rax, [rcx]
0x1800e5c0e  mov     edx, r12d
0x1800e5c11  mov     rax, [rax]
0x1800e5c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5c19  nop
0x1800e5c1a  jmp     loc_1800E602F
0x1800e5c1f  lea     r8, [rsi+0B0h]; void *
0x1800e5c26  cmp     [r8+4], r12b
0x1800e5c2a  jnz     short loc_1800E5C5F
0x1800e5c2c  lea     rdx, aConfiguresimpl; "ConfigureSimpleTCPIPServicesStartupMode"
0x1800e5c33  mov     rcx, r14; this
0x1800e5c36  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e5c3b  mov     edi, eax
0x1800e5c3d  test    eax, eax
0x1800e5c3f  jz      short loc_1800E5C5F
0x1800e5c41  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5c46  test    rcx, rcx
0x1800e5c49  jz      short loc_1800E5C5A
0x1800e5c4b  mov     rax, [rcx]
0x1800e5c4e  mov     edx, r12d
0x1800e5c51  mov     rax, [rax]
0x1800e5c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5c59  nop
0x1800e5c5a  jmp     loc_1800E602F
0x1800e5c5f  lea     r8, [rsi+0B8h]; void *
0x1800e5c66  cmp     [r8+4], r12b
0x1800e5c6a  jnz     short loc_1800E5C9F
0x1800e5c6c  lea     rdx, aConfigurespeci; "ConfigureSpecialAdministrationConsoleHe"...
0x1800e5c73  mov     rcx, r14; this
0x1800e5c76  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e5c7b  mov     edi, eax
0x1800e5c7d  test    eax, eax
0x1800e5c7f  jz      short loc_1800E5C9F
0x1800e5c81  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5c86  test    rcx, rcx
0x1800e5c89  jz      short loc_1800E5C9A
0x1800e5c8b  mov     rax, [rcx]
  ... truncated ...
```
