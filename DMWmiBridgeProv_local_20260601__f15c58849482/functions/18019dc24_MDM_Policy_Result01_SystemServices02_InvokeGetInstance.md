# MDM_Policy_Result01_SystemServices02_InvokeGetInstance

- ea: `0x18019dc24`
- end: `0x18019e4c9`
- name: `MDM_Policy_Result01_SystemServices02_InvokeGetInstance`
- size: `2213`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18019c660`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18019dc24`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18019dec3`
- `msvcrt!_wtoi` at `0x18019df00`
- `msvcrt!_wtoi` at `0x18019df3d`
- `msvcrt!_wtoi` at `0x18019df7a`
- `msvcrt!_wtoi` at `0x18019dfb7`
- `msvcrt!_wtoi` at `0x18019dff4`
- `msvcrt!_wtoi` at `0x18019e031`
- `msvcrt!_wtoi` at `0x18019e06e`
- `msvcrt!_wtoi` at `0x18019e0ab`
- `msvcrt!_wtoi` at `0x18019e0e8`
- `msvcrt!_wtoi` at `0x18019e125`
- `msvcrt!_wtoi` at `0x18019e162`
- `msvcrt!_wtoi` at `0x18019e19f`
- `msvcrt!_wtoi` at `0x18019e1dc`
- `msvcrt!_wtoi` at `0x18019e219`
- `msvcrt!_wtoi` at `0x18019e256`
- `msvcrt!_wtoi` at `0x18019e293`
- `msvcrt!_wtoi` at `0x18019e2d0`
- `msvcrt!_wtoi` at `0x18019e30d`
- `msvcrt!_wtoi` at `0x18019e34a`
- `msvcrt!_wtoi` at `0x18019e387`
- `msvcrt!_wtoi` at `0x18019e3c4`
- `msvcrt!_wtoi` at `0x18019dec3`
- `msvcrt!_wtoi` at `0x18019df00`
- `msvcrt!_wtoi` at `0x18019df3d`
- `msvcrt!_wtoi` at `0x18019df7a`
- `msvcrt!_wtoi` at `0x18019dfb7`
- `msvcrt!_wtoi` at `0x18019dff4`
- `msvcrt!_wtoi` at `0x18019e031`
- `msvcrt!_wtoi` at `0x18019e06e`
- `msvcrt!_wtoi` at `0x18019e0ab`
- `msvcrt!_wtoi` at `0x18019e0e8`
- `msvcrt!_wtoi` at `0x18019e125`
- `msvcrt!_wtoi` at `0x18019e162`
- `msvcrt!_wtoi` at `0x18019e19f`
- `msvcrt!_wtoi` at `0x18019e1dc`
- `msvcrt!_wtoi` at `0x18019e219`
- `msvcrt!_wtoi` at `0x18019e256`
- `msvcrt!_wtoi` at `0x18019e293`
- `msvcrt!_wtoi` at `0x18019e2d0`
- `msvcrt!_wtoi` at `0x18019e30d`
- `msvcrt!_wtoi` at `0x18019e34a`
- `msvcrt!_wtoi` at `0x18019e387`
- `msvcrt!_wtoi` at `0x18019e3c4`

## string_xrefs

- `0x18019dea6`: `ConfigureComputerBrowserServiceStartupMode`
- `0x18019dee3`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x18019df20`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x18019df5d`: `ConfigureIISAdminServiceStartupMode`
- `0x18019df9a`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x18019dfd7`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x18019e014`: `ConfigureLxssManagerServiceStartupMode`
- `0x18019e051`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x18019e08e`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x18019e0cb`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x18019e108`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x18019e145`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x18019e182`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x18019e1bf`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x18019e1fc`: `ConfigureWebManagementServiceStartupMode`
- `0x18019e239`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x18019e276`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x18019e2b3`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x18019e2f0`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x18019e32d`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x18019e36a`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x18019e3a7`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x18019dc93`: `MDM_Policy_Result01_SystemServices02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_SystemServices02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
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
  v11[2] = "MDM_Policy_Result01_SystemServices02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_180347864,
      v15,
      v4);
  }
  if ( LOBYTE(a2[1].classDecl) && (v9 = 0, LOBYTE(a2[1].nameSpace)) )
  {
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
                         &MDM_Policy_Result01_SystemServices02_NodeList,
                         24,
                         0,
                         &v10);
    if ( v5 == MI_RESULT_OK )
    {
      v11[4] = &v10;
      v12 = 1;
      v6 = v10;
      if ( v10 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v10,
          a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_SystemServices02_NodeList,
          0x18u);
        v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v5 )
        {
          if ( v10 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
        }
        else
        {
          v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
          if ( v5 )
          {
            if ( v10 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
          }
          else
          {
            v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_SystemServices02_rtti, &instance);
            if ( v5 )
            {
              if ( v10 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
            }
            else
            {
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
          }
        }
      }
      else
      {
        v5 = MI_RESULT_FAILED;
      }
    }
  }
  else
  {
    v5 = MI_RESULT_INVALID_PARAMETER;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_180349910,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18019dc24  mov     [rsp+arg_10], rbx
0x18019dc29  push    rsi
0x18019dc2a  push    rdi
0x18019dc2b  push    r12
0x18019dc2d  push    r14
0x18019dc2f  push    r15
0x18019dc31  sub     rsp, 1D0h
0x18019dc38  mov     rax, cs:__security_cookie
0x18019dc3f  xor     rax, rsp
0x18019dc42  mov     [rsp+1F8h+var_38], rax
0x18019dc4a  mov     rsi, rdx
0x18019dc4d  mov     r15, rcx
0x18019dc50  xor     ebx, ebx
0x18019dc52  mov     [rsp+1F8h+String], rbx
0x18019dc57  xor     edx, edx; Val
0x18019dc59  mov     r8d, 110h; Size
0x18019dc5f  lea     rcx, [rsp+1F8h+instance]; void *
0x18019dc67  call    memset_0
0x18019dc6c  mov     [rsp+1F8h+var_170], ebx
0x18019dc73  mov     [rsp+1F8h+var_16C], bl
0x18019dc7a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18019dc81  mov     [rsp+1F8h+var_1A0], rax
0x18019dc86  lea     rax, [rsp+1F8h+var_170]
0x18019dc8e  mov     [rsp+1F8h+var_198], rax
0x18019dc93  lea     rax, aMdmPolicyResul_19; "MDM_Policy_Result01_SystemServices02"
0x18019dc9a  mov     [rsp+1F8h+var_190], rax
0x18019dc9f  lea     rcx, [rsp+1F8h+var_170]
0x18019dca7  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18019dcac  mov     eax, cs:dword_180380B68
0x18019dcb2  cmp     eax, 5
0x18019dcb5  jbe     short loc_18019DD26
0x18019dcb7  mov     rdx, 200000000000h
0x18019dcc1  lea     rcx, dword_180380B68
0x18019dcc8  call    _tlgKeywordOn
0x18019dccd  test    al, al
0x18019dccf  jz      short loc_18019DD26
0x18019dcd1  cmp     [rsp+1F8h+var_16C], bl
0x18019dcd8  jz      short loc_18019DD08
0x18019dcda  cmp     [rsp+1F8h+var_158], ebx
0x18019dce1  jnz     short loc_18019DCFE
0x18019dce3  cmp     [rsp+1F8h+var_154], ebx
0x18019dcea  jnz     short loc_18019DCFE
0x18019dcec  cmp     [rsp+1F8h+var_150], ebx
0x18019dcf3  jnz     short loc_18019DCFE
0x18019dcf5  cmp     [rsp+1F8h+var_14C], ebx
0x18019dcfc  jz      short loc_18019DD08
0x18019dcfe  lea     r9, [rsp+1F8h+var_158]
0x18019dd06  jmp     short loc_18019DD0B
0x18019dd08  mov     r9, rbx
0x18019dd0b  lea     r8, [rsp+1F8h+var_168]
0x18019dd13  lea     rdx, dword_180347864
0x18019dd1a  lea     rcx, dword_180380B68
0x18019dd21  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18019dd26  cmp     [rsi+48h], bl
0x18019dd29  jz      loc_18019E427
0x18019dd2f  mov     [rsp+1F8h+var_1B0], bl
0x18019dd33  cmp     [rsi+58h], bl
0x18019dd36  jz      loc_18019E427
0x18019dd3c  mov     r9, [rsi+40h]; unsigned __int16 *
0x18019dd40  mov     r8, [rsi+50h]; unsigned __int16 *
0x18019dd44  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x18019dd4b  lea     rcx, [rsp+1F8h+var_1A0]; this
0x18019dd50  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18019dd55  nop
0x18019dd56  mov     [rsp+1F8h+var_1A8], rbx
0x18019dd5b  lea     rax, [rsp+1F8h+var_1A8]
0x18019dd60  mov     [rsp+1F8h+var_1C8], rax
0x18019dd65  mov     [rsp+1F8h+var_1D0], ebx
0x18019dd69  mov     [rsp+1F8h+var_1D8], 18h
0x18019dd71  lea     r9, ?MDM_Policy_Result01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_SystemServices02_NodeList
0x18019dd78  mov     r8, [rsi+40h]
0x18019dd7c  mov     rdx, [rsi+50h]
0x18019dd80  mov     rcx, r15
0x18019dd83  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18019dd88  mov     r14d, eax
0x18019dd8b  test    eax, eax
0x18019dd8d  jz      short loc_18019DD94
0x18019dd8f  jmp     loc_18019E42D
0x18019dd94  lea     rax, [rsp+1F8h+var_1A8]
0x18019dd99  mov     [rsp+1F8h+var_180], rax
0x18019dd9e  mov     r12d, 1
0x18019dda4  mov     [rsp+1F8h+var_178], r12b
0x18019ddac  mov     rdi, [rsp+1F8h+var_1A8]
0x18019ddb1  test    rdi, rdi
0x18019ddb4  jnz     short loc_18019DDBE
0x18019ddb6  mov     r14d, r12d
0x18019ddb9  jmp     loc_18019E42D
0x18019ddbe  mov     r9d, 18h; unsigned int
0x18019ddc4  lea     r8, ?MDM_Policy_Result01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18019ddcb  mov     rdx, rsi; struct _MI_Instance *
0x18019ddce  mov     rcx, rdi; this
0x18019ddd1  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18019ddd6  mov     rax, [rdi]
0x18019ddd9  mov     rcx, rdi
0x18019dddc  mov     rax, [rax+10h]
0x18019dde0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019dde5  mov     r14d, eax
0x18019dde8  test    eax, eax
0x18019ddea  jz      short loc_18019DE0A
0x18019ddec  mov     rcx, [rsp+1F8h+var_1A8]
0x18019ddf1  test    rcx, rcx
0x18019ddf4  jz      short loc_18019DE05
0x18019ddf6  mov     rax, [rcx]
0x18019ddf9  mov     edx, r12d
0x18019ddfc  mov     rax, [rax]
0x18019ddff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019de04  nop
0x18019de05  jmp     loc_18019E42D
0x18019de0a  mov     rax, [rdi]
0x18019de0d  mov     rcx, rdi
0x18019de10  mov     rax, [rax+8]
0x18019de14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019de19  mov     r14d, eax
0x18019de1c  test    eax, eax
0x18019de1e  jz      short loc_18019DE3E
0x18019de20  mov     rcx, [rsp+1F8h+var_1A8]
0x18019de25  test    rcx, rcx
0x18019de28  jz      short loc_18019DE39
0x18019de2a  mov     rax, [rcx]
0x18019de2d  mov     edx, r12d
0x18019de30  mov     rax, [rax]
0x18019de33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019de38  nop
0x18019de39  jmp     loc_18019E42D
0x18019de3e  lea     r8, [rsp+1F8h+instance]; instance
0x18019de46  lea     rdx, MDM_Policy_Result01_SystemServices02_rtti; classDecl
0x18019de4d  mov     rcx, r15; context
0x18019de50  call    MI_Context_ConstructInstance
0x18019de55  mov     r14d, eax
0x18019de58  test    eax, eax
0x18019de5a  jz      short loc_18019DE7A
0x18019de5c  mov     rcx, [rsp+1F8h+var_1A8]
0x18019de61  test    rcx, rcx
0x18019de64  jz      short loc_18019DE75
0x18019de66  mov     rax, [rcx]
0x18019de69  mov     edx, r12d
0x18019de6c  mov     rax, [rax]
0x18019de6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019de74  nop
0x18019de75  jmp     loc_18019E42D
0x18019de7a  mov     [rsp+1F8h+var_1B0], r12b
0x18019de7f  mov     rdx, [rsi+40h]
0x18019de83  lea     rcx, [rsp+1F8h+instance]
0x18019de8b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18019de90  mov     rdx, [rsi+50h]
0x18019de94  lea     rcx, [rsp+1F8h+instance]
0x18019de9c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18019dea1  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019dea6  lea     rdx, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x18019dead  mov     rcx, rdi; this
0x18019deb0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019deb5  test    eax, eax
0x18019deb7  jnz     short loc_18019DEDE
0x18019deb9  mov     rcx, [rsp+1F8h+String]; String
0x18019debe  test    rcx, rcx
0x18019dec1  jz      short loc_18019DEDE
0x18019dec3  call    cs:__imp__wtoi
0x18019deca  nop     dword ptr [rax+rax+00h]
0x18019decf  mov     [rsp+1F8h+var_E8], eax
0x18019ded6  mov     [rsp+1F8h+var_E4], r12b
0x18019dede  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019dee3  lea     rdx, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x18019deea  mov     rcx, rdi; this
0x18019deed  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019def2  test    eax, eax
0x18019def4  jnz     short loc_18019DF1B
0x18019def6  mov     rcx, [rsp+1F8h+String]; String
0x18019defb  test    rcx, rcx
0x18019defe  jz      short loc_18019DF1B
0x18019df00  call    cs:__imp__wtoi
0x18019df07  nop     dword ptr [rax+rax+00h]
0x18019df0c  mov     [rsp+1F8h+var_E0], eax
0x18019df13  mov     [rsp+1F8h+var_DC], r12b
0x18019df1b  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019df20  lea     rdx, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x18019df27  mov     rcx, rdi; this
0x18019df2a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019df2f  test    eax, eax
0x18019df31  jnz     short loc_18019DF58
0x18019df33  mov     rcx, [rsp+1F8h+String]; String
0x18019df38  test    rcx, rcx
0x18019df3b  jz      short loc_18019DF58
0x18019df3d  call    cs:__imp__wtoi
0x18019df44  nop     dword ptr [rax+rax+00h]
0x18019df49  mov     [rsp+1F8h+var_D8], eax
0x18019df50  mov     [rsp+1F8h+var_D4], r12b
0x18019df58  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019df5d  lea     rdx, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x18019df64  mov     rcx, rdi; this
0x18019df67  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019df6c  test    eax, eax
0x18019df6e  jnz     short loc_18019DF95
0x18019df70  mov     rcx, [rsp+1F8h+String]; String
0x18019df75  test    rcx, rcx
0x18019df78  jz      short loc_18019DF95
0x18019df7a  call    cs:__imp__wtoi
0x18019df81  nop     dword ptr [rax+rax+00h]
0x18019df86  mov     [rsp+1F8h+var_D0], eax
0x18019df8d  mov     [rsp+1F8h+var_CC], r12b
0x18019df95  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019df9a  lea     rdx, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x18019dfa1  mov     rcx, rdi; this
0x18019dfa4  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019dfa9  test    eax, eax
0x18019dfab  jnz     short loc_18019DFD2
0x18019dfad  mov     rcx, [rsp+1F8h+String]; String
0x18019dfb2  test    rcx, rcx
0x18019dfb5  jz      short loc_18019DFD2
0x18019dfb7  call    cs:__imp__wtoi
0x18019dfbe  nop     dword ptr [rax+rax+00h]
0x18019dfc3  mov     [rsp+1F8h+var_C8], eax
0x18019dfca  mov     [rsp+1F8h+var_C4], r12b
0x18019dfd2  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019dfd7  lea     rdx, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x18019dfde  mov     rcx, rdi; this
0x18019dfe1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019dfe6  test    eax, eax
0x18019dfe8  jnz     short loc_18019E00F
0x18019dfea  mov     rcx, [rsp+1F8h+String]; String
0x18019dfef  test    rcx, rcx
0x18019dff2  jz      short loc_18019E00F
0x18019dff4  call    cs:__imp__wtoi
0x18019dffb  nop     dword ptr [rax+rax+00h]
0x18019e000  mov     [rsp+1F8h+var_C0], eax
0x18019e007  mov     [rsp+1F8h+var_BC], r12b
0x18019e00f  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e014  lea     rdx, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x18019e01b  mov     rcx, rdi; this
0x18019e01e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e023  test    eax, eax
0x18019e025  jnz     short loc_18019E04C
0x18019e027  mov     rcx, [rsp+1F8h+String]; String
0x18019e02c  test    rcx, rcx
0x18019e02f  jz      short loc_18019E04C
0x18019e031  call    cs:__imp__wtoi
0x18019e038  nop     dword ptr [rax+rax+00h]
0x18019e03d  mov     [rsp+1F8h+var_B8], eax
0x18019e044  mov     [rsp+1F8h+var_B4], r12b
0x18019e04c  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e051  lea     rdx, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x18019e058  mov     rcx, rdi; this
0x18019e05b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e060  test    eax, eax
0x18019e062  jnz     short loc_18019E089
0x18019e064  mov     rcx, [rsp+1F8h+String]; String
0x18019e069  test    rcx, rcx
0x18019e06c  jz      short loc_18019E089
0x18019e06e  call    cs:__imp__wtoi
0x18019e075  nop     dword ptr [rax+rax+00h]
0x18019e07a  mov     [rsp+1F8h+var_B0], eax
0x18019e081  mov     [rsp+1F8h+var_AC], r12b
0x18019e089  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e08e  lea     rdx, aConfigureremot; "ConfigureRemoteProcedureCallLocatorServ"...
0x18019e095  mov     rcx, rdi; this
0x18019e098  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e09d  test    eax, eax
0x18019e09f  jnz     short loc_18019E0C6
0x18019e0a1  mov     rcx, [rsp+1F8h+String]; String
0x18019e0a6  test    rcx, rcx
0x18019e0a9  jz      short loc_18019E0C6
0x18019e0ab  call    cs:__imp__wtoi
0x18019e0b2  nop     dword ptr [rax+rax+00h]
0x18019e0b7  mov     [rsp+1F8h+var_A8], eax
0x18019e0be  mov     [rsp+1F8h+var_A4], r12b
0x18019e0c6  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e0cb  lea     rdx, aConfigurerouti; "ConfigureRoutingAndRemoteAccessServiceS"...
0x18019e0d2  mov     rcx, rdi; this
0x18019e0d5  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e0da  test    eax, eax
0x18019e0dc  jnz     short loc_18019E103
0x18019e0de  mov     rcx, [rsp+1F8h+String]; String
0x18019e0e3  test    rcx, rcx
0x18019e0e6  jz      short loc_18019E103
0x18019e0e8  call    cs:__imp__wtoi
0x18019e0ef  nop     dword ptr [rax+rax+00h]
0x18019e0f4  mov     [rsp+1F8h+var_A0], eax
0x18019e0fb  mov     [rsp+1F8h+var_9C], r12b
0x18019e103  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e108  lea     rdx, aConfiguresimpl; "ConfigureSimpleTCPIPServicesStartupMode"
0x18019e10f  mov     rcx, rdi; this
0x18019e112  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e117  test    eax, eax
0x18019e119  jnz     short loc_18019E140
0x18019e11b  mov     rcx, [rsp+1F8h+String]; String
0x18019e120  test    rcx, rcx
0x18019e123  jz      short loc_18019E140
0x18019e125  call    cs:__imp__wtoi
0x18019e12c  nop     dword ptr [rax+rax+00h]
0x18019e131  mov     [rsp+1F8h+var_98], eax
0x18019e138  mov     [rsp+1F8h+var_94], r12b
0x18019e140  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e145  lea     rdx, aConfigurespeci; "ConfigureSpecialAdministrationConsoleHe"...
0x18019e14c  mov     rcx, rdi; this
0x18019e14f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e154  test    eax, eax
0x18019e156  jnz     short loc_18019E17D
0x18019e158  mov     rcx, [rsp+1F8h+String]; String
0x18019e15d  test    rcx, rcx
0x18019e160  jz      short loc_18019E17D
0x18019e162  call    cs:__imp__wtoi
  ... truncated ...
```
