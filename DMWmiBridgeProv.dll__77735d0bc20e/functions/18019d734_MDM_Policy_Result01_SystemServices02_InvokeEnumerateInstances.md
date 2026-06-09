# MDM_Policy_Result01_SystemServices02_InvokeEnumerateInstances

- ea: `0x18019d734`
- end: `0x18019e0b2`
- name: `MDM_Policy_Result01_SystemServices02_InvokeEnumerateInstances`
- size: `2430`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18019cb30`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18019d734`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18019da46`
- `msvcrt!_wtoi` at `0x18019da87`
- `msvcrt!_wtoi` at `0x18019dac8`
- `msvcrt!_wtoi` at `0x18019db09`
- `msvcrt!_wtoi` at `0x18019db4a`
- `msvcrt!_wtoi` at `0x18019db8b`
- `msvcrt!_wtoi` at `0x18019dbcc`
- `msvcrt!_wtoi` at `0x18019dc0d`
- `msvcrt!_wtoi` at `0x18019dc4e`
- `msvcrt!_wtoi` at `0x18019dc8f`
- `msvcrt!_wtoi` at `0x18019dcd0`
- `msvcrt!_wtoi` at `0x18019dd11`
- `msvcrt!_wtoi` at `0x18019dd52`
- `msvcrt!_wtoi` at `0x18019dd93`
- `msvcrt!_wtoi` at `0x18019ddd4`
- `msvcrt!_wtoi` at `0x18019de15`
- `msvcrt!_wtoi` at `0x18019de56`
- `msvcrt!_wtoi` at `0x18019de97`
- `msvcrt!_wtoi` at `0x18019ded8`
- `msvcrt!_wtoi` at `0x18019df19`
- `msvcrt!_wtoi` at `0x18019df5a`
- `msvcrt!_wtoi` at `0x18019df9b`
- `msvcrt!_wtoi` at `0x18019da46`
- `msvcrt!_wtoi` at `0x18019da87`
- `msvcrt!_wtoi` at `0x18019dac8`
- `msvcrt!_wtoi` at `0x18019db09`
- `msvcrt!_wtoi` at `0x18019db4a`
- `msvcrt!_wtoi` at `0x18019db8b`
- `msvcrt!_wtoi` at `0x18019dbcc`
- `msvcrt!_wtoi` at `0x18019dc0d`
- `msvcrt!_wtoi` at `0x18019dc4e`
- `msvcrt!_wtoi` at `0x18019dc8f`
- `msvcrt!_wtoi` at `0x18019dcd0`
- `msvcrt!_wtoi` at `0x18019dd11`
- `msvcrt!_wtoi` at `0x18019dd52`
- `msvcrt!_wtoi` at `0x18019dd93`
- `msvcrt!_wtoi` at `0x18019ddd4`
- `msvcrt!_wtoi` at `0x18019de15`
- `msvcrt!_wtoi` at `0x18019de56`
- `msvcrt!_wtoi` at `0x18019de97`
- `msvcrt!_wtoi` at `0x18019ded8`
- `msvcrt!_wtoi` at `0x18019df19`
- `msvcrt!_wtoi` at `0x18019df5a`
- `msvcrt!_wtoi` at `0x18019df9b`

## string_xrefs

- `0x18019da22`: `ConfigureComputerBrowserServiceStartupMode`
- `0x18019da63`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x18019daa4`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x18019dae5`: `ConfigureIISAdminServiceStartupMode`
- `0x18019db26`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x18019db67`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x18019dba8`: `ConfigureLxssManagerServiceStartupMode`
- `0x18019dbe9`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x18019dc2a`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x18019dc6b`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x18019dcac`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x18019dced`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x18019dd2e`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x18019dd6f`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x18019ddb0`: `ConfigureWebManagementServiceStartupMode`
- `0x18019ddf1`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x18019de32`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x18019de73`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x18019deb4`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x18019def5`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x18019df36`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x18019df77`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x18019d7af`: `MDM_Policy_Result01_SystemServices02`
- `0x18019d9c1`: `SystemServices`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_SystemServices02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  unsigned int v6; // r15d
  WmiRequestHandlerAdd *v7; // rsi
  unsigned int i; // r14d
  wchar_t *String; // [rsp+40h] [rbp-1B8h] BYREF
  char v11; // [rsp+48h] [rbp-1B0h]
  WmiRequestHandlerAdd *v12; // [rsp+50h] [rbp-1A8h] BYREF
  _QWORD v13[5]; // [rsp+58h] [rbp-1A0h] BYREF
  char v14; // [rsp+80h] [rbp-178h]
  int v15; // [rsp+88h] [rbp-170h] BYREF
  char v16; // [rsp+8Ch] [rbp-16Ch]
  _BYTE v17[16]; // [rsp+90h] [rbp-168h] BYREF
  _DWORD v18[4]; // [rsp+A0h] [rbp-158h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-148h] BYREF
  int v20; // [rsp+110h] [rbp-E8h]
  char v21; // [rsp+114h] [rbp-E4h]
  int v22; // [rsp+118h] [rbp-E0h]
  char v23; // [rsp+11Ch] [rbp-DCh]
  int v24; // [rsp+120h] [rbp-D8h]
  char v25; // [rsp+124h] [rbp-D4h]
  int v26; // [rsp+128h] [rbp-D0h]
  char v27; // [rsp+12Ch] [rbp-CCh]
  int v28; // [rsp+130h] [rbp-C8h]
  char v29; // [rsp+134h] [rbp-C4h]
  int v30; // [rsp+138h] [rbp-C0h]
  char v31; // [rsp+13Ch] [rbp-BCh]
  int v32; // [rsp+140h] [rbp-B8h]
  char v33; // [rsp+144h] [rbp-B4h]
  int v34; // [rsp+148h] [rbp-B0h]
  char v35; // [rsp+14Ch] [rbp-ACh]
  int v36; // [rsp+150h] [rbp-A8h]
  char v37; // [rsp+154h] [rbp-A4h]
  int v38; // [rsp+158h] [rbp-A0h]
  char v39; // [rsp+15Ch] [rbp-9Ch]
  int v40; // [rsp+160h] [rbp-98h]
  char v41; // [rsp+164h] [rbp-94h]
  int v42; // [rsp+168h] [rbp-90h]
  char v43; // [rsp+16Ch] [rbp-8Ch]
  int v44; // [rsp+170h] [rbp-88h]
  char v45; // [rsp+174h] [rbp-84h]
  int v46; // [rsp+178h] [rbp-80h]
  char v47; // [rsp+17Ch] [rbp-7Ch]
  int v48; // [rsp+180h] [rbp-78h]
  char v49; // [rsp+184h] [rbp-74h]
  int v50; // [rsp+188h] [rbp-70h]
  char v51; // [rsp+18Ch] [rbp-6Ch]
  int v52; // [rsp+190h] [rbp-68h]
  char v53; // [rsp+194h] [rbp-64h]
  int v54; // [rsp+198h] [rbp-60h]
  char v55; // [rsp+19Ch] [rbp-5Ch]
  int v56; // [rsp+1A0h] [rbp-58h]
  char v57; // [rsp+1A4h] [rbp-54h]
  int v58; // [rsp+1A8h] [rbp-50h]
  char v59; // [rsp+1ACh] [rbp-4Ch]
  int v60; // [rsp+1B0h] [rbp-48h]
  char v61; // [rsp+1B4h] [rbp-44h]
  int v62; // [rsp+1B8h] [rbp-40h]
  char v63; // [rsp+1BCh] [rbp-3Ch]

  memset_0(&instance, 0, 0x110u);
  v11 = 0;
  String = 0;
  v15 = 0;
  v16 = 0;
  v13[0] = &TelemetryEventWriter::`vftable';
  v13[1] = &v15;
  v13[2] = "MDM_Policy_Result01_SystemServices02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v5 = v18;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_180337FEA,
      v17,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v13, v4);
  v12 = 0;
  v6 = CreateRequestHandlerInstance(
         (__int64)self,
         0,
         0,
         (struct WmiNodeInfo *)&MDM_Policy_Result01_SystemServices02_NodeList,
         0x18u,
         2,
         &v12);
  if ( !v6 )
  {
    v13[4] = &v12;
    v14 = 1;
    v7 = v12;
    if ( v12 )
    {
      v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v6 )
      {
        if ( v12 )
          (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
      }
      else
      {
        v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v12 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v7 + 33) - *((_QWORD *)v7 + 32)) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_SystemServices02_rtti, &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_104;
            }
            v11 = 1;
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Result",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
            }
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                    v7,
                    i,
                    L"SystemServices",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, String);
            }
            if ( a2 != 1 )
            {
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureComputerBrowserServiceStartupMode",
                      &String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureHomeGroupListenerServiceStartupMode",
                      &String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureHomeGroupProviderServiceStartupMode",
                      &String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureIISAdminServiceStartupMode",
                      &String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureInfraredMonitorServiceStartupMode",
                      &String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureInternetConnectionSharingServiceStartupMode",
                      &String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureLxssManagerServiceStartupMode",
                      &String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureMicrosoftFTPServiceStartupMode",
                      &String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureRemoteProcedureCallLocatorServiceStartupMode",
                      &String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureRoutingAndRemoteAccessServiceStartupMode",
                      &String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureSimpleTCPIPServicesStartupMode",
                      &String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureSpecialAdministrationConsoleHelperServiceStartupMode",
                      &String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureSSDPDiscoveryServiceStartupMode",
                      &String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureUPnPDeviceHostServiceStartupMode",
                      &String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureWebManagementServiceStartupMode",
                      &String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode",
                      &String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureWindowsMobileHotspotServiceStartupMode",
                      &String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureWorldWideWebPublishingServiceStartupMode",
                      &String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureXboxAccessoryManagementServiceStartupMode",
                      &String)
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureXboxLiveAuthManagerServiceStartupMode",
                      &String)
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureXboxLiveGameSaveServiceStartupMode",
                      &String)
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureXboxLiveNetworkingServiceStartupMode",
                      &String)
                && String )
              {
                v62 = _wtoi(String);
                v63 = 1;
              }
            }
            MI_Instance_Destruct((MI_Instance *)self);
            MI_Instance_Destruct(&instance);
            v11 = 0;
          }
          if ( v12 )
          {
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
            v12 = 0;
          }
        }
      }
    }
    else
    {
      v6 = 1;
    }
  }
