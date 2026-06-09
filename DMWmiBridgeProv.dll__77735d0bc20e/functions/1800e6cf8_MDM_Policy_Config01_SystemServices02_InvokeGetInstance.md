# MDM_Policy_Config01_SystemServices02_InvokeGetInstance

- ea: `0x1800e6cf8`
- end: `0x1800e7518`
- name: `MDM_Policy_Config01_SystemServices02_InvokeGetInstance`
- size: `2080`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e57b0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800e6cf8`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800e6f97`
- `msvcrt!_wtoi` at `0x1800e6fce`
- `msvcrt!_wtoi` at `0x1800e7005`
- `msvcrt!_wtoi` at `0x1800e703c`
- `msvcrt!_wtoi` at `0x1800e7073`
- `msvcrt!_wtoi` at `0x1800e70aa`
- `msvcrt!_wtoi` at `0x1800e70e1`
- `msvcrt!_wtoi` at `0x1800e7118`
- `msvcrt!_wtoi` at `0x1800e714f`
- `msvcrt!_wtoi` at `0x1800e7186`
- `msvcrt!_wtoi` at `0x1800e71bd`
- `msvcrt!_wtoi` at `0x1800e71f4`
- `msvcrt!_wtoi` at `0x1800e722b`
- `msvcrt!_wtoi` at `0x1800e7262`
- `msvcrt!_wtoi` at `0x1800e7299`
- `msvcrt!_wtoi` at `0x1800e72d0`
- `msvcrt!_wtoi` at `0x1800e7307`
- `msvcrt!_wtoi` at `0x1800e733e`
- `msvcrt!_wtoi` at `0x1800e7375`
- `msvcrt!_wtoi` at `0x1800e73ac`
- `msvcrt!_wtoi` at `0x1800e73e3`
- `msvcrt!_wtoi` at `0x1800e741a`
- `msvcrt!_wtoi` at `0x1800e6f97`
- `msvcrt!_wtoi` at `0x1800e6fce`
- `msvcrt!_wtoi` at `0x1800e7005`
- `msvcrt!_wtoi` at `0x1800e703c`
- `msvcrt!_wtoi` at `0x1800e7073`
- `msvcrt!_wtoi` at `0x1800e70aa`
- `msvcrt!_wtoi` at `0x1800e70e1`
- `msvcrt!_wtoi` at `0x1800e7118`
- `msvcrt!_wtoi` at `0x1800e714f`
- `msvcrt!_wtoi` at `0x1800e7186`
- `msvcrt!_wtoi` at `0x1800e71bd`
- `msvcrt!_wtoi` at `0x1800e71f4`
- `msvcrt!_wtoi` at `0x1800e722b`
- `msvcrt!_wtoi` at `0x1800e7262`
- `msvcrt!_wtoi` at `0x1800e7299`
- `msvcrt!_wtoi` at `0x1800e72d0`
- `msvcrt!_wtoi` at `0x1800e7307`
- `msvcrt!_wtoi` at `0x1800e733e`
- `msvcrt!_wtoi` at `0x1800e7375`
- `msvcrt!_wtoi` at `0x1800e73ac`
- `msvcrt!_wtoi` at `0x1800e73e3`
- `msvcrt!_wtoi` at `0x1800e741a`

## string_xrefs

