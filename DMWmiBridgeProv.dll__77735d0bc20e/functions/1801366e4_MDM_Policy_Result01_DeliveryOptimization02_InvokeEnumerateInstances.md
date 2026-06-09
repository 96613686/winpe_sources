# MDM_Policy_Result01_DeliveryOptimization02_InvokeEnumerateInstances

- ea: `0x1801366e4`
- end: `0x18013717f`
- name: `MDM_Policy_Result01_DeliveryOptimization02_InvokeEnumerateInstances`
- size: `2715`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting`

## callers

- `0x1801359a0`

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
- `0x1801366e4`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1801369f6`
- `msvcrt!_wtoi` at `0x180136a37`
- `msvcrt!_wtoi` at `0x180136ab1`
- `msvcrt!_wtoi` at `0x180136af2`
- `msvcrt!_wtoi` at `0x180136b33`
- `msvcrt!_wtoi` at `0x180136b74`
- `msvcrt!_wtoi` at `0x180136bb5`
- `msvcrt!_wtoi` at `0x180136bf6`
- `msvcrt!_wtoi` at `0x180136c70`
- `msvcrt!_wtoi` at `0x180136cb1`
- `msvcrt!_wtoi` at `0x180136cf2`
- `msvcrt!_wtoi` at `0x180136d33`
- `msvcrt!_wtoi` at `0x180136d74`
- `msvcrt!_wtoi` at `0x180136db5`
- `msvcrt!_wtoi` at `0x180136df6`
- `msvcrt!_wtoi` at `0x180136e37`
- `msvcrt!_wtoi` at `0x180136e78`
- `msvcrt!_wtoi` at `0x180136eb9`
- `msvcrt!_wtoi` at `0x180136f33`
- `msvcrt!_wtoi` at `0x180136f74`
- `msvcrt!_wtoi` at `0x180136fb5`
- `msvcrt!_wtoi` at `0x180136ff6`
- `msvcrt!_wtoi` at `0x1801369f6`
- `msvcrt!_wtoi` at `0x180136a37`
- `msvcrt!_wtoi` at `0x180136ab1`
- `msvcrt!_wtoi` at `0x180136af2`
- `msvcrt!_wtoi` at `0x180136b33`
- `msvcrt!_wtoi` at `0x180136b74`
- `msvcrt!_wtoi` at `0x180136bb5`
- `msvcrt!_wtoi` at `0x180136bf6`
- `msvcrt!_wtoi` at `0x180136c70`
- `msvcrt!_wtoi` at `0x180136cb1`
- `msvcrt!_wtoi` at `0x180136cf2`
- `msvcrt!_wtoi` at `0x180136d33`
- `msvcrt!_wtoi` at `0x180136d74`
- `msvcrt!_wtoi` at `0x180136db5`
- `msvcrt!_wtoi` at `0x180136df6`
- `msvcrt!_wtoi` at `0x180136e37`
- `msvcrt!_wtoi` at `0x180136e78`
- `msvcrt!_wtoi` at `0x180136eb9`
- `msvcrt!_wtoi` at `0x180136f33`
- `msvcrt!_wtoi` at `0x180136f74`
- `msvcrt!_wtoi` at `0x180136fb5`
- `msvcrt!_wtoi` at `0x180136ff6`

## string_xrefs

