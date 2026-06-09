# MDM_Policy_Config01_SystemServices02_InvokeEnumerateInstances

- ea: `0x1800e6374`
- end: `0x1800e6cf2`
- name: `MDM_Policy_Config01_SystemServices02_InvokeEnumerateInstances`
- size: `2430`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e5770`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800e6374`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800e6686`
- `msvcrt!_wtoi` at `0x1800e66c7`
- `msvcrt!_wtoi` at `0x1800e6708`
- `msvcrt!_wtoi` at `0x1800e6749`
- `msvcrt!_wtoi` at `0x1800e678a`
- `msvcrt!_wtoi` at `0x1800e67cb`
- `msvcrt!_wtoi` at `0x1800e680c`
- `msvcrt!_wtoi` at `0x1800e684d`
- `msvcrt!_wtoi` at `0x1800e688e`
- `msvcrt!_wtoi` at `0x1800e68cf`
- `msvcrt!_wtoi` at `0x1800e6910`
- `msvcrt!_wtoi` at `0x1800e6951`
- `msvcrt!_wtoi` at `0x1800e6992`
- `msvcrt!_wtoi` at `0x1800e69d3`
- `msvcrt!_wtoi` at `0x1800e6a14`
- `msvcrt!_wtoi` at `0x1800e6a55`
- `msvcrt!_wtoi` at `0x1800e6a96`
- `msvcrt!_wtoi` at `0x1800e6ad7`
- `msvcrt!_wtoi` at `0x1800e6b18`
- `msvcrt!_wtoi` at `0x1800e6b59`
- `msvcrt!_wtoi` at `0x1800e6b9a`
- `msvcrt!_wtoi` at `0x1800e6bdb`
- `msvcrt!_wtoi` at `0x1800e6686`
- `msvcrt!_wtoi` at `0x1800e66c7`
- `msvcrt!_wtoi` at `0x1800e6708`
- `msvcrt!_wtoi` at `0x1800e6749`
- `msvcrt!_wtoi` at `0x1800e678a`
- `msvcrt!_wtoi` at `0x1800e67cb`
- `msvcrt!_wtoi` at `0x1800e680c`
- `msvcrt!_wtoi` at `0x1800e684d`
- `msvcrt!_wtoi` at `0x1800e688e`
- `msvcrt!_wtoi` at `0x1800e68cf`
- `msvcrt!_wtoi` at `0x1800e6910`
- `msvcrt!_wtoi` at `0x1800e6951`
- `msvcrt!_wtoi` at `0x1800e6992`
- `msvcrt!_wtoi` at `0x1800e69d3`
- `msvcrt!_wtoi` at `0x1800e6a14`
- `msvcrt!_wtoi` at `0x1800e6a55`
- `msvcrt!_wtoi` at `0x1800e6a96`
- `msvcrt!_wtoi` at `0x1800e6ad7`
- `msvcrt!_wtoi` at `0x1800e6b18`
- `msvcrt!_wtoi` at `0x1800e6b59`
- `msvcrt!_wtoi` at `0x1800e6b9a`
- `msvcrt!_wtoi` at `0x1800e6bdb`

## string_xrefs

- `0x1800e6662`: `ConfigureComputerBrowserServiceStartupMode`
- `0x1800e66a3`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x1800e66e4`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x1800e6725`: `ConfigureIISAdminServiceStartupMode`
- `0x1800e6766`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x1800e67a7`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x1800e67e8`: `ConfigureLxssManagerServiceStartupMode`
- `0x1800e6829`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x1800e686a`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x1800e68ab`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x1800e68ec`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x1800e692d`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x1800e696e`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x1800e69af`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x1800e69f0`: `ConfigureWebManagementServiceStartupMode`
- `0x1800e6a31`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x1800e6a72`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x1800e6ab3`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x1800e6af4`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x1800e6b35`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x1800e6b76`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x1800e6bb7`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x1800e65c8`: `./Vendor/MSFT/Policy/Config`
- `0x1800e63ef`: `MDM_Policy_Config01_SystemServices02`
- `0x1800e6601`: `SystemServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_SystemServices02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r15d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-1B8h] BYREF
  char v14; // [rsp+48h] [rbp-1B0h]
  WmiRequestHandlerAdd *v15; // [rsp+50h] [rbp-1A8h] BYREF
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
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_SystemServices02_NodeList,
           0x18u,
           2,
           &v15);
    if ( !v7 )
    {
      v17[1] = (const exception *)&v15;
      v18 = 1;
      v8 = v15;
      if ( v15 )
      {
        v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v7 )
        {
          v6 = v15;
          if ( v15 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
        }
        else
        {
          v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = v15;
            if ( v15 )
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v8 + 33) - *((_QWORD *)v8 + 32)) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_SystemServices02_rtti, &instance);
              if ( v7 )
              {
                v6 = v15;
                if ( v15 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_115;
              }
              v14 = 1;
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureComputerBrowserServiceStartupMode",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureHomeGroupListenerServiceStartupMode",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureHomeGroupProviderServiceStartupMode",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureIISAdminServiceStartupMode",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureInfraredMonitorServiceStartupMode",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureInternetConnectionSharingServiceStartupMode",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureLxssManagerServiceStartupMode",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureMicrosoftFTPServiceStartupMode",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureRemoteProcedureCallLocatorServiceStartupMode",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureRoutingAndRemoteAccessServiceStartupMode",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureSimpleTCPIPServicesStartupMode",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureSpecialAdministrationConsoleHelperServiceStartupMode",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureSSDPDiscoveryServiceStartupMode",
                        &String)
                  && String )
                {
                  v48 = _wtoi(String);
                  v49 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureUPnPDeviceHostServiceStartupMode",
                        &String)
                  && String )
                {
                  v50 = _wtoi(String);
                  v51 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureWebManagementServiceStartupMode",
                        &String)
                  && String )
                {
                  v52 = _wtoi(String);
                  v53 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode",
                        &String)
                  && String )
                {
                  v54 = _wtoi(String);
                  v55 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureWindowsMobileHotspotServiceStartupMode",
                        &String)
                  && String )
                {
                  v56 = _wtoi(String);
                  v57 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureWorldWideWebPublishingServiceStartupMode",
                        &String)
                  && String )
                {
                  v58 = _wtoi(String);
                  v59 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureXboxAccessoryManagementServiceStartupMode",
                        &String)
                  && String )
                {
                  v60 = _wtoi(String);
                  v61 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureXboxLiveAuthManagerServiceStartupMode",
                        &String)
                  && String )
                {
                  v62 = _wtoi(String);
                  v63 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureXboxLiveGameSaveServiceStartupMode",
                        &String)
                  && String )
                {
                  v64 = _wtoi(String);
                  v65 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
            v6 = v15;
            if ( v15 )
            {
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
              v15 = 0;
            }
          }
        }
      }
      else
      {
        v7 = 1;
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
    v7 = (unsigned int)v15;
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
  return v7;
}