- `0x1800e6f7a`: `ConfigureComputerBrowserServiceStartupMode`
- `0x1800e6fb1`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x1800e6fe8`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x1800e701f`: `ConfigureIISAdminServiceStartupMode`
- `0x1800e7056`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x1800e708d`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x1800e70c4`: `ConfigureLxssManagerServiceStartupMode`
- `0x1800e70fb`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x1800e7132`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x1800e7169`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x1800e71a0`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x1800e71d7`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x1800e720e`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x1800e7245`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x1800e727c`: `ConfigureWebManagementServiceStartupMode`
- `0x1800e72b3`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x1800e72ea`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x1800e7321`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x1800e7358`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x1800e738f`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x1800e73c6`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x1800e73fd`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x1800e6d67`: `MDM_Policy_Config01_SystemServices02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_SystemServices02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // r14d
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
    v5 = 4;
    goto LABEL_95;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v11,
    "GetInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v10 = 0;
  v5 = CreateRequestHandlerInstance(
         (__int64)self,
         (wchar_t *)a2[1].serverName,
         (const unsigned __int16 *)a2[1].ft,
         (struct WmiNodeInfo *)&MDM_Policy_Config01_SystemServices02_NodeList,
         0x18u,
         0,
         &v10);
  if ( !v5 )
  {
    v11[4] = &v10;
    v12 = 1;
    v6 = v10;
    if ( !v10 )
    {
      v5 = 1;
      goto LABEL_95;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_SystemServices02_NodeList,
      0x18u);
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_95;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_95;
    }
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureComputerBrowserServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureHomeGroupListenerServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureHomeGroupProviderServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureIISAdminServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureInfraredMonitorServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureInternetConnectionSharingServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureLxssManagerServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureMicrosoftFTPServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureRemoteProcedureCallLocatorServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v34 = _wtoi(String);
      v35 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureRoutingAndRemoteAccessServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v36 = _wtoi(String);
      v37 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureSimpleTCPIPServicesStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v38 = _wtoi(String);
      v39 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureSpecialAdministrationConsoleHelperServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v40 = _wtoi(String);
      v41 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureSSDPDiscoveryServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v42 = _wtoi(String);
      v43 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureUPnPDeviceHostServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v44 = _wtoi(String);
      v45 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureWebManagementServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v46 = _wtoi(String);
      v47 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v48 = _wtoi(String);
      v49 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureWindowsMobileHotspotServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v50 = _wtoi(String);
      v51 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureWorldWideWebPublishingServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v52 = _wtoi(String);
      v53 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureXboxAccessoryManagementServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v54 = _wtoi(String);
      v55 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureXboxLiveAuthManagerServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v56 = _wtoi(String);
      v57 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureXboxLiveGameSaveServiceStartupMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v58 = _wtoi(String);
      v59 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureXboxLiveNetworkingServiceStartupMode",
                          (const unsigned __int16 **)&String)
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
  return v5;
}

```

## disassembly