- `0x1801369d2`: `DOAbsoluteMaxCacheSize`
- `0x180136a54`: `DOCacheHost`
- `0x180136a8d`: `DOCacheHostSource`
- `0x180136b0f`: `DODelayCacheServerFallbackBackground`
- `0x180136b50`: `DODelayCacheServerFallbackForeground`
- `0x180136cce`: `DOMaxCacheAge`
- `0x180136d0f`: `DOMaxCacheSize`
- `0x180136e54`: `DOMinFileSizeToCache`
- `0x180136ed6`: `DOModifyCacheDrive`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_DeliveryOptimization02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  unsigned int v6; // r15d
  WmiRequestHandlerAdd *v7; // rsi
  unsigned int i; // r14d
  wchar_t *String; // [rsp+40h] [rbp-208h] BYREF
  char v11; // [rsp+48h] [rbp-200h]
  WmiRequestHandlerAdd *v12; // [rsp+50h] [rbp-1F8h] BYREF
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
  v6 = CreateRequestHandlerInstance(
         (__int64)self,
         0,
         0,
         (struct WmiNodeInfo *)&MDM_Policy_Result01_DeliveryOptimization02_NodeList,
         0x1Du,
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
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_DeliveryOptimization02_rtti, &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_119;
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
                    L"DeliveryOptimization",
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
                      L"DOAbsoluteMaxCacheSize",
                      &String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOAllowVPNPeerCaching",
                      &String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOCacheHost",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOCacheHostSource",
                      &String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DODelayBackgroundDownloadFromHttp",
                      &String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DODelayCacheServerFallbackBackground",
                      &String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DODelayCacheServerFallbackForeground",
                      &String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DODelayForegroundDownloadFromHttp",
                      &String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DODownloadMode",
                      &String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOGroupId",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOGroupIdSource",
                      &String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOMaxBackgroundDownloadBandwidth",
                      &String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOMaxCacheAge",
                      &String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOMaxCacheSize",
                      &String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOMaxForegroundDownloadBandwidth",
                      &String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOMinBackgroundQos",
                      &String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOMinBatteryPercentageAllowedToUpload",
                      &String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOMinDiskSizeAllowedToPeer",
                      &String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOMinFileSizeToCache",
                      &String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOMinRAMAllowedToPeer",
                      &String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOModifyCacheDrive",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOMonthlyUploadDataCap",
                      &String)
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOPercentageMaxBackgroundBandwidth",
                      &String)
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOPercentageMaxForegroundBandwidth",
                      &String)
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DORestrictPeerSelectionBy",
                      &String)
                && String )
              {
                v62 = _wtoi(String);
                v63 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DOSetHoursToLimitBackgroundDownloadBandwidth",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSuggestedSites(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
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
  return v6;
}

