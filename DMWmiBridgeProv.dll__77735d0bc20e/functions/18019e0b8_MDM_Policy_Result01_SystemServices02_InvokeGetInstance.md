# MDM_Policy_Result01_SystemServices02_InvokeGetInstance

- ea: `0x18019e0b8`
- end: `0x18019e8d8`
- name: `MDM_Policy_Result01_SystemServices02_InvokeGetInstance`
- size: `2080`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18019cb70`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18019e0b8`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18019e357`
- `msvcrt!_wtoi` at `0x18019e38e`
- `msvcrt!_wtoi` at `0x18019e3c5`
- `msvcrt!_wtoi` at `0x18019e3fc`
- `msvcrt!_wtoi` at `0x18019e433`
- `msvcrt!_wtoi` at `0x18019e46a`
- `msvcrt!_wtoi` at `0x18019e4a1`
- `msvcrt!_wtoi` at `0x18019e4d8`
- `msvcrt!_wtoi` at `0x18019e50f`
- `msvcrt!_wtoi` at `0x18019e546`
- `msvcrt!_wtoi` at `0x18019e57d`
- `msvcrt!_wtoi` at `0x18019e5b4`
- `msvcrt!_wtoi` at `0x18019e5eb`
- `msvcrt!_wtoi` at `0x18019e622`
- `msvcrt!_wtoi` at `0x18019e659`
- `msvcrt!_wtoi` at `0x18019e690`
- `msvcrt!_wtoi` at `0x18019e6c7`
- `msvcrt!_wtoi` at `0x18019e6fe`
- `msvcrt!_wtoi` at `0x18019e735`
- `msvcrt!_wtoi` at `0x18019e76c`
- `msvcrt!_wtoi` at `0x18019e7a3`
- `msvcrt!_wtoi` at `0x18019e7da`
- `msvcrt!_wtoi` at `0x18019e357`
- `msvcrt!_wtoi` at `0x18019e38e`
- `msvcrt!_wtoi` at `0x18019e3c5`
- `msvcrt!_wtoi` at `0x18019e3fc`
- `msvcrt!_wtoi` at `0x18019e433`
- `msvcrt!_wtoi` at `0x18019e46a`
- `msvcrt!_wtoi` at `0x18019e4a1`
- `msvcrt!_wtoi` at `0x18019e4d8`
- `msvcrt!_wtoi` at `0x18019e50f`
- `msvcrt!_wtoi` at `0x18019e546`
- `msvcrt!_wtoi` at `0x18019e57d`
- `msvcrt!_wtoi` at `0x18019e5b4`
- `msvcrt!_wtoi` at `0x18019e5eb`
- `msvcrt!_wtoi` at `0x18019e622`
- `msvcrt!_wtoi` at `0x18019e659`
- `msvcrt!_wtoi` at `0x18019e690`
- `msvcrt!_wtoi` at `0x18019e6c7`
- `msvcrt!_wtoi` at `0x18019e6fe`
- `msvcrt!_wtoi` at `0x18019e735`
- `msvcrt!_wtoi` at `0x18019e76c`
- `msvcrt!_wtoi` at `0x18019e7a3`
- `msvcrt!_wtoi` at `0x18019e7da`

## string_xrefs

- `0x18019e33a`: `ConfigureComputerBrowserServiceStartupMode`
- `0x18019e371`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x18019e3a8`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x18019e3df`: `ConfigureIISAdminServiceStartupMode`
- `0x18019e416`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x18019e44d`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x18019e484`: `ConfigureLxssManagerServiceStartupMode`
- `0x18019e4bb`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x18019e4f2`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x18019e529`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x18019e560`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x18019e597`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x18019e5ce`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x18019e605`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x18019e63c`: `ConfigureWebManagementServiceStartupMode`
- `0x18019e673`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x18019e6aa`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x18019e6e1`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x18019e718`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x18019e74f`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x18019e786`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x18019e7bd`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x18019e127`: `MDM_Policy_Result01_SystemServices02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_SystemServices02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
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
    v5 = CreateRequestHandlerInstance(
           (__int64)self,
           (wchar_t *)a2[1].serverName,
           (const unsigned __int16 *)a2[1].ft,
           (struct WmiNodeInfo *)&MDM_Policy_Result01_SystemServices02_NodeList,
           0x18u,
           0,
           &v10);
    if ( !v5 )
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
        v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v5 )
        {
          if ( v10 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
        }
        else
        {
          v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
          }
        }
      }
      else
      {
        v5 = 1;
      }
    }
  }
  else
  {
    v5 = 4;
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
  return v5;
}

