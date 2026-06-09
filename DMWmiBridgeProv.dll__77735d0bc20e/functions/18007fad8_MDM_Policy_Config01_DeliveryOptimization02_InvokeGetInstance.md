# MDM_Policy_Config01_DeliveryOptimization02_InvokeGetInstance

- ea: `0x18007fad8`
- end: `0x1800803e3`
- name: `MDM_Policy_Config01_DeliveryOptimization02_InvokeGetInstance`
- size: `2315`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting`

## callers

- `0x18007e330`

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
- `0x18007fad8`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18007fd77`
- `msvcrt!_wtoi` at `0x18007fdae`
- `msvcrt!_wtoi` at `0x18007fe14`
- `msvcrt!_wtoi` at `0x18007fe4b`
- `msvcrt!_wtoi` at `0x18007fe82`
- `msvcrt!_wtoi` at `0x18007feb9`
- `msvcrt!_wtoi` at `0x18007fef0`
- `msvcrt!_wtoi` at `0x18007ff27`
- `msvcrt!_wtoi` at `0x18007ff8d`
- `msvcrt!_wtoi` at `0x18007ffc4`
- `msvcrt!_wtoi` at `0x18007fffb`
- `msvcrt!_wtoi` at `0x180080032`
- `msvcrt!_wtoi` at `0x180080069`
- `msvcrt!_wtoi` at `0x1800800a0`
- `msvcrt!_wtoi` at `0x1800800d7`
- `msvcrt!_wtoi` at `0x18008010e`
- `msvcrt!_wtoi` at `0x180080145`
- `msvcrt!_wtoi` at `0x18008017c`
- `msvcrt!_wtoi` at `0x1800801e2`
- `msvcrt!_wtoi` at `0x180080219`
- `msvcrt!_wtoi` at `0x180080250`
- `msvcrt!_wtoi` at `0x180080287`
- `msvcrt!_wtoi` at `0x18007fd77`
- `msvcrt!_wtoi` at `0x18007fdae`
- `msvcrt!_wtoi` at `0x18007fe14`
- `msvcrt!_wtoi` at `0x18007fe4b`
- `msvcrt!_wtoi` at `0x18007fe82`
- `msvcrt!_wtoi` at `0x18007feb9`
- `msvcrt!_wtoi` at `0x18007fef0`
- `msvcrt!_wtoi` at `0x18007ff27`
- `msvcrt!_wtoi` at `0x18007ff8d`
- `msvcrt!_wtoi` at `0x18007ffc4`
- `msvcrt!_wtoi` at `0x18007fffb`
- `msvcrt!_wtoi` at `0x180080032`
- `msvcrt!_wtoi` at `0x180080069`
- `msvcrt!_wtoi` at `0x1800800a0`
- `msvcrt!_wtoi` at `0x1800800d7`
- `msvcrt!_wtoi` at `0x18008010e`
- `msvcrt!_wtoi` at `0x180080145`
- `msvcrt!_wtoi` at `0x18008017c`
- `msvcrt!_wtoi` at `0x1800801e2`
- `msvcrt!_wtoi` at `0x180080219`
- `msvcrt!_wtoi` at `0x180080250`
- `msvcrt!_wtoi` at `0x180080287`

## string_xrefs

- `0x18007fd5a`: `DOAbsoluteMaxCacheSize`
- `0x18007fdc8`: `DOCacheHost`
- `0x18007fdf7`: `DOCacheHostSource`
- `0x18007fe65`: `DODelayCacheServerFallbackBackground`
- `0x18007fe9c`: `DODelayCacheServerFallbackForeground`
- `0x18007ffde`: `DOMaxCacheAge`
- `0x180080015`: `DOMaxCacheSize`
- `0x180080128`: `DOMinFileSizeToCache`
- `0x180080196`: `DOModifyCacheDrive`
- `0x18007fb47`: `MDM_Policy_Config01_DeliveryOptimization02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_DeliveryOptimization02_InvokeGetInstance(
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
  v11[2] = "MDM_Policy_Config01_DeliveryOptimization02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_180363C2E,
      v15,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    v5 = 4;
    goto LABEL_110;
  }
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
         (struct WmiNodeInfo *)&MDM_Policy_Config01_DeliveryOptimization02_NodeList,
         0x1Du,
         0,
         &v10);
  if ( !v5 )
  {
    v11[4] = &v10;
    v12 = 1;
    v6 = v10;
    if ( !v10 )
    {
      v5 = 1;
      goto LABEL_110;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_DeliveryOptimization02_NodeList,
      0x1Du);
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_110;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_110;
    }
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_110;
      goto LABEL_24;
    }
    v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_DeliveryOptimization02_rtti, &instance);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_110;
      goto LABEL_24;
    }
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
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(v6, L"DOCacheHost", (const unsigned __int16 **)&String)
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
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(v6, L"DOGroupId", (const unsigned __int16 **)&String)
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
LABEL_110:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18034172B,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return v5;
}

```