```

## disassembly

```asm
0x1801366e4  mov     [rsp+arg_8], rbx
0x1801366e9  mov     [rsp+arg_10], rsi
0x1801366ee  push    rdi
0x1801366ef  push    r12
0x1801366f1  push    r13
0x1801366f3  push    r14
0x1801366f5  push    r15
0x1801366f7  sub     rsp, 220h
0x1801366fe  mov     rax, cs:__security_cookie
0x180136705  xor     rax, rsp
0x180136708  mov     [rsp+248h+var_38], rax
0x180136710  mov     r13b, dl
0x180136713  mov     r12, rcx
0x180136716  xor     edx, edx; Val
0x180136718  mov     r8d, 160h; Size
0x18013671e  lea     rcx, [rsp+248h+instance]; void *
0x180136726  call    memset_0
0x18013672b  xor     edi, edi
0x18013672d  mov     [rsp+248h+var_200], dil
0x180136732  mov     [rsp+248h+String], rdi
0x180136737  mov     [rsp+248h+var_1C0], edi
0x18013673e  mov     [rsp+248h+var_1BC], dil
0x180136746  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18013674d  mov     [rsp+248h+var_1F0], rax
0x180136752  lea     rax, [rsp+248h+var_1C0]
0x18013675a  mov     [rsp+248h+var_1E8], rax
0x18013675f  lea     rax, aMdmPolicyResul_161; "MDM_Policy_Result01_DeliveryOptimizatio"...
0x180136766  mov     [rsp+248h+var_1E0], rax
0x18013676b  lea     rcx, [rsp+248h+var_1C0]
0x180136773  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180136778  mov     eax, cs:dword_180380B68
0x18013677e  cmp     eax, 5
0x180136781  jbe     short loc_1801367F3
0x180136783  mov     rdx, 200000000000h
0x18013678d  lea     rcx, dword_180380B68
0x180136794  call    _tlgKeywordOn
0x180136799  test    al, al
0x18013679b  jz      short loc_1801367F3
0x18013679d  cmp     [rsp+248h+var_1BC], dil
0x1801367a5  jz      short loc_1801367D5
0x1801367a7  cmp     [rsp+248h+var_1A8], edi
0x1801367ae  jnz     short loc_1801367CB
0x1801367b0  cmp     [rsp+248h+var_1A4], edi
0x1801367b7  jnz     short loc_1801367CB
0x1801367b9  cmp     [rsp+248h+var_1A0], edi
0x1801367c0  jnz     short loc_1801367CB
0x1801367c2  cmp     [rsp+248h+var_19C], edi
0x1801367c9  jz      short loc_1801367D5
0x1801367cb  lea     r9, [rsp+248h+var_1A8]
0x1801367d3  jmp     short loc_1801367D8
0x1801367d5  mov     r9, rdi
0x1801367d8  lea     r8, [rsp+248h+var_1B8]
0x1801367e0  lea     rdx, byte_18034365D
0x1801367e7  lea     rcx, dword_180380B68
0x1801367ee  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801367f3  lea     rcx, [rsp+248h+var_1F0]; this
0x1801367f8  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1801367fd  nop
0x1801367fe  mov     [rsp+248h+var_1F8], rdi
0x180136803  lea     rax, [rsp+248h+var_1F8]
0x180136808  mov     [rsp+248h+var_218], rax
0x18013680d  mov     [rsp+248h+var_220], 2
0x180136815  mov     [rsp+248h+var_228], 1Dh
0x18013681d  lea     r9, ?MDM_Policy_Result01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_DeliveryOptimization02_NodeList
0x180136824  xor     r8d, r8d
0x180136827  xor     edx, edx
0x180136829  mov     rcx, r12
0x18013682c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180136831  mov     r15d, eax
0x180136834  test    eax, eax
0x180136836  jz      short loc_18013683D
0x180136838  jmp     loc_1801370DF
0x18013683d  lea     rbx, [rsp+248h+var_1F8]
0x180136842  mov     [rsp+248h+var_1D0], rbx
0x180136847  mov     r14d, 1
0x18013684d  mov     [rsp+248h+var_1C8], r14b
0x180136855  mov     rsi, [rsp+248h+var_1F8]
0x18013685a  test    rsi, rsi
0x18013685d  jnz     short loc_180136867
0x18013685f  mov     r15d, r14d
0x180136862  jmp     loc_1801370DF
0x180136867  mov     rax, [rsi]
0x18013686a  mov     rcx, rsi
0x18013686d  mov     rax, [rax+10h]
0x180136871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136876  mov     r15d, eax
0x180136879  test    eax, eax
0x18013687b  jz      short loc_18013689B
0x18013687d  mov     rcx, [rsp+248h+var_1F8]
0x180136882  test    rcx, rcx
0x180136885  jz      short loc_180136896
0x180136887  mov     rax, [rcx]
0x18013688a  mov     edx, r14d
0x18013688d  mov     rax, [rax]
0x180136890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136895  nop
0x180136896  jmp     loc_1801370DF
0x18013689b  mov     rax, [rsi]
0x18013689e  mov     rcx, rsi
0x1801368a1  mov     rax, [rax+8]
0x1801368a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801368aa  mov     r15d, eax
0x1801368ad  test    eax, eax
0x1801368af  jz      short loc_1801368CF
0x1801368b1  mov     rcx, [rsp+248h+var_1F8]
0x1801368b6  test    rcx, rcx
0x1801368b9  jz      short loc_1801368CA
0x1801368bb  mov     rax, [rcx]
0x1801368be  mov     edx, r14d
0x1801368c1  mov     rax, [rax]
0x1801368c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801368c9  nop
0x1801368ca  jmp     loc_1801370DF
0x1801368cf  mov     r14d, edi
0x1801368d2  mov     rax, [rsi+108h]
0x1801368d9  sub     rax, [rsi+100h]
0x1801368e0  sar     rax, 4
0x1801368e4  cmp     r14d, eax
0x1801368e7  jnb     loc_1801370A7
0x1801368ed  lea     r8, [rsp+248h+instance]; instance
0x1801368f5  lea     rdx, MDM_Policy_Result01_DeliveryOptimization02_rtti; classDecl
0x1801368fc  mov     rcx, r12; context
0x1801368ff  call    MI_Context_ConstructInstance
0x180136904  mov     r15d, eax
0x180136907  test    eax, eax
0x180136909  jz      short loc_18013692B
0x18013690b  mov     rcx, [rbx]
0x18013690e  test    rcx, rcx
0x180136911  jz      short loc_180136926
0x180136913  mov     rax, [rcx]
0x180136916  mov     edx, 1
0x18013691b  mov     rax, [rax]
0x18013691e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136923  mov     [rbx], rdi
0x180136926  jmp     loc_1801370DF
0x18013692b  mov     [rsp+248h+var_200], 1
0x180136930  mov     rax, [rsi]
0x180136933  lea     r9, [rsp+248h+String]
0x180136938  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x18013693f  mov     edx, r14d
0x180136942  mov     rcx, rsi
0x180136945  mov     rax, [rax+18h]
0x180136949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013694e  test    eax, eax
0x180136950  jnz     short loc_180136969
0x180136952  mov     rdx, [rsp+248h+String]
0x180136957  test    rdx, rdx
0x18013695a  jz      short loc_180136969
0x18013695c  lea     rcx, [rsp+248h+instance]
0x180136964  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180136969  mov     rax, [rsi]
0x18013696c  lea     r9, [rsp+248h+String]
0x180136971  lea     r8, aDeliveryoptimi; "DeliveryOptimization"
0x180136978  mov     edx, r14d
0x18013697b  mov     rcx, rsi
0x18013697e  mov     rax, [rax+18h]
0x180136982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136987  test    eax, eax
0x180136989  jnz     short loc_1801369A2
0x18013698b  mov     rdx, [rsp+248h+String]
0x180136990  test    rdx, rdx
0x180136993  jz      short loc_1801369A2
0x180136995  lea     rcx, [rsp+248h+instance]
0x18013699d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801369a2  cmp     r13b, 1
0x1801369a6  jnz     short loc_1801369CA
0x1801369a8  lea     rdx, [rsp+248h+instance]
0x1801369b0  mov     rcx, r12; self
0x1801369b3  call    MI_Instance_Destruct
0x1801369b8  lea     rcx, [rsp+248h+instance]; self
0x1801369c0  call    MI_Instance_Destruct
0x1801369c5  jmp     loc_18013709A
0x1801369ca  mov     rax, [rsi]
0x1801369cd  lea     r9, [rsp+248h+String]
0x1801369d2  lea     r8, aDoabsolutemaxc; "DOAbsoluteMaxCacheSize"
0x1801369d9  mov     edx, r14d
0x1801369dc  mov     rcx, rsi
0x1801369df  mov     rax, [rax+18h]
0x1801369e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801369e8  test    eax, eax
0x1801369ea  jnz     short loc_180136A0B
0x1801369ec  mov     rcx, [rsp+248h+String]; String
0x1801369f1  test    rcx, rcx
0x1801369f4  jz      short loc_180136A0B
0x1801369f6  call    cs:__imp__wtoi
0x1801369fc  mov     [rsp+248h+var_138], eax
0x180136a03  mov     [rsp+248h+var_134], 1
0x180136a0b  mov     rax, [rsi]
0x180136a0e  lea     r9, [rsp+248h+String]
0x180136a13  lea     r8, aDoallowvpnpeer; "DOAllowVPNPeerCaching"
0x180136a1a  mov     edx, r14d
0x180136a1d  mov     rcx, rsi
0x180136a20  mov     rax, [rax+18h]
0x180136a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136a29  test    eax, eax
0x180136a2b  jnz     short loc_180136A4C
0x180136a2d  mov     rcx, [rsp+248h+String]; String
0x180136a32  test    rcx, rcx
0x180136a35  jz      short loc_180136A4C
0x180136a37  call    cs:__imp__wtoi
0x180136a3d  mov     [rsp+248h+var_130], eax
0x180136a44  mov     [rsp+248h+var_12C], 1
0x180136a4c  mov     rax, [rsi]
0x180136a4f  lea     r9, [rsp+248h+String]
0x180136a54  lea     r8, aDocachehost; "DOCacheHost"
0x180136a5b  mov     edx, r14d
0x180136a5e  mov     rcx, rsi
0x180136a61  mov     rax, [rax+18h]
0x180136a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136a6a  test    eax, eax
0x180136a6c  jnz     short loc_180136A85
0x180136a6e  mov     rdx, [rsp+248h+String]
0x180136a73  test    rdx, rdx
0x180136a76  jz      short loc_180136A85
0x180136a78  lea     rcx, [rsp+248h+instance]
0x180136a80  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x180136a85  mov     rax, [rsi]
0x180136a88  lea     r9, [rsp+248h+String]
0x180136a8d  lea     r8, aDocachehostsou; "DOCacheHostSource"
0x180136a94  mov     edx, r14d
0x180136a97  mov     rcx, rsi
0x180136a9a  mov     rax, [rax+18h]
0x180136a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136aa3  test    eax, eax
0x180136aa5  jnz     short loc_180136AC6
0x180136aa7  mov     rcx, [rsp+248h+String]; String
0x180136aac  test    rcx, rcx
0x180136aaf  jz      short loc_180136AC6
0x180136ab1  call    cs:__imp__wtoi
0x180136ab7  mov     [rsp+248h+var_118], eax
0x180136abe  mov     [rsp+248h+var_114], 1
0x180136ac6  mov     rax, [rsi]
0x180136ac9  lea     r9, [rsp+248h+String]
0x180136ace  lea     r8, aDodelaybackgro; "DODelayBackgroundDownloadFromHttp"
0x180136ad5  mov     edx, r14d
0x180136ad8  mov     rcx, rsi
0x180136adb  mov     rax, [rax+18h]
0x180136adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136ae4  test    eax, eax
0x180136ae6  jnz     short loc_180136B07
0x180136ae8  mov     rcx, [rsp+248h+String]; String
0x180136aed  test    rcx, rcx
0x180136af0  jz      short loc_180136B07
0x180136af2  call    cs:__imp__wtoi
0x180136af8  mov     [rsp+248h+var_110], eax
0x180136aff  mov     [rsp+248h+var_10C], 1
0x180136b07  mov     rax, [rsi]
0x180136b0a  lea     r9, [rsp+248h+String]
0x180136b0f  lea     r8, aDodelaycachese; "DODelayCacheServerFallbackBackground"
0x180136b16  mov     edx, r14d
0x180136b19  mov     rcx, rsi
0x180136b1c  mov     rax, [rax+18h]
0x180136b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136b25  test    eax, eax
0x180136b27  jnz     short loc_180136B48
0x180136b29  mov     rcx, [rsp+248h+String]; String
0x180136b2e  test    rcx, rcx
0x180136b31  jz      short loc_180136B48
0x180136b33  call    cs:__imp__wtoi
0x180136b39  mov     [rsp+248h+var_108], eax
0x180136b40  mov     [rsp+248h+var_104], 1
0x180136b48  mov     rax, [rsi]
0x180136b4b  lea     r9, [rsp+248h+String]
0x180136b50  lea     r8, aDodelaycachese_0; "DODelayCacheServerFallbackForeground"
0x180136b57  mov     edx, r14d
0x180136b5a  mov     rcx, rsi
0x180136b5d  mov     rax, [rax+18h]
0x180136b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136b66  test    eax, eax
0x180136b68  jnz     short loc_180136B89
0x180136b6a  mov     rcx, [rsp+248h+String]; String
0x180136b6f  test    rcx, rcx
0x180136b72  jz      short loc_180136B89
0x180136b74  call    cs:__imp__wtoi
0x180136b7a  mov     [rsp+248h+var_100], eax
0x180136b81  mov     [rsp+248h+var_FC], 1
0x180136b89  mov     rax, [rsi]
0x180136b8c  lea     r9, [rsp+248h+String]
0x180136b91  lea     r8, aDodelayforegro; "DODelayForegroundDownloadFromHttp"
0x180136b98  mov     edx, r14d
0x180136b9b  mov     rcx, rsi
0x180136b9e  mov     rax, [rax+18h]
0x180136ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136ba7  test    eax, eax
0x180136ba9  jnz     short loc_180136BCA
0x180136bab  mov     rcx, [rsp+248h+String]; String
0x180136bb0  test    rcx, rcx
0x180136bb3  jz      short loc_180136BCA
0x180136bb5  call    cs:__imp__wtoi
0x180136bbb  mov     [rsp+248h+var_F8], eax
0x180136bc2  mov     [rsp+248h+var_F4], 1
0x180136bca  mov     rax, [rsi]
0x180136bcd  lea     r9, [rsp+248h+String]
0x180136bd2  lea     r8, aDodownloadmode; "DODownloadMode"
0x180136bd9  mov     edx, r14d
0x180136bdc  mov     rcx, rsi
0x180136bdf  mov     rax, [rax+18h]
0x180136be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136be8  test    eax, eax
0x180136bea  jnz     short loc_180136C0B
  ... truncated ...
```