```asm
0x1800e6cf8  mov     [rsp+arg_10], rbx
0x1800e6cfd  push    rsi
0x1800e6cfe  push    rdi
0x1800e6cff  push    r12
0x1800e6d01  push    r14
0x1800e6d03  push    r15
0x1800e6d05  sub     rsp, 1D0h
0x1800e6d0c  mov     rax, cs:__security_cookie
0x1800e6d13  xor     rax, rsp
0x1800e6d16  mov     [rsp+1F8h+var_38], rax
0x1800e6d1e  mov     rsi, rdx
0x1800e6d21  mov     r15, rcx
0x1800e6d24  xor     ebx, ebx
0x1800e6d26  mov     [rsp+1F8h+String], rbx
0x1800e6d2b  xor     edx, edx; Val
0x1800e6d2d  mov     r8d, 110h; Size
0x1800e6d33  lea     rcx, [rsp+1F8h+instance]; void *
0x1800e6d3b  call    memset_0
0x1800e6d40  mov     [rsp+1F8h+var_170], ebx
0x1800e6d47  mov     [rsp+1F8h+var_16C], bl
0x1800e6d4e  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e6d55  mov     [rsp+1F8h+var_1A0], rax
0x1800e6d5a  lea     rax, [rsp+1F8h+var_170]
0x1800e6d62  mov     [rsp+1F8h+var_198], rax
0x1800e6d67  lea     rax, aMdmPolicyConfi_72; "MDM_Policy_Config01_SystemServices02"
0x1800e6d6e  mov     [rsp+1F8h+var_190], rax
0x1800e6d73  lea     rcx, [rsp+1F8h+var_170]
0x1800e6d7b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e6d80  mov     eax, cs:dword_180380B68
0x1800e6d86  cmp     eax, 5
0x1800e6d89  jbe     short loc_1800E6DFA
0x1800e6d8b  mov     rdx, 200000000000h
0x1800e6d95  lea     rcx, dword_180380B68
0x1800e6d9c  call    _tlgKeywordOn
0x1800e6da1  test    al, al
0x1800e6da3  jz      short loc_1800E6DFA
0x1800e6da5  cmp     [rsp+1F8h+var_16C], bl
0x1800e6dac  jz      short loc_1800E6DDC
0x1800e6dae  cmp     [rsp+1F8h+var_158], ebx
0x1800e6db5  jnz     short loc_1800E6DD2
0x1800e6db7  cmp     [rsp+1F8h+var_154], ebx
0x1800e6dbe  jnz     short loc_1800E6DD2
0x1800e6dc0  cmp     [rsp+1F8h+var_150], ebx
0x1800e6dc7  jnz     short loc_1800E6DD2
0x1800e6dc9  cmp     [rsp+1F8h+var_14C], ebx
0x1800e6dd0  jz      short loc_1800E6DDC
0x1800e6dd2  lea     r9, [rsp+1F8h+var_158]
0x1800e6dda  jmp     short loc_1800E6DDF
0x1800e6ddc  mov     r9, rbx
0x1800e6ddf  lea     r8, [rsp+1F8h+var_168]
0x1800e6de7  lea     rdx, byte_180360231
0x1800e6dee  lea     rcx, dword_180380B68
0x1800e6df5  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e6dfa  cmp     [rsi+48h], bl
0x1800e6dfd  jz      loc_1800E7477
0x1800e6e03  mov     [rsp+1F8h+var_1B0], bl
0x1800e6e07  cmp     [rsi+58h], bl
0x1800e6e0a  jz      loc_1800E7477
0x1800e6e10  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800e6e14  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800e6e18  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800e6e1f  lea     rcx, [rsp+1F8h+var_1A0]; this
0x1800e6e24  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800e6e29  nop
0x1800e6e2a  mov     [rsp+1F8h+var_1A8], rbx
0x1800e6e2f  lea     rax, [rsp+1F8h+var_1A8]
0x1800e6e34  mov     [rsp+1F8h+var_1C8], rax
0x1800e6e39  mov     [rsp+1F8h+var_1D0], ebx
0x1800e6e3d  mov     [rsp+1F8h+var_1D8], 18h
0x1800e6e45  lea     r9, ?MDM_Policy_Config01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_SystemServices02_NodeList
0x1800e6e4c  mov     r8, [rsi+40h]
0x1800e6e50  mov     rdx, [rsi+50h]
0x1800e6e54  mov     rcx, r15
0x1800e6e57  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e6e5c  mov     r14d, eax
0x1800e6e5f  test    eax, eax
0x1800e6e61  jz      short loc_1800E6E68
0x1800e6e63  jmp     loc_1800E747D
0x1800e6e68  lea     rax, [rsp+1F8h+var_1A8]
0x1800e6e6d  mov     [rsp+1F8h+var_180], rax
0x1800e6e72  mov     r12d, 1
0x1800e6e78  mov     [rsp+1F8h+var_178], r12b
0x1800e6e80  mov     rdi, [rsp+1F8h+var_1A8]
0x1800e6e85  test    rdi, rdi
0x1800e6e88  jnz     short loc_1800E6E92
0x1800e6e8a  mov     r14d, r12d
0x1800e6e8d  jmp     loc_1800E747D
0x1800e6e92  mov     r9d, 18h; unsigned int
0x1800e6e98  lea     r8, ?MDM_Policy_Config01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800e6e9f  mov     rdx, rsi; struct _MI_Instance *
0x1800e6ea2  mov     rcx, rdi; this
0x1800e6ea5  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800e6eaa  mov     rax, [rdi]
0x1800e6ead  mov     rcx, rdi
0x1800e6eb0  mov     rax, [rax+10h]
0x1800e6eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6eb9  mov     r14d, eax
0x1800e6ebc  test    eax, eax
0x1800e6ebe  jz      short loc_1800E6EDE
0x1800e6ec0  mov     rcx, [rsp+1F8h+var_1A8]
0x1800e6ec5  test    rcx, rcx
0x1800e6ec8  jz      short loc_1800E6ED9
0x1800e6eca  mov     rax, [rcx]
0x1800e6ecd  mov     edx, r12d
0x1800e6ed0  mov     rax, [rax]
0x1800e6ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6ed8  nop
0x1800e6ed9  jmp     loc_1800E747D
0x1800e6ede  mov     rax, [rdi]
0x1800e6ee1  mov     rcx, rdi
0x1800e6ee4  mov     rax, [rax+8]
0x1800e6ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6eed  mov     r14d, eax
0x1800e6ef0  test    eax, eax
0x1800e6ef2  jz      short loc_1800E6F12
0x1800e6ef4  mov     rcx, [rsp+1F8h+var_1A8]
0x1800e6ef9  test    rcx, rcx
0x1800e6efc  jz      short loc_1800E6F0D
0x1800e6efe  mov     rax, [rcx]
0x1800e6f01  mov     edx, r12d
0x1800e6f04  mov     rax, [rax]
0x1800e6f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6f0c  nop
0x1800e6f0d  jmp     loc_1800E747D
0x1800e6f12  lea     r8, [rsp+1F8h+instance]; instance
0x1800e6f1a  lea     rdx, MDM_Policy_Config01_SystemServices02_rtti; classDecl
0x1800e6f21  mov     rcx, r15; context
0x1800e6f24  call    MI_Context_ConstructInstance
0x1800e6f29  mov     r14d, eax
0x1800e6f2c  test    eax, eax
0x1800e6f2e  jz      short loc_1800E6F4E
0x1800e6f30  mov     rcx, [rsp+1F8h+var_1A8]
0x1800e6f35  test    rcx, rcx
0x1800e6f38  jz      short loc_1800E6F49
0x1800e6f3a  mov     rax, [rcx]
0x1800e6f3d  mov     edx, r12d
0x1800e6f40  mov     rax, [rax]
0x1800e6f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6f48  nop
0x1800e6f49  jmp     loc_1800E747D
0x1800e6f4e  mov     [rsp+1F8h+var_1B0], r12b
0x1800e6f53  mov     rdx, [rsi+40h]
0x1800e6f57  lea     rcx, [rsp+1F8h+instance]
0x1800e6f5f  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800e6f64  mov     rdx, [rsi+50h]
0x1800e6f68  lea     rcx, [rsp+1F8h+instance]
0x1800e6f70  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800e6f75  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e6f7a  lea     rdx, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x1800e6f81  mov     rcx, rdi; this
0x1800e6f84  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e6f89  test    eax, eax
0x1800e6f8b  jnz     short loc_1800E6FAC
0x1800e6f8d  mov     rcx, [rsp+1F8h+String]; String
0x1800e6f92  test    rcx, rcx
0x1800e6f95  jz      short loc_1800E6FAC
0x1800e6f97  call    cs:__imp__wtoi
0x1800e6f9d  mov     [rsp+1F8h+var_E8], eax
0x1800e6fa4  mov     [rsp+1F8h+var_E4], r12b
0x1800e6fac  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e6fb1  lea     rdx, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x1800e6fb8  mov     rcx, rdi; this
0x1800e6fbb  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e6fc0  test    eax, eax
0x1800e6fc2  jnz     short loc_1800E6FE3
0x1800e6fc4  mov     rcx, [rsp+1F8h+String]; String
0x1800e6fc9  test    rcx, rcx
0x1800e6fcc  jz      short loc_1800E6FE3
0x1800e6fce  call    cs:__imp__wtoi
0x1800e6fd4  mov     [rsp+1F8h+var_E0], eax
0x1800e6fdb  mov     [rsp+1F8h+var_DC], r12b
0x1800e6fe3  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e6fe8  lea     rdx, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x1800e6fef  mov     rcx, rdi; this
0x1800e6ff2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e6ff7  test    eax, eax
0x1800e6ff9  jnz     short loc_1800E701A
0x1800e6ffb  mov     rcx, [rsp+1F8h+String]; String
0x1800e7000  test    rcx, rcx
0x1800e7003  jz      short loc_1800E701A
0x1800e7005  call    cs:__imp__wtoi
0x1800e700b  mov     [rsp+1F8h+var_D8], eax
0x1800e7012  mov     [rsp+1F8h+var_D4], r12b
0x1800e701a  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e701f  lea     rdx, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x1800e7026  mov     rcx, rdi; this
0x1800e7029  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e702e  test    eax, eax
0x1800e7030  jnz     short loc_1800E7051
0x1800e7032  mov     rcx, [rsp+1F8h+String]; String
0x1800e7037  test    rcx, rcx
0x1800e703a  jz      short loc_1800E7051
0x1800e703c  call    cs:__imp__wtoi
0x1800e7042  mov     [rsp+1F8h+var_D0], eax
0x1800e7049  mov     [rsp+1F8h+var_CC], r12b
0x1800e7051  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e7056  lea     rdx, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x1800e705d  mov     rcx, rdi; this
0x1800e7060  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e7065  test    eax, eax
0x1800e7067  jnz     short loc_1800E7088
0x1800e7069  mov     rcx, [rsp+1F8h+String]; String
0x1800e706e  test    rcx, rcx
0x1800e7071  jz      short loc_1800E7088
0x1800e7073  call    cs:__imp__wtoi
0x1800e7079  mov     [rsp+1F8h+var_C8], eax
0x1800e7080  mov     [rsp+1F8h+var_C4], r12b
0x1800e7088  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e708d  lea     rdx, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x1800e7094  mov     rcx, rdi; this
0x1800e7097  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e709c  test    eax, eax
0x1800e709e  jnz     short loc_1800E70BF
0x1800e70a0  mov     rcx, [rsp+1F8h+String]; String
0x1800e70a5  test    rcx, rcx
0x1800e70a8  jz      short loc_1800E70BF
0x1800e70aa  call    cs:__imp__wtoi
0x1800e70b0  mov     [rsp+1F8h+var_C0], eax
0x1800e70b7  mov     [rsp+1F8h+var_BC], r12b
0x1800e70bf  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e70c4  lea     rdx, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x1800e70cb  mov     rcx, rdi; this
0x1800e70ce  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e70d3  test    eax, eax
0x1800e70d5  jnz     short loc_1800E70F6
0x1800e70d7  mov     rcx, [rsp+1F8h+String]; String
0x1800e70dc  test    rcx, rcx
0x1800e70df  jz      short loc_1800E70F6
0x1800e70e1  call    cs:__imp__wtoi
0x1800e70e7  mov     [rsp+1F8h+var_B8], eax
0x1800e70ee  mov     [rsp+1F8h+var_B4], r12b
0x1800e70f6  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e70fb  lea     rdx, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x1800e7102  mov     rcx, rdi; this
0x1800e7105  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e710a  test    eax, eax
0x1800e710c  jnz     short loc_1800E712D
0x1800e710e  mov     rcx, [rsp+1F8h+String]; String
0x1800e7113  test    rcx, rcx
0x1800e7116  jz      short loc_1800E712D
0x1800e7118  call    cs:__imp__wtoi
0x1800e711e  mov     [rsp+1F8h+var_B0], eax
0x1800e7125  mov     [rsp+1F8h+var_AC], r12b
0x1800e712d  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e7132  lea     rdx, aConfigureremot; "ConfigureRemoteProcedureCallLocatorServ"...
0x1800e7139  mov     rcx, rdi; this
0x1800e713c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e7141  test    eax, eax
0x1800e7143  jnz     short loc_1800E7164
0x1800e7145  mov     rcx, [rsp+1F8h+String]; String
0x1800e714a  test    rcx, rcx
0x1800e714d  jz      short loc_1800E7164
0x1800e714f  call    cs:__imp__wtoi
0x1800e7155  mov     [rsp+1F8h+var_A8], eax
0x1800e715c  mov     [rsp+1F8h+var_A4], r12b
0x1800e7164  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e7169  lea     rdx, aConfigurerouti; "ConfigureRoutingAndRemoteAccessServiceS"...
0x1800e7170  mov     rcx, rdi; this
0x1800e7173  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e7178  test    eax, eax
0x1800e717a  jnz     short loc_1800E719B
0x1800e717c  mov     rcx, [rsp+1F8h+String]; String
0x1800e7181  test    rcx, rcx
0x1800e7184  jz      short loc_1800E719B
0x1800e7186  call    cs:__imp__wtoi
0x1800e718c  mov     [rsp+1F8h+var_A0], eax
0x1800e7193  mov     [rsp+1F8h+var_9C], r12b
0x1800e719b  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e71a0  lea     rdx, aConfiguresimpl; "ConfigureSimpleTCPIPServicesStartupMode"
0x1800e71a7  mov     rcx, rdi; this
0x1800e71aa  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e71af  test    eax, eax
0x1800e71b1  jnz     short loc_1800E71D2
0x1800e71b3  mov     rcx, [rsp+1F8h+String]; String
0x1800e71b8  test    rcx, rcx
0x1800e71bb  jz      short loc_1800E71D2
0x1800e71bd  call    cs:__imp__wtoi
0x1800e71c3  mov     [rsp+1F8h+var_98], eax
0x1800e71ca  mov     [rsp+1F8h+var_94], r12b
0x1800e71d2  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e71d7  lea     rdx, aConfigurespeci; "ConfigureSpecialAdministrationConsoleHe"...
0x1800e71de  mov     rcx, rdi; this
0x1800e71e1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e71e6  test    eax, eax
0x1800e71e8  jnz     short loc_1800E7209
0x1800e71ea  mov     rcx, [rsp+1F8h+String]; String
0x1800e71ef  test    rcx, rcx
0x1800e71f2  jz      short loc_1800E7209
0x1800e71f4  call    cs:__imp__wtoi
0x1800e71fa  mov     [rsp+1F8h+var_90], eax
0x1800e7201  mov     [rsp+1F8h+var_8C], r12b
0x1800e7209  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x1800e720e  lea     rdx, aConfiguressdpd; "ConfigureSSDPDiscoveryServiceStartupMod"...
0x1800e7215  mov     rcx, rdi; this
0x1800e7218  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e721d  test    eax, eax
0x1800e721f  jnz     short loc_1800E7240
0x1800e7221  mov     rcx, [rsp+1F8h+String]; String
0x1800e7226  test    rcx, rcx
0x1800e7229  jz      short loc_1800E7240
  ... truncated ...
```
