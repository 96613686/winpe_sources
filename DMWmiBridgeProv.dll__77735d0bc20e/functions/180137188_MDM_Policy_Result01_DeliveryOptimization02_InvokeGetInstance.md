# MDM_Policy_Result01_DeliveryOptimization02_InvokeGetInstance

- ea: `0x180137188`
- end: `0x180137a93`
- name: `MDM_Policy_Result01_DeliveryOptimization02_InvokeGetInstance`
- size: `2315`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting`

## callers

- `0x1801359e0`

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
- `0x180137188`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180137427`
- `msvcrt!_wtoi` at `0x18013745e`
- `msvcrt!_wtoi` at `0x1801374c4`
- `msvcrt!_wtoi` at `0x1801374fb`
- `msvcrt!_wtoi` at `0x180137532`
- `msvcrt!_wtoi` at `0x180137569`
- `msvcrt!_wtoi` at `0x1801375a0`
- `msvcrt!_wtoi` at `0x1801375d7`
- `msvcrt!_wtoi` at `0x18013763d`
- `msvcrt!_wtoi` at `0x180137674`
- `msvcrt!_wtoi` at `0x1801376ab`
- `msvcrt!_wtoi` at `0x1801376e2`
- `msvcrt!_wtoi` at `0x180137719`
- `msvcrt!_wtoi` at `0x180137750`
- `msvcrt!_wtoi` at `0x180137787`
- `msvcrt!_wtoi` at `0x1801377be`
- `msvcrt!_wtoi` at `0x1801377f5`
- `msvcrt!_wtoi` at `0x18013782c`
- `msvcrt!_wtoi` at `0x180137892`
- `msvcrt!_wtoi` at `0x1801378c9`
- `msvcrt!_wtoi` at `0x180137900`
- `msvcrt!_wtoi` at `0x180137937`
- `msvcrt!_wtoi` at `0x180137427`
- `msvcrt!_wtoi` at `0x18013745e`
- `msvcrt!_wtoi` at `0x1801374c4`
- `msvcrt!_wtoi` at `0x1801374fb`
- `msvcrt!_wtoi` at `0x180137532`
- `msvcrt!_wtoi` at `0x180137569`
- `msvcrt!_wtoi` at `0x1801375a0`
- `msvcrt!_wtoi` at `0x1801375d7`
- `msvcrt!_wtoi` at `0x18013763d`
- `msvcrt!_wtoi` at `0x180137674`
- `msvcrt!_wtoi` at `0x1801376ab`
- `msvcrt!_wtoi` at `0x1801376e2`
- `msvcrt!_wtoi` at `0x180137719`
- `msvcrt!_wtoi` at `0x180137750`
- `msvcrt!_wtoi` at `0x180137787`
- `msvcrt!_wtoi` at `0x1801377be`
- `msvcrt!_wtoi` at `0x1801377f5`
- `msvcrt!_wtoi` at `0x18013782c`
- `msvcrt!_wtoi` at `0x180137892`
- `msvcrt!_wtoi` at `0x1801378c9`
- `msvcrt!_wtoi` at `0x180137900`
- `msvcrt!_wtoi` at `0x180137937`

## string_xrefs

