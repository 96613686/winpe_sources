# MDM_Policy_Config01_DeliveryOptimization02_InvokeEnumerateInstances

- ea: `0x18007e8fc`
- end: `0x18007f41c`
- name: `MDM_Policy_Config01_DeliveryOptimization02_InvokeEnumerateInstances`
- size: `2848`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting`

## callers

- `0x18007dbd0`

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
- `0x18007e8fc`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18007ec0e`
- `msvcrt!_wtoi` at `0x18007ec55`
- `msvcrt!_wtoi` at `0x18007ecd5`
- `msvcrt!_wtoi` at `0x18007ed1c`
- `msvcrt!_wtoi` at `0x18007ed63`
- `msvcrt!_wtoi` at `0x18007edaa`
- `msvcrt!_wtoi` at `0x18007edf1`
- `msvcrt!_wtoi` at `0x18007ee38`
- `msvcrt!_wtoi` at `0x18007eeb8`
- `msvcrt!_wtoi` at `0x18007eeff`
- `msvcrt!_wtoi` at `0x18007ef46`
- `msvcrt!_wtoi` at `0x18007ef8d`
- `msvcrt!_wtoi` at `0x18007efd4`
- `msvcrt!_wtoi` at `0x18007f01b`
- `msvcrt!_wtoi` at `0x18007f062`
- `msvcrt!_wtoi` at `0x18007f0a9`
- `msvcrt!_wtoi` at `0x18007f0f0`
- `msvcrt!_wtoi` at `0x18007f137`
- `msvcrt!_wtoi` at `0x18007f1b7`
- `msvcrt!_wtoi` at `0x18007f1fe`
- `msvcrt!_wtoi` at `0x18007f245`
- `msvcrt!_wtoi` at `0x18007f28c`
- `msvcrt!_wtoi` at `0x18007ec0e`
- `msvcrt!_wtoi` at `0x18007ec55`
- `msvcrt!_wtoi` at `0x18007ecd5`
- `msvcrt!_wtoi` at `0x18007ed1c`
- `msvcrt!_wtoi` at `0x18007ed63`
- `msvcrt!_wtoi` at `0x18007edaa`
- `msvcrt!_wtoi` at `0x18007edf1`
- `msvcrt!_wtoi` at `0x18007ee38`
- `msvcrt!_wtoi` at `0x18007eeb8`
- `msvcrt!_wtoi` at `0x18007eeff`
- `msvcrt!_wtoi` at `0x18007ef46`
- `msvcrt!_wtoi` at `0x18007ef8d`
- `msvcrt!_wtoi` at `0x18007efd4`
- `msvcrt!_wtoi` at `0x18007f01b`
- `msvcrt!_wtoi` at `0x18007f062`
- `msvcrt!_wtoi` at `0x18007f0a9`
- `msvcrt!_wtoi` at `0x18007f0f0`
- `msvcrt!_wtoi` at `0x18007f137`
- `msvcrt!_wtoi` at `0x18007f1b7`
- `msvcrt!_wtoi` at `0x18007f1fe`
- `msvcrt!_wtoi` at `0x18007f245`
- `msvcrt!_wtoi` at `0x18007f28c`

## string_xrefs