```

## disassembly

```asm
0x18019e0b8  mov     [rsp+arg_10], rbx
0x18019e0bd  push    rsi
0x18019e0be  push    rdi
0x18019e0bf  push    r12
0x18019e0c1  push    r14
0x18019e0c3  push    r15
0x18019e0c5  sub     rsp, 1D0h
0x18019e0cc  mov     rax, cs:__security_cookie
0x18019e0d3  xor     rax, rsp
0x18019e0d6  mov     [rsp+1F8h+var_38], rax
0x18019e0de  mov     rsi, rdx
0x18019e0e1  mov     r15, rcx
0x18019e0e4  xor     ebx, ebx
0x18019e0e6  mov     [rsp+1F8h+String], rbx
0x18019e0eb  xor     edx, edx; Val
0x18019e0ed  mov     r8d, 110h; Size
0x18019e0f3  lea     rcx, [rsp+1F8h+instance]; void *
0x18019e0fb  call    memset_0
0x18019e100  mov     [rsp+1F8h+var_170], ebx
0x18019e107  mov     [rsp+1F8h+var_16C], bl
0x18019e10e  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18019e115  mov     [rsp+1F8h+var_1A0], rax
0x18019e11a  lea     rax, [rsp+1F8h+var_170]
0x18019e122  mov     [rsp+1F8h+var_198], rax
0x18019e127  lea     rax, aMdmPolicyResul_19; "MDM_Policy_Result01_SystemServices02"
0x18019e12e  mov     [rsp+1F8h+var_190], rax
0x18019e133  lea     rcx, [rsp+1F8h+var_170]
0x18019e13b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18019e140  mov     eax, cs:dword_180380B68
0x18019e146  cmp     eax, 5
0x18019e149  jbe     short loc_18019E1BA
0x18019e14b  mov     rdx, 200000000000h
0x18019e155  lea     rcx, dword_180380B68
0x18019e15c  call    _tlgKeywordOn
0x18019e161  test    al, al
0x18019e163  jz      short loc_18019E1BA
0x18019e165  cmp     [rsp+1F8h+var_16C], bl
0x18019e16c  jz      short loc_18019E19C
0x18019e16e  cmp     [rsp+1F8h+var_158], ebx
0x18019e175  jnz     short loc_18019E192
0x18019e177  cmp     [rsp+1F8h+var_154], ebx
0x18019e17e  jnz     short loc_18019E192
0x18019e180  cmp     [rsp+1F8h+var_150], ebx
0x18019e187  jnz     short loc_18019E192
0x18019e189  cmp     [rsp+1F8h+var_14C], ebx
0x18019e190  jz      short loc_18019E19C
0x18019e192  lea     r9, [rsp+1F8h+var_158]
0x18019e19a  jmp     short loc_18019E19F
0x18019e19c  mov     r9, rbx
0x18019e19f  lea     r8, [rsp+1F8h+var_168]
0x18019e1a7  lea     rdx, dword_180347864
0x18019e1ae  lea     rcx, dword_180380B68
0x18019e1b5  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18019e1ba  cmp     [rsi+48h], bl
0x18019e1bd  jz      loc_18019E837
0x18019e1c3  mov     [rsp+1F8h+var_1B0], bl
0x18019e1c7  cmp     [rsi+58h], bl
0x18019e1ca  jz      loc_18019E837
0x18019e1d0  mov     r9, [rsi+40h]; unsigned __int16 *
0x18019e1d4  mov     r8, [rsi+50h]; unsigned __int16 *
0x18019e1d8  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x18019e1df  lea     rcx, [rsp+1F8h+var_1A0]; this
0x18019e1e4  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18019e1e9  nop
0x18019e1ea  mov     [rsp+1F8h+var_1A8], rbx
0x18019e1ef  lea     rax, [rsp+1F8h+var_1A8]
0x18019e1f4  mov     [rsp+1F8h+var_1C8], rax
0x18019e1f9  mov     [rsp+1F8h+var_1D0], ebx
0x18019e1fd  mov     [rsp+1F8h+var_1D8], 18h
0x18019e205  lea     r9, ?MDM_Policy_Result01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_SystemServices02_NodeList
0x18019e20c  mov     r8, [rsi+40h]
0x18019e210  mov     rdx, [rsi+50h]
0x18019e214  mov     rcx, r15
0x18019e217  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18019e21c  mov     r14d, eax
0x18019e21f  test    eax, eax
0x18019e221  jz      short loc_18019E228
0x18019e223  jmp     loc_18019E83D
0x18019e228  lea     rax, [rsp+1F8h+var_1A8]
0x18019e22d  mov     [rsp+1F8h+var_180], rax
0x18019e232  mov     r12d, 1
0x18019e238  mov     [rsp+1F8h+var_178], r12b
0x18019e240  mov     rdi, [rsp+1F8h+var_1A8]
0x18019e245  test    rdi, rdi
0x18019e248  jnz     short loc_18019E252
0x18019e24a  mov     r14d, r12d
0x18019e24d  jmp     loc_18019E83D
0x18019e252  mov     r9d, 18h; unsigned int
0x18019e258  lea     r8, ?MDM_Policy_Result01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18019e25f  mov     rdx, rsi; struct _MI_Instance *
0x18019e262  mov     rcx, rdi; this
0x18019e265  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18019e26a  mov     rax, [rdi]
0x18019e26d  mov     rcx, rdi
0x18019e270  mov     rax, [rax+10h]
0x18019e274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e279  mov     r14d, eax
0x18019e27c  test    eax, eax
0x18019e27e  jz      short loc_18019E29E
0x18019e280  mov     rcx, [rsp+1F8h+var_1A8]
0x18019e285  test    rcx, rcx
0x18019e288  jz      short loc_18019E299
0x18019e28a  mov     rax, [rcx]
0x18019e28d  mov     edx, r12d
0x18019e290  mov     rax, [rax]
0x18019e293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e298  nop
0x18019e299  jmp     loc_18019E83D
0x18019e29e  mov     rax, [rdi]
0x18019e2a1  mov     rcx, rdi
0x18019e2a4  mov     rax, [rax+8]
0x18019e2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e2ad  mov     r14d, eax
0x18019e2b0  test    eax, eax
0x18019e2b2  jz      short loc_18019E2D2
0x18019e2b4  mov     rcx, [rsp+1F8h+var_1A8]
0x18019e2b9  test    rcx, rcx
0x18019e2bc  jz      short loc_18019E2CD
0x18019e2be  mov     rax, [rcx]
0x18019e2c1  mov     edx, r12d
0x18019e2c4  mov     rax, [rax]
0x18019e2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e2cc  nop
0x18019e2cd  jmp     loc_18019E83D
0x18019e2d2  lea     r8, [rsp+1F8h+instance]; instance
0x18019e2da  lea     rdx, MDM_Policy_Result01_SystemServices02_rtti; classDecl
0x18019e2e1  mov     rcx, r15; context
0x18019e2e4  call    MI_Context_ConstructInstance
0x18019e2e9  mov     r14d, eax
0x18019e2ec  test    eax, eax
0x18019e2ee  jz      short loc_18019E30E
0x18019e2f0  mov     rcx, [rsp+1F8h+var_1A8]
0x18019e2f5  test    rcx, rcx
0x18019e2f8  jz      short loc_18019E309
0x18019e2fa  mov     rax, [rcx]
0x18019e2fd  mov     edx, r12d
0x18019e300  mov     rax, [rax]
0x18019e303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e308  nop
0x18019e309  jmp     loc_18019E83D
0x18019e30e  mov     [rsp+1F8h+var_1B0], r12b
0x18019e313  mov     rdx, [rsi+40h]
0x18019e317  lea     rcx, [rsp+1F8h+instance]
0x18019e31f  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18019e324  mov     rdx, [rsi+50h]
0x18019e328  lea     rcx, [rsp+1F8h+instance]
0x18019e330  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18019e335  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e33a  lea     rdx, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x18019e341  mov     rcx, rdi; this
0x18019e344  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e349  test    eax, eax
0x18019e34b  jnz     short loc_18019E36C
0x18019e34d  mov     rcx, [rsp+1F8h+String]; String
0x18019e352  test    rcx, rcx
0x18019e355  jz      short loc_18019E36C
0x18019e357  call    cs:__imp__wtoi
0x18019e35d  mov     [rsp+1F8h+var_E8], eax
0x18019e364  mov     [rsp+1F8h+var_E4], r12b
0x18019e36c  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e371  lea     rdx, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x18019e378  mov     rcx, rdi; this
0x18019e37b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e380  test    eax, eax
0x18019e382  jnz     short loc_18019E3A3
0x18019e384  mov     rcx, [rsp+1F8h+String]; String
0x18019e389  test    rcx, rcx
0x18019e38c  jz      short loc_18019E3A3
0x18019e38e  call    cs:__imp__wtoi
0x18019e394  mov     [rsp+1F8h+var_E0], eax
0x18019e39b  mov     [rsp+1F8h+var_DC], r12b
0x18019e3a3  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e3a8  lea     rdx, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x18019e3af  mov     rcx, rdi; this
0x18019e3b2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e3b7  test    eax, eax
0x18019e3b9  jnz     short loc_18019E3DA
0x18019e3bb  mov     rcx, [rsp+1F8h+String]; String
0x18019e3c0  test    rcx, rcx
0x18019e3c3  jz      short loc_18019E3DA
0x18019e3c5  call    cs:__imp__wtoi
0x18019e3cb  mov     [rsp+1F8h+var_D8], eax
0x18019e3d2  mov     [rsp+1F8h+var_D4], r12b
0x18019e3da  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e3df  lea     rdx, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x18019e3e6  mov     rcx, rdi; this
0x18019e3e9  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e3ee  test    eax, eax
0x18019e3f0  jnz     short loc_18019E411
0x18019e3f2  mov     rcx, [rsp+1F8h+String]; String
0x18019e3f7  test    rcx, rcx
0x18019e3fa  jz      short loc_18019E411
0x18019e3fc  call    cs:__imp__wtoi
0x18019e402  mov     [rsp+1F8h+var_D0], eax
0x18019e409  mov     [rsp+1F8h+var_CC], r12b
0x18019e411  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e416  lea     rdx, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x18019e41d  mov     rcx, rdi; this
0x18019e420  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e425  test    eax, eax
0x18019e427  jnz     short loc_18019E448
0x18019e429  mov     rcx, [rsp+1F8h+String]; String
0x18019e42e  test    rcx, rcx
0x18019e431  jz      short loc_18019E448
0x18019e433  call    cs:__imp__wtoi
0x18019e439  mov     [rsp+1F8h+var_C8], eax
0x18019e440  mov     [rsp+1F8h+var_C4], r12b
0x18019e448  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e44d  lea     rdx, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x18019e454  mov     rcx, rdi; this
0x18019e457  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e45c  test    eax, eax
0x18019e45e  jnz     short loc_18019E47F
0x18019e460  mov     rcx, [rsp+1F8h+String]; String
0x18019e465  test    rcx, rcx
0x18019e468  jz      short loc_18019E47F
0x18019e46a  call    cs:__imp__wtoi
0x18019e470  mov     [rsp+1F8h+var_C0], eax
0x18019e477  mov     [rsp+1F8h+var_BC], r12b
0x18019e47f  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e484  lea     rdx, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x18019e48b  mov     rcx, rdi; this
0x18019e48e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e493  test    eax, eax
0x18019e495  jnz     short loc_18019E4B6
0x18019e497  mov     rcx, [rsp+1F8h+String]; String
0x18019e49c  test    rcx, rcx
0x18019e49f  jz      short loc_18019E4B6
0x18019e4a1  call    cs:__imp__wtoi
0x18019e4a7  mov     [rsp+1F8h+var_B8], eax
0x18019e4ae  mov     [rsp+1F8h+var_B4], r12b
0x18019e4b6  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e4bb  lea     rdx, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x18019e4c2  mov     rcx, rdi; this
0x18019e4c5  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e4ca  test    eax, eax
0x18019e4cc  jnz     short loc_18019E4ED
0x18019e4ce  mov     rcx, [rsp+1F8h+String]; String
0x18019e4d3  test    rcx, rcx
0x18019e4d6  jz      short loc_18019E4ED
0x18019e4d8  call    cs:__imp__wtoi
0x18019e4de  mov     [rsp+1F8h+var_B0], eax
0x18019e4e5  mov     [rsp+1F8h+var_AC], r12b
0x18019e4ed  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e4f2  lea     rdx, aConfigureremot; "ConfigureRemoteProcedureCallLocatorServ"...
0x18019e4f9  mov     rcx, rdi; this
0x18019e4fc  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e501  test    eax, eax
0x18019e503  jnz     short loc_18019E524
0x18019e505  mov     rcx, [rsp+1F8h+String]; String
0x18019e50a  test    rcx, rcx
0x18019e50d  jz      short loc_18019E524
0x18019e50f  call    cs:__imp__wtoi
0x18019e515  mov     [rsp+1F8h+var_A8], eax
0x18019e51c  mov     [rsp+1F8h+var_A4], r12b
0x18019e524  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e529  lea     rdx, aConfigurerouti; "ConfigureRoutingAndRemoteAccessServiceS"...
0x18019e530  mov     rcx, rdi; this
0x18019e533  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e538  test    eax, eax
0x18019e53a  jnz     short loc_18019E55B
0x18019e53c  mov     rcx, [rsp+1F8h+String]; String
0x18019e541  test    rcx, rcx
0x18019e544  jz      short loc_18019E55B
0x18019e546  call    cs:__imp__wtoi
0x18019e54c  mov     [rsp+1F8h+var_A0], eax
0x18019e553  mov     [rsp+1F8h+var_9C], r12b
0x18019e55b  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e560  lea     rdx, aConfiguresimpl; "ConfigureSimpleTCPIPServicesStartupMode"
0x18019e567  mov     rcx, rdi; this
0x18019e56a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e56f  test    eax, eax
0x18019e571  jnz     short loc_18019E592
0x18019e573  mov     rcx, [rsp+1F8h+String]; String
0x18019e578  test    rcx, rcx
0x18019e57b  jz      short loc_18019E592
0x18019e57d  call    cs:__imp__wtoi
0x18019e583  mov     [rsp+1F8h+var_98], eax
0x18019e58a  mov     [rsp+1F8h+var_94], r12b
0x18019e592  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e597  lea     rdx, aConfigurespeci; "ConfigureSpecialAdministrationConsoleHe"...
0x18019e59e  mov     rcx, rdi; this
0x18019e5a1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e5a6  test    eax, eax
0x18019e5a8  jnz     short loc_18019E5C9
0x18019e5aa  mov     rcx, [rsp+1F8h+String]; String
0x18019e5af  test    rcx, rcx
0x18019e5b2  jz      short loc_18019E5C9
0x18019e5b4  call    cs:__imp__wtoi
0x18019e5ba  mov     [rsp+1F8h+var_90], eax
0x18019e5c1  mov     [rsp+1F8h+var_8C], r12b
0x18019e5c9  lea     r8, [rsp+1F8h+String]; unsigned __int16 **
0x18019e5ce  lea     rdx, aConfiguressdpd; "ConfigureSSDPDiscoveryServiceStartupMod"...
0x18019e5d5  mov     rcx, rdi; this
0x18019e5d8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019e5dd  test    eax, eax
0x18019e5df  jnz     short loc_18019E600
0x18019e5e1  mov     rcx, [rsp+1F8h+String]; String
0x18019e5e6  test    rcx, rcx
0x18019e5e9  jz      short loc_18019E600
  ... truncated ...
```
