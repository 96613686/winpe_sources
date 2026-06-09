# MDM_Policy_Result01_DeliveryOptimization02_InvokeGetInstance

- ea: `0x180136e34`
- end: `0x1801377c4`
- name: `MDM_Policy_Result01_DeliveryOptimization02_InvokeGetInstance`
- size: `2448`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting`

## callers

- `0x180135610`

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
- `0x180136e34`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1801370d3`
- `msvcrt!_wtoi` at `0x180137110`
- `msvcrt!_wtoi` at `0x18013717c`
- `msvcrt!_wtoi` at `0x1801371b9`
- `msvcrt!_wtoi` at `0x1801371f6`
- `msvcrt!_wtoi` at `0x180137233`
- `msvcrt!_wtoi` at `0x180137270`
- `msvcrt!_wtoi` at `0x1801372ad`
- `msvcrt!_wtoi` at `0x180137319`
- `msvcrt!_wtoi` at `0x180137356`
- `msvcrt!_wtoi` at `0x180137393`
- `msvcrt!_wtoi` at `0x1801373d0`
- `msvcrt!_wtoi` at `0x18013740d`
- `msvcrt!_wtoi` at `0x18013744a`
- `msvcrt!_wtoi` at `0x180137487`
- `msvcrt!_wtoi` at `0x1801374c4`
- `msvcrt!_wtoi` at `0x180137501`
- `msvcrt!_wtoi` at `0x18013753e`
- `msvcrt!_wtoi` at `0x1801375aa`
- `msvcrt!_wtoi` at `0x1801375e7`
- `msvcrt!_wtoi` at `0x180137624`
- `msvcrt!_wtoi` at `0x180137661`
- `msvcrt!_wtoi` at `0x1801370d3`
- `msvcrt!_wtoi` at `0x180137110`
- `msvcrt!_wtoi` at `0x18013717c`
- `msvcrt!_wtoi` at `0x1801371b9`
- `msvcrt!_wtoi` at `0x1801371f6`
- `msvcrt!_wtoi` at `0x180137233`
- `msvcrt!_wtoi` at `0x180137270`
- `msvcrt!_wtoi` at `0x1801372ad`
- `msvcrt!_wtoi` at `0x180137319`
- `msvcrt!_wtoi` at `0x180137356`
- `msvcrt!_wtoi` at `0x180137393`
- `msvcrt!_wtoi` at `0x1801373d0`
- `msvcrt!_wtoi` at `0x18013740d`
- `msvcrt!_wtoi` at `0x18013744a`
- `msvcrt!_wtoi` at `0x180137487`
- `msvcrt!_wtoi` at `0x1801374c4`
- `msvcrt!_wtoi` at `0x180137501`
- `msvcrt!_wtoi` at `0x18013753e`
- `msvcrt!_wtoi` at `0x1801375aa`
- `msvcrt!_wtoi` at `0x1801375e7`
- `msvcrt!_wtoi` at `0x180137624`
- `msvcrt!_wtoi` at `0x180137661`

## string_xrefs

