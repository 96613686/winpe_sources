# MDM_Policy_Config01_SystemServices02_InvokeEnumerateInstances

- ea: `0x1800e5b08`
- end: `0x1800e650b`
- name: `MDM_Policy_Config01_SystemServices02_InvokeEnumerateInstances`
- size: `2563`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e4f20`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800e5b08`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800e5e1a`
- `msvcrt!_wtoi` at `0x1800e5e61`
- `msvcrt!_wtoi` at `0x1800e5ea8`
- `msvcrt!_wtoi` at `0x1800e5eef`
- `msvcrt!_wtoi` at `0x1800e5f36`
- `msvcrt!_wtoi` at `0x1800e5f7d`
- `msvcrt!_wtoi` at `0x1800e5fc4`
- `msvcrt!_wtoi` at `0x1800e600b`
- `msvcrt!_wtoi` at `0x1800e6052`
- `msvcrt!_wtoi` at `0x1800e6099`
- `msvcrt!_wtoi` at `0x1800e60e0`
- `msvcrt!_wtoi` at `0x1800e6127`
- `msvcrt!_wtoi` at `0x1800e616e`
- `msvcrt!_wtoi` at `0x1800e61b5`
- `msvcrt!_wtoi` at `0x1800e61fc`
- `msvcrt!_wtoi` at `0x1800e6243`
- `msvcrt!_wtoi` at `0x1800e628a`
- `msvcrt!_wtoi` at `0x1800e62d1`
- `msvcrt!_wtoi` at `0x1800e6318`
- `msvcrt!_wtoi` at `0x1800e635f`
- `msvcrt!_wtoi` at `0x1800e63a6`
- `msvcrt!_wtoi` at `0x1800e63ed`
- `msvcrt!_wtoi` at `0x1800e5e1a`
- `msvcrt!_wtoi` at `0x1800e5e61`
- `msvcrt!_wtoi` at `0x1800e5ea8`
- `msvcrt!_wtoi` at `0x1800e5eef`
- `msvcrt!_wtoi` at `0x1800e5f36`
- `msvcrt!_wtoi` at `0x1800e5f7d`
- `msvcrt!_wtoi` at `0x1800e5fc4`
- `msvcrt!_wtoi` at `0x1800e600b`
- `msvcrt!_wtoi` at `0x1800e6052`
- `msvcrt!_wtoi` at `0x1800e6099`
- `msvcrt!_wtoi` at `0x1800e60e0`
- `msvcrt!_wtoi` at `0x1800e6127`
- `msvcrt!_wtoi` at `0x1800e616e`
- `msvcrt!_wtoi` at `0x1800e61b5`
- `msvcrt!_wtoi` at `0x1800e61fc`
- `msvcrt!_wtoi` at `0x1800e6243`
- `msvcrt!_wtoi` at `0x1800e628a`
- `msvcrt!_wtoi` at `0x1800e62d1`
- `msvcrt!_wtoi` at `0x1800e6318`
- `msvcrt!_wtoi` at `0x1800e635f`
- `msvcrt!_wtoi` at `0x1800e63a6`
- `msvcrt!_wtoi` at `0x1800e63ed`

## string_xrefs

- `0x1800e5df6`: `ConfigureComputerBrowserServiceStartupMode`
- `0x1800e5e3d`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x1800e5e84`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x1800e5ecb`: `ConfigureIISAdminServiceStartupMode`
- `0x1800e5f12`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x1800e5f59`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x1800e5fa0`: `ConfigureLxssManagerServiceStartupMode`
- `0x1800e5fe7`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x1800e602e`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x1800e6075`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x1800e60bc`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x1800e6103`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x1800e614a`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x1800e6191`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x1800e61d8`: `ConfigureWebManagementServiceStartupMode`
- `0x1800e621f`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x1800e6266`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x1800e62ad`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x1800e62f4`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x1800e633b`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x1800e6382`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x1800e63c9`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x1800e5d5c`: `./Vendor/MSFT/Policy/Config`
- `0x1800e5b83`: `MDM_Policy_Config01_SystemServices02`
- `0x1800e5d95`: `SystemServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_SystemServices02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r15d
  _QWORD *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-1B8h] BYREF
  char v14; // [rsp+48h] [rbp-1B0h]
  _QWORD *v15; // [rsp+50h] [rbp-1A8h] BYREF
  _QWORD v16[3]; // [rsp+58h] [rbp-1A0h] BYREF
  const exception *v17[2]; // [rsp+70h] [rbp-188h] BYREF
  char v18; // [rsp+80h] [rbp-178h]
  int v19; // [rsp+88h] [rbp-170h] BYREF
  char v20; // [rsp+8Ch] [rbp-16Ch]
  _BYTE v21[16]; // [rsp+90h] [rbp-168h] BYREF
  _DWORD v22[4]; // [rsp+A0h] [rbp-158h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-148h] BYREF
  int v24; // [rsp+110h] [rbp-E8h]
  char v25; // [rsp+114h] [rbp-E4h]
  int v26; // [rsp+118h] [rbp-E0h]
  char v27; // [rsp+11Ch] [rbp-DCh]
  int v28; // [rsp+120h] [rbp-D8h]
  char v29; // [rsp+124h] [rbp-D4h]
  int v30; // [rsp+128h] [rbp-D0h]
  char v31; // [rsp+12Ch] [rbp-CCh]
  int v32; // [rsp+130h] [rbp-C8h]
  char v33; // [rsp+134h] [rbp-C4h]
  int v34; // [rsp+138h] [rbp-C0h]
  char v35; // [rsp+13Ch] [rbp-BCh]
  int v36; // [rsp+140h] [rbp-B8h]
  char v37; // [rsp+144h] [rbp-B4h]
  int v38; // [rsp+148h] [rbp-B0h]
  char v39; // [rsp+14Ch] [rbp-ACh]
  int v40; // [rsp+150h] [rbp-A8h]
  char v41; // [rsp+154h] [rbp-A4h]
  int v42; // [rsp+158h] [rbp-A0h]
  char v43; // [rsp+15Ch] [rbp-9Ch]
  int v44; // [rsp+160h] [rbp-98h]
  char v45; // [rsp+164h] [rbp-94h]
  int v46; // [rsp+168h] [rbp-90h]
  char v47; // [rsp+16Ch] [rbp-8Ch]
  int v48; // [rsp+170h] [rbp-88h]
  char v49; // [rsp+174h] [rbp-84h]
  int v50; // [rsp+178h] [rbp-80h]
  char v51; // [rsp+17Ch] [rbp-7Ch]
  int v52; // [rsp+180h] [rbp-78h]
  char v53; // [rsp+184h] [rbp-74h]
  int v54; // [rsp+188h] [rbp-70h]
  char v55; // [rsp+18Ch] [rbp-6Ch]
  int v56; // [rsp+190h] [rbp-68h]
  char v57; // [rsp+194h] [rbp-64h]
  int v58; // [rsp+198h] [rbp-60h]
  char v59; // [rsp+19Ch] [rbp-5Ch]
  int v60; // [rsp+1A0h] [rbp-58h]
  char v61; // [rsp+1A4h] [rbp-54h]
  int v62; // [rsp+1A8h] [rbp-50h]
  char v63; // [rsp+1ACh] [rbp-4Ch]
  int v64; // [rsp+1B0h] [rbp-48h]
  char v65; // [rsp+1B4h] [rbp-44h]
  int v66; // [rsp+1B8h] [rbp-40h]
  char v67; // [rsp+1BCh] [rbp-3Ch]

  memset_0(&instance, 0, 0x110u);
  v14 = 0;
  String = 0;
  v19 = 0;
  v20 = 0;
  v16[0] = &TelemetryEventWriter::`vftable';
  v16[1] = &v19;
  v16[2] = "MDM_Policy_Config01_SystemServices02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v19);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v20 && (v22[0] || v22[1] || v22[2] || v22[3]) )
      v5 = v22;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180359E71,
      v21,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v16, v4);
  try
  {
    v15 = 0;
    v7 = (unsigned int)CreateRequestHandlerInstance(
                         self,
                         0,
                         0,
                         &MDM_Policy_Config01_SystemServices02_NodeList,
                         24,
                         2,
                         &v15);
    if ( v7 == MI_RESULT_OK )
    {
      v17[1] = (const exception *)&v15;
      v18 = 1;
      v8 = v15;
      if ( v15 )
      {
        v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
        if ( v7 )
        {
          v6 = (wil *)v15;
          if ( v15 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
        }
        else
        {
          v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = (wil *)v15;
            if ( v15 )
              (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(v8[33] - v8[32]) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_SystemServices02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v15;
                if ( v15 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_115;
              }
              v14 = 1;
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v8 + 24LL))(
                      v8,
                      i,
                      L"SystemServices",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, String);
              }
              if ( a2 != 1 )
              {
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureComputerBrowserServiceStartupMode",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureHomeGroupListenerServiceStartupMode",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureHomeGroupProviderServiceStartupMode",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureIISAdminServiceStartupMode",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureInfraredMonitorServiceStartupMode",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureInternetConnectionSharingServiceStartupMode",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureLxssManagerServiceStartupMode",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureMicrosoftFTPServiceStartupMode",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureRemoteProcedureCallLocatorServiceStartupMode",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureRoutingAndRemoteAccessServiceStartupMode",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureSimpleTCPIPServicesStartupMode",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureSpecialAdministrationConsoleHelperServiceStartupMode",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureSSDPDiscoveryServiceStartupMode",
                        &String)
                  && String )
                {
                  v48 = _wtoi(String);
                  v49 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureUPnPDeviceHostServiceStartupMode",
                        &String)
                  && String )
                {
                  v50 = _wtoi(String);
                  v51 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureWebManagementServiceStartupMode",
                        &String)
                  && String )
                {
                  v52 = _wtoi(String);
                  v53 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode",
                        &String)
                  && String )
                {
                  v54 = _wtoi(String);
                  v55 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureWindowsMobileHotspotServiceStartupMode",
                        &String)
                  && String )
                {
                  v56 = _wtoi(String);
                  v57 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureWorldWideWebPublishingServiceStartupMode",
                        &String)
                  && String )
                {
                  v58 = _wtoi(String);
                  v59 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureXboxAccessoryManagementServiceStartupMode",
                        &String)
                  && String )
                {
                  v60 = _wtoi(String);
                  v61 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureXboxLiveAuthManagerServiceStartupMode",
                        &String)
                  && String )
                {
                  v62 = _wtoi(String);
                  v63 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureXboxLiveGameSaveServiceStartupMode",
                        &String)
                  && String )
                {
                  v64 = _wtoi(String);
                  v65 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureXboxLiveNetworkingServiceStartupMode",
                        &String)
                  && String )
                {
                  v66 = _wtoi(String);
                  v67 = 1;
                }
              }
              MI_Instance_Destruct((MI_Instance *)self);
              MI_Instance_Destruct(&instance);
              v14 = 0;
            }
            v6 = (wil *)v15;
            if ( v15 )
            {
              (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
              v15 = 0;
            }
          }
        }
      }
      else
      {
        v7 = MI_RESULT_FAILED;
      }
    }
  }
  catch ( const exception *v17 )
  {
    v11 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v17[0] + 8LL))(v17[0]);
    TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v16, v11);
    LODWORD(v15) = 1;
    goto LABEL_106;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v16, v12);
    LODWORD(v15) = 1;
LABEL_106:
    if ( v14 )
      MI_Instance_Destruct(&instance);
    v7 = (int)v15;
  }
LABEL_115:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v16, "EnumerateInstancesEnd", v7);
  v19 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_180350300,
      v21,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800e5b08  mov     [rsp+arg_8], rbx
0x1800e5b0d  mov     [rsp+arg_10], rsi
0x1800e5b12  push    rdi
0x1800e5b13  push    r12
0x1800e5b15  push    r13
0x1800e5b17  push    r14
0x1800e5b19  push    r15
0x1800e5b1b  sub     rsp, 1D0h
0x1800e5b22  mov     rax, cs:__security_cookie
0x1800e5b29  xor     rax, rsp
0x1800e5b2c  mov     [rsp+1F8h+var_38], rax
0x1800e5b34  mov     r13b, dl
0x1800e5b37  mov     r12, rcx
0x1800e5b3a  xor     edx, edx; Val
0x1800e5b3c  mov     r8d, 110h; Size
0x1800e5b42  lea     rcx, [rsp+1F8h+instance]; void *
0x1800e5b4a  call    memset_0
0x1800e5b4f  xor     edi, edi
0x1800e5b51  mov     [rsp+1F8h+var_1B0], dil
0x1800e5b56  mov     [rsp+1F8h+String], rdi
0x1800e5b5b  mov     [rsp+1F8h+var_170], edi
0x1800e5b62  mov     [rsp+1F8h+var_16C], dil
0x1800e5b6a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e5b71  mov     [rsp+1F8h+var_1A0], rax
0x1800e5b76  lea     rax, [rsp+1F8h+var_170]
0x1800e5b7e  mov     [rsp+1F8h+var_198], rax
0x1800e5b83  lea     rax, aMdmPolicyConfi_72; "MDM_Policy_Config01_SystemServices02"
0x1800e5b8a  mov     [rsp+1F8h+var_190], rax
0x1800e5b8f  lea     rcx, [rsp+1F8h+var_170]
0x1800e5b97  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e5b9c  mov     eax, cs:dword_180380B68
0x1800e5ba2  cmp     eax, 5
0x1800e5ba5  jbe     short loc_1800E5C17
0x1800e5ba7  mov     rdx, 200000000000h
0x1800e5bb1  lea     rcx, dword_180380B68
0x1800e5bb8  call    _tlgKeywordOn
0x1800e5bbd  test    al, al
0x1800e5bbf  jz      short loc_1800E5C17
0x1800e5bc1  cmp     [rsp+1F8h+var_16C], dil
0x1800e5bc9  jz      short loc_1800E5BF9
0x1800e5bcb  cmp     [rsp+1F8h+var_158], edi
0x1800e5bd2  jnz     short loc_1800E5BEF
0x1800e5bd4  cmp     [rsp+1F8h+var_154], edi
0x1800e5bdb  jnz     short loc_1800E5BEF
0x1800e5bdd  cmp     [rsp+1F8h+var_150], edi
0x1800e5be4  jnz     short loc_1800E5BEF
0x1800e5be6  cmp     [rsp+1F8h+var_14C], edi
0x1800e5bed  jz      short loc_1800E5BF9
0x1800e5bef  lea     r9, [rsp+1F8h+var_158]
0x1800e5bf7  jmp     short loc_1800E5BFC
0x1800e5bf9  mov     r9, rdi
0x1800e5bfc  lea     r8, [rsp+1F8h+var_168]
0x1800e5c04  lea     rdx, byte_180359E71
0x1800e5c0b  lea     rcx, dword_180380B68
0x1800e5c12  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e5c17  lea     rcx, [rsp+1F8h+var_1A0]; this
0x1800e5c1c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800e5c21  nop
0x1800e5c22  mov     [rsp+1F8h+var_1A8], rdi
0x1800e5c27  lea     rax, [rsp+1F8h+var_1A8]
0x1800e5c2c  mov     [rsp+1F8h+var_1C8], rax
0x1800e5c31  mov     [rsp+1F8h+var_1D0], 2
0x1800e5c39  mov     [rsp+1F8h+var_1D8], 18h
0x1800e5c41  lea     r9, ?MDM_Policy_Config01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_SystemServices02_NodeList
0x1800e5c48  xor     r8d, r8d
0x1800e5c4b  xor     edx, edx
0x1800e5c4d  mov     rcx, r12
0x1800e5c50  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e5c55  mov     r15d, eax
0x1800e5c58  test    eax, eax
0x1800e5c5a  jz      short loc_1800E5C61
0x1800e5c5c  jmp     loc_1800E646A
0x1800e5c61  lea     rbx, [rsp+1F8h+var_1A8]
0x1800e5c66  mov     [rsp+1F8h+var_180], rbx
0x1800e5c6b  mov     r14d, 1
0x1800e5c71  mov     [rsp+1F8h+var_178], r14b
0x1800e5c79  mov     rsi, [rsp+1F8h+var_1A8]
0x1800e5c7e  test    rsi, rsi
0x1800e5c81  jnz     short loc_1800E5C8B
0x1800e5c83  mov     r15d, r14d
0x1800e5c86  jmp     loc_1800E646A
0x1800e5c8b  mov     rax, [rsi]
0x1800e5c8e  mov     rcx, rsi
0x1800e5c91  mov     rax, [rax+10h]
0x1800e5c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5c9a  mov     r15d, eax
0x1800e5c9d  test    eax, eax
0x1800e5c9f  jz      short loc_1800E5CBF
0x1800e5ca1  mov     rcx, [rsp+1F8h+var_1A8]
0x1800e5ca6  test    rcx, rcx
0x1800e5ca9  jz      short loc_1800E5CBA
0x1800e5cab  mov     rax, [rcx]
0x1800e5cae  mov     edx, r14d
0x1800e5cb1  mov     rax, [rax]
0x1800e5cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5cb9  nop
0x1800e5cba  jmp     loc_1800E646A
0x1800e5cbf  mov     rax, [rsi]
0x1800e5cc2  mov     rcx, rsi
0x1800e5cc5  mov     rax, [rax+8]
0x1800e5cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5cce  mov     r15d, eax
0x1800e5cd1  test    eax, eax
0x1800e5cd3  jz      short loc_1800E5CF3
0x1800e5cd5  mov     rcx, [rsp+1F8h+var_1A8]
0x1800e5cda  test    rcx, rcx
0x1800e5cdd  jz      short loc_1800E5CEE
0x1800e5cdf  mov     rax, [rcx]
0x1800e5ce2  mov     edx, r14d
0x1800e5ce5  mov     rax, [rax]
0x1800e5ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5ced  nop
0x1800e5cee  jmp     loc_1800E646A
0x1800e5cf3  mov     r14d, edi
0x1800e5cf6  mov     rax, [rsi+108h]
0x1800e5cfd  sub     rax, [rsi+100h]
0x1800e5d04  sar     rax, 4
0x1800e5d08  cmp     r14d, eax
0x1800e5d0b  jnb     loc_1800E6432
0x1800e5d11  lea     r8, [rsp+1F8h+instance]; instance
0x1800e5d19  lea     rdx, MDM_Policy_Config01_SystemServices02_rtti; classDecl
0x1800e5d20  mov     rcx, r12; context
0x1800e5d23  call    MI_Context_ConstructInstance
0x1800e5d28  mov     r15d, eax
0x1800e5d2b  test    eax, eax
0x1800e5d2d  jz      short loc_1800E5D4F
0x1800e5d2f  mov     rcx, [rbx]
0x1800e5d32  test    rcx, rcx
0x1800e5d35  jz      short loc_1800E5D4A
0x1800e5d37  mov     rax, [rcx]
0x1800e5d3a  mov     edx, 1
0x1800e5d3f  mov     rax, [rax]
0x1800e5d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5d47  mov     [rbx], rdi
0x1800e5d4a  jmp     loc_1800E646A
0x1800e5d4f  mov     [rsp+1F8h+var_1B0], 1
0x1800e5d54  mov     rax, [rsi]
0x1800e5d57  lea     r9, [rsp+1F8h+String]
0x1800e5d5c  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800e5d63  mov     edx, r14d
0x1800e5d66  mov     rcx, rsi
0x1800e5d69  mov     rax, [rax+18h]
0x1800e5d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5d72  test    eax, eax
0x1800e5d74  jnz     short loc_1800E5D8D
0x1800e5d76  mov     rdx, [rsp+1F8h+String]
0x1800e5d7b  test    rdx, rdx
0x1800e5d7e  jz      short loc_1800E5D8D
0x1800e5d80  lea     rcx, [rsp+1F8h+instance]
0x1800e5d88  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800e5d8d  mov     rax, [rsi]
0x1800e5d90  lea     r9, [rsp+1F8h+String]
0x1800e5d95  lea     r8, aSystemservices; "SystemServices"
0x1800e5d9c  mov     edx, r14d
0x1800e5d9f  mov     rcx, rsi
0x1800e5da2  mov     rax, [rax+18h]
0x1800e5da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5dab  test    eax, eax
0x1800e5dad  jnz     short loc_1800E5DC6
0x1800e5daf  mov     rdx, [rsp+1F8h+String]
0x1800e5db4  test    rdx, rdx
0x1800e5db7  jz      short loc_1800E5DC6
0x1800e5db9  lea     rcx, [rsp+1F8h+instance]
0x1800e5dc1  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800e5dc6  cmp     r13b, 1
0x1800e5dca  jnz     short loc_1800E5DEE
0x1800e5dcc  lea     rdx, [rsp+1F8h+instance]
0x1800e5dd4  mov     rcx, r12; self
0x1800e5dd7  call    MI_Instance_Destruct
0x1800e5ddc  lea     rcx, [rsp+1F8h+instance]; self
0x1800e5de4  call    MI_Instance_Destruct
0x1800e5de9  jmp     loc_1800E6425
0x1800e5dee  mov     rax, [rsi]
0x1800e5df1  lea     r9, [rsp+1F8h+String]
0x1800e5df6  lea     r8, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x1800e5dfd  mov     edx, r14d
0x1800e5e00  mov     rcx, rsi
0x1800e5e03  mov     rax, [rax+18h]
0x1800e5e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5e0c  test    eax, eax
0x1800e5e0e  jnz     short loc_1800E5E35
0x1800e5e10  mov     rcx, [rsp+1F8h+String]; String
0x1800e5e15  test    rcx, rcx
0x1800e5e18  jz      short loc_1800E5E35
0x1800e5e1a  call    cs:__imp__wtoi
0x1800e5e21  nop     dword ptr [rax+rax+00h]
0x1800e5e26  mov     [rsp+1F8h+var_E8], eax
0x1800e5e2d  mov     [rsp+1F8h+var_E4], 1
0x1800e5e35  mov     rax, [rsi]
0x1800e5e38  lea     r9, [rsp+1F8h+String]
0x1800e5e3d  lea     r8, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x1800e5e44  mov     edx, r14d
0x1800e5e47  mov     rcx, rsi
0x1800e5e4a  mov     rax, [rax+18h]
0x1800e5e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5e53  test    eax, eax
0x1800e5e55  jnz     short loc_1800E5E7C
0x1800e5e57  mov     rcx, [rsp+1F8h+String]; String
0x1800e5e5c  test    rcx, rcx
0x1800e5e5f  jz      short loc_1800E5E7C
0x1800e5e61  call    cs:__imp__wtoi
0x1800e5e68  nop     dword ptr [rax+rax+00h]
0x1800e5e6d  mov     [rsp+1F8h+var_E0], eax
0x1800e5e74  mov     [rsp+1F8h+var_DC], 1
0x1800e5e7c  mov     rax, [rsi]
0x1800e5e7f  lea     r9, [rsp+1F8h+String]
0x1800e5e84  lea     r8, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x1800e5e8b  mov     edx, r14d
0x1800e5e8e  mov     rcx, rsi
0x1800e5e91  mov     rax, [rax+18h]
0x1800e5e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5e9a  test    eax, eax
0x1800e5e9c  jnz     short loc_1800E5EC3
0x1800e5e9e  mov     rcx, [rsp+1F8h+String]; String
0x1800e5ea3  test    rcx, rcx
0x1800e5ea6  jz      short loc_1800E5EC3
0x1800e5ea8  call    cs:__imp__wtoi
0x1800e5eaf  nop     dword ptr [rax+rax+00h]
0x1800e5eb4  mov     [rsp+1F8h+var_D8], eax
0x1800e5ebb  mov     [rsp+1F8h+var_D4], 1
0x1800e5ec3  mov     rax, [rsi]
0x1800e5ec6  lea     r9, [rsp+1F8h+String]
0x1800e5ecb  lea     r8, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x1800e5ed2  mov     edx, r14d
0x1800e5ed5  mov     rcx, rsi
0x1800e5ed8  mov     rax, [rax+18h]
0x1800e5edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5ee1  test    eax, eax
0x1800e5ee3  jnz     short loc_1800E5F0A
0x1800e5ee5  mov     rcx, [rsp+1F8h+String]; String
0x1800e5eea  test    rcx, rcx
0x1800e5eed  jz      short loc_1800E5F0A
0x1800e5eef  call    cs:__imp__wtoi
0x1800e5ef6  nop     dword ptr [rax+rax+00h]
0x1800e5efb  mov     [rsp+1F8h+var_D0], eax
0x1800e5f02  mov     [rsp+1F8h+var_CC], 1
0x1800e5f0a  mov     rax, [rsi]
0x1800e5f0d  lea     r9, [rsp+1F8h+String]
0x1800e5f12  lea     r8, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x1800e5f19  mov     edx, r14d
0x1800e5f1c  mov     rcx, rsi
0x1800e5f1f  mov     rax, [rax+18h]
0x1800e5f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5f28  test    eax, eax
0x1800e5f2a  jnz     short loc_1800E5F51
0x1800e5f2c  mov     rcx, [rsp+1F8h+String]; String
0x1800e5f31  test    rcx, rcx
0x1800e5f34  jz      short loc_1800E5F51
0x1800e5f36  call    cs:__imp__wtoi
0x1800e5f3d  nop     dword ptr [rax+rax+00h]
0x1800e5f42  mov     [rsp+1F8h+var_C8], eax
0x1800e5f49  mov     [rsp+1F8h+var_C4], 1
0x1800e5f51  mov     rax, [rsi]
0x1800e5f54  lea     r9, [rsp+1F8h+String]
0x1800e5f59  lea     r8, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x1800e5f60  mov     edx, r14d
0x1800e5f63  mov     rcx, rsi
0x1800e5f66  mov     rax, [rax+18h]
0x1800e5f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5f6f  test    eax, eax
0x1800e5f71  jnz     short loc_1800E5F98
0x1800e5f73  mov     rcx, [rsp+1F8h+String]; String
0x1800e5f78  test    rcx, rcx
0x1800e5f7b  jz      short loc_1800E5F98
0x1800e5f7d  call    cs:__imp__wtoi
0x1800e5f84  nop     dword ptr [rax+rax+00h]
0x1800e5f89  mov     [rsp+1F8h+var_C0], eax
0x1800e5f90  mov     [rsp+1F8h+var_BC], 1
0x1800e5f98  mov     rax, [rsi]
0x1800e5f9b  lea     r9, [rsp+1F8h+String]
0x1800e5fa0  lea     r8, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x1800e5fa7  mov     edx, r14d
0x1800e5faa  mov     rcx, rsi
0x1800e5fad  mov     rax, [rax+18h]
0x1800e5fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5fb6  test    eax, eax
0x1800e5fb8  jnz     short loc_1800E5FDF
0x1800e5fba  mov     rcx, [rsp+1F8h+String]; String
0x1800e5fbf  test    rcx, rcx
0x1800e5fc2  jz      short loc_1800E5FDF
0x1800e5fc4  call    cs:__imp__wtoi
0x1800e5fcb  nop     dword ptr [rax+rax+00h]
0x1800e5fd0  mov     [rsp+1F8h+var_B8], eax
0x1800e5fd7  mov     [rsp+1F8h+var_B4], 1
0x1800e5fdf  mov     rax, [rsi]
0x1800e5fe2  lea     r9, [rsp+1F8h+String]
0x1800e5fe7  lea     r8, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x1800e5fee  mov     edx, r14d
0x1800e5ff1  mov     rcx, rsi
0x1800e5ff4  mov     rax, [rax+18h]
0x1800e5ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5ffd  test    eax, eax
0x1800e5fff  jnz     short loc_1800E6026
0x1800e6001  mov     rcx, [rsp+1F8h+String]; String
0x1800e6006  test    rcx, rcx
0x1800e6009  jz      short loc_1800E6026
0x1800e600b  call    cs:__imp__wtoi
0x1800e6012  nop     dword ptr [rax+rax+00h]
0x1800e6017  mov     [rsp+1F8h+var_B0], eax
0x1800e601e  mov     [rsp+1F8h+var_AC], 1
  ... truncated ...
```
