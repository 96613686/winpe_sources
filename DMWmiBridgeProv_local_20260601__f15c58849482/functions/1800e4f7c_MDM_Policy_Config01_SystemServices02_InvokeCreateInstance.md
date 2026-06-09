# MDM_Policy_Config01_SystemServices02_InvokeCreateInstance

- ea: `0x1800e4f7c`
- end: `0x1800e585c`
- name: `MDM_Policy_Config01_SystemServices02_InvokeCreateInstance`
- size: `2272`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e4ec0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800e4f7c`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1800e5145`: `ConfigureComputerBrowserServiceStartupMode`
- `0x1800e5182`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x1800e51bf`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x1800e51fc`: `ConfigureIISAdminServiceStartupMode`
- `0x1800e523c`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x1800e527c`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x1800e52bc`: `ConfigureLxssManagerServiceStartupMode`
- `0x1800e52fc`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x1800e533c`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x1800e537c`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x1800e53bc`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x1800e53fc`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x1800e543c`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x1800e547c`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x1800e54bc`: `ConfigureWebManagementServiceStartupMode`
- `0x1800e54fc`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x1800e553c`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x1800e557c`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x1800e55bc`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x1800e55fc`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x1800e563c`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x1800e567c`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x1800e50a5`: `CreateInstanceStart`
- `0x1800e57c2`: `CreateInstanceEnd`
- `0x1800e4fec`: `MDM_Policy_Config01_SystemServices02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_SystemServices02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
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
    inserted = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_117;
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
                             &MDM_Policy_Config01_SystemServices02_NodeList,
                             24,
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
                   a2[1].reserved);
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
                   &a2[1].reserved[1]);
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
                   &a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureIISAdminServiceStartupMode", &a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[2].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureInfraredMonitorServiceStartupMode", &a2[2]);
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
                   &a2[2].classDecl);
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
                   &a2[2].serverName);
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
                   &a2[2].nameSpace);
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
                   a2[2].reserved);
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
                   &a2[2].reserved[1]);
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
                   &a2[2].reserved[2]);
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
                   &a2[2].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureSSDPDiscoveryServiceStartupMode", &a2[3]);
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
                   &a2[3].classDecl);
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
                   &a2[3].serverName);
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
                   &a2[3].nameSpace);
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
                   a2[3].reserved);
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
                   &a2[3].reserved[1]);
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
                   &a2[3].reserved[2]);
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
                   &a2[3].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    if ( BYTE4(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureXboxLiveGameSaveServiceStartupMode", &a2[4]);
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
                   &a2[4].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_117;
        goto LABEL_112;
      }
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_117;
      goto LABEL_112;
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800e4f7c  mov     [rsp+arg_10], rsi
0x1800e4f81  mov     [rsp+arg_18], rdi
0x1800e4f86  push    r12
0x1800e4f88  push    r14
0x1800e4f8a  push    r15
0x1800e4f8c  sub     rsp, 1D0h
0x1800e4f93  mov     rax, cs:__security_cookie
0x1800e4f9a  xor     rax, rsp
0x1800e4f9d  mov     [rsp+1E8h+var_28], rax
0x1800e4fa5  mov     rsi, rdx
0x1800e4fa8  mov     r15, rcx
0x1800e4fab  xor     edx, edx; Val
0x1800e4fad  mov     r8d, 110h; Size
0x1800e4fb3  lea     rcx, [rsp+1E8h+instance]; void *
0x1800e4fbb  call    memset_0
0x1800e4fc0  mov     [rsp+1E8h+var_168], 0
0x1800e4fcb  mov     [rsp+1E8h+var_164], 0
0x1800e4fd3  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e4fda  mov     [rsp+1E8h+var_198], rax
0x1800e4fdf  lea     rax, [rsp+1E8h+var_168]
0x1800e4fe7  mov     [rsp+1E8h+var_190], rax
0x1800e4fec  lea     rax, aMdmPolicyConfi_72; "MDM_Policy_Config01_SystemServices02"
0x1800e4ff3  mov     [rsp+1E8h+var_188], rax
0x1800e4ff8  lea     rcx, [rsp+1E8h+var_168]
0x1800e5000  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e5005  mov     eax, cs:dword_180380B68
0x1800e500b  cmp     eax, 5
0x1800e500e  jbe     short loc_1800E5084
0x1800e5010  mov     rdx, 200000000000h
0x1800e501a  lea     rcx, dword_180380B68
0x1800e5021  call    _tlgKeywordOn
0x1800e5026  test    al, al
0x1800e5028  jz      short loc_1800E5084
0x1800e502a  cmp     [rsp+1E8h+var_164], 0
0x1800e5032  jz      short loc_1800E5066
0x1800e5034  cmp     [rsp+1E8h+var_150], 0
0x1800e503c  jnz     short loc_1800E505C
0x1800e503e  cmp     [rsp+1E8h+var_14C], 0
0x1800e5046  jnz     short loc_1800E505C
0x1800e5048  cmp     [rsp+1E8h+var_148], 0
0x1800e5050  jnz     short loc_1800E505C
0x1800e5052  cmp     [rsp+1E8h+var_144], 0
0x1800e505a  jz      short loc_1800E5066
0x1800e505c  lea     r9, [rsp+1E8h+var_150]
0x1800e5064  jmp     short loc_1800E5069
0x1800e5066  xor     r9d, r9d
0x1800e5069  lea     r8, [rsp+1E8h+var_160]
0x1800e5071  lea     rdx, byte_18035C5D5
0x1800e5078  lea     rcx, dword_180380B68
0x1800e507f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e5084  cmp     byte ptr [rsi+48h], 0
0x1800e5088  jz      loc_1800E57BA
0x1800e508e  mov     [rsp+1E8h+var_1A0], 0
0x1800e5093  cmp     byte ptr [rsi+58h], 0
0x1800e5097  jz      loc_1800E57BA
0x1800e509d  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800e50a1  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800e50a5  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1800e50ac  lea     rcx, [rsp+1E8h+var_198]; this
0x1800e50b1  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800e50b6  nop
0x1800e50b7  mov     [rsp+1E8h+var_1A8], 0
0x1800e50c0  lea     rax, [rsp+1E8h+var_1A8]
0x1800e50c5  mov     [rsp+1E8h+var_1B8], rax
0x1800e50ca  mov     [rsp+1E8h+var_1C0], 4
0x1800e50d2  mov     [rsp+1E8h+var_1C8], 18h
0x1800e50da  lea     r9, ?MDM_Policy_Config01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_SystemServices02_NodeList
0x1800e50e1  mov     r8, [rsi+40h]
0x1800e50e5  mov     rdx, [rsi+50h]
0x1800e50e9  mov     rcx, r15
0x1800e50ec  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e50f1  mov     edi, eax
0x1800e50f3  test    eax, eax
0x1800e50f5  jz      short loc_1800E50FC
0x1800e50f7  jmp     loc_1800E57BF
0x1800e50fc  lea     rax, [rsp+1E8h+var_1A8]
0x1800e5101  mov     [rsp+1E8h+var_178], rax
0x1800e5106  mov     r12d, 1
0x1800e510c  mov     [rsp+1E8h+var_170], r12b
0x1800e5111  mov     r14, [rsp+1E8h+var_1A8]
0x1800e5116  test    r14, r14
0x1800e5119  jnz     short loc_1800E5123
0x1800e511b  mov     edi, r12d
0x1800e511e  jmp     loc_1800E57BF
0x1800e5123  mov     r9d, 18h; unsigned int
0x1800e5129  lea     r8, ?MDM_Policy_Config01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800e5130  mov     rdx, rsi; struct _MI_Instance *
0x1800e5133  mov     rcx, r14; this
0x1800e5136  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800e513b  lea     r8, [rsi+60h]; void *
0x1800e513f  cmp     [r8+4], r12b
0x1800e5143  jnz     short loc_1800E5178
0x1800e5145  lea     rdx, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x1800e514c  mov     rcx, r14; this
0x1800e514f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e5154  mov     edi, eax
0x1800e5156  test    eax, eax
0x1800e5158  jz      short loc_1800E5178
0x1800e515a  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e515f  test    rcx, rcx
0x1800e5162  jz      short loc_1800E5173
0x1800e5164  mov     rax, [rcx]
0x1800e5167  mov     edx, r12d
0x1800e516a  mov     rax, [rax]
0x1800e516d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5172  nop
0x1800e5173  jmp     loc_1800E57BF
0x1800e5178  lea     r8, [rsi+68h]; void *
0x1800e517c  cmp     [r8+4], r12b
0x1800e5180  jnz     short loc_1800E51B5
0x1800e5182  lea     rdx, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x1800e5189  mov     rcx, r14; this
0x1800e518c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e5191  mov     edi, eax
0x1800e5193  test    eax, eax
0x1800e5195  jz      short loc_1800E51B5
0x1800e5197  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e519c  test    rcx, rcx
0x1800e519f  jz      short loc_1800E51B0
0x1800e51a1  mov     rax, [rcx]
0x1800e51a4  mov     edx, r12d
0x1800e51a7  mov     rax, [rax]
0x1800e51aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e51af  nop
0x1800e51b0  jmp     loc_1800E57BF
0x1800e51b5  lea     r8, [rsi+70h]; void *
0x1800e51b9  cmp     [r8+4], r12b
0x1800e51bd  jnz     short loc_1800E51F2
0x1800e51bf  lea     rdx, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x1800e51c6  mov     rcx, r14; this
0x1800e51c9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e51ce  mov     edi, eax
0x1800e51d0  test    eax, eax
0x1800e51d2  jz      short loc_1800E51F2
0x1800e51d4  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e51d9  test    rcx, rcx
0x1800e51dc  jz      short loc_1800E51ED
0x1800e51de  mov     rax, [rcx]
0x1800e51e1  mov     edx, r12d
0x1800e51e4  mov     rax, [rax]
0x1800e51e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e51ec  nop
0x1800e51ed  jmp     loc_1800E57BF
0x1800e51f2  lea     r8, [rsi+78h]; void *
0x1800e51f6  cmp     [r8+4], r12b
0x1800e51fa  jnz     short loc_1800E522F
0x1800e51fc  lea     rdx, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x1800e5203  mov     rcx, r14; this
0x1800e5206  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e520b  mov     edi, eax
0x1800e520d  test    eax, eax
0x1800e520f  jz      short loc_1800E522F
0x1800e5211  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5216  test    rcx, rcx
0x1800e5219  jz      short loc_1800E522A
0x1800e521b  mov     rax, [rcx]
0x1800e521e  mov     edx, r12d
0x1800e5221  mov     rax, [rax]
0x1800e5224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5229  nop
0x1800e522a  jmp     loc_1800E57BF
0x1800e522f  lea     r8, [rsi+80h]; void *
0x1800e5236  cmp     [r8+4], r12b
0x1800e523a  jnz     short loc_1800E526F
0x1800e523c  lea     rdx, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x1800e5243  mov     rcx, r14; this
0x1800e5246  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e524b  mov     edi, eax
0x1800e524d  test    eax, eax
0x1800e524f  jz      short loc_1800E526F
0x1800e5251  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5256  test    rcx, rcx
0x1800e5259  jz      short loc_1800E526A
0x1800e525b  mov     rax, [rcx]
0x1800e525e  mov     edx, r12d
0x1800e5261  mov     rax, [rax]
0x1800e5264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5269  nop
0x1800e526a  jmp     loc_1800E57BF
0x1800e526f  lea     r8, [rsi+88h]; void *
0x1800e5276  cmp     [r8+4], r12b
0x1800e527a  jnz     short loc_1800E52AF
0x1800e527c  lea     rdx, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x1800e5283  mov     rcx, r14; this
0x1800e5286  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e528b  mov     edi, eax
0x1800e528d  test    eax, eax
0x1800e528f  jz      short loc_1800E52AF
0x1800e5291  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5296  test    rcx, rcx
0x1800e5299  jz      short loc_1800E52AA
0x1800e529b  mov     rax, [rcx]
0x1800e529e  mov     edx, r12d
0x1800e52a1  mov     rax, [rax]
0x1800e52a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e52a9  nop
0x1800e52aa  jmp     loc_1800E57BF
0x1800e52af  lea     r8, [rsi+90h]; void *
0x1800e52b6  cmp     [r8+4], r12b
0x1800e52ba  jnz     short loc_1800E52EF
0x1800e52bc  lea     rdx, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x1800e52c3  mov     rcx, r14; this
0x1800e52c6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e52cb  mov     edi, eax
0x1800e52cd  test    eax, eax
0x1800e52cf  jz      short loc_1800E52EF
0x1800e52d1  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e52d6  test    rcx, rcx
0x1800e52d9  jz      short loc_1800E52EA
0x1800e52db  mov     rax, [rcx]
0x1800e52de  mov     edx, r12d
0x1800e52e1  mov     rax, [rax]
0x1800e52e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e52e9  nop
0x1800e52ea  jmp     loc_1800E57BF
0x1800e52ef  lea     r8, [rsi+98h]; void *
0x1800e52f6  cmp     [r8+4], r12b
0x1800e52fa  jnz     short loc_1800E532F
0x1800e52fc  lea     rdx, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x1800e5303  mov     rcx, r14; this
0x1800e5306  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e530b  mov     edi, eax
0x1800e530d  test    eax, eax
0x1800e530f  jz      short loc_1800E532F
0x1800e5311  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5316  test    rcx, rcx
0x1800e5319  jz      short loc_1800E532A
0x1800e531b  mov     rax, [rcx]
0x1800e531e  mov     edx, r12d
0x1800e5321  mov     rax, [rax]
0x1800e5324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5329  nop
0x1800e532a  jmp     loc_1800E57BF
0x1800e532f  lea     r8, [rsi+0A0h]; void *
0x1800e5336  cmp     [r8+4], r12b
0x1800e533a  jnz     short loc_1800E536F
0x1800e533c  lea     rdx, aConfigureremot; "ConfigureRemoteProcedureCallLocatorServ"...
0x1800e5343  mov     rcx, r14; this
0x1800e5346  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e534b  mov     edi, eax
0x1800e534d  test    eax, eax
0x1800e534f  jz      short loc_1800E536F
0x1800e5351  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5356  test    rcx, rcx
0x1800e5359  jz      short loc_1800E536A
0x1800e535b  mov     rax, [rcx]
0x1800e535e  mov     edx, r12d
0x1800e5361  mov     rax, [rax]
0x1800e5364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5369  nop
0x1800e536a  jmp     loc_1800E57BF
0x1800e536f  lea     r8, [rsi+0A8h]; void *
0x1800e5376  cmp     [r8+4], r12b
0x1800e537a  jnz     short loc_1800E53AF
0x1800e537c  lea     rdx, aConfigurerouti; "ConfigureRoutingAndRemoteAccessServiceS"...
0x1800e5383  mov     rcx, r14; this
0x1800e5386  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e538b  mov     edi, eax
0x1800e538d  test    eax, eax
0x1800e538f  jz      short loc_1800E53AF
0x1800e5391  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5396  test    rcx, rcx
0x1800e5399  jz      short loc_1800E53AA
0x1800e539b  mov     rax, [rcx]
0x1800e539e  mov     edx, r12d
0x1800e53a1  mov     rax, [rax]
0x1800e53a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e53a9  nop
0x1800e53aa  jmp     loc_1800E57BF
0x1800e53af  lea     r8, [rsi+0B0h]; void *
0x1800e53b6  cmp     [r8+4], r12b
0x1800e53ba  jnz     short loc_1800E53EF
0x1800e53bc  lea     rdx, aConfiguresimpl; "ConfigureSimpleTCPIPServicesStartupMode"
0x1800e53c3  mov     rcx, r14; this
0x1800e53c6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e53cb  mov     edi, eax
0x1800e53cd  test    eax, eax
0x1800e53cf  jz      short loc_1800E53EF
0x1800e53d1  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e53d6  test    rcx, rcx
0x1800e53d9  jz      short loc_1800E53EA
0x1800e53db  mov     rax, [rcx]
0x1800e53de  mov     edx, r12d
0x1800e53e1  mov     rax, [rax]
0x1800e53e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e53e9  nop
0x1800e53ea  jmp     loc_1800E57BF
0x1800e53ef  lea     r8, [rsi+0B8h]; void *
0x1800e53f6  cmp     [r8+4], r12b
0x1800e53fa  jnz     short loc_1800E542F
0x1800e53fc  lea     rdx, aConfigurespeci; "ConfigureSpecialAdministrationConsoleHe"...
0x1800e5403  mov     rcx, r14; this
0x1800e5406  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e540b  mov     edi, eax
0x1800e540d  test    eax, eax
0x1800e540f  jz      short loc_1800E542F
0x1800e5411  mov     rcx, [rsp+1E8h+var_1A8]
0x1800e5416  test    rcx, rcx
0x1800e5419  jz      short loc_1800E542A
0x1800e541b  mov     rax, [rcx]
  ... truncated ...
```