- `0x18007ebea`: `DOAbsoluteMaxCacheSize`
- `0x18007ec78`: `DOCacheHost`
- `0x18007ecb1`: `DOCacheHostSource`
- `0x18007ed3f`: `DODelayCacheServerFallbackBackground`
- `0x18007ed86`: `DODelayCacheServerFallbackForeground`
- `0x18007ef22`: `DOMaxCacheAge`
- `0x18007ef69`: `DOMaxCacheSize`
- `0x18007f0cc`: `DOMinFileSizeToCache`
- `0x18007f15a`: `DOModifyCacheDrive`
- `0x18007eb50`: `./Vendor/MSFT/Policy/Config`
- `0x18007e977`: `MDM_Policy_Config01_DeliveryOptimization02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_DeliveryOptimization02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r15d
  _QWORD *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-208h] BYREF
  char v14; // [rsp+48h] [rbp-200h]
  _QWORD *v15; // [rsp+50h] [rbp-1F8h] BYREF
  _QWORD v16[3]; // [rsp+58h] [rbp-1F0h] BYREF
  const exception *v17[2]; // [rsp+70h] [rbp-1D8h] BYREF
  char v18; // [rsp+80h] [rbp-1C8h]
  int v19; // [rsp+88h] [rbp-1C0h] BYREF
  char v20; // [rsp+8Ch] [rbp-1BCh]
  _BYTE v21[16]; // [rsp+90h] [rbp-1B8h] BYREF
  _DWORD v22[4]; // [rsp+A0h] [rbp-1A8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-198h] BYREF
  int v24; // [rsp+110h] [rbp-138h]
  char v25; // [rsp+114h] [rbp-134h]
  int v26; // [rsp+118h] [rbp-130h]
  char v27; // [rsp+11Ch] [rbp-12Ch]
  int v28; // [rsp+130h] [rbp-118h]
  char v29; // [rsp+134h] [rbp-114h]
  int v30; // [rsp+138h] [rbp-110h]
  char v31; // [rsp+13Ch] [rbp-10Ch]
  int v32; // [rsp+140h] [rbp-108h]
  char v33; // [rsp+144h] [rbp-104h]
  int v34; // [rsp+148h] [rbp-100h]
  char v35; // [rsp+14Ch] [rbp-FCh]
  int v36; // [rsp+150h] [rbp-F8h]
  char v37; // [rsp+154h] [rbp-F4h]
  int v38; // [rsp+158h] [rbp-F0h]
  char v39; // [rsp+15Ch] [rbp-ECh]
  int v40; // [rsp+170h] [rbp-D8h]
  char v41; // [rsp+174h] [rbp-D4h]
  int v42; // [rsp+178h] [rbp-D0h]
  char v43; // [rsp+17Ch] [rbp-CCh]
  int v44; // [rsp+180h] [rbp-C8h]
  char v45; // [rsp+184h] [rbp-C4h]
  int v46; // [rsp+188h] [rbp-C0h]
  char v47; // [rsp+18Ch] [rbp-BCh]
  int v48; // [rsp+190h] [rbp-B8h]
  char v49; // [rsp+194h] [rbp-B4h]
  int v50; // [rsp+198h] [rbp-B0h]
  char v51; // [rsp+19Ch] [rbp-ACh]
  int v52; // [rsp+1A0h] [rbp-A8h]
  char v53; // [rsp+1A4h] [rbp-A4h]
  int v54; // [rsp+1A8h] [rbp-A0h]
  char v55; // [rsp+1ACh] [rbp-9Ch]
  int v56; // [rsp+1B0h] [rbp-98h]
  char v57; // [rsp+1B4h] [rbp-94h]
  int v58; // [rsp+1B8h] [rbp-90h]
  char v59; // [rsp+1BCh] [rbp-8Ch]
  int v60; // [rsp+1D0h] [rbp-78h]
  char v61; // [rsp+1D4h] [rbp-74h]
  int v62; // [rsp+1D8h] [rbp-70h]
  char v63; // [rsp+1DCh] [rbp-6Ch]
  int v64; // [rsp+1E0h] [rbp-68h]
  char v65; // [rsp+1E4h] [rbp-64h]
  int v66; // [rsp+1E8h] [rbp-60h]
  char v67; // [rsp+1ECh] [rbp-5Ch]

  memset_0(&instance, 0, 0x160u);
  v14 = 0;
  String = 0;
  v19 = 0;
  v20 = 0;
  v16[0] = &TelemetryEventWriter::`vftable';
  v16[1] = &v19;
  v16[2] = "MDM_Policy_Config01_DeliveryOptimization02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v19);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v20 && (v22[0] || v22[1] || v22[2] || v22[3]) )
      v5 = v22;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &unk_180364190,
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
                         &MDM_Policy_Config01_DeliveryOptimization02_NodeList,
                         29,
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_DeliveryOptimization02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v15;
                if ( v15 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_130;
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
                      L"DeliveryOptimization",
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
                        L"DOAbsoluteMaxCacheSize",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOAllowVPNPeerCaching",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOCacheHost",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOCacheHostSource",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DODelayBackgroundDownloadFromHttp",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DODelayCacheServerFallbackBackground",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DODelayCacheServerFallbackForeground",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DODelayForegroundDownloadFromHttp",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DODownloadMode",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOGroupId",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOGroupIdSource",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOMaxBackgroundDownloadBandwidth",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOMaxCacheAge",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOMaxCacheSize",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOMaxForegroundDownloadBandwidth",
                        &String)
                  && String )
                {
                  v48 = _wtoi(String);
                  v49 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOMinBackgroundQos",
                        &String)
                  && String )
                {
                  v50 = _wtoi(String);
                  v51 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOMinBatteryPercentageAllowedToUpload",
                        &String)
                  && String )
                {
                  v52 = _wtoi(String);
                  v53 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOMinDiskSizeAllowedToPeer",
                        &String)
                  && String )
                {
                  v54 = _wtoi(String);
                  v55 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOMinFileSizeToCache",
                        &String)
                  && String )
                {
                  v56 = _wtoi(String);
                  v57 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOMinRAMAllowedToPeer",
                        &String)
                  && String )
                {
                  v58 = _wtoi(String);
                  v59 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOModifyCacheDrive",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOMonthlyUploadDataCap",
                        &String)
                  && String )
                {
                  v60 = _wtoi(String);
                  v61 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOPercentageMaxBackgroundBandwidth",
                        &String)
                  && String )
                {
                  v62 = _wtoi(String);
                  v63 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOPercentageMaxForegroundBandwidth",
                        &String)
                  && String )
                {
                  v64 = _wtoi(String);
                  v65 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DORestrictPeerSelectionBy",
                        &String)
                  && String )
                {
                  v66 = _wtoi(String);
                  v67 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DOSetHoursToLimitBackgroundDownloadBandwidth",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSuggestedSites(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
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
    goto LABEL_121;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v16, v12);
    LODWORD(v15) = 1;
