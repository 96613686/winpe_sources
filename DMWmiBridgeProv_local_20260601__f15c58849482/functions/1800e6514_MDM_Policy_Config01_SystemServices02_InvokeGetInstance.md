# MDM_Policy_Config01_SystemServices02_InvokeGetInstance

- ea: `0x1800e6514`
- end: `0x1800e6db9`
- name: `MDM_Policy_Config01_SystemServices02_InvokeGetInstance`
- size: `2213`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e4f50`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800e6514`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800e67b3`
- `msvcrt!_wtoi` at `0x1800e67f0`
- `msvcrt!_wtoi` at `0x1800e682d`
- `msvcrt!_wtoi` at `0x1800e686a`
- `msvcrt!_wtoi` at `0x1800e68a7`
- `msvcrt!_wtoi` at `0x1800e68e4`
- `msvcrt!_wtoi` at `0x1800e6921`
- `msvcrt!_wtoi` at `0x1800e695e`
- `msvcrt!_wtoi` at `0x1800e699b`
- `msvcrt!_wtoi` at `0x1800e69d8`
- `msvcrt!_wtoi` at `0x1800e6a15`
- `msvcrt!_wtoi` at `0x1800e6a52`
- `msvcrt!_wtoi` at `0x1800e6a8f`
- `msvcrt!_wtoi` at `0x1800e6acc`
- `msvcrt!_wtoi` at `0x1800e6b09`
- `msvcrt!_wtoi` at `0x1800e6b46`
- `msvcrt!_wtoi` at `0x1800e6b83`
- `msvcrt!_wtoi` at `0x1800e6bc0`
- `msvcrt!_wtoi` at `0x1800e6bfd`
- `msvcrt!_wtoi` at `0x1800e6c3a`
- `msvcrt!_wtoi` at `0x1800e6c77`
- `msvcrt!_wtoi` at `0x1800e6cb4`
- `msvcrt!_wtoi` at `0x1800e67b3`
- `msvcrt!_wtoi` at `0x1800e67f0`
- `msvcrt!_wtoi` at `0x1800e682d`
- `msvcrt!_wtoi` at `0x1800e686a`
- `msvcrt!_wtoi` at `0x1800e68a7`
- `msvcrt!_wtoi` at `0x1800e68e4`
- `msvcrt!_wtoi` at `0x1800e6921`
- `msvcrt!_wtoi` at `0x1800e695e`
- `msvcrt!_wtoi` at `0x1800e699b`
- `msvcrt!_wtoi` at `0x1800e69d8`
- `msvcrt!_wtoi` at `0x1800e6a15`
- `msvcrt!_wtoi` at `0x1800e6a52`
- `msvcrt!_wtoi` at `0x1800e6a8f`
- `msvcrt!_wtoi` at `0x1800e6acc`
- `msvcrt!_wtoi` at `0x1800e6b09`
- `msvcrt!_wtoi` at `0x1800e6b46`
- `msvcrt!_wtoi` at `0x1800e6b83`
- `msvcrt!_wtoi` at `0x1800e6bc0`
- `msvcrt!_wtoi` at `0x1800e6bfd`
- `msvcrt!_wtoi` at `0x1800e6c3a`
- `msvcrt!_wtoi` at `0x1800e6c77`
- `msvcrt!_wtoi` at `0x1800e6cb4`

## string_xrefs

- `0x1800e6796`: `ConfigureComputerBrowserServiceStartupMode`
- `0x1800e67d3`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x1800e6810`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x1800e684d`: `ConfigureIISAdminServiceStartupMode`
- `0x1800e688a`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x1800e68c7`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x1800e6904`: `ConfigureLxssManagerServiceStartupMode`
- `0x1800e6941`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x1800e697e`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x1800e69bb`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x1800e69f8`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x1800e6a35`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x1800e6a72`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x1800e6aaf`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x1800e6aec`: `ConfigureWebManagementServiceStartupMode`
- `0x1800e6b29`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x1800e6b66`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x1800e6ba3`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x1800e6be0`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x1800e6c1d`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x1800e6c5a`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x1800e6c97`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x1800e6583`: `MDM_Policy_Config01_SystemServices02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_SystemServices02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  MI_Result v5; // r14d
  WmiRequestHandler *v6; // rdi
  wchar_t *String; // [rsp+40h] [rbp-1B8h] BYREF
  char v9; // [rsp+48h] [rbp-1B0h]
  WmiRequestHandler *v10; // [rsp+50h] [rbp-1A8h] BYREF
  _QWORD v11[5]; // [rsp+58h] [rbp-1A0h] BYREF
  char v12; // [rsp+80h] [rbp-178h]
  int v13; // [rsp+88h] [rbp-170h] BYREF
  char v14; // [rsp+8Ch] [rbp-16Ch]
  _BYTE v15[16]; // [rsp+90h] [rbp-168h] BYREF
  _DWORD v16[4]; // [rsp+A0h] [rbp-158h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-148h] BYREF
  int v18; // [rsp+110h] [rbp-E8h]
  char v19; // [rsp+114h] [rbp-E4h]
  int v20; // [rsp+118h] [rbp-E0h]
  char v21; // [rsp+11Ch] [rbp-DCh]
  int v22; // [rsp+120h] [rbp-D8h]
  char v23; // [rsp+124h] [rbp-D4h]
  int v24; // [rsp+128h] [rbp-D0h]
  char v25; // [rsp+12Ch] [rbp-CCh]
  int v26; // [rsp+130h] [rbp-C8h]
  char v27; // [rsp+134h] [rbp-C4h]
  int v28; // [rsp+138h] [rbp-C0h]
  char v29; // [rsp+13Ch] [rbp-BCh]
  int v30; // [rsp+140h] [rbp-B8h]
  char v31; // [rsp+144h] [rbp-B4h]
  int v32; // [rsp+148h] [rbp-B0h]
  char v33; // [rsp+14Ch] [rbp-ACh]
  int v34; // [rsp+150h] [rbp-A8h]
  char v35; // [rsp+154h] [rbp-A4h]
  int v36; // [rsp+158h] [rbp-A0h]
  char v37; // [rsp+15Ch] [rbp-9Ch]
  int v38; // [rsp+160h] [rbp-98h]
  char v39; // [rsp+164h] [rbp-94h]
  int v40; // [rsp+168h] [rbp-90h]
  char v41; // [rsp+16Ch] [rbp-8Ch]
  int v42; // [rsp+170h] [rbp-88h]
  char v43; // [rsp+174h] [rbp-84h]
  int v44; // [rsp+178h] [rbp-80h]
  char v45; // [rsp+17Ch] [rbp-7Ch]
  int v46; // [rsp+180h] [rbp-78h]
  char v47; // [rsp+184h] [rbp-74h]
  int v48; // [rsp+188h] [rbp-70h]
  char v49; // [rsp+18Ch] [rbp-6Ch]
  int v50; // [rsp+190h] [rbp-68h]
  char v51; // [rsp+194h] [rbp-64h]
  int v52; // [rsp+198h] [rbp-60h]
  char v53; // [rsp+19Ch] [rbp-5Ch]
  int v54; // [rsp+1A0h] [rbp-58h]
  char v55; // [rsp+1A4h] [rbp-54h]
  int v56; // [rsp+1A8h] [rbp-50h]
  char v57; // [rsp+1ACh] [rbp-4Ch]
  int v58; // [rsp+1B0h] [rbp-48h]
  char v59; // [rsp+1B4h] [rbp-44h]
  int v60; // [rsp+1B8h] [rbp-40h]
  char v61; // [rsp+1BCh] [rbp-3Ch]

  String = 0;
  memset_0(&instance, 0, 0x110u);
  v13 = 0;
  v14 = 0;
  v11[0] = &TelemetryEventWriter::`vftable';
  v11[1] = &v13;
  v11[2] = "MDM_Policy_Config01_SystemServices02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180360231,
      v15,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    v5 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_95;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v11,
    "GetInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v10 = 0;
  v5 = (unsigned int)CreateRequestHandlerInstance(
                       self,
                       a2[1].serverName,
                       a2[1].ft,
                       &MDM_Policy_Config01_SystemServices02_NodeList,
                       24,
                       0,
                       &v10);
  if ( v5 == MI_RESULT_OK )
  {
    v11[4] = &v10;
    v12 = 1;
    v6 = v10;
    if ( !v10 )
    {
      v5 = MI_RESULT_FAILED;
      goto LABEL_95;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_SystemServices02_NodeList,
      0x18u);
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_95;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_95;
    }
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_95;
      goto LABEL_24;
    }
    v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_SystemServices02_rtti, &instance);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_95;
      goto LABEL_24;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureComputerBrowserServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureHomeGroupListenerServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureHomeGroupProviderServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureIISAdminServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureInfraredMonitorServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureInternetConnectionSharingServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureLxssManagerServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureMicrosoftFTPServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureRemoteProcedureCallLocatorServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v34 = _wtoi(String);
      v35 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureRoutingAndRemoteAccessServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v36 = _wtoi(String);
      v37 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureSimpleTCPIPServicesStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v38 = _wtoi(String);
      v39 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureSpecialAdministrationConsoleHelperServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v40 = _wtoi(String);
      v41 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureSSDPDiscoveryServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v42 = _wtoi(String);
      v43 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureUPnPDeviceHostServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v44 = _wtoi(String);
      v45 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureWebManagementServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v46 = _wtoi(String);
      v47 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v48 = _wtoi(String);
      v49 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureWindowsMobileHotspotServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v50 = _wtoi(String);
      v51 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureWorldWideWebPublishingServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v52 = _wtoi(String);
      v53 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureXboxAccessoryManagementServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v54 = _wtoi(String);
      v55 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureXboxLiveAuthManagerServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v56 = _wtoi(String);
      v57 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureXboxLiveGameSaveServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v58 = _wtoi(String);
      v59 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureXboxLiveNetworkingServiceStartupMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v60 = _wtoi(String);
      v61 = 1;
    }
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v10 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_95:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18034B925,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800e6514  mov     [rsp+arg_10], rbx
0x1800e6519  push    rsi
0x1800e651a  push    rdi
0x1800e651b  push    r12
0x1800e651d  push    r14
0x1800e651f  push    r15
0x1800e6521  sub     rsp, 1D0h
0x1800e6528  mov     rax, cs:__security_cookie
0x1800e652f  xor     rax, rsp
0x1800e6532  mov     [rsp+1F8h+var_38], rax
0x1800e653a  mov     rsi, rdx
0x1800e653d  mov     r15, rcx
0x1800e6540  xor     ebx, ebx
0x1800e6542  mov     [rsp+1F8h+String], rbx
0x1800e6547  xor     edx, edx; Val
0x1800e6549  mov     r8d, 110h; Size
0x1800e654f  lea     rcx, [rsp+1F8h+instance]; void *
0x1800e6557  call    memset_0
0x1800e655c  mov     [rsp+1F8h+var_170], ebx
0x1800e6563  mov     [rsp+1F8h+var_16C], bl
0x1800e656a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e6571  mov     [rsp+1F8h+var_1A0], rax
0x1800e6576  lea     rax, [rsp+1F8h+var_170]
0x1800e657e  mov     [rsp+1F8h+var_198], rax
0x1800e6583  lea     rax, aMdmPolicyConfi_72; "MDM_Policy_Config01_SystemServices02"
0x1800e658a  mov     [rsp+1F8h+var_190], rax
0x1800e658f  lea     rcx, [rsp+1F8h+var_170]
0x1800e6597  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e659c  mov     eax, cs:dword_180380B68
0x1800e65a2  cmp     eax, 5
0x1800e65a5  jbe     short loc_1800E6616
0x1800e65a7  mov     rdx, 200000000000h
0x1800e65b1  lea     rcx, dword_180380B68
0x1800e65b8  call    _tlgKeywordOn
0x1800e65bd  test    al, al
0x1800e65bf  jz      short loc_1800E6616
0x1800e65c1  cmp     [rsp+1F8h+var_16C], bl
0x1800e65c8  jz      short loc_1800E65F8
0x1800e65ca  cmp     [rsp+1F8h+var_158], ebx
0x1800e65d1  jnz     short loc_1800E65EE
0x1800e65d3  cmp     [rsp+1F8h+var_154], ebx
0x1800e65da  jnz     short loc_1800E65EE
0x1800e65dc  cmp     [rsp+1F8h+var_150], ebx
0x1800e65e3  jnz     short loc_1800E65EE
0x1800e65e5  cmp     [rsp+1F8h+var_14C], ebx
0x1800e65ec  jz      short loc_1800E65F8
0x1800e65ee  lea     r9, [rsp+1F8h+var_158]
0x1800e65f6  jmp     short loc_1800E65FB
0x1800e65f8  mov     r9, rbx
0x1800e65fb  lea     r8, [rsp+1F8h+var_168]
0x1800e6603  lea     rdx, byte_180360231
0x1800e660a  lea     rcx, dword_180380B68
0x1800e6611  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e6616  cmp     [rsi+48h], bl
0x1800e6619  jz      loc_1800E6D17
0x1800e661f  mov     [rsp+1F8h+var_1B0], bl
0x1800e6623  cmp     [rsi+58h], bl
0x1800e6626  jz      loc_1800E6D17
0x1800e662c  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800e6630  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800e6634  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800e663b  lea     rcx, [rsp+1F8h+var_1A0]; this
0x1800e6640  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800e6645  nop
0x1800e6646  mov     [rsp+1F8h+var_1A8], rbx
0x1800e664b  lea     rax, [rsp+1F8h+var_1A8]
0x1800e6650  mov     [rsp+1F8h+var_1C8], rax
0x1800e6655  mov     [rsp+1F8h+var_1D0], ebx
0x1800e6659  mov     [rsp+1F8h+var_1D8], 18h
0x1800e6661  lea     r9, ?MDM_Policy_Config01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_SystemServices02_NodeList
0x1800e6668  mov     r8, [rsi+40h]
0x1800e666c  mov     rdx, [rsi+50h]
0x1800e6670  mov     rcx, r15
0x1800e6673  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e6678  mov     r14d, eax
0x1800e667b  test    eax, eax
0x1800e667d  jz      short loc_1800E6684
0x1800e667f  jmp     loc_1800E6D1D
0x1800e6684  lea     rax, [rsp+1F8h+var_1A8]
0x1800e6689  mov     [rsp+1F8h+var_180], rax
0x1800e668e  mov     r12d, 1
0x1800e6694  mov     [rsp+1F8h+var_178], r12b
0x1800e669c  mov     rdi, [rsp+1F8h+var_1A8]
0x1800e66a1  test    rdi, rdi
0x1800e66a4  jnz     short loc_1800E66AE
0x1800e66a6  mov     r14d, r12d
0x1800e66a9  jmp     loc_1800E6D1D
0x1800e66ae  mov     r9d, 18h; unsigned int
0x1800e66b4  lea     r8, ?MDM_Policy_Config01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800e66bb  mov     rdx, rsi; struct _MI_Instance *
0x1800e66be  mov     rcx, rdi; this
0x1800e66c1  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800e66c6  mov     rax, [rdi]
0x1800e66c9  mov     rcx, rdi
0x1800e66cc  mov     rax, [rax+10h]
0x1800e66d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e66d5  mov     r14d, eax
0x1800e66d8  test    eax, eax
0x1800e66da  jz      short loc_1800E66FA
0x1800e66dc  mov     rcx, [rsp+1F8h+var_1A8]
0x1800e66e1  test    rcx, rcx
0x1800e66e4  jz      short loc_1800E66F5
0x1800e66e6  mov     rax, [rcx]
0x1800e66e9  mov     edx, r12d
0x1800e66ec  mov     rax, [rax]
0x1800e66ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e66f4  nop
0x1800e66f5  jmp     loc_1800E6D1D
0x1800e66fa  mov     rax, [rdi]
0x1800e66fd  mov     rcx, rdi
0x1800e6700  mov     rax, [rax+8]
0x1800e6704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6709  mov     r14d, eax
0x1800e670c  test    eax, eax
0x1800e670e  jz      short loc_1800E672E
0x1800e6710  mov     rcx, [rsp+1F8h+var_1A8]
0x1800e6715  test    rcx, rcx
0x1800e6718  jz      short loc_1800E6729
0x1800e671a  mov     rax, [rcx]
0x1800e671d  mov     edx, r12d
0x1800e6720  mov     rax, [rax]
0x1800e6723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6728  nop
0x1800e6729  jmp     loc_1800E6D1D
0x1800e672e  lea     r8, [rsp+1F8h+instance]; instance
0x1800e6736  lea     rdx, MDM_Policy_Config01_SystemServices02_rtti; classDecl
0x1800e673d  mov     rcx, r15; context
0x1800e6740  call    MI_Context_ConstructInstance
0x1800e6745  mov     r14d, eax
0x1800e6748  test    eax, eax
0x1800e674a  jz      short loc_1800E676A
0x1800e674c  mov     rcx, [rsp+1F8h+var_1A8]
0x1800e6751  test    rcx, rcx
0x1800e6754  jz      short loc_1800E6765
0x1800e6756  mov     rax, [rcx]
0x1800e6759  mov     edx, r12d
0x1800e675c  mov     rax, [rax]
0x1800e675f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6764  nop
0x1800e6765  jmp     loc_1800E6D1D
0x1800e676a  mov     [rsp+1F8h+var_1B0], r12b
0x1800e676f  mov     rdx, [rsi+40h]
0x1800e6773  lea     rcx, [rsp+1F8h+instance]
0x1800e677b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800e6780  mov     rdx, [rsi+50h]
0x1800e6784  lea     rcx, [rsp+1F8h+instance]
0x1800e678c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800e6791  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e6796  lea     rdx, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x1800e679d  mov     rcx, rdi; this
0x1800e67a0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e67a5  test    eax, eax
0x1800e67a7  jnz     short loc_1800E67CE
0x1800e67a9  mov     rcx, [rsp+1F8h+String]; String
0x1800e67ae  test    rcx, rcx
0x1800e67b1  jz      short loc_1800E67CE
0x1800e67b3  call    cs:__imp__wtoi
0x1800e67ba  nop     dword ptr [rax+rax+00h]
0x1800e67bf  mov     [rsp+1F8h+var_E8], eax
0x1800e67c6  mov     [rsp+1F8h+var_E4], r12b
0x1800e67ce  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e67d3  lea     rdx, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x1800e67da  mov     rcx, rdi; this
0x1800e67dd  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e67e2  test    eax, eax
0x1800e67e4  jnz     short loc_1800E680B
0x1800e67e6  mov     rcx, [rsp+1F8h+String]; String
0x1800e67eb  test    rcx, rcx
0x1800e67ee  jz      short loc_1800E680B
0x1800e67f0  call    cs:__imp__wtoi
0x1800e67f7  nop     dword ptr [rax+rax+00h]
0x1800e67fc  mov     [rsp+1F8h+var_E0], eax
0x1800e6803  mov     [rsp+1F8h+var_DC], r12b
0x1800e680b  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e6810  lea     rdx, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x1800e6817  mov     rcx, rdi; this
0x1800e681a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e681f  test    eax, eax
0x1800e6821  jnz     short loc_1800E6848
0x1800e6823  mov     rcx, [rsp+1F8h+String]; String
0x1800e6828  test    rcx, rcx
0x1800e682b  jz      short loc_1800E6848
0x1800e682d  call    cs:__imp__wtoi
0x1800e6834  nop     dword ptr [rax+rax+00h]
0x1800e6839  mov     [rsp+1F8h+var_D8], eax
0x1800e6840  mov     [rsp+1F8h+var_D4], r12b
0x1800e6848  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e684d  lea     rdx, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x1800e6854  mov     rcx, rdi; this
0x1800e6857  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e685c  test    eax, eax
0x1800e685e  jnz     short loc_1800E6885
0x1800e6860  mov     rcx, [rsp+1F8h+String]; String
0x1800e6865  test    rcx, rcx
0x1800e6868  jz      short loc_1800E6885
0x1800e686a  call    cs:__imp__wtoi
0x1800e6871  nop     dword ptr [rax+rax+00h]
0x1800e6876  mov     [rsp+1F8h+var_D0], eax
0x1800e687d  mov     [rsp+1F8h+var_CC], r12b
0x1800e6885  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e688a  lea     rdx, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x1800e6891  mov     rcx, rdi; this
0x1800e6894  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e6899  test    eax, eax
0x1800e689b  jnz     short loc_1800E68C2
0x1800e689d  mov     rcx, [rsp+1F8h+String]; String
0x1800e68a2  test    rcx, rcx
0x1800e68a5  jz      short loc_1800E68C2
0x1800e68a7  call    cs:__imp__wtoi
0x1800e68ae  nop     dword ptr [rax+rax+00h]
0x1800e68b3  mov     [rsp+1F8h+var_C8], eax
0x1800e68ba  mov     [rsp+1F8h+var_C4], r12b
0x1800e68c2  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e68c7  lea     rdx, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x1800e68ce  mov     rcx, rdi; this
0x1800e68d1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e68d6  test    eax, eax
0x1800e68d8  jnz     short loc_1800E68FF
0x1800e68da  mov     rcx, [rsp+1F8h+String]; String
0x1800e68df  test    rcx, rcx
0x1800e68e2  jz      short loc_1800E68FF
0x1800e68e4  call    cs:__imp__wtoi
0x1800e68eb  nop     dword ptr [rax+rax+00h]
0x1800e68f0  mov     [rsp+1F8h+var_C0], eax
0x1800e68f7  mov     [rsp+1F8h+var_BC], r12b
0x1800e68ff  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e6904  lea     rdx, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x1800e690b  mov     rcx, rdi; this
0x1800e690e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e6913  test    eax, eax
0x1800e6915  jnz     short loc_1800E693C
0x1800e6917  mov     rcx, [rsp+1F8h+String]; String
0x1800e691c  test    rcx, rcx
0x1800e691f  jz      short loc_1800E693C
0x1800e6921  call    cs:__imp__wtoi
0x1800e6928  nop     dword ptr [rax+rax+00h]
0x1800e692d  mov     [rsp+1F8h+var_B8], eax
0x1800e6934  mov     [rsp+1F8h+var_B4], r12b
0x1800e693c  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e6941  lea     rdx, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x1800e6948  mov     rcx, rdi; this
0x1800e694b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e6950  test    eax, eax
0x1800e6952  jnz     short loc_1800E6979
0x1800e6954  mov     rcx, [rsp+1F8h+String]; String
0x1800e6959  test    rcx, rcx
0x1800e695c  jz      short loc_1800E6979
0x1800e695e  call    cs:__imp__wtoi
0x1800e6965  nop     dword ptr [rax+rax+00h]
0x1800e696a  mov     [rsp+1F8h+var_B0], eax
0x1800e6971  mov     [rsp+1F8h+var_AC], r12b
0x1800e6979  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e697e  lea     rdx, aConfigureremot; "ConfigureRemoteProcedureCallLocatorServ"...
0x1800e6985  mov     rcx, rdi; this
0x1800e6988  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e698d  test    eax, eax
0x1800e698f  jnz     short loc_1800E69B6
0x1800e6991  mov     rcx, [rsp+1F8h+String]; String
0x1800e6996  test    rcx, rcx
0x1800e6999  jz      short loc_1800E69B6
0x1800e699b  call    cs:__imp__wtoi
0x1800e69a2  nop     dword ptr [rax+rax+00h]
0x1800e69a7  mov     [rsp+1F8h+var_A8], eax
0x1800e69ae  mov     [rsp+1F8h+var_A4], r12b
0x1800e69b6  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e69bb  lea     rdx, aConfigurerouti; "ConfigureRoutingAndRemoteAccessServiceS"...
0x1800e69c2  mov     rcx, rdi; this
0x1800e69c5  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e69ca  test    eax, eax
0x1800e69cc  jnz     short loc_1800E69F3
0x1800e69ce  mov     rcx, [rsp+1F8h+String]; String
0x1800e69d3  test    rcx, rcx
0x1800e69d6  jz      short loc_1800E69F3
0x1800e69d8  call    cs:__imp__wtoi
0x1800e69df  nop     dword ptr [rax+rax+00h]
0x1800e69e4  mov     [rsp+1F8h+var_A0], eax
0x1800e69eb  mov     [rsp+1F8h+var_9C], r12b
0x1800e69f3  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e69f8  lea     rdx, aConfiguresimpl; "ConfigureSimpleTCPIPServicesStartupMode"
0x1800e69ff  mov     rcx, rdi; this
0x1800e6a02  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e6a07  test    eax, eax
0x1800e6a09  jnz     short loc_1800E6A30
0x1800e6a0b  mov     rcx, [rsp+1F8h+String]; String
0x1800e6a10  test    rcx, rcx
0x1800e6a13  jz      short loc_1800E6A30
0x1800e6a15  call    cs:__imp__wtoi
0x1800e6a1c  nop     dword ptr [rax+rax+00h]
0x1800e6a21  mov     [rsp+1F8h+var_98], eax
0x1800e6a28  mov     [rsp+1F8h+var_94], r12b
0x1800e6a30  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e6a35  lea     rdx, aConfigurespeci; "ConfigureSpecialAdministrationConsoleHe"...
0x1800e6a3c  mov     rcx, rdi; this
0x1800e6a3f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e6a44  test    eax, eax
0x1800e6a46  jnz     short loc_1800E6A6D
0x1800e6a48  mov     rcx, [rsp+1F8h+String]; String
0x1800e6a4d  test    rcx, rcx
0x1800e6a50  jz      short loc_1800E6A6D
0x1800e6a52  call    cs:__imp__wtoi
  ... truncated ...
```
