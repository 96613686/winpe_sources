# MDM_Policy_Config01_DeliveryOptimization02_InvokeEnumerateInstances

- ea: `0x18007f034`
- end: `0x18007facf`
- name: `MDM_Policy_Config01_DeliveryOptimization02_InvokeEnumerateInstances`
- size: `2715`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting`

## callers

- `0x18007e2f0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004e74`
- `0x180004f8c`
- `0x180004fc4`
- `0x180005264`
- `0x180005344`
- `0x18000545c`
- `0x180005494`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18007f034`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18007f346`
- `msvcrt!_wtoi` at `0x18007f387`
- `msvcrt!_wtoi` at `0x18007f401`
- `msvcrt!_wtoi` at `0x18007f442`
- `msvcrt!_wtoi` at `0x18007f483`
- `msvcrt!_wtoi` at `0x18007f4c4`
- `msvcrt!_wtoi` at `0x18007f505`
- `msvcrt!_wtoi` at `0x18007f546`
- `msvcrt!_wtoi` at `0x18007f5c0`
- `msvcrt!_wtoi` at `0x18007f601`
- `msvcrt!_wtoi` at `0x18007f642`
- `msvcrt!_wtoi` at `0x18007f683`
- `msvcrt!_wtoi` at `0x18007f6c4`
- `msvcrt!_wtoi` at `0x18007f705`
- `msvcrt!_wtoi` at `0x18007f746`
- `msvcrt!_wtoi` at `0x18007f787`
- `msvcrt!_wtoi` at `0x18007f7c8`
- `msvcrt!_wtoi` at `0x18007f809`
- `msvcrt!_wtoi` at `0x18007f883`
- `msvcrt!_wtoi` at `0x18007f8c4`
- `msvcrt!_wtoi` at `0x18007f905`
- `msvcrt!_wtoi` at `0x18007f946`
- `msvcrt!_wtoi` at `0x18007f346`
- `msvcrt!_wtoi` at `0x18007f387`
- `msvcrt!_wtoi` at `0x18007f401`
- `msvcrt!_wtoi` at `0x18007f442`
- `msvcrt!_wtoi` at `0x18007f483`
- `msvcrt!_wtoi` at `0x18007f4c4`
- `msvcrt!_wtoi` at `0x18007f505`
- `msvcrt!_wtoi` at `0x18007f546`
- `msvcrt!_wtoi` at `0x18007f5c0`
- `msvcrt!_wtoi` at `0x18007f601`
- `msvcrt!_wtoi` at `0x18007f642`
- `msvcrt!_wtoi` at `0x18007f683`
- `msvcrt!_wtoi` at `0x18007f6c4`
- `msvcrt!_wtoi` at `0x18007f705`
- `msvcrt!_wtoi` at `0x18007f746`
- `msvcrt!_wtoi` at `0x18007f787`
- `msvcrt!_wtoi` at `0x18007f7c8`
- `msvcrt!_wtoi` at `0x18007f809`
- `msvcrt!_wtoi` at `0x18007f883`
- `msvcrt!_wtoi` at `0x18007f8c4`
- `msvcrt!_wtoi` at `0x18007f905`
- `msvcrt!_wtoi` at `0x18007f946`

## string_xrefs

- `0x18007f322`: `DOAbsoluteMaxCacheSize`
- `0x18007f3a4`: `DOCacheHost`
- `0x18007f3dd`: `DOCacheHostSource`
- `0x18007f45f`: `DODelayCacheServerFallbackBackground`
- `0x18007f4a0`: `DODelayCacheServerFallbackForeground`
- `0x18007f61e`: `DOMaxCacheAge`
- `0x18007f65f`: `DOMaxCacheSize`
- `0x18007f7a4`: `DOMinFileSizeToCache`
- `0x18007f826`: `DOModifyCacheDrive`
- `0x18007f288`: `./Vendor/MSFT/Policy/Config`
- `0x18007f0af`: `MDM_Policy_Config01_DeliveryOptimization02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_DeliveryOptimization02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r15d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-208h] BYREF
  char v14; // [rsp+48h] [rbp-200h]
  WmiRequestHandlerAdd *v15; // [rsp+50h] [rbp-1F8h] BYREF
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
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_DeliveryOptimization02_NodeList,
           0x1Du,
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_DeliveryOptimization02_rtti, &instance);
              if ( v7 )
              {
                v6 = v15;
                if ( v15 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_130;
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
                      L"DeliveryOptimization",
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
                        L"DOAbsoluteMaxCacheSize",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOAllowVPNPeerCaching",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOCacheHost",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOCacheHostSource",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DODelayBackgroundDownloadFromHttp",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DODelayCacheServerFallbackBackground",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DODelayCacheServerFallbackForeground",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DODelayForegroundDownloadFromHttp",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DODownloadMode",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOGroupId",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOGroupIdSource",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOMaxBackgroundDownloadBandwidth",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOMaxCacheAge",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOMaxCacheSize",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOMaxForegroundDownloadBandwidth",
                        &String)
                  && String )
                {
                  v48 = _wtoi(String);
                  v49 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOMinBackgroundQos",
                        &String)
                  && String )
                {
                  v50 = _wtoi(String);
                  v51 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOMinBatteryPercentageAllowedToUpload",
                        &String)
                  && String )
                {
                  v52 = _wtoi(String);
                  v53 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOMinDiskSizeAllowedToPeer",
                        &String)
                  && String )
                {
                  v54 = _wtoi(String);
                  v55 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOMinFileSizeToCache",
                        &String)
                  && String )
                {
                  v56 = _wtoi(String);
                  v57 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOMinRAMAllowedToPeer",
                        &String)
                  && String )
                {
                  v58 = _wtoi(String);
                  v59 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOModifyCacheDrive",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOMonthlyUploadDataCap",
                        &String)
                  && String )
                {
                  v60 = _wtoi(String);
                  v61 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOPercentageMaxBackgroundBandwidth",
                        &String)
                  && String )
                {
                  v62 = _wtoi(String);
                  v63 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOPercentageMaxForegroundBandwidth",
                        &String)
                  && String )
                {
                  v64 = _wtoi(String);
                  v65 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DORestrictPeerSelectionBy",
                        &String)
                  && String )
                {
                  v66 = _wtoi(String);
                  v67 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DOSetHoursToLimitBackgroundDownloadBandwidth",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSuggestedSites(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
    v7 = (unsigned int)v15;
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
  return v7;
}