- `0x18013740a`: `DOAbsoluteMaxCacheSize`
- `0x180137478`: `DOCacheHost`
- `0x1801374a7`: `DOCacheHostSource`
- `0x180137515`: `DODelayCacheServerFallbackBackground`
- `0x18013754c`: `DODelayCacheServerFallbackForeground`
- `0x18013768e`: `DOMaxCacheAge`
- `0x1801376c5`: `DOMaxCacheSize`
- `0x1801377d8`: `DOMinFileSizeToCache`
- `0x180137846`: `DOModifyCacheDrive`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_DeliveryOptimization02_InvokeGetInstance(
        MI_Context *self,
        struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // r14d
  WmiRequestHandler *v6; // rdi
  wchar_t *String; // [rsp+40h] [rbp-208h] BYREF
  char v9; // [rsp+48h] [rbp-200h]
  WmiRequestHandler *v10; // [rsp+50h] [rbp-1F8h] BYREF
  _QWORD v11[5]; // [rsp+58h] [rbp-1F0h] BYREF
  char v12; // [rsp+80h] [rbp-1C8h]
  int v13; // [rsp+88h] [rbp-1C0h] BYREF
  char v14; // [rsp+8Ch] [rbp-1BCh]
  _BYTE v15[16]; // [rsp+90h] [rbp-1B8h] BYREF
  _DWORD v16[4]; // [rsp+A0h] [rbp-1A8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-198h] BYREF
  int v18; // [rsp+110h] [rbp-138h]
  char v19; // [rsp+114h] [rbp-134h]
  int v20; // [rsp+118h] [rbp-130h]
  char v21; // [rsp+11Ch] [rbp-12Ch]
  int v22; // [rsp+130h] [rbp-118h]
  char v23; // [rsp+134h] [rbp-114h]
  int v24; // [rsp+138h] [rbp-110h]
  char v25; // [rsp+13Ch] [rbp-10Ch]
  int v26; // [rsp+140h] [rbp-108h]
  char v27; // [rsp+144h] [rbp-104h]
  int v28; // [rsp+148h] [rbp-100h]
  char v29; // [rsp+14Ch] [rbp-FCh]
  int v30; // [rsp+150h] [rbp-F8h]
  char v31; // [rsp+154h] [rbp-F4h]
  int v32; // [rsp+158h] [rbp-F0h]
  char v33; // [rsp+15Ch] [rbp-ECh]
  int v34; // [rsp+170h] [rbp-D8h]
  char v35; // [rsp+174h] [rbp-D4h]
  int v36; // [rsp+178h] [rbp-D0h]
  char v37; // [rsp+17Ch] [rbp-CCh]
  int v38; // [rsp+180h] [rbp-C8h]
  char v39; // [rsp+184h] [rbp-C4h]
  int v40; // [rsp+188h] [rbp-C0h]
  char v41; // [rsp+18Ch] [rbp-BCh]
  int v42; // [rsp+190h] [rbp-B8h]
  char v43; // [rsp+194h] [rbp-B4h]
  int v44; // [rsp+198h] [rbp-B0h]
  char v45; // [rsp+19Ch] [rbp-ACh]
  int v46; // [rsp+1A0h] [rbp-A8h]
  char v47; // [rsp+1A4h] [rbp-A4h]
  int v48; // [rsp+1A8h] [rbp-A0h]
  char v49; // [rsp+1ACh] [rbp-9Ch]
  int v50; // [rsp+1B0h] [rbp-98h]
  char v51; // [rsp+1B4h] [rbp-94h]
  int v52; // [rsp+1B8h] [rbp-90h]
  char v53; // [rsp+1BCh] [rbp-8Ch]
  int v54; // [rsp+1D0h] [rbp-78h]
  char v55; // [rsp+1D4h] [rbp-74h]
  int v56; // [rsp+1D8h] [rbp-70h]
  char v57; // [rsp+1DCh] [rbp-6Ch]
  int v58; // [rsp+1E0h] [rbp-68h]
  char v59; // [rsp+1E4h] [rbp-64h]
  int v60; // [rsp+1E8h] [rbp-60h]
  char v61; // [rsp+1ECh] [rbp-5Ch]

  String = 0;
  memset_0(&instance, 0, 0x160u);
  v13 = 0;
  v14 = 0;
  v11[0] = &TelemetryEventWriter::`vftable';
  v11[1] = &v13;
  v11[2] = "MDM_Policy_Result01_DeliveryOptimization02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_180337C2E,
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
           (struct WmiNodeInfo *)&MDM_Policy_Result01_DeliveryOptimization02_NodeList,
           0x1Du,
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
          (struct WmiNodeInfo *)&MDM_Policy_Result01_DeliveryOptimization02_NodeList,
          0x1Du);
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
            v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_DeliveryOptimization02_rtti, &instance);
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
                                    L"DOAbsoluteMaxCacheSize",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v18 = _wtoi(String);
                v19 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOAllowVPNPeerCaching",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOCacheHost",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOCacheHostSource",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DODelayBackgroundDownloadFromHttp",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DODelayCacheServerFallbackBackground",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DODelayCacheServerFallbackForeground",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DODelayForegroundDownloadFromHttp",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DODownloadMode",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOGroupId",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOGroupIdSource",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOMaxBackgroundDownloadBandwidth",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOMaxCacheAge",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOMaxCacheSize",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOMaxForegroundDownloadBandwidth",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOMinBackgroundQos",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOMinBatteryPercentageAllowedToUpload",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOMinDiskSizeAllowedToPeer",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOMinFileSizeToCache",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOMinRAMAllowedToPeer",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOModifyCacheDrive",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOMonthlyUploadDataCap",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOPercentageMaxBackgroundBandwidth",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOPercentageMaxForegroundBandwidth",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DORestrictPeerSelectionBy",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOSetHoursToLimitBackgroundDownloadBandwidth",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSuggestedSites(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DOSetHoursToLimitForegroundDownloadBandwidth",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowTrustedSitesZoneTemplate(&instance);
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
      word_18035C10A,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return v5;
}

```

## disassembly

```asm
0x180137188  mov     [rsp+arg_10], rbx
0x18013718d  push    rsi
0x18013718e  push    rdi
0x18013718f  push    r12
0x180137191  push    r14
0x180137193  push    r15
0x180137195  sub     rsp, 220h
0x18013719c  mov     rax, cs:__security_cookie
0x1801371a3  xor     rax, rsp
0x1801371a6  mov     [rsp+248h+var_38], rax
0x1801371ae  mov     rsi, rdx
0x1801371b1  mov     r15, rcx
0x1801371b4  xor     ebx, ebx
0x1801371b6  mov     [rsp+248h+String], rbx
0x1801371bb  xor     edx, edx; Val
0x1801371bd  mov     r8d, 160h; Size
0x1801371c3  lea     rcx, [rsp+248h+instance]; void *
0x1801371cb  call    memset_0
0x1801371d0  mov     [rsp+248h+var_1C0], ebx
0x1801371d7  mov     [rsp+248h+var_1BC], bl
0x1801371de  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801371e5  mov     [rsp+248h+var_1F0], rax
0x1801371ea  lea     rax, [rsp+248h+var_1C0]
0x1801371f2  mov     [rsp+248h+var_1E8], rax
0x1801371f7  lea     rax, aMdmPolicyResul_161; "MDM_Policy_Result01_DeliveryOptimizatio"...
0x1801371fe  mov     [rsp+248h+var_1E0], rax
0x180137203  lea     rcx, [rsp+248h+var_1C0]
0x18013720b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180137210  mov     eax, cs:dword_180380B68
0x180137216  cmp     eax, 5
0x180137219  jbe     short loc_18013728A
0x18013721b  mov     rdx, 200000000000h
0x180137225  lea     rcx, dword_180380B68
0x18013722c  call    _tlgKeywordOn
0x180137231  test    al, al
0x180137233  jz      short loc_18013728A
0x180137235  cmp     [rsp+248h+var_1BC], bl
0x18013723c  jz      short loc_18013726C
0x18013723e  cmp     [rsp+248h+var_1A8], ebx
0x180137245  jnz     short loc_180137262
0x180137247  cmp     [rsp+248h+var_1A4], ebx
0x18013724e  jnz     short loc_180137262
0x180137250  cmp     [rsp+248h+var_1A0], ebx
0x180137257  jnz     short loc_180137262
0x180137259  cmp     [rsp+248h+var_19C], ebx
0x180137260  jz      short loc_18013726C
0x180137262  lea     r9, [rsp+248h+var_1A8]
0x18013726a  jmp     short loc_18013726F
0x18013726c  mov     r9, rbx
0x18013726f  lea     r8, [rsp+248h+var_1B8]
0x180137277  lea     rdx, word_180337C2E
0x18013727e  lea     rcx, dword_180380B68
0x180137285  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18013728a  cmp     [rsi+48h], bl
0x18013728d  jz      loc_1801379F2
0x180137293  mov     [rsp+248h+var_200], bl
0x180137297  cmp     [rsi+58h], bl
0x18013729a  jz      loc_1801379F2
0x1801372a0  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801372a4  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801372a8  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1801372af  lea     rcx, [rsp+248h+var_1F0]; this
0x1801372b4  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801372b9  nop
0x1801372ba  mov     [rsp+248h+var_1F8], rbx
0x1801372bf  lea     rax, [rsp+248h+var_1F8]
0x1801372c4  mov     [rsp+248h+var_218], rax
0x1801372c9  mov     [rsp+248h+var_220], ebx
0x1801372cd  mov     [rsp+248h+var_228], 1Dh
0x1801372d5  lea     r9, ?MDM_Policy_Result01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_DeliveryOptimization02_NodeList
0x1801372dc  mov     r8, [rsi+40h]
0x1801372e0  mov     rdx, [rsi+50h]
0x1801372e4  mov     rcx, r15
0x1801372e7  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801372ec  mov     r14d, eax
0x1801372ef  test    eax, eax
0x1801372f1  jz      short loc_1801372F8
0x1801372f3  jmp     loc_1801379F8
0x1801372f8  lea     rax, [rsp+248h+var_1F8]
0x1801372fd  mov     [rsp+248h+var_1D0], rax
0x180137302  mov     r12d, 1
0x180137308  mov     [rsp+248h+var_1C8], r12b
0x180137310  mov     rdi, [rsp+248h+var_1F8]
0x180137315  test    rdi, rdi
0x180137318  jnz     short loc_180137322
0x18013731a  mov     r14d, r12d
0x18013731d  jmp     loc_1801379F8
0x180137322  mov     r9d, 1Dh; unsigned int
0x180137328  lea     r8, ?MDM_Policy_Result01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18013732f  mov     rdx, rsi; struct _MI_Instance *
0x180137332  mov     rcx, rdi; this
0x180137335  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18013733a  mov     rax, [rdi]
0x18013733d  mov     rcx, rdi
0x180137340  mov     rax, [rax+10h]
0x180137344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137349  mov     r14d, eax
0x18013734c  test    eax, eax
0x18013734e  jz      short loc_18013736E
0x180137350  mov     rcx, [rsp+248h+var_1F8]
0x180137355  test    rcx, rcx
0x180137358  jz      short loc_180137369
0x18013735a  mov     rax, [rcx]
0x18013735d  mov     edx, r12d
0x180137360  mov     rax, [rax]
0x180137363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137368  nop
0x180137369  jmp     loc_1801379F8
0x18013736e  mov     rax, [rdi]
0x180137371  mov     rcx, rdi
0x180137374  mov     rax, [rax+8]
0x180137378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013737d  mov     r14d, eax
0x180137380  test    eax, eax
0x180137382  jz      short loc_1801373A2
0x180137384  mov     rcx, [rsp+248h+var_1F8]
0x180137389  test    rcx, rcx
0x18013738c  jz      short loc_18013739D
0x18013738e  mov     rax, [rcx]
0x180137391  mov     edx, r12d
0x180137394  mov     rax, [rax]
0x180137397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013739c  nop
0x18013739d  jmp     loc_1801379F8
0x1801373a2  lea     r8, [rsp+248h+instance]; instance
0x1801373aa  lea     rdx, MDM_Policy_Result01_DeliveryOptimization02_rtti; classDecl
0x1801373b1  mov     rcx, r15; context
0x1801373b4  call    MI_Context_ConstructInstance
0x1801373b9  mov     r14d, eax
0x1801373bc  test    eax, eax
0x1801373be  jz      short loc_1801373DE
0x1801373c0  mov     rcx, [rsp+248h+var_1F8]
0x1801373c5  test    rcx, rcx
0x1801373c8  jz      short loc_1801373D9
0x1801373ca  mov     rax, [rcx]
0x1801373cd  mov     edx, r12d
0x1801373d0  mov     rax, [rax]
0x1801373d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801373d8  nop
0x1801373d9  jmp     loc_1801379F8
0x1801373de  mov     [rsp+248h+var_200], r12b
0x1801373e3  mov     rdx, [rsi+40h]
0x1801373e7  lea     rcx, [rsp+248h+instance]
0x1801373ef  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801373f4  mov     rdx, [rsi+50h]
0x1801373f8  lea     rcx, [rsp+248h+instance]
0x180137400  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180137405  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18013740a  lea     rdx, aDoabsolutemaxc; "DOAbsoluteMaxCacheSize"
0x180137411  mov     rcx, rdi; this
0x180137414  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180137419  test    eax, eax
0x18013741b  jnz     short loc_18013743C
0x18013741d  mov     rcx, [rsp+248h+String]; String
0x180137422  test    rcx, rcx
0x180137425  jz      short loc_18013743C
0x180137427  call    cs:__imp__wtoi
0x18013742d  mov     [rsp+248h+var_138], eax
0x180137434  mov     [rsp+248h+var_134], r12b
0x18013743c  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x180137441  lea     rdx, aDoallowvpnpeer; "DOAllowVPNPeerCaching"
0x180137448  mov     rcx, rdi; this
0x18013744b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180137450  test    eax, eax
0x180137452  jnz     short loc_180137473
0x180137454  mov     rcx, [rsp+248h+String]; String
0x180137459  test    rcx, rcx
0x18013745c  jz      short loc_180137473
0x18013745e  call    cs:__imp__wtoi
0x180137464  mov     [rsp+248h+var_130], eax
0x18013746b  mov     [rsp+248h+var_12C], r12b
0x180137473  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x180137478  lea     rdx, aDocachehost; "DOCacheHost"
0x18013747f  mov     rcx, rdi; this
0x180137482  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180137487  test    eax, eax
0x180137489  jnz     short loc_1801374A2
0x18013748b  mov     rdx, [rsp+248h+String]
0x180137490  test    rdx, rdx
0x180137493  jz      short loc_1801374A2
0x180137495  lea     rcx, [rsp+248h+instance]
0x18013749d  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x1801374a2  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x1801374a7  lea     rdx, aDocachehostsou; "DOCacheHostSource"
0x1801374ae  mov     rcx, rdi; this
0x1801374b1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801374b6  test    eax, eax
0x1801374b8  jnz     short loc_1801374D9
0x1801374ba  mov     rcx, [rsp+248h+String]; String
0x1801374bf  test    rcx, rcx
0x1801374c2  jz      short loc_1801374D9
0x1801374c4  call    cs:__imp__wtoi
0x1801374ca  mov     [rsp+248h+var_118], eax
0x1801374d1  mov     [rsp+248h+var_114], r12b
0x1801374d9  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x1801374de  lea     rdx, aDodelaybackgro; "DODelayBackgroundDownloadFromHttp"
0x1801374e5  mov     rcx, rdi; this
0x1801374e8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801374ed  test    eax, eax
0x1801374ef  jnz     short loc_180137510
0x1801374f1  mov     rcx, [rsp+248h+String]; String
0x1801374f6  test    rcx, rcx
0x1801374f9  jz      short loc_180137510
0x1801374fb  call    cs:__imp__wtoi
0x180137501  mov     [rsp+248h+var_110], eax
0x180137508  mov     [rsp+248h+var_10C], r12b
0x180137510  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x180137515  lea     rdx, aDodelaycachese; "DODelayCacheServerFallbackBackground"
0x18013751c  mov     rcx, rdi; this
0x18013751f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180137524  test    eax, eax
0x180137526  jnz     short loc_180137547
0x180137528  mov     rcx, [rsp+248h+String]; String
0x18013752d  test    rcx, rcx
0x180137530  jz      short loc_180137547
0x180137532  call    cs:__imp__wtoi
0x180137538  mov     [rsp+248h+var_108], eax
0x18013753f  mov     [rsp+248h+var_104], r12b
0x180137547  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18013754c  lea     rdx, aDodelaycachese_0; "DODelayCacheServerFallbackForeground"
0x180137553  mov     rcx, rdi; this
0x180137556  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18013755b  test    eax, eax
0x18013755d  jnz     short loc_18013757E
0x18013755f  mov     rcx, [rsp+248h+String]; String
0x180137564  test    rcx, rcx
0x180137567  jz      short loc_18013757E
0x180137569  call    cs:__imp__wtoi
0x18013756f  mov     [rsp+248h+var_100], eax
0x180137576  mov     [rsp+248h+var_FC], r12b
0x18013757e  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x180137583  lea     rdx, aDodelayforegro; "DODelayForegroundDownloadFromHttp"
0x18013758a  mov     rcx, rdi; this
0x18013758d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180137592  test    eax, eax
0x180137594  jnz     short loc_1801375B5
0x180137596  mov     rcx, [rsp+248h+String]; String
0x18013759b  test    rcx, rcx
0x18013759e  jz      short loc_1801375B5
0x1801375a0  call    cs:__imp__wtoi
0x1801375a6  mov     [rsp+248h+var_F8], eax
0x1801375ad  mov     [rsp+248h+var_F4], r12b
0x1801375b5  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x1801375ba  lea     rdx, aDodownloadmode; "DODownloadMode"
0x1801375c1  mov     rcx, rdi; this
0x1801375c4  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801375c9  test    eax, eax
0x1801375cb  jnz     short loc_1801375EC
0x1801375cd  mov     rcx, [rsp+248h+String]; String
0x1801375d2  test    rcx, rcx
0x1801375d5  jz      short loc_1801375EC
0x1801375d7  call    cs:__imp__wtoi
0x1801375dd  mov     [rsp+248h+var_F0], eax
0x1801375e4  mov     [rsp+248h+var_EC], r12b
0x1801375ec  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x1801375f1  lea     rdx, aDogroupid; "DOGroupId"
0x1801375f8  mov     rcx, rdi; this
0x1801375fb  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180137600  test    eax, eax
0x180137602  jnz     short loc_18013761B
0x180137604  mov     rdx, [rsp+248h+String]
0x180137609  test    rdx, rdx
0x18013760c  jz      short loc_18013761B
0x18013760e  lea     rcx, [rsp+248h+instance]
0x180137616  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList
0x18013761b  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x180137620  lea     rdx, aDogroupidsourc; "DOGroupIdSource"
0x180137627  mov     rcx, rdi; this
0x18013762a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18013762f  test    eax, eax
0x180137631  jnz     short loc_180137652
0x180137633  mov     rcx, [rsp+248h+String]; String
0x180137638  test    rcx, rcx
0x18013763b  jz      short loc_180137652
0x18013763d  call    cs:__imp__wtoi
0x180137643  mov     [rsp+248h+var_D8], eax
0x18013764a  mov     [rsp+248h+var_D4], r12b
0x180137652  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x180137657  lea     rdx, aDomaxbackgroun; "DOMaxBackgroundDownloadBandwidth"
0x18013765e  mov     rcx, rdi; this
0x180137661  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180137666  test    eax, eax
0x180137668  jnz     short loc_180137689
0x18013766a  mov     rcx, [rsp+248h+String]; String
0x18013766f  test    rcx, rcx
0x180137672  jz      short loc_180137689
0x180137674  call    cs:__imp__wtoi
0x18013767a  mov     [rsp+248h+var_D0], eax
0x180137681  mov     [rsp+248h+var_CC], r12b
0x180137689  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18013768e  lea     rdx, aDomaxcacheage; "DOMaxCacheAge"
0x180137695  mov     rcx, rdi; this
0x180137698  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18013769d  test    eax, eax
0x18013769f  jnz     short loc_1801376C0
0x1801376a1  mov     rcx, [rsp+248h+String]; String
0x1801376a6  test    rcx, rcx
0x1801376a9  jz      short loc_1801376C0
0x1801376ab  call    cs:__imp__wtoi
0x1801376b1  mov     [rsp+248h+var_C8], eax
  ... truncated ...
```