- `0x1801370b6`: `DOAbsoluteMaxCacheSize`
- `0x180137130`: `DOCacheHost`
- `0x18013715f`: `DOCacheHostSource`
- `0x1801371d9`: `DODelayCacheServerFallbackBackground`
- `0x180137216`: `DODelayCacheServerFallbackForeground`
- `0x180137376`: `DOMaxCacheAge`
- `0x1801373b3`: `DOMaxCacheSize`
- `0x1801374e4`: `DOMinFileSizeToCache`
- `0x18013755e`: `DOModifyCacheDrive`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_DeliveryOptimization02_InvokeGetInstance(
        MI_Context *self,
        struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  MI_Result v5; // r14d
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
    v5 = (unsigned int)CreateRequestHandlerInstance(
                         self,
                         a2[1].serverName,
                         a2[1].ft,
                         &MDM_Policy_Result01_DeliveryOptimization02_NodeList,
                         29,
                         0,
                         &v10);
    if ( v5 == MI_RESULT_OK )
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
        v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v5 )
        {
          if ( v10 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
        }
        else
        {
          v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOAbsoluteMaxCacheSize",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v18 = _wtoi(String);
                v19 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOAllowVPNPeerCaching",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"DOCacheHost", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOCacheHostSource",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DODelayBackgroundDownloadFromHttp",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DODelayCacheServerFallbackBackground",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DODelayCacheServerFallbackForeground",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DODelayForegroundDownloadFromHttp",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"DODownloadMode", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"DOGroupId", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"DOGroupIdSource", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOMaxBackgroundDownloadBandwidth",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"DOMaxCacheAge", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"DOMaxCacheSize", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOMaxForegroundDownloadBandwidth",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOMinBackgroundQos",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOMinBatteryPercentageAllowedToUpload",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOMinDiskSizeAllowedToPeer",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOMinFileSizeToCache",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOMinRAMAllowedToPeer",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOModifyCacheDrive",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOMonthlyUploadDataCap",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOPercentageMaxBackgroundBandwidth",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOPercentageMaxForegroundBandwidth",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DORestrictPeerSelectionBy",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOSetHoursToLimitBackgroundDownloadBandwidth",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSuggestedSites(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DOSetHoursToLimitForegroundDownloadBandwidth",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
        v5 = MI_RESULT_FAILED;
      }
    }
  }
  else
  {
    v5 = MI_RESULT_INVALID_PARAMETER;
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
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180136e34  mov     [rsp+arg_10], rbx
0x180136e39  push    rsi
0x180136e3a  push    rdi
0x180136e3b  push    r12
0x180136e3d  push    r14
0x180136e3f  push    r15
0x180136e41  sub     rsp, 220h
0x180136e48  mov     rax, cs:__security_cookie
0x180136e4f  xor     rax, rsp
0x180136e52  mov     [rsp+248h+var_38], rax
0x180136e5a  mov     rsi, rdx
0x180136e5d  mov     r15, rcx
0x180136e60  xor     ebx, ebx
0x180136e62  mov     [rsp+248h+String], rbx
0x180136e67  xor     edx, edx; Val
0x180136e69  mov     r8d, 160h; Size
0x180136e6f  lea     rcx, [rsp+248h+instance]; void *
0x180136e77  call    memset_0
0x180136e7c  mov     [rsp+248h+var_1C0], ebx
0x180136e83  mov     [rsp+248h+var_1BC], bl
0x180136e8a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180136e91  mov     [rsp+248h+var_1F0], rax
0x180136e96  lea     rax, [rsp+248h+var_1C0]
0x180136e9e  mov     [rsp+248h+var_1E8], rax
0x180136ea3  lea     rax, aMdmPolicyResul_161; "MDM_Policy_Result01_DeliveryOptimizatio"...
0x180136eaa  mov     [rsp+248h+var_1E0], rax
0x180136eaf  lea     rcx, [rsp+248h+var_1C0]
0x180136eb7  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180136ebc  mov     eax, cs:dword_180380B68
0x180136ec2  cmp     eax, 5
0x180136ec5  jbe     short loc_180136F36
0x180136ec7  mov     rdx, 200000000000h
0x180136ed1  lea     rcx, dword_180380B68
0x180136ed8  call    _tlgKeywordOn
0x180136edd  test    al, al
0x180136edf  jz      short loc_180136F36
0x180136ee1  cmp     [rsp+248h+var_1BC], bl
0x180136ee8  jz      short loc_180136F18
0x180136eea  cmp     [rsp+248h+var_1A8], ebx
0x180136ef1  jnz     short loc_180136F0E
0x180136ef3  cmp     [rsp+248h+var_1A4], ebx
0x180136efa  jnz     short loc_180136F0E
0x180136efc  cmp     [rsp+248h+var_1A0], ebx
0x180136f03  jnz     short loc_180136F0E
0x180136f05  cmp     [rsp+248h+var_19C], ebx
0x180136f0c  jz      short loc_180136F18
0x180136f0e  lea     r9, [rsp+248h+var_1A8]
0x180136f16  jmp     short loc_180136F1B
0x180136f18  mov     r9, rbx
0x180136f1b  lea     r8, [rsp+248h+var_1B8]
0x180136f23  lea     rdx, word_180337C2E
0x180136f2a  lea     rcx, dword_180380B68
0x180136f31  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180136f36  cmp     [rsi+48h], bl
0x180136f39  jz      loc_180137722
0x180136f3f  mov     [rsp+248h+var_200], bl
0x180136f43  cmp     [rsi+58h], bl
0x180136f46  jz      loc_180137722
0x180136f4c  mov     r9, [rsi+40h]; unsigned __int16 *
0x180136f50  mov     r8, [rsi+50h]; unsigned __int16 *
0x180136f54  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x180136f5b  lea     rcx, [rsp+248h+var_1F0]; this
0x180136f60  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180136f65  nop
0x180136f66  mov     [rsp+248h+var_1F8], rbx
0x180136f6b  lea     rax, [rsp+248h+var_1F8]
0x180136f70  mov     [rsp+248h+var_218], rax
0x180136f75  mov     [rsp+248h+var_220], ebx
0x180136f79  mov     [rsp+248h+var_228], 1Dh
0x180136f81  lea     r9, ?MDM_Policy_Result01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_DeliveryOptimization02_NodeList
0x180136f88  mov     r8, [rsi+40h]
0x180136f8c  mov     rdx, [rsi+50h]
0x180136f90  mov     rcx, r15
0x180136f93  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180136f98  mov     r14d, eax
0x180136f9b  test    eax, eax
0x180136f9d  jz      short loc_180136FA4
0x180136f9f  jmp     loc_180137728
0x180136fa4  lea     rax, [rsp+248h+var_1F8]
0x180136fa9  mov     [rsp+248h+var_1D0], rax
0x180136fae  mov     r12d, 1
0x180136fb4  mov     [rsp+248h+var_1C8], r12b
0x180136fbc  mov     rdi, [rsp+248h+var_1F8]
0x180136fc1  test    rdi, rdi
0x180136fc4  jnz     short loc_180136FCE
0x180136fc6  mov     r14d, r12d
0x180136fc9  jmp     loc_180137728
0x180136fce  mov     r9d, 1Dh; unsigned int
0x180136fd4  lea     r8, ?MDM_Policy_Result01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180136fdb  mov     rdx, rsi; struct _MI_Instance *
0x180136fde  mov     rcx, rdi; this
0x180136fe1  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180136fe6  mov     rax, [rdi]
0x180136fe9  mov     rcx, rdi
0x180136fec  mov     rax, [rax+10h]
0x180136ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136ff5  mov     r14d, eax
0x180136ff8  test    eax, eax
0x180136ffa  jz      short loc_18013701A
0x180136ffc  mov     rcx, [rsp+248h+var_1F8]
0x180137001  test    rcx, rcx
0x180137004  jz      short loc_180137015
0x180137006  mov     rax, [rcx]
0x180137009  mov     edx, r12d
0x18013700c  mov     rax, [rax]
0x18013700f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137014  nop
0x180137015  jmp     loc_180137728
0x18013701a  mov     rax, [rdi]
0x18013701d  mov     rcx, rdi
0x180137020  mov     rax, [rax+8]
0x180137024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137029  mov     r14d, eax
0x18013702c  test    eax, eax
0x18013702e  jz      short loc_18013704E
0x180137030  mov     rcx, [rsp+248h+var_1F8]
0x180137035  test    rcx, rcx
0x180137038  jz      short loc_180137049
0x18013703a  mov     rax, [rcx]
0x18013703d  mov     edx, r12d
0x180137040  mov     rax, [rax]
0x180137043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137048  nop
0x180137049  jmp     loc_180137728
0x18013704e  lea     r8, [rsp+248h+instance]; instance
0x180137056  lea     rdx, MDM_Policy_Result01_DeliveryOptimization02_rtti; classDecl
0x18013705d  mov     rcx, r15; context
0x180137060  call    MI_Context_ConstructInstance
0x180137065  mov     r14d, eax
0x180137068  test    eax, eax
0x18013706a  jz      short loc_18013708A
0x18013706c  mov     rcx, [rsp+248h+var_1F8]
0x180137071  test    rcx, rcx
0x180137074  jz      short loc_180137085
0x180137076  mov     rax, [rcx]
0x180137079  mov     edx, r12d
0x18013707c  mov     rax, [rax]
0x18013707f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137084  nop
0x180137085  jmp     loc_180137728
0x18013708a  mov     [rsp+248h+var_200], r12b
0x18013708f  mov     rdx, [rsi+40h]
0x180137093  lea     rcx, [rsp+248h+instance]
0x18013709b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801370a0  mov     rdx, [rsi+50h]
0x1801370a4  lea     rcx, [rsp+248h+instance]
0x1801370ac  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801370b1  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x1801370b6  lea     rdx, aDoabsolutemaxc; "DOAbsoluteMaxCacheSize"
0x1801370bd  mov     rcx, rdi; this
0x1801370c0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801370c5  test    eax, eax
0x1801370c7  jnz     short loc_1801370EE
0x1801370c9  mov     rcx, [rsp+248h+String]; String
0x1801370ce  test    rcx, rcx
0x1801370d1  jz      short loc_1801370EE
0x1801370d3  call    cs:__imp__wtoi
0x1801370da  nop     dword ptr [rax+rax+00h]
0x1801370df  mov     [rsp+248h+var_138], eax
0x1801370e6  mov     [rsp+248h+var_134], r12b
0x1801370ee  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x1801370f3  lea     rdx, aDoallowvpnpeer; "DOAllowVPNPeerCaching"
0x1801370fa  mov     rcx, rdi; this
0x1801370fd  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180137102  test    eax, eax
0x180137104  jnz     short loc_18013712B
0x180137106  mov     rcx, [rsp+248h+String]; String
0x18013710b  test    rcx, rcx
0x18013710e  jz      short loc_18013712B
0x180137110  call    cs:__imp__wtoi
0x180137117  nop     dword ptr [rax+rax+00h]
0x18013711c  mov     [rsp+248h+var_130], eax
0x180137123  mov     [rsp+248h+var_12C], r12b
0x18013712b  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x180137130  lea     rdx, aDocachehost; "DOCacheHost"
0x180137137  mov     rcx, rdi; this
0x18013713a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18013713f  test    eax, eax
0x180137141  jnz     short loc_18013715A
0x180137143  mov     rdx, [rsp+248h+String]
0x180137148  test    rdx, rdx
0x18013714b  jz      short loc_18013715A
0x18013714d  lea     rcx, [rsp+248h+instance]
0x180137155  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x18013715a  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18013715f  lea     rdx, aDocachehostsou; "DOCacheHostSource"
0x180137166  mov     rcx, rdi; this
0x180137169  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18013716e  test    eax, eax
0x180137170  jnz     short loc_180137197
0x180137172  mov     rcx, [rsp+248h+String]; String
0x180137177  test    rcx, rcx
0x18013717a  jz      short loc_180137197
0x18013717c  call    cs:__imp__wtoi
0x180137183  nop     dword ptr [rax+rax+00h]
0x180137188  mov     [rsp+248h+var_118], eax
0x18013718f  mov     [rsp+248h+var_114], r12b
0x180137197  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18013719c  lea     rdx, aDodelaybackgro; "DODelayBackgroundDownloadFromHttp"
0x1801371a3  mov     rcx, rdi; this
0x1801371a6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801371ab  test    eax, eax
0x1801371ad  jnz     short loc_1801371D4
0x1801371af  mov     rcx, [rsp+248h+String]; String
0x1801371b4  test    rcx, rcx
0x1801371b7  jz      short loc_1801371D4
0x1801371b9  call    cs:__imp__wtoi
0x1801371c0  nop     dword ptr [rax+rax+00h]
0x1801371c5  mov     [rsp+248h+var_110], eax
0x1801371cc  mov     [rsp+248h+var_10C], r12b
0x1801371d4  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x1801371d9  lea     rdx, aDodelaycachese; "DODelayCacheServerFallbackBackground"
0x1801371e0  mov     rcx, rdi; this
0x1801371e3  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801371e8  test    eax, eax
0x1801371ea  jnz     short loc_180137211
0x1801371ec  mov     rcx, [rsp+248h+String]; String
0x1801371f1  test    rcx, rcx
0x1801371f4  jz      short loc_180137211
0x1801371f6  call    cs:__imp__wtoi
0x1801371fd  nop     dword ptr [rax+rax+00h]
0x180137202  mov     [rsp+248h+var_108], eax
0x180137209  mov     [rsp+248h+var_104], r12b
0x180137211  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x180137216  lea     rdx, aDodelaycachese_0; "DODelayCacheServerFallbackForeground"
0x18013721d  mov     rcx, rdi; this
0x180137220  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180137225  test    eax, eax
0x180137227  jnz     short loc_18013724E
0x180137229  mov     rcx, [rsp+248h+String]; String
0x18013722e  test    rcx, rcx
0x180137231  jz      short loc_18013724E
0x180137233  call    cs:__imp__wtoi
0x18013723a  nop     dword ptr [rax+rax+00h]
0x18013723f  mov     [rsp+248h+var_100], eax
0x180137246  mov     [rsp+248h+var_FC], r12b
0x18013724e  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x180137253  lea     rdx, aDodelayforegro; "DODelayForegroundDownloadFromHttp"
0x18013725a  mov     rcx, rdi; this
0x18013725d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180137262  test    eax, eax
0x180137264  jnz     short loc_18013728B
0x180137266  mov     rcx, [rsp+248h+String]; String
0x18013726b  test    rcx, rcx
0x18013726e  jz      short loc_18013728B
0x180137270  call    cs:__imp__wtoi
0x180137277  nop     dword ptr [rax+rax+00h]
0x18013727c  mov     [rsp+248h+var_F8], eax
0x180137283  mov     [rsp+248h+var_F4], r12b
0x18013728b  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x180137290  lea     rdx, aDodownloadmode; "DODownloadMode"
0x180137297  mov     rcx, rdi; this
0x18013729a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18013729f  test    eax, eax
0x1801372a1  jnz     short loc_1801372C8
0x1801372a3  mov     rcx, [rsp+248h+String]; String
0x1801372a8  test    rcx, rcx
0x1801372ab  jz      short loc_1801372C8
0x1801372ad  call    cs:__imp__wtoi
0x1801372b4  nop     dword ptr [rax+rax+00h]
0x1801372b9  mov     [rsp+248h+var_F0], eax
0x1801372c0  mov     [rsp+248h+var_EC], r12b
0x1801372c8  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x1801372cd  lea     rdx, aDogroupid; "DOGroupId"
0x1801372d4  mov     rcx, rdi; this
0x1801372d7  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801372dc  test    eax, eax
0x1801372de  jnz     short loc_1801372F7
0x1801372e0  mov     rdx, [rsp+248h+String]
0x1801372e5  test    rdx, rdx
0x1801372e8  jz      short loc_1801372F7
0x1801372ea  lea     rcx, [rsp+248h+instance]
0x1801372f2  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList
0x1801372f7  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x1801372fc  lea     rdx, aDogroupidsourc; "DOGroupIdSource"
0x180137303  mov     rcx, rdi; this
0x180137306  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18013730b  test    eax, eax
0x18013730d  jnz     short loc_180137334
0x18013730f  mov     rcx, [rsp+248h+String]; String
0x180137314  test    rcx, rcx
0x180137317  jz      short loc_180137334
0x180137319  call    cs:__imp__wtoi
0x180137320  nop     dword ptr [rax+rax+00h]
0x180137325  mov     [rsp+248h+var_D8], eax
0x18013732c  mov     [rsp+248h+var_D4], r12b
0x180137334  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x180137339  lea     rdx, aDomaxbackgroun; "DOMaxBackgroundDownloadBandwidth"
0x180137340  mov     rcx, rdi; this
0x180137343  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180137348  test    eax, eax
0x18013734a  jnz     short loc_180137371
0x18013734c  mov     rcx, [rsp+248h+String]; String
0x180137351  test    rcx, rcx
0x180137354  jz      short loc_180137371
0x180137356  call    cs:__imp__wtoi
0x18013735d  nop     dword ptr [rax+rax+00h]
0x180137362  mov     [rsp+248h+var_D0], eax
0x180137369  mov     [rsp+248h+var_CC], r12b
0x180137371  lea     r8, [rsp+248h+String]; unsigned __int16 **
  ... truncated ...
```