LABEL_104:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v13, "EnumerateInstancesEnd", v6);
  v15 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_18033740E,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return v6;
}

```

## disassembly

```asm
0x18019d734  mov     [rsp+arg_8], rbx
0x18019d739  mov     [rsp+arg_10], rsi
0x18019d73e  push    rdi
0x18019d73f  push    r12
0x18019d741  push    r13
0x18019d743  push    r14
0x18019d745  push    r15
0x18019d747  sub     rsp, 1D0h
0x18019d74e  mov     rax, cs:__security_cookie
0x18019d755  xor     rax, rsp
0x18019d758  mov     [rsp+1F8h+var_38], rax
0x18019d760  mov     r13b, dl
0x18019d763  mov     r12, rcx
0x18019d766  xor     edx, edx; Val
0x18019d768  mov     r8d, 110h; Size
0x18019d76e  lea     rcx, [rsp+1F8h+instance]; void *
0x18019d776  call    memset_0
0x18019d77b  xor     edi, edi
0x18019d77d  mov     [rsp+1F8h+var_1B0], dil
0x18019d782  mov     [rsp+1F8h+String], rdi
0x18019d787  mov     [rsp+1F8h+var_170], edi
0x18019d78e  mov     [rsp+1F8h+var_16C], dil
0x18019d796  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18019d79d  mov     [rsp+1F8h+var_1A0], rax
0x18019d7a2  lea     rax, [rsp+1F8h+var_170]
0x18019d7aa  mov     [rsp+1F8h+var_198], rax
0x18019d7af  lea     rax, aMdmPolicyResul_19; "MDM_Policy_Result01_SystemServices02"
0x18019d7b6  mov     [rsp+1F8h+var_190], rax
0x18019d7bb  lea     rcx, [rsp+1F8h+var_170]
0x18019d7c3  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18019d7c8  mov     eax, cs:dword_180380B68
0x18019d7ce  cmp     eax, 5
0x18019d7d1  jbe     short loc_18019D843
0x18019d7d3  mov     rdx, 200000000000h
0x18019d7dd  lea     rcx, dword_180380B68
0x18019d7e4  call    _tlgKeywordOn
0x18019d7e9  test    al, al
0x18019d7eb  jz      short loc_18019D843
0x18019d7ed  cmp     [rsp+1F8h+var_16C], dil
0x18019d7f5  jz      short loc_18019D825
0x18019d7f7  cmp     [rsp+1F8h+var_158], edi
0x18019d7fe  jnz     short loc_18019D81B
0x18019d800  cmp     [rsp+1F8h+var_154], edi
0x18019d807  jnz     short loc_18019D81B
0x18019d809  cmp     [rsp+1F8h+var_150], edi
0x18019d810  jnz     short loc_18019D81B
0x18019d812  cmp     [rsp+1F8h+var_14C], edi
0x18019d819  jz      short loc_18019D825
0x18019d81b  lea     r9, [rsp+1F8h+var_158]
0x18019d823  jmp     short loc_18019D828
0x18019d825  mov     r9, rdi
0x18019d828  lea     r8, [rsp+1F8h+var_168]
0x18019d830  lea     rdx, word_180337FEA
0x18019d837  lea     rcx, dword_180380B68
0x18019d83e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18019d843  lea     rcx, [rsp+1F8h+var_1A0]; this
0x18019d848  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18019d84d  nop
0x18019d84e  mov     [rsp+1F8h+var_1A8], rdi
0x18019d853  lea     rax, [rsp+1F8h+var_1A8]
0x18019d858  mov     [rsp+1F8h+var_1C8], rax
0x18019d85d  mov     [rsp+1F8h+var_1D0], 2
0x18019d865  mov     [rsp+1F8h+var_1D8], 18h
0x18019d86d  lea     r9, ?MDM_Policy_Result01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_SystemServices02_NodeList
0x18019d874  xor     r8d, r8d
0x18019d877  xor     edx, edx
0x18019d879  mov     rcx, r12
0x18019d87c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18019d881  mov     r15d, eax
0x18019d884  test    eax, eax
0x18019d886  jz      short loc_18019D88D
0x18019d888  jmp     loc_18019E012
0x18019d88d  lea     rbx, [rsp+1F8h+var_1A8]
0x18019d892  mov     [rsp+1F8h+var_180], rbx
0x18019d897  mov     r14d, 1
0x18019d89d  mov     [rsp+1F8h+var_178], r14b
0x18019d8a5  mov     rsi, [rsp+1F8h+var_1A8]
0x18019d8aa  test    rsi, rsi
0x18019d8ad  jnz     short loc_18019D8B7
0x18019d8af  mov     r15d, r14d
0x18019d8b2  jmp     loc_18019E012
0x18019d8b7  mov     rax, [rsi]
0x18019d8ba  mov     rcx, rsi
0x18019d8bd  mov     rax, [rax+10h]
0x18019d8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d8c6  mov     r15d, eax
0x18019d8c9  test    eax, eax
0x18019d8cb  jz      short loc_18019D8EB
0x18019d8cd  mov     rcx, [rsp+1F8h+var_1A8]
0x18019d8d2  test    rcx, rcx
0x18019d8d5  jz      short loc_18019D8E6
0x18019d8d7  mov     rax, [rcx]
0x18019d8da  mov     edx, r14d
0x18019d8dd  mov     rax, [rax]
0x18019d8e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d8e5  nop
0x18019d8e6  jmp     loc_18019E012
0x18019d8eb  mov     rax, [rsi]
0x18019d8ee  mov     rcx, rsi
0x18019d8f1  mov     rax, [rax+8]
0x18019d8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d8fa  mov     r15d, eax
0x18019d8fd  test    eax, eax
0x18019d8ff  jz      short loc_18019D91F
0x18019d901  mov     rcx, [rsp+1F8h+var_1A8]
0x18019d906  test    rcx, rcx
0x18019d909  jz      short loc_18019D91A
0x18019d90b  mov     rax, [rcx]
0x18019d90e  mov     edx, r14d
0x18019d911  mov     rax, [rax]
0x18019d914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d919  nop
0x18019d91a  jmp     loc_18019E012
0x18019d91f  mov     r14d, edi
0x18019d922  mov     rax, [rsi+108h]
0x18019d929  sub     rax, [rsi+100h]
0x18019d930  sar     rax, 4
0x18019d934  cmp     r14d, eax
0x18019d937  jnb     loc_18019DFDA
0x18019d93d  lea     r8, [rsp+1F8h+instance]; instance
0x18019d945  lea     rdx, MDM_Policy_Result01_SystemServices02_rtti; classDecl
0x18019d94c  mov     rcx, r12; context
0x18019d94f  call    MI_Context_ConstructInstance
0x18019d954  mov     r15d, eax
0x18019d957  test    eax, eax
0x18019d959  jz      short loc_18019D97B
0x18019d95b  mov     rcx, [rbx]
0x18019d95e  test    rcx, rcx
0x18019d961  jz      short loc_18019D976
0x18019d963  mov     rax, [rcx]
0x18019d966  mov     edx, 1
0x18019d96b  mov     rax, [rax]
0x18019d96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d973  mov     [rbx], rdi
0x18019d976  jmp     loc_18019E012
0x18019d97b  mov     [rsp+1F8h+var_1B0], 1
0x18019d980  mov     rax, [rsi]
0x18019d983  lea     r9, [rsp+1F8h+String]
0x18019d988  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x18019d98f  mov     edx, r14d
0x18019d992  mov     rcx, rsi
0x18019d995  mov     rax, [rax+18h]
0x18019d999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d99e  test    eax, eax
0x18019d9a0  jnz     short loc_18019D9B9
0x18019d9a2  mov     rdx, [rsp+1F8h+String]
0x18019d9a7  test    rdx, rdx
0x18019d9aa  jz      short loc_18019D9B9
0x18019d9ac  lea     rcx, [rsp+1F8h+instance]
0x18019d9b4  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18019d9b9  mov     rax, [rsi]
0x18019d9bc  lea     r9, [rsp+1F8h+String]
0x18019d9c1  lea     r8, aSystemservices; "SystemServices"
0x18019d9c8  mov     edx, r14d
0x18019d9cb  mov     rcx, rsi
0x18019d9ce  mov     rax, [rax+18h]
0x18019d9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d9d7  test    eax, eax
0x18019d9d9  jnz     short loc_18019D9F2
0x18019d9db  mov     rdx, [rsp+1F8h+String]
0x18019d9e0  test    rdx, rdx
0x18019d9e3  jz      short loc_18019D9F2
0x18019d9e5  lea     rcx, [rsp+1F8h+instance]
0x18019d9ed  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18019d9f2  cmp     r13b, 1
0x18019d9f6  jnz     short loc_18019DA1A
0x18019d9f8  lea     rdx, [rsp+1F8h+instance]
0x18019da00  mov     rcx, r12; self
0x18019da03  call    MI_Instance_Destruct
0x18019da08  lea     rcx, [rsp+1F8h+instance]; self
0x18019da10  call    MI_Instance_Destruct
0x18019da15  jmp     loc_18019DFCD
0x18019da1a  mov     rax, [rsi]
0x18019da1d  lea     r9, [rsp+1F8h+String]
0x18019da22  lea     r8, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x18019da29  mov     edx, r14d
0x18019da2c  mov     rcx, rsi
0x18019da2f  mov     rax, [rax+18h]
0x18019da33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019da38  test    eax, eax
0x18019da3a  jnz     short loc_18019DA5B
0x18019da3c  mov     rcx, [rsp+1F8h+String]; String
0x18019da41  test    rcx, rcx
0x18019da44  jz      short loc_18019DA5B
0x18019da46  call    cs:__imp__wtoi
0x18019da4c  mov     [rsp+1F8h+var_E8], eax
0x18019da53  mov     [rsp+1F8h+var_E4], 1
0x18019da5b  mov     rax, [rsi]
0x18019da5e  lea     r9, [rsp+1F8h+String]
0x18019da63  lea     r8, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x18019da6a  mov     edx, r14d
0x18019da6d  mov     rcx, rsi
0x18019da70  mov     rax, [rax+18h]
0x18019da74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019da79  test    eax, eax
0x18019da7b  jnz     short loc_18019DA9C
0x18019da7d  mov     rcx, [rsp+1F8h+String]; String
0x18019da82  test    rcx, rcx
0x18019da85  jz      short loc_18019DA9C
0x18019da87  call    cs:__imp__wtoi
0x18019da8d  mov     [rsp+1F8h+var_E0], eax
0x18019da94  mov     [rsp+1F8h+var_DC], 1
0x18019da9c  mov     rax, [rsi]
0x18019da9f  lea     r9, [rsp+1F8h+String]
0x18019daa4  lea     r8, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x18019daab  mov     edx, r14d
0x18019daae  mov     rcx, rsi
0x18019dab1  mov     rax, [rax+18h]
0x18019dab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019daba  test    eax, eax
0x18019dabc  jnz     short loc_18019DADD
0x18019dabe  mov     rcx, [rsp+1F8h+String]; String
0x18019dac3  test    rcx, rcx
0x18019dac6  jz      short loc_18019DADD
0x18019dac8  call    cs:__imp__wtoi
0x18019dace  mov     [rsp+1F8h+var_D8], eax
0x18019dad5  mov     [rsp+1F8h+var_D4], 1
0x18019dadd  mov     rax, [rsi]
0x18019dae0  lea     r9, [rsp+1F8h+String]
0x18019dae5  lea     r8, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x18019daec  mov     edx, r14d
0x18019daef  mov     rcx, rsi
0x18019daf2  mov     rax, [rax+18h]
0x18019daf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019dafb  test    eax, eax
0x18019dafd  jnz     short loc_18019DB1E
0x18019daff  mov     rcx, [rsp+1F8h+String]; String
0x18019db04  test    rcx, rcx
0x18019db07  jz      short loc_18019DB1E
0x18019db09  call    cs:__imp__wtoi
0x18019db0f  mov     [rsp+1F8h+var_D0], eax
0x18019db16  mov     [rsp+1F8h+var_CC], 1
0x18019db1e  mov     rax, [rsi]
0x18019db21  lea     r9, [rsp+1F8h+String]
0x18019db26  lea     r8, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x18019db2d  mov     edx, r14d
0x18019db30  mov     rcx, rsi
0x18019db33  mov     rax, [rax+18h]
0x18019db37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019db3c  test    eax, eax
0x18019db3e  jnz     short loc_18019DB5F
0x18019db40  mov     rcx, [rsp+1F8h+String]; String
0x18019db45  test    rcx, rcx
0x18019db48  jz      short loc_18019DB5F
0x18019db4a  call    cs:__imp__wtoi
0x18019db50  mov     [rsp+1F8h+var_C8], eax
0x18019db57  mov     [rsp+1F8h+var_C4], 1
0x18019db5f  mov     rax, [rsi]
0x18019db62  lea     r9, [rsp+1F8h+String]
0x18019db67  lea     r8, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x18019db6e  mov     edx, r14d
0x18019db71  mov     rcx, rsi
0x18019db74  mov     rax, [rax+18h]
0x18019db78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019db7d  test    eax, eax
0x18019db7f  jnz     short loc_18019DBA0
0x18019db81  mov     rcx, [rsp+1F8h+String]; String
0x18019db86  test    rcx, rcx
0x18019db89  jz      short loc_18019DBA0
0x18019db8b  call    cs:__imp__wtoi
0x18019db91  mov     [rsp+1F8h+var_C0], eax
0x18019db98  mov     [rsp+1F8h+var_BC], 1
0x18019dba0  mov     rax, [rsi]
0x18019dba3  lea     r9, [rsp+1F8h+String]
0x18019dba8  lea     r8, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x18019dbaf  mov     edx, r14d
0x18019dbb2  mov     rcx, rsi
0x18019dbb5  mov     rax, [rax+18h]
0x18019dbb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019dbbe  test    eax, eax
0x18019dbc0  jnz     short loc_18019DBE1
0x18019dbc2  mov     rcx, [rsp+1F8h+String]; String
0x18019dbc7  test    rcx, rcx
0x18019dbca  jz      short loc_18019DBE1
0x18019dbcc  call    cs:__imp__wtoi
0x18019dbd2  mov     [rsp+1F8h+var_B8], eax
0x18019dbd9  mov     [rsp+1F8h+var_B4], 1
0x18019dbe1  mov     rax, [rsi]
0x18019dbe4  lea     r9, [rsp+1F8h+String]
0x18019dbe9  lea     r8, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x18019dbf0  mov     edx, r14d
0x18019dbf3  mov     rcx, rsi
0x18019dbf6  mov     rax, [rax+18h]
0x18019dbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019dbff  test    eax, eax
0x18019dc01  jnz     short loc_18019DC22
0x18019dc03  mov     rcx, [rsp+1F8h+String]; String
0x18019dc08  test    rcx, rcx
0x18019dc0b  jz      short loc_18019DC22
0x18019dc0d  call    cs:__imp__wtoi
0x18019dc13  mov     [rsp+1F8h+var_B0], eax
0x18019dc1a  mov     [rsp+1F8h+var_AC], 1
0x18019dc22  mov     rax, [rsi]
0x18019dc25  lea     r9, [rsp+1F8h+String]
0x18019dc2a  lea     r8, aConfigureremot; "ConfigureRemoteProcedureCallLocatorServ"...
0x18019dc31  mov     edx, r14d
0x18019dc34  mov     rcx, rsi
0x18019dc37  mov     rax, [rax+18h]
0x18019dc3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019dc40  test    eax, eax
  ... truncated ...
```