## disassembly

```asm
0x18007fad8  mov     [rsp+arg_10], rbx
0x18007fadd  push    rsi
0x18007fade  push    rdi
0x18007fadf  push    r12
0x18007fae1  push    r14
0x18007fae3  push    r15
0x18007fae5  sub     rsp, 220h
0x18007faec  mov     rax, cs:__security_cookie
0x18007faf3  xor     rax, rsp
0x18007faf6  mov     [rsp+248h+var_38], rax
0x18007fafe  mov     rsi, rdx
0x18007fb01  mov     r15, rcx
0x18007fb04  xor     ebx, ebx
0x18007fb06  mov     [rsp+248h+String], rbx
0x18007fb0b  xor     edx, edx; Val
0x18007fb0d  mov     r8d, 160h; Size
0x18007fb13  lea     rcx, [rsp+248h+instance]; void *
0x18007fb1b  call    memset_0
0x18007fb20  mov     [rsp+248h+var_1C0], ebx
0x18007fb27  mov     [rsp+248h+var_1BC], bl
0x18007fb2e  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18007fb35  mov     [rsp+248h+var_1F0], rax
0x18007fb3a  lea     rax, [rsp+248h+var_1C0]
0x18007fb42  mov     [rsp+248h+var_1E8], rax
0x18007fb47  lea     rax, aMdmPolicyConfi_34; "MDM_Policy_Config01_DeliveryOptimizatio"...
0x18007fb4e  mov     [rsp+248h+var_1E0], rax
0x18007fb53  lea     rcx, [rsp+248h+var_1C0]
0x18007fb5b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007fb60  mov     eax, cs:dword_180380B68
0x18007fb66  cmp     eax, 5
0x18007fb69  jbe     short loc_18007FBDA
0x18007fb6b  mov     rdx, 200000000000h
0x18007fb75  lea     rcx, dword_180380B68
0x18007fb7c  call    _tlgKeywordOn
0x18007fb81  test    al, al
0x18007fb83  jz      short loc_18007FBDA
0x18007fb85  cmp     [rsp+248h+var_1BC], bl
0x18007fb8c  jz      short loc_18007FBBC
0x18007fb8e  cmp     [rsp+248h+var_1A8], ebx
0x18007fb95  jnz     short loc_18007FBB2
0x18007fb97  cmp     [rsp+248h+var_1A4], ebx
0x18007fb9e  jnz     short loc_18007FBB2
0x18007fba0  cmp     [rsp+248h+var_1A0], ebx
0x18007fba7  jnz     short loc_18007FBB2
0x18007fba9  cmp     [rsp+248h+var_19C], ebx
0x18007fbb0  jz      short loc_18007FBBC
0x18007fbb2  lea     r9, [rsp+248h+var_1A8]
0x18007fbba  jmp     short loc_18007FBBF
0x18007fbbc  mov     r9, rbx
0x18007fbbf  lea     r8, [rsp+248h+var_1B8]
0x18007fbc7  lea     rdx, word_180363C2E
0x18007fbce  lea     rcx, dword_180380B68
0x18007fbd5  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007fbda  cmp     [rsi+48h], bl
0x18007fbdd  jz      loc_180080342
0x18007fbe3  mov     [rsp+248h+var_200], bl
0x18007fbe7  cmp     [rsi+58h], bl
0x18007fbea  jz      loc_180080342
0x18007fbf0  mov     r9, [rsi+40h]; unsigned __int16 *
0x18007fbf4  mov     r8, [rsi+50h]; unsigned __int16 *
0x18007fbf8  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x18007fbff  lea     rcx, [rsp+248h+var_1F0]; this
0x18007fc04  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18007fc09  nop
0x18007fc0a  mov     [rsp+248h+var_1F8], rbx
0x18007fc0f  lea     rax, [rsp+248h+var_1F8]
0x18007fc14  mov     [rsp+248h+var_218], rax
0x18007fc19  mov     [rsp+248h+var_220], ebx
0x18007fc1d  mov     [rsp+248h+var_228], 1Dh
0x18007fc25  lea     r9, ?MDM_Policy_Config01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_DeliveryOptimization02_NodeList
0x18007fc2c  mov     r8, [rsi+40h]
0x18007fc30  mov     rdx, [rsi+50h]
0x18007fc34  mov     rcx, r15
0x18007fc37  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18007fc3c  mov     r14d, eax
0x18007fc3f  test    eax, eax
0x18007fc41  jz      short loc_18007FC48
0x18007fc43  jmp     loc_180080348
0x18007fc48  lea     rax, [rsp+248h+var_1F8]
0x18007fc4d  mov     [rsp+248h+var_1D0], rax
0x18007fc52  mov     r12d, 1
0x18007fc58  mov     [rsp+248h+var_1C8], r12b
0x18007fc60  mov     rdi, [rsp+248h+var_1F8]
0x18007fc65  test    rdi, rdi
0x18007fc68  jnz     short loc_18007FC72
0x18007fc6a  mov     r14d, r12d
0x18007fc6d  jmp     loc_180080348
0x18007fc72  mov     r9d, 1Dh; unsigned int
0x18007fc78  lea     r8, ?MDM_Policy_Config01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18007fc7f  mov     rdx, rsi; struct _MI_Instance *
0x18007fc82  mov     rcx, rdi; this
0x18007fc85  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18007fc8a  mov     rax, [rdi]
0x18007fc8d  mov     rcx, rdi
0x18007fc90  mov     rax, [rax+10h]
0x18007fc94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fc99  mov     r14d, eax
0x18007fc9c  test    eax, eax
0x18007fc9e  jz      short loc_18007FCBE
0x18007fca0  mov     rcx, [rsp+248h+var_1F8]
0x18007fca5  test    rcx, rcx
0x18007fca8  jz      short loc_18007FCB9
0x18007fcaa  mov     rax, [rcx]
0x18007fcad  mov     edx, r12d
0x18007fcb0  mov     rax, [rax]
0x18007fcb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fcb8  nop
0x18007fcb9  jmp     loc_180080348
0x18007fcbe  mov     rax, [rdi]
0x18007fcc1  mov     rcx, rdi
0x18007fcc4  mov     rax, [rax+8]
0x18007fcc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fccd  mov     r14d, eax
0x18007fcd0  test    eax, eax
0x18007fcd2  jz      short loc_18007FCF2
0x18007fcd4  mov     rcx, [rsp+248h+var_1F8]
0x18007fcd9  test    rcx, rcx
0x18007fcdc  jz      short loc_18007FCED
0x18007fcde  mov     rax, [rcx]
0x18007fce1  mov     edx, r12d
0x18007fce4  mov     rax, [rax]
0x18007fce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fcec  nop
0x18007fced  jmp     loc_180080348
0x18007fcf2  lea     r8, [rsp+248h+instance]; instance
0x18007fcfa  lea     rdx, MDM_Policy_Config01_DeliveryOptimization02_rtti; classDecl
0x18007fd01  mov     rcx, r15; context
0x18007fd04  call    MI_Context_ConstructInstance
0x18007fd09  mov     r14d, eax
0x18007fd0c  test    eax, eax
0x18007fd0e  jz      short loc_18007FD2E
0x18007fd10  mov     rcx, [rsp+248h+var_1F8]
0x18007fd15  test    rcx, rcx
0x18007fd18  jz      short loc_18007FD29
0x18007fd1a  mov     rax, [rcx]
0x18007fd1d  mov     edx, r12d
0x18007fd20  mov     rax, [rax]
0x18007fd23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fd28  nop
0x18007fd29  jmp     loc_180080348
0x18007fd2e  mov     [rsp+248h+var_200], r12b
0x18007fd33  mov     rdx, [rsi+40h]
0x18007fd37  lea     rcx, [rsp+248h+instance]
0x18007fd3f  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18007fd44  mov     rdx, [rsi+50h]
0x18007fd48  lea     rcx, [rsp+248h+instance]
0x18007fd50  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18007fd55  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007fd5a  lea     rdx, aDoabsolutemaxc; "DOAbsoluteMaxCacheSize"
0x18007fd61  mov     rcx, rdi; this
0x18007fd64  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007fd69  test    eax, eax
0x18007fd6b  jnz     short loc_18007FD8C
0x18007fd6d  mov     rcx, [rsp+248h+String]; String
0x18007fd72  test    rcx, rcx
0x18007fd75  jz      short loc_18007FD8C
0x18007fd77  call    cs:__imp__wtoi
0x18007fd7d  mov     [rsp+248h+var_138], eax
0x18007fd84  mov     [rsp+248h+var_134], r12b
0x18007fd8c  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007fd91  lea     rdx, aDoallowvpnpeer; "DOAllowVPNPeerCaching"
0x18007fd98  mov     rcx, rdi; this
0x18007fd9b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007fda0  test    eax, eax
0x18007fda2  jnz     short loc_18007FDC3
0x18007fda4  mov     rcx, [rsp+248h+String]; String
0x18007fda9  test    rcx, rcx
0x18007fdac  jz      short loc_18007FDC3
0x18007fdae  call    cs:__imp__wtoi
0x18007fdb4  mov     [rsp+248h+var_130], eax
0x18007fdbb  mov     [rsp+248h+var_12C], r12b
0x18007fdc3  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007fdc8  lea     rdx, aDocachehost; "DOCacheHost"
0x18007fdcf  mov     rcx, rdi; this
0x18007fdd2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007fdd7  test    eax, eax
0x18007fdd9  jnz     short loc_18007FDF2
0x18007fddb  mov     rdx, [rsp+248h+String]
0x18007fde0  test    rdx, rdx
0x18007fde3  jz      short loc_18007FDF2
0x18007fde5  lea     rcx, [rsp+248h+instance]
0x18007fded  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x18007fdf2  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007fdf7  lea     rdx, aDocachehostsou; "DOCacheHostSource"
0x18007fdfe  mov     rcx, rdi; this
0x18007fe01  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007fe06  test    eax, eax
0x18007fe08  jnz     short loc_18007FE29
0x18007fe0a  mov     rcx, [rsp+248h+String]; String
0x18007fe0f  test    rcx, rcx
0x18007fe12  jz      short loc_18007FE29
0x18007fe14  call    cs:__imp__wtoi
0x18007fe1a  mov     [rsp+248h+var_118], eax
0x18007fe21  mov     [rsp+248h+var_114], r12b
0x18007fe29  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007fe2e  lea     rdx, aDodelaybackgro; "DODelayBackgroundDownloadFromHttp"
0x18007fe35  mov     rcx, rdi; this
0x18007fe38  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007fe3d  test    eax, eax
0x18007fe3f  jnz     short loc_18007FE60
0x18007fe41  mov     rcx, [rsp+248h+String]; String
0x18007fe46  test    rcx, rcx
0x18007fe49  jz      short loc_18007FE60
0x18007fe4b  call    cs:__imp__wtoi
0x18007fe51  mov     [rsp+248h+var_110], eax
0x18007fe58  mov     [rsp+248h+var_10C], r12b
0x18007fe60  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007fe65  lea     rdx, aDodelaycachese; "DODelayCacheServerFallbackBackground"
0x18007fe6c  mov     rcx, rdi; this
0x18007fe6f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007fe74  test    eax, eax
0x18007fe76  jnz     short loc_18007FE97
0x18007fe78  mov     rcx, [rsp+248h+String]; String
0x18007fe7d  test    rcx, rcx
0x18007fe80  jz      short loc_18007FE97
0x18007fe82  call    cs:__imp__wtoi
0x18007fe88  mov     [rsp+248h+var_108], eax
0x18007fe8f  mov     [rsp+248h+var_104], r12b
0x18007fe97  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007fe9c  lea     rdx, aDodelaycachese_0; "DODelayCacheServerFallbackForeground"
0x18007fea3  mov     rcx, rdi; this
0x18007fea6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007feab  test    eax, eax
0x18007fead  jnz     short loc_18007FECE
0x18007feaf  mov     rcx, [rsp+248h+String]; String
0x18007feb4  test    rcx, rcx
0x18007feb7  jz      short loc_18007FECE
0x18007feb9  call    cs:__imp__wtoi
0x18007febf  mov     [rsp+248h+var_100], eax
0x18007fec6  mov     [rsp+248h+var_FC], r12b
0x18007fece  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007fed3  lea     rdx, aDodelayforegro; "DODelayForegroundDownloadFromHttp"
0x18007feda  mov     rcx, rdi; this
0x18007fedd  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007fee2  test    eax, eax
0x18007fee4  jnz     short loc_18007FF05
0x18007fee6  mov     rcx, [rsp+248h+String]; String
0x18007feeb  test    rcx, rcx
0x18007feee  jz      short loc_18007FF05
0x18007fef0  call    cs:__imp__wtoi
0x18007fef6  mov     [rsp+248h+var_F8], eax
0x18007fefd  mov     [rsp+248h+var_F4], r12b
0x18007ff05  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007ff0a  lea     rdx, aDodownloadmode; "DODownloadMode"
0x18007ff11  mov     rcx, rdi; this
0x18007ff14  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007ff19  test    eax, eax
0x18007ff1b  jnz     short loc_18007FF3C
0x18007ff1d  mov     rcx, [rsp+248h+String]; String
0x18007ff22  test    rcx, rcx
0x18007ff25  jz      short loc_18007FF3C
0x18007ff27  call    cs:__imp__wtoi
0x18007ff2d  mov     [rsp+248h+var_F0], eax
0x18007ff34  mov     [rsp+248h+var_EC], r12b
0x18007ff3c  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007ff41  lea     rdx, aDogroupid; "DOGroupId"
0x18007ff48  mov     rcx, rdi; this
0x18007ff4b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007ff50  test    eax, eax
0x18007ff52  jnz     short loc_18007FF6B
0x18007ff54  mov     rdx, [rsp+248h+String]
0x18007ff59  test    rdx, rdx
0x18007ff5c  jz      short loc_18007FF6B
0x18007ff5e  lea     rcx, [rsp+248h+instance]
0x18007ff66  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList
0x18007ff6b  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007ff70  lea     rdx, aDogroupidsourc; "DOGroupIdSource"
0x18007ff77  mov     rcx, rdi; this
0x18007ff7a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007ff7f  test    eax, eax
0x18007ff81  jnz     short loc_18007FFA2
0x18007ff83  mov     rcx, [rsp+248h+String]; String
0x18007ff88  test    rcx, rcx
0x18007ff8b  jz      short loc_18007FFA2
0x18007ff8d  call    cs:__imp__wtoi
0x18007ff93  mov     [rsp+248h+var_D8], eax
0x18007ff9a  mov     [rsp+248h+var_D4], r12b
0x18007ffa2  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007ffa7  lea     rdx, aDomaxbackgroun; "DOMaxBackgroundDownloadBandwidth"
0x18007ffae  mov     rcx, rdi; this
0x18007ffb1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007ffb6  test    eax, eax
0x18007ffb8  jnz     short loc_18007FFD9
0x18007ffba  mov     rcx, [rsp+248h+String]; String
0x18007ffbf  test    rcx, rcx
0x18007ffc2  jz      short loc_18007FFD9
0x18007ffc4  call    cs:__imp__wtoi
0x18007ffca  mov     [rsp+248h+var_D0], eax
0x18007ffd1  mov     [rsp+248h+var_CC], r12b
0x18007ffd9  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007ffde  lea     rdx, aDomaxcacheage; "DOMaxCacheAge"
0x18007ffe5  mov     rcx, rdi; this
0x18007ffe8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007ffed  test    eax, eax
0x18007ffef  jnz     short loc_180080010
0x18007fff1  mov     rcx, [rsp+248h+String]; String
0x18007fff6  test    rcx, rcx
0x18007fff9  jz      short loc_180080010
0x18007fffb  call    cs:__imp__wtoi
0x180080001  mov     [rsp+248h+var_C8], eax
  ... truncated ...
```
