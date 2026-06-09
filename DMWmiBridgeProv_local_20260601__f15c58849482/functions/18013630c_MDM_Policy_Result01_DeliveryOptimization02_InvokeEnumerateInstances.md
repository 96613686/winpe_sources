# MDM_Policy_Result01_DeliveryOptimization02_InvokeEnumerateInstances

- ea: `0x18013630c`
- end: `0x180136e2c`
- name: `MDM_Policy_Result01_DeliveryOptimization02_InvokeEnumerateInstances`
- size: `2848`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting`

## callers

- `0x1801355e0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005048`
- `0x180005160`
- `0x180005198`
- `0x180005438`
- `0x180005518`
- `0x180005630`
- `0x180005668`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18013630c`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18013661e`
- `msvcrt!_wtoi` at `0x180136665`
- `msvcrt!_wtoi` at `0x1801366e5`
- `msvcrt!_wtoi` at `0x18013672c`
- `msvcrt!_wtoi` at `0x180136773`
- `msvcrt!_wtoi` at `0x1801367ba`
- `msvcrt!_wtoi` at `0x180136801`
- `msvcrt!_wtoi` at `0x180136848`
- `msvcrt!_wtoi` at `0x1801368c8`
- `msvcrt!_wtoi` at `0x18013690f`
- `msvcrt!_wtoi` at `0x180136956`
- `msvcrt!_wtoi` at `0x18013699d`
- `msvcrt!_wtoi` at `0x1801369e4`
- `msvcrt!_wtoi` at `0x180136a2b`
- `msvcrt!_wtoi` at `0x180136a72`
- `msvcrt!_wtoi` at `0x180136ab9`
- `msvcrt!_wtoi` at `0x180136b00`
- `msvcrt!_wtoi` at `0x180136b47`
- `msvcrt!_wtoi` at `0x180136bc7`
- `msvcrt!_wtoi` at `0x180136c0e`
- `msvcrt!_wtoi` at `0x180136c55`
- `msvcrt!_wtoi` at `0x180136c9c`
- `msvcrt!_wtoi` at `0x18013661e`
- `msvcrt!_wtoi` at `0x180136665`
- `msvcrt!_wtoi` at `0x1801366e5`
- `msvcrt!_wtoi` at `0x18013672c`
- `msvcrt!_wtoi` at `0x180136773`
- `msvcrt!_wtoi` at `0x1801367ba`
- `msvcrt!_wtoi` at `0x180136801`
- `msvcrt!_wtoi` at `0x180136848`
- `msvcrt!_wtoi` at `0x1801368c8`
- `msvcrt!_wtoi` at `0x18013690f`
- `msvcrt!_wtoi` at `0x180136956`
- `msvcrt!_wtoi` at `0x18013699d`
- `msvcrt!_wtoi` at `0x1801369e4`
- `msvcrt!_wtoi` at `0x180136a2b`
- `msvcrt!_wtoi` at `0x180136a72`
- `msvcrt!_wtoi` at `0x180136ab9`
- `msvcrt!_wtoi` at `0x180136b00`
- `msvcrt!_wtoi` at `0x180136b47`
- `msvcrt!_wtoi` at `0x180136bc7`
- `msvcrt!_wtoi` at `0x180136c0e`
- `msvcrt!_wtoi` at `0x180136c55`
- `msvcrt!_wtoi` at `0x180136c9c`

## string_xrefs

- `0x1801365fa`: `DOAbsoluteMaxCacheSize`
- `0x180136688`: `DOCacheHost`
- `0x1801366c1`: `DOCacheHostSource`
- `0x18013674f`: `DODelayCacheServerFallbackBackground`
- `0x180136796`: `DODelayCacheServerFallbackForeground`
- `0x180136932`: `DOMaxCacheAge`
- `0x180136979`: `DOMaxCacheSize`
- `0x180136adc`: `DOMinFileSizeToCache`
- `0x180136b6a`: `DOModifyCacheDrive`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_DeliveryOptimization02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  MI_Result v6; // r15d
  _QWORD *v7; // rsi
  unsigned int i; // r14d
  wchar_t *String; // [rsp+40h] [rbp-208h] BYREF
  char v11; // [rsp+48h] [rbp-200h]
  _QWORD *v12; // [rsp+50h] [rbp-1F8h] BYREF
  _QWORD v13[5]; // [rsp+58h] [rbp-1F0h] BYREF
  char v14; // [rsp+80h] [rbp-1C8h]
  int v15; // [rsp+88h] [rbp-1C0h] BYREF
  char v16; // [rsp+8Ch] [rbp-1BCh]
  _BYTE v17[16]; // [rsp+90h] [rbp-1B8h] BYREF
  _DWORD v18[4]; // [rsp+A0h] [rbp-1A8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-198h] BYREF
  int v20; // [rsp+110h] [rbp-138h]
  char v21; // [rsp+114h] [rbp-134h]
  int v22; // [rsp+118h] [rbp-130h]
  char v23; // [rsp+11Ch] [rbp-12Ch]
  int v24; // [rsp+130h] [rbp-118h]
  char v25; // [rsp+134h] [rbp-114h]
  int v26; // [rsp+138h] [rbp-110h]
  char v27; // [rsp+13Ch] [rbp-10Ch]
  int v28; // [rsp+140h] [rbp-108h]
  char v29; // [rsp+144h] [rbp-104h]
  int v30; // [rsp+148h] [rbp-100h]
  char v31; // [rsp+14Ch] [rbp-FCh]
  int v32; // [rsp+150h] [rbp-F8h]
  char v33; // [rsp+154h] [rbp-F4h]
  int v34; // [rsp+158h] [rbp-F0h]
  char v35; // [rsp+15Ch] [rbp-ECh]
  int v36; // [rsp+170h] [rbp-D8h]
  char v37; // [rsp+174h] [rbp-D4h]
  int v38; // [rsp+178h] [rbp-D0h]
  char v39; // [rsp+17Ch] [rbp-CCh]
  int v40; // [rsp+180h] [rbp-C8h]
  char v41; // [rsp+184h] [rbp-C4h]
  int v42; // [rsp+188h] [rbp-C0h]
  char v43; // [rsp+18Ch] [rbp-BCh]
  int v44; // [rsp+190h] [rbp-B8h]
  char v45; // [rsp+194h] [rbp-B4h]
  int v46; // [rsp+198h] [rbp-B0h]
  char v47; // [rsp+19Ch] [rbp-ACh]
  int v48; // [rsp+1A0h] [rbp-A8h]
  char v49; // [rsp+1A4h] [rbp-A4h]
  int v50; // [rsp+1A8h] [rbp-A0h]
  char v51; // [rsp+1ACh] [rbp-9Ch]
  int v52; // [rsp+1B0h] [rbp-98h]
  char v53; // [rsp+1B4h] [rbp-94h]
  int v54; // [rsp+1B8h] [rbp-90h]
  char v55; // [rsp+1BCh] [rbp-8Ch]
  int v56; // [rsp+1D0h] [rbp-78h]
  char v57; // [rsp+1D4h] [rbp-74h]
  int v58; // [rsp+1D8h] [rbp-70h]
  char v59; // [rsp+1DCh] [rbp-6Ch]
  int v60; // [rsp+1E0h] [rbp-68h]
  char v61; // [rsp+1E4h] [rbp-64h]
  int v62; // [rsp+1E8h] [rbp-60h]
  char v63; // [rsp+1ECh] [rbp-5Ch]

  memset_0(&instance, 0, 0x160u);
  v11 = 0;
  String = 0;
  v15 = 0;
  v16 = 0;
  v13[0] = &TelemetryEventWriter::`vftable';
  v13[1] = &v15;
  v13[2] = "MDM_Policy_Result01_DeliveryOptimization02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v5 = v18;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18034365D,
      v17,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v13, v4);
  v12 = 0;
  v6 = (unsigned int)CreateRequestHandlerInstance(
                       self,
                       0,
                       0,
                       &MDM_Policy_Result01_DeliveryOptimization02_NodeList,
                       29,
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
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_DeliveryOptimization02_rtti, &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_119;
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
                    L"DeliveryOptimization",
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
                      L"DOAbsoluteMaxCacheSize",
                      &String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOAllowVPNPeerCaching",
                      &String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOCacheHost",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOCacheHostSource",
                      &String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DODelayBackgroundDownloadFromHttp",
                      &String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DODelayCacheServerFallbackBackground",
                      &String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DODelayCacheServerFallbackForeground",
                      &String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DODelayForegroundDownloadFromHttp",
                      &String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DODownloadMode",
                      &String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOGroupId",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOGroupIdSource",
                      &String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOMaxBackgroundDownloadBandwidth",
                      &String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOMaxCacheAge",
                      &String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOMaxCacheSize",
                      &String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOMaxForegroundDownloadBandwidth",
                      &String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOMinBackgroundQos",
                      &String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOMinBatteryPercentageAllowedToUpload",
                      &String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOMinDiskSizeAllowedToPeer",
                      &String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOMinFileSizeToCache",
                      &String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOMinRAMAllowedToPeer",
                      &String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOModifyCacheDrive",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOMonthlyUploadDataCap",
                      &String)
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOPercentageMaxBackgroundBandwidth",
                      &String)
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOPercentageMaxForegroundBandwidth",
                      &String)
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DORestrictPeerSelectionBy",
                      &String)
                && String )
              {
                v62 = _wtoi(String);
                v63 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOSetHoursToLimitBackgroundDownloadBandwidth",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSuggestedSites(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DOSetHoursToLimitForegroundDownloadBandwidth",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowTrustedSitesZoneTemplate(&instance);
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
LABEL_119:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v13, "EnumerateInstancesEnd", v6);
  v15 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_18036E9BC,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18013630c  mov     [rsp+arg_8], rbx