```

## disassembly

```asm
0x18007f034  mov     [rsp+arg_8], rbx
0x18007f039  mov     [rsp+arg_10], rsi
0x18007f03e  push    rdi
0x18007f03f  push    r12
0x18007f041  push    r13
0x18007f043  push    r14
0x18007f045  push    r15
0x18007f047  sub     rsp, 220h
0x18007f04e  mov     rax, cs:__security_cookie
0x18007f055  xor     rax, rsp
0x18007f058  mov     [rsp+248h+var_38], rax
0x18007f060  mov     r13b, dl
0x18007f063  mov     r12, rcx
0x18007f066  xor     edx, edx; Val
0x18007f068  mov     r8d, 160h; Size
0x18007f06e  lea     rcx, [rsp+248h+instance]; void *
0x18007f076  call    memset_0
0x18007f07b  xor     edi, edi
0x18007f07d  mov     [rsp+248h+var_200], dil
0x18007f082  mov     [rsp+248h+String], rdi
0x18007f087  mov     [rsp+248h+var_1C0], edi
0x18007f08e  mov     [rsp+248h+var_1BC], dil
0x18007f096  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18007f09d  mov     [rsp+248h+var_1F0], rax
0x18007f0a2  lea     rax, [rsp+248h+var_1C0]
0x18007f0aa  mov     [rsp+248h+var_1E8], rax
0x18007f0af  lea     rax, aMdmPolicyConfi_34; "MDM_Policy_Config01_DeliveryOptimizatio"...
0x18007f0b6  mov     [rsp+248h+var_1E0], rax
0x18007f0bb  lea     rcx, [rsp+248h+var_1C0]
0x18007f0c3  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007f0c8  mov     eax, cs:dword_180380B68
0x18007f0ce  cmp     eax, 5
0x18007f0d1  jbe     short loc_18007F143
0x18007f0d3  mov     rdx, 200000000000h
0x18007f0dd  lea     rcx, dword_180380B68
0x18007f0e4  call    _tlgKeywordOn
0x18007f0e9  test    al, al
0x18007f0eb  jz      short loc_18007F143
0x18007f0ed  cmp     [rsp+248h+var_1BC], dil
0x18007f0f5  jz      short loc_18007F125
0x18007f0f7  cmp     [rsp+248h+var_1A8], edi
0x18007f0fe  jnz     short loc_18007F11B
0x18007f100  cmp     [rsp+248h+var_1A4], edi
0x18007f107  jnz     short loc_18007F11B
0x18007f109  cmp     [rsp+248h+var_1A0], edi
0x18007f110  jnz     short loc_18007F11B
0x18007f112  cmp     [rsp+248h+var_19C], edi
0x18007f119  jz      short loc_18007F125
0x18007f11b  lea     r9, [rsp+248h+var_1A8]
0x18007f123  jmp     short loc_18007F128
0x18007f125  mov     r9, rdi
0x18007f128  lea     r8, [rsp+248h+var_1B8]
0x18007f130  lea     rdx, unk_180364190
0x18007f137  lea     rcx, dword_180380B68
0x18007f13e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007f143  lea     rcx, [rsp+248h+var_1F0]; this
0x18007f148  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18007f14d  nop
0x18007f14e  mov     [rsp+248h+var_1F8], rdi
0x18007f153  lea     rax, [rsp+248h+var_1F8]
0x18007f158  mov     [rsp+248h+var_218], rax
0x18007f15d  mov     [rsp+248h+var_220], 2
0x18007f165  mov     [rsp+248h+var_228], 1Dh
0x18007f16d  lea     r9, ?MDM_Policy_Config01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_DeliveryOptimization02_NodeList
0x18007f174  xor     r8d, r8d
0x18007f177  xor     edx, edx
0x18007f179  mov     rcx, r12
0x18007f17c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18007f181  mov     r15d, eax
0x18007f184  test    eax, eax
0x18007f186  jz      short loc_18007F18D
0x18007f188  jmp     loc_18007FA2F
0x18007f18d  lea     rbx, [rsp+248h+var_1F8]
0x18007f192  mov     [rsp+248h+var_1D0], rbx
0x18007f197  mov     r14d, 1
0x18007f19d  mov     [rsp+248h+var_1C8], r14b
0x18007f1a5  mov     rsi, [rsp+248h+var_1F8]
0x18007f1aa  test    rsi, rsi
0x18007f1ad  jnz     short loc_18007F1B7
0x18007f1af  mov     r15d, r14d
0x18007f1b2  jmp     loc_18007FA2F
0x18007f1b7  mov     rax, [rsi]
0x18007f1ba  mov     rcx, rsi
0x18007f1bd  mov     rax, [rax+10h]
0x18007f1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f1c6  mov     r15d, eax
0x18007f1c9  test    eax, eax
0x18007f1cb  jz      short loc_18007F1EB
0x18007f1cd  mov     rcx, [rsp+248h+var_1F8]
0x18007f1d2  test    rcx, rcx
0x18007f1d5  jz      short loc_18007F1E6
0x18007f1d7  mov     rax, [rcx]
0x18007f1da  mov     edx, r14d
0x18007f1dd  mov     rax, [rax]
0x18007f1e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f1e5  nop
0x18007f1e6  jmp     loc_18007FA2F
0x18007f1eb  mov     rax, [rsi]
0x18007f1ee  mov     rcx, rsi
0x18007f1f1  mov     rax, [rax+8]
0x18007f1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f1fa  mov     r15d, eax
0x18007f1fd  test    eax, eax
0x18007f1ff  jz      short loc_18007F21F
0x18007f201  mov     rcx, [rsp+248h+var_1F8]
0x18007f206  test    rcx, rcx
0x18007f209  jz      short loc_18007F21A
0x18007f20b  mov     rax, [rcx]
0x18007f20e  mov     edx, r14d
0x18007f211  mov     rax, [rax]
0x18007f214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f219  nop
0x18007f21a  jmp     loc_18007FA2F
0x18007f21f  mov     r14d, edi
0x18007f222  mov     rax, [rsi+108h]
0x18007f229  sub     rax, [rsi+100h]
0x18007f230  sar     rax, 4
0x18007f234  cmp     r14d, eax
0x18007f237  jnb     loc_18007F9F7
0x18007f23d  lea     r8, [rsp+248h+instance]; instance
0x18007f245  lea     rdx, MDM_Policy_Config01_DeliveryOptimization02_rtti; classDecl
0x18007f24c  mov     rcx, r12; context
0x18007f24f  call    MI_Context_ConstructInstance
0x18007f254  mov     r15d, eax
0x18007f257  test    eax, eax
0x18007f259  jz      short loc_18007F27B
0x18007f25b  mov     rcx, [rbx]
0x18007f25e  test    rcx, rcx
0x18007f261  jz      short loc_18007F276
0x18007f263  mov     rax, [rcx]
0x18007f266  mov     edx, 1
0x18007f26b  mov     rax, [rax]
0x18007f26e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f273  mov     [rbx], rdi
0x18007f276  jmp     loc_18007FA2F
0x18007f27b  mov     [rsp+248h+var_200], 1
0x18007f280  mov     rax, [rsi]
0x18007f283  lea     r9, [rsp+248h+String]
0x18007f288  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x18007f28f  mov     edx, r14d
0x18007f292  mov     rcx, rsi
0x18007f295  mov     rax, [rax+18h]
0x18007f299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f29e  test    eax, eax
0x18007f2a0  jnz     short loc_18007F2B9
0x18007f2a2  mov     rdx, [rsp+248h+String]
0x18007f2a7  test    rdx, rdx
0x18007f2aa  jz      short loc_18007F2B9
0x18007f2ac  lea     rcx, [rsp+248h+instance]
0x18007f2b4  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18007f2b9  mov     rax, [rsi]
0x18007f2bc  lea     r9, [rsp+248h+String]
0x18007f2c1  lea     r8, aDeliveryoptimi; "DeliveryOptimization"
0x18007f2c8  mov     edx, r14d
0x18007f2cb  mov     rcx, rsi
0x18007f2ce  mov     rax, [rax+18h]
0x18007f2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f2d7  test    eax, eax
0x18007f2d9  jnz     short loc_18007F2F2
0x18007f2db  mov     rdx, [rsp+248h+String]
0x18007f2e0  test    rdx, rdx
0x18007f2e3  jz      short loc_18007F2F2
0x18007f2e5  lea     rcx, [rsp+248h+instance]
0x18007f2ed  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18007f2f2  cmp     r13b, 1
0x18007f2f6  jnz     short loc_18007F31A
0x18007f2f8  lea     rdx, [rsp+248h+instance]
0x18007f300  mov     rcx, r12; self
0x18007f303  call    MI_Instance_Destruct
0x18007f308  lea     rcx, [rsp+248h+instance]; self
0x18007f310  call    MI_Instance_Destruct
0x18007f315  jmp     loc_18007F9EA
0x18007f31a  mov     rax, [rsi]
0x18007f31d  lea     r9, [rsp+248h+String]
0x18007f322  lea     r8, aDoabsolutemaxc; "DOAbsoluteMaxCacheSize"
0x18007f329  mov     edx, r14d
0x18007f32c  mov     rcx, rsi
0x18007f32f  mov     rax, [rax+18h]
0x18007f333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f338  test    eax, eax
0x18007f33a  jnz     short loc_18007F35B
0x18007f33c  mov     rcx, [rsp+248h+String]; String
0x18007f341  test    rcx, rcx
0x18007f344  jz      short loc_18007F35B
0x18007f346  call    cs:__imp__wtoi
0x18007f34c  mov     [rsp+248h+var_138], eax
0x18007f353  mov     [rsp+248h+var_134], 1
0x18007f35b  mov     rax, [rsi]
0x18007f35e  lea     r9, [rsp+248h+String]
0x18007f363  lea     r8, aDoallowvpnpeer; "DOAllowVPNPeerCaching"
0x18007f36a  mov     edx, r14d
0x18007f36d  mov     rcx, rsi
0x18007f370  mov     rax, [rax+18h]
0x18007f374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f379  test    eax, eax
0x18007f37b  jnz     short loc_18007F39C
0x18007f37d  mov     rcx, [rsp+248h+String]; String
0x18007f382  test    rcx, rcx
0x18007f385  jz      short loc_18007F39C
0x18007f387  call    cs:__imp__wtoi
0x18007f38d  mov     [rsp+248h+var_130], eax
0x18007f394  mov     [rsp+248h+var_12C], 1
0x18007f39c  mov     rax, [rsi]
0x18007f39f  lea     r9, [rsp+248h+String]
0x18007f3a4  lea     r8, aDocachehost; "DOCacheHost"
0x18007f3ab  mov     edx, r14d
0x18007f3ae  mov     rcx, rsi
0x18007f3b1  mov     rax, [rax+18h]
0x18007f3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f3ba  test    eax, eax
0x18007f3bc  jnz     short loc_18007F3D5
0x18007f3be  mov     rdx, [rsp+248h+String]
0x18007f3c3  test    rdx, rdx
0x18007f3c6  jz      short loc_18007F3D5
0x18007f3c8  lea     rcx, [rsp+248h+instance]
0x18007f3d0  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x18007f3d5  mov     rax, [rsi]
0x18007f3d8  lea     r9, [rsp+248h+String]
0x18007f3dd  lea     r8, aDocachehostsou; "DOCacheHostSource"
0x18007f3e4  mov     edx, r14d
0x18007f3e7  mov     rcx, rsi
0x18007f3ea  mov     rax, [rax+18h]
0x18007f3ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f3f3  test    eax, eax
0x18007f3f5  jnz     short loc_18007F416
0x18007f3f7  mov     rcx, [rsp+248h+String]; String
0x18007f3fc  test    rcx, rcx
0x18007f3ff  jz      short loc_18007F416
0x18007f401  call    cs:__imp__wtoi
0x18007f407  mov     [rsp+248h+var_118], eax
0x18007f40e  mov     [rsp+248h+var_114], 1
0x18007f416  mov     rax, [rsi]
0x18007f419  lea     r9, [rsp+248h+String]
0x18007f41e  lea     r8, aDodelaybackgro; "DODelayBackgroundDownloadFromHttp"
0x18007f425  mov     edx, r14d
0x18007f428  mov     rcx, rsi
0x18007f42b  mov     rax, [rax+18h]
0x18007f42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f434  test    eax, eax
0x18007f436  jnz     short loc_18007F457
0x18007f438  mov     rcx, [rsp+248h+String]; String
0x18007f43d  test    rcx, rcx
0x18007f440  jz      short loc_18007F457
0x18007f442  call    cs:__imp__wtoi
0x18007f448  mov     [rsp+248h+var_110], eax
0x18007f44f  mov     [rsp+248h+var_10C], 1
0x18007f457  mov     rax, [rsi]
0x18007f45a  lea     r9, [rsp+248h+String]
0x18007f45f  lea     r8, aDodelaycachese; "DODelayCacheServerFallbackBackground"
0x18007f466  mov     edx, r14d
0x18007f469  mov     rcx, rsi
0x18007f46c  mov     rax, [rax+18h]
0x18007f470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f475  test    eax, eax
0x18007f477  jnz     short loc_18007F498
0x18007f479  mov     rcx, [rsp+248h+String]; String
0x18007f47e  test    rcx, rcx
0x18007f481  jz      short loc_18007F498
0x18007f483  call    cs:__imp__wtoi
0x18007f489  mov     [rsp+248h+var_108], eax
0x18007f490  mov     [rsp+248h+var_104], 1
0x18007f498  mov     rax, [rsi]
0x18007f49b  lea     r9, [rsp+248h+String]
0x18007f4a0  lea     r8, aDodelaycachese_0; "DODelayCacheServerFallbackForeground"
0x18007f4a7  mov     edx, r14d
0x18007f4aa  mov     rcx, rsi
0x18007f4ad  mov     rax, [rax+18h]
0x18007f4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f4b6  test    eax, eax
0x18007f4b8  jnz     short loc_18007F4D9
0x18007f4ba  mov     rcx, [rsp+248h+String]; String
0x18007f4bf  test    rcx, rcx
0x18007f4c2  jz      short loc_18007F4D9
0x18007f4c4  call    cs:__imp__wtoi
0x18007f4ca  mov     [rsp+248h+var_100], eax
0x18007f4d1  mov     [rsp+248h+var_FC], 1
0x18007f4d9  mov     rax, [rsi]
0x18007f4dc  lea     r9, [rsp+248h+String]
0x18007f4e1  lea     r8, aDodelayforegro; "DODelayForegroundDownloadFromHttp"
0x18007f4e8  mov     edx, r14d
0x18007f4eb  mov     rcx, rsi
0x18007f4ee  mov     rax, [rax+18h]
0x18007f4f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f4f7  test    eax, eax
0x18007f4f9  jnz     short loc_18007F51A
0x18007f4fb  mov     rcx, [rsp+248h+String]; String
0x18007f500  test    rcx, rcx
0x18007f503  jz      short loc_18007F51A
0x18007f505  call    cs:__imp__wtoi
0x18007f50b  mov     [rsp+248h+var_F8], eax
0x18007f512  mov     [rsp+248h+var_F4], 1
0x18007f51a  mov     rax, [rsi]
0x18007f51d  lea     r9, [rsp+248h+String]
0x18007f522  lea     r8, aDodownloadmode; "DODownloadMode"
0x18007f529  mov     edx, r14d
0x18007f52c  mov     rcx, rsi
0x18007f52f  mov     rax, [rax+18h]
0x18007f533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f538  test    eax, eax
0x18007f53a  jnz     short loc_18007F55B
  ... truncated ...
```