LABEL_121:
    if ( v14 )
      MI_Instance_Destruct(&instance);
    v7 = (int)v15;
  }
LABEL_130:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v16, "EnumerateInstancesEnd", v7);
  v19 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_18034D376,
      v21,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007e8fc  mov     [rsp+arg_8], rbx
0x18007e901  mov     [rsp+arg_10], rsi
0x18007e906  push    rdi
0x18007e907  push    r12
0x18007e909  push    r13
0x18007e90b  push    r14
0x18007e90d  push    r15
0x18007e90f  sub     rsp, 220h
0x18007e916  mov     rax, cs:__security_cookie
0x18007e91d  xor     rax, rsp
0x18007e920  mov     [rsp+248h+var_38], rax
0x18007e928  mov     r13b, dl
0x18007e92b  mov     r12, rcx
0x18007e92e  xor     edx, edx; Val
0x18007e930  mov     r8d, 160h; Size
0x18007e936  lea     rcx, [rsp+248h+instance]; void *
0x18007e93e  call    memset_0
0x18007e943  xor     edi, edi
0x18007e945  mov     [rsp+248h+var_200], dil
0x18007e94a  mov     [rsp+248h+String], rdi
0x18007e94f  mov     [rsp+248h+var_1C0], edi
0x18007e956  mov     [rsp+248h+var_1BC], dil
0x18007e95e  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18007e965  mov     [rsp+248h+var_1F0], rax
0x18007e96a  lea     rax, [rsp+248h+var_1C0]
0x18007e972  mov     [rsp+248h+var_1E8], rax
0x18007e977  lea     rax, aMdmPolicyConfi_34; "MDM_Policy_Config01_DeliveryOptimizatio"...
0x18007e97e  mov     [rsp+248h+var_1E0], rax
0x18007e983  lea     rcx, [rsp+248h+var_1C0]
0x18007e98b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007e990  mov     eax, cs:dword_180380B68
0x18007e996  cmp     eax, 5
0x18007e999  jbe     short loc_18007EA0B
0x18007e99b  mov     rdx, 200000000000h
0x18007e9a5  lea     rcx, dword_180380B68
0x18007e9ac  call    _tlgKeywordOn
0x18007e9b1  test    al, al
0x18007e9b3  jz      short loc_18007EA0B
0x18007e9b5  cmp     [rsp+248h+var_1BC], dil
0x18007e9bd  jz      short loc_18007E9ED
0x18007e9bf  cmp     [rsp+248h+var_1A8], edi
0x18007e9c6  jnz     short loc_18007E9E3
0x18007e9c8  cmp     [rsp+248h+var_1A4], edi
0x18007e9cf  jnz     short loc_18007E9E3
0x18007e9d1  cmp     [rsp+248h+var_1A0], edi
0x18007e9d8  jnz     short loc_18007E9E3
0x18007e9da  cmp     [rsp+248h+var_19C], edi
0x18007e9e1  jz      short loc_18007E9ED
0x18007e9e3  lea     r9, [rsp+248h+var_1A8]
0x18007e9eb  jmp     short loc_18007E9F0
0x18007e9ed  mov     r9, rdi
0x18007e9f0  lea     r8, [rsp+248h+var_1B8]
0x18007e9f8  lea     rdx, unk_180364190
0x18007e9ff  lea     rcx, dword_180380B68
0x18007ea06  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007ea0b  lea     rcx, [rsp+248h+var_1F0]; this
0x18007ea10  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18007ea15  nop
0x18007ea16  mov     [rsp+248h+var_1F8], rdi
0x18007ea1b  lea     rax, [rsp+248h+var_1F8]
0x18007ea20  mov     [rsp+248h+var_218], rax
0x18007ea25  mov     [rsp+248h+var_220], 2
0x18007ea2d  mov     [rsp+248h+var_228], 1Dh
0x18007ea35  lea     r9, ?MDM_Policy_Config01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_DeliveryOptimization02_NodeList
0x18007ea3c  xor     r8d, r8d
0x18007ea3f  xor     edx, edx
0x18007ea41  mov     rcx, r12
0x18007ea44  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18007ea49  mov     r15d, eax
0x18007ea4c  test    eax, eax
0x18007ea4e  jz      short loc_18007EA55
0x18007ea50  jmp     loc_18007F37B
0x18007ea55  lea     rbx, [rsp+248h+var_1F8]
0x18007ea5a  mov     [rsp+248h+var_1D0], rbx
0x18007ea5f  mov     r14d, 1
0x18007ea65  mov     [rsp+248h+var_1C8], r14b
0x18007ea6d  mov     rsi, [rsp+248h+var_1F8]
0x18007ea72  test    rsi, rsi
0x18007ea75  jnz     short loc_18007EA7F
0x18007ea77  mov     r15d, r14d
0x18007ea7a  jmp     loc_18007F37B
0x18007ea7f  mov     rax, [rsi]
0x18007ea82  mov     rcx, rsi
0x18007ea85  mov     rax, [rax+10h]
0x18007ea89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ea8e  mov     r15d, eax
0x18007ea91  test    eax, eax
0x18007ea93  jz      short loc_18007EAB3
0x18007ea95  mov     rcx, [rsp+248h+var_1F8]
0x18007ea9a  test    rcx, rcx
0x18007ea9d  jz      short loc_18007EAAE
0x18007ea9f  mov     rax, [rcx]
0x18007eaa2  mov     edx, r14d
0x18007eaa5  mov     rax, [rax]
0x18007eaa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eaad  nop
0x18007eaae  jmp     loc_18007F37B
0x18007eab3  mov     rax, [rsi]
0x18007eab6  mov     rcx, rsi
0x18007eab9  mov     rax, [rax+8]
0x18007eabd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eac2  mov     r15d, eax
0x18007eac5  test    eax, eax
0x18007eac7  jz      short loc_18007EAE7
0x18007eac9  mov     rcx, [rsp+248h+var_1F8]
0x18007eace  test    rcx, rcx
0x18007ead1  jz      short loc_18007EAE2
0x18007ead3  mov     rax, [rcx]
0x18007ead6  mov     edx, r14d
0x18007ead9  mov     rax, [rax]
0x18007eadc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eae1  nop
0x18007eae2  jmp     loc_18007F37B
0x18007eae7  mov     r14d, edi
0x18007eaea  mov     rax, [rsi+108h]
0x18007eaf1  sub     rax, [rsi+100h]
0x18007eaf8  sar     rax, 4
0x18007eafc  cmp     r14d, eax
0x18007eaff  jnb     loc_18007F343
0x18007eb05  lea     r8, [rsp+248h+instance]; instance
0x18007eb0d  lea     rdx, MDM_Policy_Config01_DeliveryOptimization02_rtti; classDecl
0x18007eb14  mov     rcx, r12; context
0x18007eb17  call    MI_Context_ConstructInstance
0x18007eb1c  mov     r15d, eax
0x18007eb1f  test    eax, eax
0x18007eb21  jz      short loc_18007EB43
0x18007eb23  mov     rcx, [rbx]
0x18007eb26  test    rcx, rcx
0x18007eb29  jz      short loc_18007EB3E
0x18007eb2b  mov     rax, [rcx]
0x18007eb2e  mov     edx, 1
0x18007eb33  mov     rax, [rax]
0x18007eb36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb3b  mov     [rbx], rdi
0x18007eb3e  jmp     loc_18007F37B
0x18007eb43  mov     [rsp+248h+var_200], 1
0x18007eb48  mov     rax, [rsi]
0x18007eb4b  lea     r9, [rsp+248h+String]
0x18007eb50  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x18007eb57  mov     edx, r14d
0x18007eb5a  mov     rcx, rsi
0x18007eb5d  mov     rax, [rax+18h]
0x18007eb61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb66  test    eax, eax
0x18007eb68  jnz     short loc_18007EB81
0x18007eb6a  mov     rdx, [rsp+248h+String]
0x18007eb6f  test    rdx, rdx
0x18007eb72  jz      short loc_18007EB81
0x18007eb74  lea     rcx, [rsp+248h+instance]
0x18007eb7c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18007eb81  mov     rax, [rsi]
0x18007eb84  lea     r9, [rsp+248h+String]
0x18007eb89  lea     r8, aDeliveryoptimi; "DeliveryOptimization"
0x18007eb90  mov     edx, r14d
0x18007eb93  mov     rcx, rsi
0x18007eb96  mov     rax, [rax+18h]
0x18007eb9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb9f  test    eax, eax
0x18007eba1  jnz     short loc_18007EBBA
0x18007eba3  mov     rdx, [rsp+248h+String]
0x18007eba8  test    rdx, rdx
0x18007ebab  jz      short loc_18007EBBA
0x18007ebad  lea     rcx, [rsp+248h+instance]
0x18007ebb5  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18007ebba  cmp     r13b, 1
0x18007ebbe  jnz     short loc_18007EBE2
0x18007ebc0  lea     rdx, [rsp+248h+instance]
0x18007ebc8  mov     rcx, r12; self
0x18007ebcb  call    MI_Instance_Destruct
0x18007ebd0  lea     rcx, [rsp+248h+instance]; self
0x18007ebd8  call    MI_Instance_Destruct
0x18007ebdd  jmp     loc_18007F336
0x18007ebe2  mov     rax, [rsi]
0x18007ebe5  lea     r9, [rsp+248h+String]
0x18007ebea  lea     r8, aDoabsolutemaxc; "DOAbsoluteMaxCacheSize"
0x18007ebf1  mov     edx, r14d
0x18007ebf4  mov     rcx, rsi
0x18007ebf7  mov     rax, [rax+18h]
0x18007ebfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ec00  test    eax, eax
0x18007ec02  jnz     short loc_18007EC29
0x18007ec04  mov     rcx, [rsp+248h+String]; String
0x18007ec09  test    rcx, rcx
0x18007ec0c  jz      short loc_18007EC29
0x18007ec0e  call    cs:__imp__wtoi
0x18007ec15  nop     dword ptr [rax+rax+00h]
0x18007ec1a  mov     [rsp+248h+var_138], eax
0x18007ec21  mov     [rsp+248h+var_134], 1
0x18007ec29  mov     rax, [rsi]
0x18007ec2c  lea     r9, [rsp+248h+String]
0x18007ec31  lea     r8, aDoallowvpnpeer; "DOAllowVPNPeerCaching"
0x18007ec38  mov     edx, r14d
0x18007ec3b  mov     rcx, rsi
0x18007ec3e  mov     rax, [rax+18h]
0x18007ec42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ec47  test    eax, eax
0x18007ec49  jnz     short loc_18007EC70
0x18007ec4b  mov     rcx, [rsp+248h+String]; String
0x18007ec50  test    rcx, rcx
0x18007ec53  jz      short loc_18007EC70
0x18007ec55  call    cs:__imp__wtoi
0x18007ec5c  nop     dword ptr [rax+rax+00h]
0x18007ec61  mov     [rsp+248h+var_130], eax
0x18007ec68  mov     [rsp+248h+var_12C], 1
0x18007ec70  mov     rax, [rsi]
0x18007ec73  lea     r9, [rsp+248h+String]
0x18007ec78  lea     r8, aDocachehost; "DOCacheHost"
0x18007ec7f  mov     edx, r14d
0x18007ec82  mov     rcx, rsi
0x18007ec85  mov     rax, [rax+18h]
0x18007ec89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ec8e  test    eax, eax
0x18007ec90  jnz     short loc_18007ECA9
0x18007ec92  mov     rdx, [rsp+248h+String]
0x18007ec97  test    rdx, rdx
0x18007ec9a  jz      short loc_18007ECA9
0x18007ec9c  lea     rcx, [rsp+248h+instance]
0x18007eca4  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x18007eca9  mov     rax, [rsi]
0x18007ecac  lea     r9, [rsp+248h+String]
0x18007ecb1  lea     r8, aDocachehostsou; "DOCacheHostSource"
0x18007ecb8  mov     edx, r14d
0x18007ecbb  mov     rcx, rsi
0x18007ecbe  mov     rax, [rax+18h]
0x18007ecc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ecc7  test    eax, eax
0x18007ecc9  jnz     short loc_18007ECF0
0x18007eccb  mov     rcx, [rsp+248h+String]; String
0x18007ecd0  test    rcx, rcx
0x18007ecd3  jz      short loc_18007ECF0
0x18007ecd5  call    cs:__imp__wtoi
0x18007ecdc  nop     dword ptr [rax+rax+00h]
0x18007ece1  mov     [rsp+248h+var_118], eax
0x18007ece8  mov     [rsp+248h+var_114], 1
0x18007ecf0  mov     rax, [rsi]
0x18007ecf3  lea     r9, [rsp+248h+String]
0x18007ecf8  lea     r8, aDodelaybackgro; "DODelayBackgroundDownloadFromHttp"
0x18007ecff  mov     edx, r14d
0x18007ed02  mov     rcx, rsi
0x18007ed05  mov     rax, [rax+18h]
0x18007ed09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ed0e  test    eax, eax
0x18007ed10  jnz     short loc_18007ED37
0x18007ed12  mov     rcx, [rsp+248h+String]; String
0x18007ed17  test    rcx, rcx
0x18007ed1a  jz      short loc_18007ED37
0x18007ed1c  call    cs:__imp__wtoi
0x18007ed23  nop     dword ptr [rax+rax+00h]
0x18007ed28  mov     [rsp+248h+var_110], eax
0x18007ed2f  mov     [rsp+248h+var_10C], 1
0x18007ed37  mov     rax, [rsi]
0x18007ed3a  lea     r9, [rsp+248h+String]
0x18007ed3f  lea     r8, aDodelaycachese; "DODelayCacheServerFallbackBackground"
0x18007ed46  mov     edx, r14d
0x18007ed49  mov     rcx, rsi
0x18007ed4c  mov     rax, [rax+18h]
0x18007ed50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ed55  test    eax, eax
0x18007ed57  jnz     short loc_18007ED7E
0x18007ed59  mov     rcx, [rsp+248h+String]; String
0x18007ed5e  test    rcx, rcx
0x18007ed61  jz      short loc_18007ED7E
0x18007ed63  call    cs:__imp__wtoi
0x18007ed6a  nop     dword ptr [rax+rax+00h]
0x18007ed6f  mov     [rsp+248h+var_108], eax
0x18007ed76  mov     [rsp+248h+var_104], 1
0x18007ed7e  mov     rax, [rsi]
0x18007ed81  lea     r9, [rsp+248h+String]
0x18007ed86  lea     r8, aDodelaycachese_0; "DODelayCacheServerFallbackForeground"
0x18007ed8d  mov     edx, r14d
0x18007ed90  mov     rcx, rsi
0x18007ed93  mov     rax, [rax+18h]
0x18007ed97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ed9c  test    eax, eax
0x18007ed9e  jnz     short loc_18007EDC5
0x18007eda0  mov     rcx, [rsp+248h+String]; String
0x18007eda5  test    rcx, rcx
0x18007eda8  jz      short loc_18007EDC5
0x18007edaa  call    cs:__imp__wtoi
0x18007edb1  nop     dword ptr [rax+rax+00h]
0x18007edb6  mov     [rsp+248h+var_100], eax
0x18007edbd  mov     [rsp+248h+var_FC], 1
0x18007edc5  mov     rax, [rsi]
0x18007edc8  lea     r9, [rsp+248h+String]
0x18007edcd  lea     r8, aDodelayforegro; "DODelayForegroundDownloadFromHttp"
0x18007edd4  mov     edx, r14d
0x18007edd7  mov     rcx, rsi
0x18007edda  mov     rax, [rax+18h]
0x18007edde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ede3  test    eax, eax
0x18007ede5  jnz     short loc_18007EE0C
0x18007ede7  mov     rcx, [rsp+248h+String]; String
0x18007edec  test    rcx, rcx
0x18007edef  jz      short loc_18007EE0C
0x18007edf1  call    cs:__imp__wtoi
0x18007edf8  nop     dword ptr [rax+rax+00h]
0x18007edfd  mov     [rsp+248h+var_F8], eax
0x18007ee04  mov     [rsp+248h+var_F4], 1
0x18007ee0c  mov     rax, [rsi]
0x18007ee0f  lea     r9, [rsp+248h+String]
  ... truncated ...
```
