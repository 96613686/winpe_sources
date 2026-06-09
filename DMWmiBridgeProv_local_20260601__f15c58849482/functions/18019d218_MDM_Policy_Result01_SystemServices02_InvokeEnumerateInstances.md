# MDM_Policy_Result01_SystemServices02_InvokeEnumerateInstances

- ea: `0x18019d218`
- end: `0x18019dc1b`
- name: `MDM_Policy_Result01_SystemServices02_InvokeEnumerateInstances`
- size: `2563`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18019c630`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18019d218`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18019d52a`
- `msvcrt!_wtoi` at `0x18019d571`
- `msvcrt!_wtoi` at `0x18019d5b8`
- `msvcrt!_wtoi` at `0x18019d5ff`
- `msvcrt!_wtoi` at `0x18019d646`
- `msvcrt!_wtoi` at `0x18019d68d`
- `msvcrt!_wtoi` at `0x18019d6d4`
- `msvcrt!_wtoi` at `0x18019d71b`
- `msvcrt!_wtoi` at `0x18019d762`
- `msvcrt!_wtoi` at `0x18019d7a9`
- `msvcrt!_wtoi` at `0x18019d7f0`
- `msvcrt!_wtoi` at `0x18019d837`
- `msvcrt!_wtoi` at `0x18019d87e`
- `msvcrt!_wtoi` at `0x18019d8c5`
- `msvcrt!_wtoi` at `0x18019d90c`
- `msvcrt!_wtoi` at `0x18019d953`
- `msvcrt!_wtoi` at `0x18019d99a`
- `msvcrt!_wtoi` at `0x18019d9e1`
- `msvcrt!_wtoi` at `0x18019da28`
- `msvcrt!_wtoi` at `0x18019da6f`
- `msvcrt!_wtoi` at `0x18019dab6`
- `msvcrt!_wtoi` at `0x18019dafd`
- `msvcrt!_wtoi` at `0x18019d52a`
- `msvcrt!_wtoi` at `0x18019d571`
- `msvcrt!_wtoi` at `0x18019d5b8`
- `msvcrt!_wtoi` at `0x18019d5ff`
- `msvcrt!_wtoi` at `0x18019d646`
- `msvcrt!_wtoi` at `0x18019d68d`
- `msvcrt!_wtoi` at `0x18019d6d4`
- `msvcrt!_wtoi` at `0x18019d71b`
- `msvcrt!_wtoi` at `0x18019d762`
- `msvcrt!_wtoi` at `0x18019d7a9`
- `msvcrt!_wtoi` at `0x18019d7f0`
- `msvcrt!_wtoi` at `0x18019d837`
- `msvcrt!_wtoi` at `0x18019d87e`
- `msvcrt!_wtoi` at `0x18019d8c5`
- `msvcrt!_wtoi` at `0x18019d90c`
- `msvcrt!_wtoi` at `0x18019d953`
- `msvcrt!_wtoi` at `0x18019d99a`
- `msvcrt!_wtoi` at `0x18019d9e1`
- `msvcrt!_wtoi` at `0x18019da28`
- `msvcrt!_wtoi` at `0x18019da6f`
- `msvcrt!_wtoi` at `0x18019dab6`
- `msvcrt!_wtoi` at `0x18019dafd`

## string_xrefs

- `0x18019d506`: `ConfigureComputerBrowserServiceStartupMode`
- `0x18019d54d`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x18019d594`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x18019d5db`: `ConfigureIISAdminServiceStartupMode`
- `0x18019d622`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x18019d669`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x18019d6b0`: `ConfigureLxssManagerServiceStartupMode`
- `0x18019d6f7`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x18019d73e`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x18019d785`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x18019d7cc`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x18019d813`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x18019d85a`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x18019d8a1`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x18019d8e8`: `ConfigureWebManagementServiceStartupMode`
- `0x18019d92f`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x18019d976`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x18019d9bd`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x18019da04`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x18019da4b`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x18019da92`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x18019dad9`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x18019d293`: `MDM_Policy_Result01_SystemServices02`
- `0x18019d4a5`: `SystemServices`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_SystemServices02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  MI_Result v6; // r15d
  _QWORD *v7; // rsi
  unsigned int i; // r14d
  wchar_t *String; // [rsp+40h] [rbp-1B8h] BYREF
  char v11; // [rsp+48h] [rbp-1B0h]
  _QWORD *v12; // [rsp+50h] [rbp-1A8h] BYREF
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
  v6 = (unsigned int)CreateRequestHandlerInstance(
                       self,
                       0,
                       0,
                       &MDM_Policy_Result01_SystemServices02_NodeList,
                       24,
                       2,
                       &v12);
  if ( v6 == MI_RESULT_OK )
  {
    v13[4] = &v12;
    v14 = 1;
    v7 = v12;
    if ( v12 )
    {
      v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
      if ( v6 )
      {
        if ( v12 )
          (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
      }
      else
      {
        v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v12 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(v7[33] - v7[32]) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_SystemServices02_rtti, &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_104;
            }
            v11 = 1;
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Result",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
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
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureComputerBrowserServiceStartupMode",
                      &String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureHomeGroupListenerServiceStartupMode",
                      &String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureHomeGroupProviderServiceStartupMode",
                      &String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureIISAdminServiceStartupMode",
                      &String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureInfraredMonitorServiceStartupMode",
                      &String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureInternetConnectionSharingServiceStartupMode",
                      &String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureLxssManagerServiceStartupMode",
                      &String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureMicrosoftFTPServiceStartupMode",
                      &String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureRemoteProcedureCallLocatorServiceStartupMode",
                      &String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureRoutingAndRemoteAccessServiceStartupMode",
                      &String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureSimpleTCPIPServicesStartupMode",
                      &String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureSpecialAdministrationConsoleHelperServiceStartupMode",
                      &String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureSSDPDiscoveryServiceStartupMode",
                      &String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureUPnPDeviceHostServiceStartupMode",
                      &String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureWebManagementServiceStartupMode",
                      &String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode",
                      &String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureWindowsMobileHotspotServiceStartupMode",
                      &String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureWorldWideWebPublishingServiceStartupMode",
                      &String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureXboxAccessoryManagementServiceStartupMode",
                      &String)
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureXboxLiveAuthManagerServiceStartupMode",
                      &String)
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureXboxLiveGameSaveServiceStartupMode",
                      &String)
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
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
            (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
            v12 = 0;
          }
        }
      }
    }
    else
    {
      v6 = MI_RESULT_FAILED;
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
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18019d218  mov     [rsp+arg_8], rbx
0x18019d21d  mov     [rsp+arg_10], rsi
0x18019d222  push    rdi
0x18019d223  push    r12
0x18019d225  push    r13
0x18019d227  push    r14
0x18019d229  push    r15
0x18019d22b  sub     rsp, 1D0h
0x18019d232  mov     rax, cs:__security_cookie
0x18019d239  xor     rax, rsp
0x18019d23c  mov     [rsp+1F8h+var_38], rax
0x18019d244  mov     r13b, dl
0x18019d247  mov     r12, rcx
0x18019d24a  xor     edx, edx; Val
0x18019d24c  mov     r8d, 110h; Size
0x18019d252  lea     rcx, [rsp+1F8h+instance]; void *
0x18019d25a  call    memset_0
0x18019d25f  xor     edi, edi
0x18019d261  mov     [rsp+1F8h+var_1B0], dil
0x18019d266  mov     [rsp+1F8h+String], rdi
0x18019d26b  mov     [rsp+1F8h+var_170], edi
0x18019d272  mov     [rsp+1F8h+var_16C], dil
0x18019d27a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18019d281  mov     [rsp+1F8h+var_1A0], rax
0x18019d286  lea     rax, [rsp+1F8h+var_170]
0x18019d28e  mov     [rsp+1F8h+var_198], rax
0x18019d293  lea     rax, aMdmPolicyResul_19; "MDM_Policy_Result01_SystemServices02"
0x18019d29a  mov     [rsp+1F8h+var_190], rax
0x18019d29f  lea     rcx, [rsp+1F8h+var_170]
0x18019d2a7  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18019d2ac  mov     eax, cs:dword_180380B68
0x18019d2b2  cmp     eax, 5
0x18019d2b5  jbe     short loc_18019D327
0x18019d2b7  mov     rdx, 200000000000h
0x18019d2c1  lea     rcx, dword_180380B68
0x18019d2c8  call    _tlgKeywordOn
0x18019d2cd  test    al, al
0x18019d2cf  jz      short loc_18019D327
0x18019d2d1  cmp     [rsp+1F8h+var_16C], dil
0x18019d2d9  jz      short loc_18019D309
0x18019d2db  cmp     [rsp+1F8h+var_158], edi
0x18019d2e2  jnz     short loc_18019D2FF
0x18019d2e4  cmp     [rsp+1F8h+var_154], edi
0x18019d2eb  jnz     short loc_18019D2FF
0x18019d2ed  cmp     [rsp+1F8h+var_150], edi
0x18019d2f4  jnz     short loc_18019D2FF
0x18019d2f6  cmp     [rsp+1F8h+var_14C], edi
0x18019d2fd  jz      short loc_18019D309
0x18019d2ff  lea     r9, [rsp+1F8h+var_158]
0x18019d307  jmp     short loc_18019D30C
0x18019d309  mov     r9, rdi
0x18019d30c  lea     r8, [rsp+1F8h+var_168]
0x18019d314  lea     rdx, word_180337FEA
0x18019d31b  lea     rcx, dword_180380B68
0x18019d322  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18019d327  lea     rcx, [rsp+1F8h+var_1A0]; this
0x18019d32c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18019d331  nop
0x18019d332  mov     [rsp+1F8h+var_1A8], rdi
0x18019d337  lea     rax, [rsp+1F8h+var_1A8]
0x18019d33c  mov     [rsp+1F8h+var_1C8], rax
0x18019d341  mov     [rsp+1F8h+var_1D0], 2
0x18019d349  mov     [rsp+1F8h+var_1D8], 18h
0x18019d351  lea     r9, ?MDM_Policy_Result01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_SystemServices02_NodeList
0x18019d358  xor     r8d, r8d
0x18019d35b  xor     edx, edx
0x18019d35d  mov     rcx, r12
0x18019d360  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18019d365  mov     r15d, eax
0x18019d368  test    eax, eax
0x18019d36a  jz      short loc_18019D371
0x18019d36c  jmp     loc_18019DB7A
0x18019d371  lea     rbx, [rsp+1F8h+var_1A8]
0x18019d376  mov     [rsp+1F8h+var_180], rbx
0x18019d37b  mov     r14d, 1
0x18019d381  mov     [rsp+1F8h+var_178], r14b
0x18019d389  mov     rsi, [rsp+1F8h+var_1A8]
0x18019d38e  test    rsi, rsi
0x18019d391  jnz     short loc_18019D39B
0x18019d393  mov     r15d, r14d
0x18019d396  jmp     loc_18019DB7A
0x18019d39b  mov     rax, [rsi]
0x18019d39e  mov     rcx, rsi
0x18019d3a1  mov     rax, [rax+10h]
0x18019d3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d3aa  mov     r15d, eax
0x18019d3ad  test    eax, eax
0x18019d3af  jz      short loc_18019D3CF
0x18019d3b1  mov     rcx, [rsp+1F8h+var_1A8]
0x18019d3b6  test    rcx, rcx
0x18019d3b9  jz      short loc_18019D3CA
0x18019d3bb  mov     rax, [rcx]
0x18019d3be  mov     edx, r14d
0x18019d3c1  mov     rax, [rax]
0x18019d3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d3c9  nop
0x18019d3ca  jmp     loc_18019DB7A
0x18019d3cf  mov     rax, [rsi]
0x18019d3d2  mov     rcx, rsi
0x18019d3d5  mov     rax, [rax+8]
0x18019d3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d3de  mov     r15d, eax
0x18019d3e1  test    eax, eax
0x18019d3e3  jz      short loc_18019D403
0x18019d3e5  mov     rcx, [rsp+1F8h+var_1A8]
0x18019d3ea  test    rcx, rcx
0x18019d3ed  jz      short loc_18019D3FE
0x18019d3ef  mov     rax, [rcx]
0x18019d3f2  mov     edx, r14d
0x18019d3f5  mov     rax, [rax]
0x18019d3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d3fd  nop
0x18019d3fe  jmp     loc_18019DB7A
0x18019d403  mov     r14d, edi
0x18019d406  mov     rax, [rsi+108h]
0x18019d40d  sub     rax, [rsi+100h]
0x18019d414  sar     rax, 4
0x18019d418  cmp     r14d, eax
0x18019d41b  jnb     loc_18019DB42
0x18019d421  lea     r8, [rsp+1F8h+instance]; instance
0x18019d429  lea     rdx, MDM_Policy_Result01_SystemServices02_rtti; classDecl
0x18019d430  mov     rcx, r12; context
0x18019d433  call    MI_Context_ConstructInstance
0x18019d438  mov     r15d, eax
0x18019d43b  test    eax, eax
0x18019d43d  jz      short loc_18019D45F
0x18019d43f  mov     rcx, [rbx]
0x18019d442  test    rcx, rcx
0x18019d445  jz      short loc_18019D45A
0x18019d447  mov     rax, [rcx]
0x18019d44a  mov     edx, 1
0x18019d44f  mov     rax, [rax]
0x18019d452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d457  mov     [rbx], rdi
0x18019d45a  jmp     loc_18019DB7A
0x18019d45f  mov     [rsp+1F8h+var_1B0], 1
0x18019d464  mov     rax, [rsi]
0x18019d467  lea     r9, [rsp+1F8h+String]
0x18019d46c  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x18019d473  mov     edx, r14d
0x18019d476  mov     rcx, rsi
0x18019d479  mov     rax, [rax+18h]
0x18019d47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d482  test    eax, eax
0x18019d484  jnz     short loc_18019D49D
0x18019d486  mov     rdx, [rsp+1F8h+String]
0x18019d48b  test    rdx, rdx
0x18019d48e  jz      short loc_18019D49D
0x18019d490  lea     rcx, [rsp+1F8h+instance]
0x18019d498  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18019d49d  mov     rax, [rsi]
0x18019d4a0  lea     r9, [rsp+1F8h+String]
0x18019d4a5  lea     r8, aSystemservices; "SystemServices"
0x18019d4ac  mov     edx, r14d
0x18019d4af  mov     rcx, rsi
0x18019d4b2  mov     rax, [rax+18h]
0x18019d4b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d4bb  test    eax, eax
0x18019d4bd  jnz     short loc_18019D4D6
0x18019d4bf  mov     rdx, [rsp+1F8h+String]
0x18019d4c4  test    rdx, rdx
0x18019d4c7  jz      short loc_18019D4D6
0x18019d4c9  lea     rcx, [rsp+1F8h+instance]
0x18019d4d1  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18019d4d6  cmp     r13b, 1
0x18019d4da  jnz     short loc_18019D4FE
0x18019d4dc  lea     rdx, [rsp+1F8h+instance]
0x18019d4e4  mov     rcx, r12; self
0x18019d4e7  call    MI_Instance_Destruct
0x18019d4ec  lea     rcx, [rsp+1F8h+instance]; self
0x18019d4f4  call    MI_Instance_Destruct
0x18019d4f9  jmp     loc_18019DB35
0x18019d4fe  mov     rax, [rsi]
0x18019d501  lea     r9, [rsp+1F8h+String]
0x18019d506  lea     r8, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x18019d50d  mov     edx, r14d
0x18019d510  mov     rcx, rsi
0x18019d513  mov     rax, [rax+18h]
0x18019d517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d51c  test    eax, eax
0x18019d51e  jnz     short loc_18019D545
0x18019d520  mov     rcx, [rsp+1F8h+String]; String
0x18019d525  test    rcx, rcx
0x18019d528  jz      short loc_18019D545
0x18019d52a  call    cs:__imp__wtoi
0x18019d531  nop     dword ptr [rax+rax+00h]
0x18019d536  mov     [rsp+1F8h+var_E8], eax
0x18019d53d  mov     [rsp+1F8h+var_E4], 1
0x18019d545  mov     rax, [rsi]
0x18019d548  lea     r9, [rsp+1F8h+String]
0x18019d54d  lea     r8, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x18019d554  mov     edx, r14d
0x18019d557  mov     rcx, rsi
0x18019d55a  mov     rax, [rax+18h]
0x18019d55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d563  test    eax, eax
0x18019d565  jnz     short loc_18019D58C
0x18019d567  mov     rcx, [rsp+1F8h+String]; String
0x18019d56c  test    rcx, rcx
0x18019d56f  jz      short loc_18019D58C
0x18019d571  call    cs:__imp__wtoi
0x18019d578  nop     dword ptr [rax+rax+00h]
0x18019d57d  mov     [rsp+1F8h+var_E0], eax
0x18019d584  mov     [rsp+1F8h+var_DC], 1
0x18019d58c  mov     rax, [rsi]
0x18019d58f  lea     r9, [rsp+1F8h+String]
0x18019d594  lea     r8, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x18019d59b  mov     edx, r14d
0x18019d59e  mov     rcx, rsi
0x18019d5a1  mov     rax, [rax+18h]
0x18019d5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d5aa  test    eax, eax
0x18019d5ac  jnz     short loc_18019D5D3
0x18019d5ae  mov     rcx, [rsp+1F8h+String]; String
0x18019d5b3  test    rcx, rcx
0x18019d5b6  jz      short loc_18019D5D3
0x18019d5b8  call    cs:__imp__wtoi
0x18019d5bf  nop     dword ptr [rax+rax+00h]
0x18019d5c4  mov     [rsp+1F8h+var_D8], eax
0x18019d5cb  mov     [rsp+1F8h+var_D4], 1
0x18019d5d3  mov     rax, [rsi]
0x18019d5d6  lea     r9, [rsp+1F8h+String]
0x18019d5db  lea     r8, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x18019d5e2  mov     edx, r14d
0x18019d5e5  mov     rcx, rsi
0x18019d5e8  mov     rax, [rax+18h]
0x18019d5ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d5f1  test    eax, eax
0x18019d5f3  jnz     short loc_18019D61A
0x18019d5f5  mov     rcx, [rsp+1F8h+String]; String
0x18019d5fa  test    rcx, rcx
0x18019d5fd  jz      short loc_18019D61A
0x18019d5ff  call    cs:__imp__wtoi
0x18019d606  nop     dword ptr [rax+rax+00h]
0x18019d60b  mov     [rsp+1F8h+var_D0], eax
0x18019d612  mov     [rsp+1F8h+var_CC], 1
0x18019d61a  mov     rax, [rsi]
0x18019d61d  lea     r9, [rsp+1F8h+String]
0x18019d622  lea     r8, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x18019d629  mov     edx, r14d
0x18019d62c  mov     rcx, rsi
0x18019d62f  mov     rax, [rax+18h]
0x18019d633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d638  test    eax, eax
0x18019d63a  jnz     short loc_18019D661
0x18019d63c  mov     rcx, [rsp+1F8h+String]; String
0x18019d641  test    rcx, rcx
0x18019d644  jz      short loc_18019D661
0x18019d646  call    cs:__imp__wtoi
0x18019d64d  nop     dword ptr [rax+rax+00h]
0x18019d652  mov     [rsp+1F8h+var_C8], eax
0x18019d659  mov     [rsp+1F8h+var_C4], 1
0x18019d661  mov     rax, [rsi]
0x18019d664  lea     r9, [rsp+1F8h+String]
0x18019d669  lea     r8, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x18019d670  mov     edx, r14d
0x18019d673  mov     rcx, rsi
0x18019d676  mov     rax, [rax+18h]
0x18019d67a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d67f  test    eax, eax
0x18019d681  jnz     short loc_18019D6A8
0x18019d683  mov     rcx, [rsp+1F8h+String]; String
0x18019d688  test    rcx, rcx
0x18019d68b  jz      short loc_18019D6A8
0x18019d68d  call    cs:__imp__wtoi
0x18019d694  nop     dword ptr [rax+rax+00h]
0x18019d699  mov     [rsp+1F8h+var_C0], eax
0x18019d6a0  mov     [rsp+1F8h+var_BC], 1
0x18019d6a8  mov     rax, [rsi]
0x18019d6ab  lea     r9, [rsp+1F8h+String]
0x18019d6b0  lea     r8, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x18019d6b7  mov     edx, r14d
0x18019d6ba  mov     rcx, rsi
0x18019d6bd  mov     rax, [rax+18h]
0x18019d6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d6c6  test    eax, eax
0x18019d6c8  jnz     short loc_18019D6EF
0x18019d6ca  mov     rcx, [rsp+1F8h+String]; String
0x18019d6cf  test    rcx, rcx
0x18019d6d2  jz      short loc_18019D6EF
0x18019d6d4  call    cs:__imp__wtoi
0x18019d6db  nop     dword ptr [rax+rax+00h]
0x18019d6e0  mov     [rsp+1F8h+var_B8], eax
0x18019d6e7  mov     [rsp+1F8h+var_B4], 1
0x18019d6ef  mov     rax, [rsi]
0x18019d6f2  lea     r9, [rsp+1F8h+String]
0x18019d6f7  lea     r8, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x18019d6fe  mov     edx, r14d
0x18019d701  mov     rcx, rsi
0x18019d704  mov     rax, [rax+18h]
0x18019d708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d70d  test    eax, eax
0x18019d70f  jnz     short loc_18019D736
0x18019d711  mov     rcx, [rsp+1F8h+String]; String
0x18019d716  test    rcx, rcx
0x18019d719  jz      short loc_18019D736
0x18019d71b  call    cs:__imp__wtoi
0x18019d722  nop     dword ptr [rax+rax+00h]
0x18019d727  mov     [rsp+1F8h+var_B0], eax
0x18019d72e  mov     [rsp+1F8h+var_AC], 1
  ... truncated ...
```