```

## disassembly

```asm
0x1800e6374  mov     [rsp+arg_8], rbx
0x1800e6379  mov     [rsp+arg_10], rsi
0x1800e637e  push    rdi
0x1800e637f  push    r12
0x1800e6381  push    r13
0x1800e6383  push    r14
0x1800e6385  push    r15
0x1800e6387  sub     rsp, 1D0h
0x1800e638e  mov     rax, cs:__security_cookie
0x1800e6395  xor     rax, rsp
0x1800e6398  mov     [rsp+1F8h+var_38], rax
0x1800e63a0  mov     r13b, dl
0x1800e63a3  mov     r12, rcx
0x1800e63a6  xor     edx, edx; Val
0x1800e63a8  mov     r8d, 110h; Size
0x1800e63ae  lea     rcx, [rsp+1F8h+instance]; void *
0x1800e63b6  call    memset_0
0x1800e63bb  xor     edi, edi
0x1800e63bd  mov     [rsp+1F8h+var_1B0], dil
0x1800e63c2  mov     [rsp+1F8h+String], rdi
0x1800e63c7  mov     [rsp+1F8h+var_170], edi
0x1800e63ce  mov     [rsp+1F8h+var_16C], dil
0x1800e63d6  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e63dd  mov     [rsp+1F8h+var_1A0], rax
0x1800e63e2  lea     rax, [rsp+1F8h+var_170]
0x1800e63ea  mov     [rsp+1F8h+var_198], rax
0x1800e63ef  lea     rax, aMdmPolicyConfi_72; "MDM_Policy_Config01_SystemServices02"
0x1800e63f6  mov     [rsp+1F8h+var_190], rax
0x1800e63fb  lea     rcx, [rsp+1F8h+var_170]
0x1800e6403  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e6408  mov     eax, cs:dword_180380B68
0x1800e640e  cmp     eax, 5
0x1800e6411  jbe     short loc_1800E6483
0x1800e6413  mov     rdx, 200000000000h
0x1800e641d  lea     rcx, dword_180380B68
0x1800e6424  call    _tlgKeywordOn
0x1800e6429  test    al, al
0x1800e642b  jz      short loc_1800E6483
0x1800e642d  cmp     [rsp+1F8h+var_16C], dil
0x1800e6435  jz      short loc_1800E6465
0x1800e6437  cmp     [rsp+1F8h+var_158], edi
0x1800e643e  jnz     short loc_1800E645B
0x1800e6440  cmp     [rsp+1F8h+var_154], edi
0x1800e6447  jnz     short loc_1800E645B
0x1800e6449  cmp     [rsp+1F8h+var_150], edi
0x1800e6450  jnz     short loc_1800E645B
0x1800e6452  cmp     [rsp+1F8h+var_14C], edi
0x1800e6459  jz      short loc_1800E6465
0x1800e645b  lea     r9, [rsp+1F8h+var_158]
0x1800e6463  jmp     short loc_1800E6468
0x1800e6465  mov     r9, rdi
0x1800e6468  lea     r8, [rsp+1F8h+var_168]
0x1800e6470  lea     rdx, byte_180359E71
0x1800e6477  lea     rcx, dword_180380B68
0x1800e647e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e6483  lea     rcx, [rsp+1F8h+var_1A0]; this
0x1800e6488  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800e648d  nop
0x1800e648e  mov     [rsp+1F8h+var_1A8], rdi
0x1800e6493  lea     rax, [rsp+1F8h+var_1A8]
0x1800e6498  mov     [rsp+1F8h+var_1C8], rax
0x1800e649d  mov     [rsp+1F8h+var_1D0], 2
0x1800e64a5  mov     [rsp+1F8h+var_1D8], 18h
0x1800e64ad  lea     r9, ?MDM_Policy_Config01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_SystemServices02_NodeList
0x1800e64b4  xor     r8d, r8d
0x1800e64b7  xor     edx, edx
0x1800e64b9  mov     rcx, r12
0x1800e64bc  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e64c1  mov     r15d, eax
0x1800e64c4  test    eax, eax
0x1800e64c6  jz      short loc_1800E64CD
0x1800e64c8  jmp     loc_1800E6C52
0x1800e64cd  lea     rbx, [rsp+1F8h+var_1A8]
0x1800e64d2  mov     [rsp+1F8h+var_180], rbx
0x1800e64d7  mov     r14d, 1
0x1800e64dd  mov     [rsp+1F8h+var_178], r14b
0x1800e64e5  mov     rsi, [rsp+1F8h+var_1A8]
0x1800e64ea  test    rsi, rsi
0x1800e64ed  jnz     short loc_1800E64F7
0x1800e64ef  mov     r15d, r14d
0x1800e64f2  jmp     loc_1800E6C52
0x1800e64f7  mov     rax, [rsi]
0x1800e64fa  mov     rcx, rsi
0x1800e64fd  mov     rax, [rax+10h]
0x1800e6501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6506  mov     r15d, eax
0x1800e6509  test    eax, eax
0x1800e650b  jz      short loc_1800E652B
0x1800e650d  mov     rcx, [rsp+1F8h+var_1A8]
0x1800e6512  test    rcx, rcx
0x1800e6515  jz      short loc_1800E6526
0x1800e6517  mov     rax, [rcx]
0x1800e651a  mov     edx, r14d
0x1800e651d  mov     rax, [rax]
0x1800e6520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6525  nop
0x1800e6526  jmp     loc_1800E6C52
0x1800e652b  mov     rax, [rsi]
0x1800e652e  mov     rcx, rsi
0x1800e6531  mov     rax, [rax+8]
0x1800e6535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e653a  mov     r15d, eax
0x1800e653d  test    eax, eax
0x1800e653f  jz      short loc_1800E655F
0x1800e6541  mov     rcx, [rsp+1F8h+var_1A8]
0x1800e6546  test    rcx, rcx
0x1800e6549  jz      short loc_1800E655A
0x1800e654b  mov     rax, [rcx]
0x1800e654e  mov     edx, r14d
0x1800e6551  mov     rax, [rax]
0x1800e6554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6559  nop
0x1800e655a  jmp     loc_1800E6C52
0x1800e655f  mov     r14d, edi
0x1800e6562  mov     rax, [rsi+108h]
0x1800e6569  sub     rax, [rsi+100h]
0x1800e6570  sar     rax, 4
0x1800e6574  cmp     r14d, eax
0x1800e6577  jnb     loc_1800E6C1A
0x1800e657d  lea     r8, [rsp+1F8h+instance]; instance
0x1800e6585  lea     rdx, MDM_Policy_Config01_SystemServices02_rtti; classDecl
0x1800e658c  mov     rcx, r12; context
0x1800e658f  call    MI_Context_ConstructInstance
0x1800e6594  mov     r15d, eax
0x1800e6597  test    eax, eax
0x1800e6599  jz      short loc_1800E65BB
0x1800e659b  mov     rcx, [rbx]
0x1800e659e  test    rcx, rcx
0x1800e65a1  jz      short loc_1800E65B6
0x1800e65a3  mov     rax, [rcx]
0x1800e65a6  mov     edx, 1
0x1800e65ab  mov     rax, [rax]
0x1800e65ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e65b3  mov     [rbx], rdi
0x1800e65b6  jmp     loc_1800E6C52
0x1800e65bb  mov     [rsp+1F8h+var_1B0], 1
0x1800e65c0  mov     rax, [rsi]
0x1800e65c3  lea     r9, [rsp+1F8h+String]
0x1800e65c8  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800e65cf  mov     edx, r14d
0x1800e65d2  mov     rcx, rsi
0x1800e65d5  mov     rax, [rax+18h]
0x1800e65d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e65de  test    eax, eax
0x1800e65e0  jnz     short loc_1800E65F9
0x1800e65e2  mov     rdx, [rsp+1F8h+String]
0x1800e65e7  test    rdx, rdx
0x1800e65ea  jz      short loc_1800E65F9
0x1800e65ec  lea     rcx, [rsp+1F8h+instance]
0x1800e65f4  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800e65f9  mov     rax, [rsi]
0x1800e65fc  lea     r9, [rsp+1F8h+String]
0x1800e6601  lea     r8, aSystemservices; "SystemServices"
0x1800e6608  mov     edx, r14d
0x1800e660b  mov     rcx, rsi
0x1800e660e  mov     rax, [rax+18h]
0x1800e6612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6617  test    eax, eax
0x1800e6619  jnz     short loc_1800E6632
0x1800e661b  mov     rdx, [rsp+1F8h+String]
0x1800e6620  test    rdx, rdx
0x1800e6623  jz      short loc_1800E6632
0x1800e6625  lea     rcx, [rsp+1F8h+instance]
0x1800e662d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800e6632  cmp     r13b, 1
0x1800e6636  jnz     short loc_1800E665A
0x1800e6638  lea     rdx, [rsp+1F8h+instance]
0x1800e6640  mov     rcx, r12; self
0x1800e6643  call    MI_Instance_Destruct
0x1800e6648  lea     rcx, [rsp+1F8h+instance]; self
0x1800e6650  call    MI_Instance_Destruct
0x1800e6655  jmp     loc_1800E6C0D
0x1800e665a  mov     rax, [rsi]
0x1800e665d  lea     r9, [rsp+1F8h+String]
0x1800e6662  lea     r8, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x1800e6669  mov     edx, r14d
0x1800e666c  mov     rcx, rsi
0x1800e666f  mov     rax, [rax+18h]
0x1800e6673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6678  test    eax, eax
0x1800e667a  jnz     short loc_1800E669B
0x1800e667c  mov     rcx, [rsp+1F8h+String]; String
0x1800e6681  test    rcx, rcx
0x1800e6684  jz      short loc_1800E669B
0x1800e6686  call    cs:__imp__wtoi
0x1800e668c  mov     [rsp+1F8h+var_E8], eax
0x1800e6693  mov     [rsp+1F8h+var_E4], 1
0x1800e669b  mov     rax, [rsi]
0x1800e669e  lea     r9, [rsp+1F8h+String]
0x1800e66a3  lea     r8, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x1800e66aa  mov     edx, r14d
0x1800e66ad  mov     rcx, rsi
0x1800e66b0  mov     rax, [rax+18h]
0x1800e66b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e66b9  test    eax, eax
0x1800e66bb  jnz     short loc_1800E66DC
0x1800e66bd  mov     rcx, [rsp+1F8h+String]; String
0x1800e66c2  test    rcx, rcx
0x1800e66c5  jz      short loc_1800E66DC
0x1800e66c7  call    cs:__imp__wtoi
0x1800e66cd  mov     [rsp+1F8h+var_E0], eax
0x1800e66d4  mov     [rsp+1F8h+var_DC], 1
0x1800e66dc  mov     rax, [rsi]
0x1800e66df  lea     r9, [rsp+1F8h+String]
0x1800e66e4  lea     r8, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x1800e66eb  mov     edx, r14d
0x1800e66ee  mov     rcx, rsi
0x1800e66f1  mov     rax, [rax+18h]
0x1800e66f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e66fa  test    eax, eax
0x1800e66fc  jnz     short loc_1800E671D
0x1800e66fe  mov     rcx, [rsp+1F8h+String]; String
0x1800e6703  test    rcx, rcx
0x1800e6706  jz      short loc_1800E671D
0x1800e6708  call    cs:__imp__wtoi
0x1800e670e  mov     [rsp+1F8h+var_D8], eax
0x1800e6715  mov     [rsp+1F8h+var_D4], 1
0x1800e671d  mov     rax, [rsi]
0x1800e6720  lea     r9, [rsp+1F8h+String]
0x1800e6725  lea     r8, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x1800e672c  mov     edx, r14d
0x1800e672f  mov     rcx, rsi
0x1800e6732  mov     rax, [rax+18h]
0x1800e6736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e673b  test    eax, eax
0x1800e673d  jnz     short loc_1800E675E
0x1800e673f  mov     rcx, [rsp+1F8h+String]; String
0x1800e6744  test    rcx, rcx
0x1800e6747  jz      short loc_1800E675E
0x1800e6749  call    cs:__imp__wtoi
0x1800e674f  mov     [rsp+1F8h+var_D0], eax
0x1800e6756  mov     [rsp+1F8h+var_CC], 1
0x1800e675e  mov     rax, [rsi]
0x1800e6761  lea     r9, [rsp+1F8h+String]
0x1800e6766  lea     r8, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x1800e676d  mov     edx, r14d
0x1800e6770  mov     rcx, rsi
0x1800e6773  mov     rax, [rax+18h]
0x1800e6777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e677c  test    eax, eax
0x1800e677e  jnz     short loc_1800E679F
0x1800e6780  mov     rcx, [rsp+1F8h+String]; String
0x1800e6785  test    rcx, rcx
0x1800e6788  jz      short loc_1800E679F
0x1800e678a  call    cs:__imp__wtoi
0x1800e6790  mov     [rsp+1F8h+var_C8], eax
0x1800e6797  mov     [rsp+1F8h+var_C4], 1
0x1800e679f  mov     rax, [rsi]
0x1800e67a2  lea     r9, [rsp+1F8h+String]
0x1800e67a7  lea     r8, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x1800e67ae  mov     edx, r14d
0x1800e67b1  mov     rcx, rsi
0x1800e67b4  mov     rax, [rax+18h]
0x1800e67b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e67bd  test    eax, eax
0x1800e67bf  jnz     short loc_1800E67E0
0x1800e67c1  mov     rcx, [rsp+1F8h+String]; String
0x1800e67c6  test    rcx, rcx
0x1800e67c9  jz      short loc_1800E67E0
0x1800e67cb  call    cs:__imp__wtoi
0x1800e67d1  mov     [rsp+1F8h+var_C0], eax
0x1800e67d8  mov     [rsp+1F8h+var_BC], 1
0x1800e67e0  mov     rax, [rsi]
0x1800e67e3  lea     r9, [rsp+1F8h+String]
0x1800e67e8  lea     r8, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x1800e67ef  mov     edx, r14d
0x1800e67f2  mov     rcx, rsi
0x1800e67f5  mov     rax, [rax+18h]
0x1800e67f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e67fe  test    eax, eax
0x1800e6800  jnz     short loc_1800E6821
0x1800e6802  mov     rcx, [rsp+1F8h+String]; String
0x1800e6807  test    rcx, rcx
0x1800e680a  jz      short loc_1800E6821
0x1800e680c  call    cs:__imp__wtoi
0x1800e6812  mov     [rsp+1F8h+var_B8], eax
0x1800e6819  mov     [rsp+1F8h+var_B4], 1
0x1800e6821  mov     rax, [rsi]
0x1800e6824  lea     r9, [rsp+1F8h+String]
0x1800e6829  lea     r8, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x1800e6830  mov     edx, r14d
0x1800e6833  mov     rcx, rsi
0x1800e6836  mov     rax, [rax+18h]
0x1800e683a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e683f  test    eax, eax
0x1800e6841  jnz     short loc_1800E6862
0x1800e6843  mov     rcx, [rsp+1F8h+String]; String
0x1800e6848  test    rcx, rcx
0x1800e684b  jz      short loc_1800E6862
0x1800e684d  call    cs:__imp__wtoi
0x1800e6853  mov     [rsp+1F8h+var_B0], eax
0x1800e685a  mov     [rsp+1F8h+var_AC], 1
0x1800e6862  mov     rax, [rsi]
0x1800e6865  lea     r9, [rsp+1F8h+String]
0x1800e686a  lea     r8, aConfigureremot; "ConfigureRemoteProcedureCallLocatorServ"...
0x1800e6871  mov     edx, r14d
0x1800e6874  mov     rcx, rsi
0x1800e6877  mov     rax, [rax+18h]
0x1800e687b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6880  test    eax, eax
  ... truncated ...
```