0x180136311  mov     [rsp+arg_10], rsi
0x180136316  push    rdi
0x180136317  push    r12
0x180136319  push    r13
0x18013631b  push    r14
0x18013631d  push    r15
0x18013631f  sub     rsp, 220h
0x180136326  mov     rax, cs:__security_cookie
0x18013632d  xor     rax, rsp
0x180136330  mov     [rsp+248h+var_38], rax
0x180136338  mov     r13b, dl
0x18013633b  mov     r12, rcx
0x18013633e  xor     edx, edx; Val
0x180136340  mov     r8d, 160h; Size
0x180136346  lea     rcx, [rsp+248h+instance]; void *
0x18013634e  call    memset_0
0x180136353  xor     edi, edi
0x180136355  mov     [rsp+248h+var_200], dil
0x18013635a  mov     [rsp+248h+String], rdi
0x18013635f  mov     [rsp+248h+var_1C0], edi
0x180136366  mov     [rsp+248h+var_1BC], dil
0x18013636e  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180136375  mov     [rsp+248h+var_1F0], rax
0x18013637a  lea     rax, [rsp+248h+var_1C0]
0x180136382  mov     [rsp+248h+var_1E8], rax
0x180136387  lea     rax, aMdmPolicyResul_161; "MDM_Policy_Result01_DeliveryOptimizatio"...
0x18013638e  mov     [rsp+248h+var_1E0], rax
0x180136393  lea     rcx, [rsp+248h+var_1C0]
0x18013639b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801363a0  mov     eax, cs:dword_180380B68
0x1801363a6  cmp     eax, 5
0x1801363a9  jbe     short loc_18013641B
0x1801363ab  mov     rdx, 200000000000h
0x1801363b5  lea     rcx, dword_180380B68
0x1801363bc  call    _tlgKeywordOn
0x1801363c1  test    al, al
0x1801363c3  jz      short loc_18013641B
0x1801363c5  cmp     [rsp+248h+var_1BC], dil
0x1801363cd  jz      short loc_1801363FD
0x1801363cf  cmp     [rsp+248h+var_1A8], edi
0x1801363d6  jnz     short loc_1801363F3
0x1801363d8  cmp     [rsp+248h+var_1A4], edi
0x1801363df  jnz     short loc_1801363F3
0x1801363e1  cmp     [rsp+248h+var_1A0], edi
0x1801363e8  jnz     short loc_1801363F3
0x1801363ea  cmp     [rsp+248h+var_19C], edi
0x1801363f1  jz      short loc_1801363FD
0x1801363f3  lea     r9, [rsp+248h+var_1A8]
0x1801363fb  jmp     short loc_180136400
0x1801363fd  mov     r9, rdi
0x180136400  lea     r8, [rsp+248h+var_1B8]
0x180136408  lea     rdx, byte_18034365D
0x18013640f  lea     rcx, dword_180380B68
0x180136416  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18013641b  lea     rcx, [rsp+248h+var_1F0]; this
0x180136420  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180136425  nop
0x180136426  mov     [rsp+248h+var_1F8], rdi
0x18013642b  lea     rax, [rsp+248h+var_1F8]
0x180136430  mov     [rsp+248h+var_218], rax
0x180136435  mov     [rsp+248h+var_220], 2
0x18013643d  mov     [rsp+248h+var_228], 1Dh
0x180136445  lea     r9, ?MDM_Policy_Result01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_DeliveryOptimization02_NodeList
0x18013644c  xor     r8d, r8d
0x18013644f  xor     edx, edx
0x180136451  mov     rcx, r12
0x180136454  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180136459  mov     r15d, eax
0x18013645c  test    eax, eax
0x18013645e  jz      short loc_180136465
0x180136460  jmp     loc_180136D8B
0x180136465  lea     rbx, [rsp+248h+var_1F8]
0x18013646a  mov     [rsp+248h+var_1D0], rbx
0x18013646f  mov     r14d, 1
0x180136475  mov     [rsp+248h+var_1C8], r14b
0x18013647d  mov     rsi, [rsp+248h+var_1F8]
0x180136482  test    rsi, rsi
0x180136485  jnz     short loc_18013648F
0x180136487  mov     r15d, r14d
0x18013648a  jmp     loc_180136D8B
0x18013648f  mov     rax, [rsi]
0x180136492  mov     rcx, rsi
0x180136495  mov     rax, [rax+10h]
0x180136499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013649e  mov     r15d, eax
0x1801364a1  test    eax, eax
0x1801364a3  jz      short loc_1801364C3
0x1801364a5  mov     rcx, [rsp+248h+var_1F8]
0x1801364aa  test    rcx, rcx
0x1801364ad  jz      short loc_1801364BE
0x1801364af  mov     rax, [rcx]
0x1801364b2  mov     edx, r14d
0x1801364b5  mov     rax, [rax]
0x1801364b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801364bd  nop
0x1801364be  jmp     loc_180136D8B
0x1801364c3  mov     rax, [rsi]
0x1801364c6  mov     rcx, rsi
0x1801364c9  mov     rax, [rax+8]
0x1801364cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801364d2  mov     r15d, eax
0x1801364d5  test    eax, eax
0x1801364d7  jz      short loc_1801364F7
0x1801364d9  mov     rcx, [rsp+248h+var_1F8]
0x1801364de  test    rcx, rcx
0x1801364e1  jz      short loc_1801364F2
0x1801364e3  mov     rax, [rcx]
0x1801364e6  mov     edx, r14d
0x1801364e9  mov     rax, [rax]
0x1801364ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801364f1  nop
0x1801364f2  jmp     loc_180136D8B
0x1801364f7  mov     r14d, edi
0x1801364fa  mov     rax, [rsi+108h]
0x180136501  sub     rax, [rsi+100h]
0x180136508  sar     rax, 4
0x18013650c  cmp     r14d, eax
0x18013650f  jnb     loc_180136D53
0x180136515  lea     r8, [rsp+248h+instance]; instance
0x18013651d  lea     rdx, MDM_Policy_Result01_DeliveryOptimization02_rtti; classDecl
0x180136524  mov     rcx, r12; context
0x180136527  call    MI_Context_ConstructInstance
0x18013652c  mov     r15d, eax
0x18013652f  test    eax, eax
0x180136531  jz      short loc_180136553
0x180136533  mov     rcx, [rbx]
0x180136536  test    rcx, rcx
0x180136539  jz      short loc_18013654E
0x18013653b  mov     rax, [rcx]
0x18013653e  mov     edx, 1
0x180136543  mov     rax, [rax]
0x180136546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013654b  mov     [rbx], rdi
0x18013654e  jmp     loc_180136D8B
0x180136553  mov     [rsp+248h+var_200], 1
0x180136558  mov     rax, [rsi]
0x18013655b  lea     r9, [rsp+248h+String]
0x180136560  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x180136567  mov     edx, r14d
0x18013656a  mov     rcx, rsi
0x18013656d  mov     rax, [rax+18h]
0x180136571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136576  test    eax, eax
0x180136578  jnz     short loc_180136591
0x18013657a  mov     rdx, [rsp+248h+String]
0x18013657f  test    rdx, rdx
0x180136582  jz      short loc_180136591
0x180136584  lea     rcx, [rsp+248h+instance]
0x18013658c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180136591  mov     rax, [rsi]
0x180136594  lea     r9, [rsp+248h+String]
0x180136599  lea     r8, aDeliveryoptimi; "DeliveryOptimization"
0x1801365a0  mov     edx, r14d
0x1801365a3  mov     rcx, rsi
0x1801365a6  mov     rax, [rax+18h]
0x1801365aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801365af  test    eax, eax
0x1801365b1  jnz     short loc_1801365CA
0x1801365b3  mov     rdx, [rsp+248h+String]
0x1801365b8  test    rdx, rdx
0x1801365bb  jz      short loc_1801365CA
0x1801365bd  lea     rcx, [rsp+248h+instance]
0x1801365c5  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801365ca  cmp     r13b, 1
0x1801365ce  jnz     short loc_1801365F2
0x1801365d0  lea     rdx, [rsp+248h+instance]
0x1801365d8  mov     rcx, r12; self
0x1801365db  call    MI_Instance_Destruct
0x1801365e0  lea     rcx, [rsp+248h+instance]; self
0x1801365e8  call    MI_Instance_Destruct
0x1801365ed  jmp     loc_180136D46
0x1801365f2  mov     rax, [rsi]
0x1801365f5  lea     r9, [rsp+248h+String]
0x1801365fa  lea     r8, aDoabsolutemaxc; "DOAbsoluteMaxCacheSize"
0x180136601  mov     edx, r14d
0x180136604  mov     rcx, rsi
0x180136607  mov     rax, [rax+18h]
0x18013660b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136610  test    eax, eax
0x180136612  jnz     short loc_180136639
0x180136614  mov     rcx, [rsp+248h+String]; String
0x180136619  test    rcx, rcx
0x18013661c  jz      short loc_180136639
0x18013661e  call    cs:__imp__wtoi
0x180136625  nop     dword ptr [rax+rax+00h]
0x18013662a  mov     [rsp+248h+var_138], eax
0x180136631  mov     [rsp+248h+var_134], 1
0x180136639  mov     rax, [rsi]
0x18013663c  lea     r9, [rsp+248h+String]
0x180136641  lea     r8, aDoallowvpnpeer; "DOAllowVPNPeerCaching"
0x180136648  mov     edx, r14d
0x18013664b  mov     rcx, rsi
0x18013664e  mov     rax, [rax+18h]
0x180136652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136657  test    eax, eax
0x180136659  jnz     short loc_180136680
0x18013665b  mov     rcx, [rsp+248h+String]; String
0x180136660  test    rcx, rcx
0x180136663  jz      short loc_180136680
0x180136665  call    cs:__imp__wtoi
0x18013666c  nop     dword ptr [rax+rax+00h]
0x180136671  mov     [rsp+248h+var_130], eax
0x180136678  mov     [rsp+248h+var_12C], 1
0x180136680  mov     rax, [rsi]
0x180136683  lea     r9, [rsp+248h+String]
0x180136688  lea     r8, aDocachehost; "DOCacheHost"
0x18013668f  mov     edx, r14d
0x180136692  mov     rcx, rsi
0x180136695  mov     rax, [rax+18h]
0x180136699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013669e  test    eax, eax
0x1801366a0  jnz     short loc_1801366B9
0x1801366a2  mov     rdx, [rsp+248h+String]
0x1801366a7  test    rdx, rdx
0x1801366aa  jz      short loc_1801366B9
0x1801366ac  lea     rcx, [rsp+248h+instance]
0x1801366b4  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x1801366b9  mov     rax, [rsi]
0x1801366bc  lea     r9, [rsp+248h+String]
0x1801366c1  lea     r8, aDocachehostsou; "DOCacheHostSource"
0x1801366c8  mov     edx, r14d
0x1801366cb  mov     rcx, rsi
0x1801366ce  mov     rax, [rax+18h]
0x1801366d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801366d7  test    eax, eax
0x1801366d9  jnz     short loc_180136700
0x1801366db  mov     rcx, [rsp+248h+String]; String
0x1801366e0  test    rcx, rcx
0x1801366e3  jz      short loc_180136700
0x1801366e5  call    cs:__imp__wtoi
0x1801366ec  nop     dword ptr [rax+rax+00h]
0x1801366f1  mov     [rsp+248h+var_118], eax
0x1801366f8  mov     [rsp+248h+var_114], 1
0x180136700  mov     rax, [rsi]
0x180136703  lea     r9, [rsp+248h+String]
0x180136708  lea     r8, aDodelaybackgro; "DODelayBackgroundDownloadFromHttp"
0x18013670f  mov     edx, r14d
0x180136712  mov     rcx, rsi
0x180136715  mov     rax, [rax+18h]
0x180136719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013671e  test    eax, eax
0x180136720  jnz     short loc_180136747
0x180136722  mov     rcx, [rsp+248h+String]; String
0x180136727  test    rcx, rcx
0x18013672a  jz      short loc_180136747
0x18013672c  call    cs:__imp__wtoi
0x180136733  nop     dword ptr [rax+rax+00h]
0x180136738  mov     [rsp+248h+var_110], eax
0x18013673f  mov     [rsp+248h+var_10C], 1
0x180136747  mov     rax, [rsi]
0x18013674a  lea     r9, [rsp+248h+String]
0x18013674f  lea     r8, aDodelaycachese; "DODelayCacheServerFallbackBackground"
0x180136756  mov     edx, r14d
0x180136759  mov     rcx, rsi
0x18013675c  mov     rax, [rax+18h]
0x180136760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136765  test    eax, eax
0x180136767  jnz     short loc_18013678E
0x180136769  mov     rcx, [rsp+248h+String]; String
0x18013676e  test    rcx, rcx
0x180136771  jz      short loc_18013678E
0x180136773  call    cs:__imp__wtoi
0x18013677a  nop     dword ptr [rax+rax+00h]
0x18013677f  mov     [rsp+248h+var_108], eax
0x180136786  mov     [rsp+248h+var_104], 1
0x18013678e  mov     rax, [rsi]
0x180136791  lea     r9, [rsp+248h+String]
0x180136796  lea     r8, aDodelaycachese_0; "DODelayCacheServerFallbackForeground"
0x18013679d  mov     edx, r14d
0x1801367a0  mov     rcx, rsi
0x1801367a3  mov     rax, [rax+18h]
0x1801367a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801367ac  test    eax, eax
0x1801367ae  jnz     short loc_1801367D5
0x1801367b0  mov     rcx, [rsp+248h+String]; String
0x1801367b5  test    rcx, rcx
0x1801367b8  jz      short loc_1801367D5
0x1801367ba  call    cs:__imp__wtoi
0x1801367c1  nop     dword ptr [rax+rax+00h]
0x1801367c6  mov     [rsp+248h+var_100], eax
0x1801367cd  mov     [rsp+248h+var_FC], 1
0x1801367d5  mov     rax, [rsi]
0x1801367d8  lea     r9, [rsp+248h+String]
0x1801367dd  lea     r8, aDodelayforegro; "DODelayForegroundDownloadFromHttp"
0x1801367e4  mov     edx, r14d
0x1801367e7  mov     rcx, rsi
0x1801367ea  mov     rax, [rax+18h]
0x1801367ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801367f3  test    eax, eax
0x1801367f5  jnz     short loc_18013681C
0x1801367f7  mov     rcx, [rsp+248h+String]; String
0x1801367fc  test    rcx, rcx
0x1801367ff  jz      short loc_18013681C
0x180136801  call    cs:__imp__wtoi
0x180136808  nop     dword ptr [rax+rax+00h]
0x18013680d  mov     [rsp+248h+var_F8], eax
0x180136814  mov     [rsp+248h+var_F4], 1
0x18013681c  mov     rax, [rsi]
0x18013681f  lea     r9, [rsp+248h+String]
  ... truncated ...
```
