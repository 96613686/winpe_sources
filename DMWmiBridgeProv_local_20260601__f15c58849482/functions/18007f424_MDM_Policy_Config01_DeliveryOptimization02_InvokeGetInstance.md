# MDM_Policy_Config01_DeliveryOptimization02_InvokeGetInstance

- ea: `0x18007f424`
- end: `0x18007fdb4`
- name: `MDM_Policy_Config01_DeliveryOptimization02_InvokeGetInstance`
- size: `2448`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting`

## callers

- `0x18007dc00`

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
- `0x18007f424`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18007f6c3`
- `msvcrt!_wtoi` at `0x18007f700`
- `msvcrt!_wtoi` at `0x18007f76c`
- `msvcrt!_wtoi` at `0x18007f7a9`
- `msvcrt!_wtoi` at `0x18007f7e6`
- `msvcrt!_wtoi` at `0x18007f823`
- `msvcrt!_wtoi` at `0x18007f860`
- `msvcrt!_wtoi` at `0x18007f89d`
- `msvcrt!_wtoi` at `0x18007f909`
- `msvcrt!_wtoi` at `0x18007f946`
- `msvcrt!_wtoi` at `0x18007f983`
- `msvcrt!_wtoi` at `0x18007f9c0`
- `msvcrt!_wtoi` at `0x18007f9fd`
- `msvcrt!_wtoi` at `0x18007fa3a`
- `msvcrt!_wtoi` at `0x18007fa77`
- `msvcrt!_wtoi` at `0x18007fab4`
- `msvcrt!_wtoi` at `0x18007faf1`
- `msvcrt!_wtoi` at `0x18007fb2e`
- `msvcrt!_wtoi` at `0x18007fb9a`
- `msvcrt!_wtoi` at `0x18007fbd7`
- `msvcrt!_wtoi` at `0x18007fc14`
- `msvcrt!_wtoi` at `0x18007fc51`
- `msvcrt!_wtoi` at `0x18007f6c3`
- `msvcrt!_wtoi` at `0x18007f700`
- `msvcrt!_wtoi` at `0x18007f76c`
- `msvcrt!_wtoi` at `0x18007f7a9`
- `msvcrt!_wtoi` at `0x18007f7e6`
- `msvcrt!_wtoi` at `0x18007f823`
- `msvcrt!_wtoi` at `0x18007f860`
- `msvcrt!_wtoi` at `0x18007f89d`
- `msvcrt!_wtoi` at `0x18007f909`
- `msvcrt!_wtoi` at `0x18007f946`
- `msvcrt!_wtoi` at `0x18007f983`
- `msvcrt!_wtoi` at `0x18007f9c0`
- `msvcrt!_wtoi` at `0x18007f9fd`
- `msvcrt!_wtoi` at `0x18007fa3a`
- `msvcrt!_wtoi` at `0x18007fa77`
- `msvcrt!_wtoi` at `0x18007fab4`
- `msvcrt!_wtoi` at `0x18007faf1`
- `msvcrt!_wtoi` at `0x18007fb2e`
- `msvcrt!_wtoi` at `0x18007fb9a`
- `msvcrt!_wtoi` at `0x18007fbd7`
- `msvcrt!_wtoi` at `0x18007fc14`
- `msvcrt!_wtoi` at `0x18007fc51`

## string_xrefs

- `0x18007f6a6`: `DOAbsoluteMaxCacheSize`
- `0x18007f720`: `DOCacheHost`
- `0x18007f74f`: `DOCacheHostSource`
- `0x18007f7c9`: `DODelayCacheServerFallbackBackground`
- `0x18007f806`: `DODelayCacheServerFallbackForeground`
- `0x18007f966`: `DOMaxCacheAge`
- `0x18007f9a3`: `DOMaxCacheSize`
- `0x18007fad4`: `DOMinFileSizeToCache`
- `0x18007fb4e`: `DOModifyCacheDrive`
- `0x18007f493`: `MDM_Policy_Config01_DeliveryOptimization02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_DeliveryOptimization02_InvokeGetInstance(
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
    v5 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_110;
  }
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
                       &MDM_Policy_Config01_DeliveryOptimization02_NodeList,
                       29,
                       0,
                       &v10);
  if ( v5 == MI_RESULT_OK )
  {
    v11[4] = &v10;
    v12 = 1;
    v6 = v10;
    if ( !v10 )
    {
      v5 = MI_RESULT_FAILED;
      goto LABEL_110;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_DeliveryOptimization02_NodeList,
      0x1Du);
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_110;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_110;
    }
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DOAbsoluteMaxCacheSize", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DOAllowVPNPeerCaching", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DOCacheHostSource", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DOMinBackgroundQos", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DOMinDiskSizeAllowedToPeer", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v48 = _wtoi(String);
      v49 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DOMinFileSizeToCache", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v50 = _wtoi(String);
      v51 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DOMinRAMAllowedToPeer", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v52 = _wtoi(String);
      v53 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DOModifyCacheDrive", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DOMonthlyUploadDataCap", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DORestrictPeerSelectionBy", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007f424  mov     [rsp+arg_10], rbx
0x18007f429  push    rsi
0x18007f42a  push    rdi
0x18007f42b  push    r12
0x18007f42d  push    r14
0x18007f42f  push    r15
0x18007f431  sub     rsp, 220h
0x18007f438  mov     rax, cs:__security_cookie
0x18007f43f  xor     rax, rsp
0x18007f442  mov     [rsp+248h+var_38], rax
0x18007f44a  mov     rsi, rdx
0x18007f44d  mov     r15, rcx
0x18007f450  xor     ebx, ebx
0x18007f452  mov     [rsp+248h+String], rbx
0x18007f457  xor     edx, edx; Val
0x18007f459  mov     r8d, 160h; Size
0x18007f45f  lea     rcx, [rsp+248h+instance]; void *
0x18007f467  call    memset_0
0x18007f46c  mov     [rsp+248h+var_1C0], ebx
0x18007f473  mov     [rsp+248h+var_1BC], bl
0x18007f47a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18007f481  mov     [rsp+248h+var_1F0], rax
0x18007f486  lea     rax, [rsp+248h+var_1C0]
0x18007f48e  mov     [rsp+248h+var_1E8], rax
0x18007f493  lea     rax, aMdmPolicyConfi_34; "MDM_Policy_Config01_DeliveryOptimizatio"...
0x18007f49a  mov     [rsp+248h+var_1E0], rax
0x18007f49f  lea     rcx, [rsp+248h+var_1C0]
0x18007f4a7  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007f4ac  mov     eax, cs:dword_180380B68
0x18007f4b2  cmp     eax, 5
0x18007f4b5  jbe     short loc_18007F526
0x18007f4b7  mov     rdx, 200000000000h
0x18007f4c1  lea     rcx, dword_180380B68
0x18007f4c8  call    _tlgKeywordOn
0x18007f4cd  test    al, al
0x18007f4cf  jz      short loc_18007F526
0x18007f4d1  cmp     [rsp+248h+var_1BC], bl
0x18007f4d8  jz      short loc_18007F508
0x18007f4da  cmp     [rsp+248h+var_1A8], ebx
0x18007f4e1  jnz     short loc_18007F4FE
0x18007f4e3  cmp     [rsp+248h+var_1A4], ebx
0x18007f4ea  jnz     short loc_18007F4FE
0x18007f4ec  cmp     [rsp+248h+var_1A0], ebx
0x18007f4f3  jnz     short loc_18007F4FE
0x18007f4f5  cmp     [rsp+248h+var_19C], ebx
0x18007f4fc  jz      short loc_18007F508
0x18007f4fe  lea     r9, [rsp+248h+var_1A8]
0x18007f506  jmp     short loc_18007F50B
0x18007f508  mov     r9, rbx
0x18007f50b  lea     r8, [rsp+248h+var_1B8]
0x18007f513  lea     rdx, word_180363C2E
0x18007f51a  lea     rcx, dword_180380B68
0x18007f521  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007f526  cmp     [rsi+48h], bl
0x18007f529  jz      loc_18007FD12
0x18007f52f  mov     [rsp+248h+var_200], bl
0x18007f533  cmp     [rsi+58h], bl
0x18007f536  jz      loc_18007FD12
0x18007f53c  mov     r9, [rsi+40h]; unsigned __int16 *
0x18007f540  mov     r8, [rsi+50h]; unsigned __int16 *
0x18007f544  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x18007f54b  lea     rcx, [rsp+248h+var_1F0]; this
0x18007f550  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18007f555  nop
0x18007f556  mov     [rsp+248h+var_1F8], rbx
0x18007f55b  lea     rax, [rsp+248h+var_1F8]
0x18007f560  mov     [rsp+248h+var_218], rax
0x18007f565  mov     [rsp+248h+var_220], ebx
0x18007f569  mov     [rsp+248h+var_228], 1Dh
0x18007f571  lea     r9, ?MDM_Policy_Config01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_DeliveryOptimization02_NodeList
0x18007f578  mov     r8, [rsi+40h]
0x18007f57c  mov     rdx, [rsi+50h]
0x18007f580  mov     rcx, r15
0x18007f583  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18007f588  mov     r14d, eax
0x18007f58b  test    eax, eax
0x18007f58d  jz      short loc_18007F594
0x18007f58f  jmp     loc_18007FD18
0x18007f594  lea     rax, [rsp+248h+var_1F8]
0x18007f599  mov     [rsp+248h+var_1D0], rax
0x18007f59e  mov     r12d, 1
0x18007f5a4  mov     [rsp+248h+var_1C8], r12b
0x18007f5ac  mov     rdi, [rsp+248h+var_1F8]
0x18007f5b1  test    rdi, rdi
0x18007f5b4  jnz     short loc_18007F5BE
0x18007f5b6  mov     r14d, r12d
0x18007f5b9  jmp     loc_18007FD18
0x18007f5be  mov     r9d, 1Dh; unsigned int
0x18007f5c4  lea     r8, ?MDM_Policy_Config01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18007f5cb  mov     rdx, rsi; struct _MI_Instance *
0x18007f5ce  mov     rcx, rdi; this
0x18007f5d1  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18007f5d6  mov     rax, [rdi]
0x18007f5d9  mov     rcx, rdi
0x18007f5dc  mov     rax, [rax+10h]
0x18007f5e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f5e5  mov     r14d, eax
0x18007f5e8  test    eax, eax
0x18007f5ea  jz      short loc_18007F60A
0x18007f5ec  mov     rcx, [rsp+248h+var_1F8]
0x18007f5f1  test    rcx, rcx
0x18007f5f4  jz      short loc_18007F605
0x18007f5f6  mov     rax, [rcx]
0x18007f5f9  mov     edx, r12d
0x18007f5fc  mov     rax, [rax]
0x18007f5ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f604  nop
0x18007f605  jmp     loc_18007FD18
0x18007f60a  mov     rax, [rdi]
0x18007f60d  mov     rcx, rdi
0x18007f610  mov     rax, [rax+8]
0x18007f614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f619  mov     r14d, eax
0x18007f61c  test    eax, eax
0x18007f61e  jz      short loc_18007F63E
0x18007f620  mov     rcx, [rsp+248h+var_1F8]
0x18007f625  test    rcx, rcx
0x18007f628  jz      short loc_18007F639
0x18007f62a  mov     rax, [rcx]
0x18007f62d  mov     edx, r12d
0x18007f630  mov     rax, [rax]
0x18007f633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f638  nop
0x18007f639  jmp     loc_18007FD18
0x18007f63e  lea     r8, [rsp+248h+instance]; instance
0x18007f646  lea     rdx, MDM_Policy_Config01_DeliveryOptimization02_rtti; classDecl
0x18007f64d  mov     rcx, r15; context
0x18007f650  call    MI_Context_ConstructInstance
0x18007f655  mov     r14d, eax
0x18007f658  test    eax, eax
0x18007f65a  jz      short loc_18007F67A
0x18007f65c  mov     rcx, [rsp+248h+var_1F8]
0x18007f661  test    rcx, rcx
0x18007f664  jz      short loc_18007F675
0x18007f666  mov     rax, [rcx]
0x18007f669  mov     edx, r12d
0x18007f66c  mov     rax, [rax]
0x18007f66f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f674  nop
0x18007f675  jmp     loc_18007FD18
0x18007f67a  mov     [rsp+248h+var_200], r12b
0x18007f67f  mov     rdx, [rsi+40h]
0x18007f683  lea     rcx, [rsp+248h+instance]
0x18007f68b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18007f690  mov     rdx, [rsi+50h]
0x18007f694  lea     rcx, [rsp+248h+instance]
0x18007f69c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18007f6a1  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007f6a6  lea     rdx, aDoabsolutemaxc; "DOAbsoluteMaxCacheSize"
0x18007f6ad  mov     rcx, rdi; this
0x18007f6b0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007f6b5  test    eax, eax
0x18007f6b7  jnz     short loc_18007F6DE
0x18007f6b9  mov     rcx, [rsp+248h+String]; String
0x18007f6be  test    rcx, rcx
0x18007f6c1  jz      short loc_18007F6DE
0x18007f6c3  call    cs:__imp__wtoi
0x18007f6ca  nop     dword ptr [rax+rax+00h]
0x18007f6cf  mov     [rsp+248h+var_138], eax
0x18007f6d6  mov     [rsp+248h+var_134], r12b
0x18007f6de  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007f6e3  lea     rdx, aDoallowvpnpeer; "DOAllowVPNPeerCaching"
0x18007f6ea  mov     rcx, rdi; this
0x18007f6ed  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007f6f2  test    eax, eax
0x18007f6f4  jnz     short loc_18007F71B
0x18007f6f6  mov     rcx, [rsp+248h+String]; String
0x18007f6fb  test    rcx, rcx
0x18007f6fe  jz      short loc_18007F71B
0x18007f700  call    cs:__imp__wtoi
0x18007f707  nop     dword ptr [rax+rax+00h]
0x18007f70c  mov     [rsp+248h+var_130], eax
0x18007f713  mov     [rsp+248h+var_12C], r12b
0x18007f71b  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007f720  lea     rdx, aDocachehost; "DOCacheHost"
0x18007f727  mov     rcx, rdi; this
0x18007f72a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007f72f  test    eax, eax
0x18007f731  jnz     short loc_18007F74A
0x18007f733  mov     rdx, [rsp+248h+String]
0x18007f738  test    rdx, rdx
0x18007f73b  jz      short loc_18007F74A
0x18007f73d  lea     rcx, [rsp+248h+instance]
0x18007f745  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x18007f74a  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007f74f  lea     rdx, aDocachehostsou; "DOCacheHostSource"
0x18007f756  mov     rcx, rdi; this
0x18007f759  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007f75e  test    eax, eax
0x18007f760  jnz     short loc_18007F787
0x18007f762  mov     rcx, [rsp+248h+String]; String
0x18007f767  test    rcx, rcx
0x18007f76a  jz      short loc_18007F787
0x18007f76c  call    cs:__imp__wtoi
0x18007f773  nop     dword ptr [rax+rax+00h]
0x18007f778  mov     [rsp+248h+var_118], eax
0x18007f77f  mov     [rsp+248h+var_114], r12b
0x18007f787  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007f78c  lea     rdx, aDodelaybackgro; "DODelayBackgroundDownloadFromHttp"
0x18007f793  mov     rcx, rdi; this
0x18007f796  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007f79b  test    eax, eax
0x18007f79d  jnz     short loc_18007F7C4
0x18007f79f  mov     rcx, [rsp+248h+String]; String
0x18007f7a4  test    rcx, rcx
0x18007f7a7  jz      short loc_18007F7C4
0x18007f7a9  call    cs:__imp__wtoi
0x18007f7b0  nop     dword ptr [rax+rax+00h]
0x18007f7b5  mov     [rsp+248h+var_110], eax
0x18007f7bc  mov     [rsp+248h+var_10C], r12b
0x18007f7c4  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007f7c9  lea     rdx, aDodelaycachese; "DODelayCacheServerFallbackBackground"
0x18007f7d0  mov     rcx, rdi; this
0x18007f7d3  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007f7d8  test    eax, eax
0x18007f7da  jnz     short loc_18007F801
0x18007f7dc  mov     rcx, [rsp+248h+String]; String
0x18007f7e1  test    rcx, rcx
0x18007f7e4  jz      short loc_18007F801
0x18007f7e6  call    cs:__imp__wtoi
0x18007f7ed  nop     dword ptr [rax+rax+00h]
0x18007f7f2  mov     [rsp+248h+var_108], eax
0x18007f7f9  mov     [rsp+248h+var_104], r12b
0x18007f801  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007f806  lea     rdx, aDodelaycachese_0; "DODelayCacheServerFallbackForeground"
0x18007f80d  mov     rcx, rdi; this
0x18007f810  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007f815  test    eax, eax
0x18007f817  jnz     short loc_18007F83E
0x18007f819  mov     rcx, [rsp+248h+String]; String
0x18007f81e  test    rcx, rcx
0x18007f821  jz      short loc_18007F83E
0x18007f823  call    cs:__imp__wtoi
0x18007f82a  nop     dword ptr [rax+rax+00h]
0x18007f82f  mov     [rsp+248h+var_100], eax
0x18007f836  mov     [rsp+248h+var_FC], r12b
0x18007f83e  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007f843  lea     rdx, aDodelayforegro; "DODelayForegroundDownloadFromHttp"
0x18007f84a  mov     rcx, rdi; this
0x18007f84d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007f852  test    eax, eax
0x18007f854  jnz     short loc_18007F87B
0x18007f856  mov     rcx, [rsp+248h+String]; String
0x18007f85b  test    rcx, rcx
0x18007f85e  jz      short loc_18007F87B
0x18007f860  call    cs:__imp__wtoi
0x18007f867  nop     dword ptr [rax+rax+00h]
0x18007f86c  mov     [rsp+248h+var_F8], eax
0x18007f873  mov     [rsp+248h+var_F4], r12b
0x18007f87b  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007f880  lea     rdx, aDodownloadmode; "DODownloadMode"
0x18007f887  mov     rcx, rdi; this
0x18007f88a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007f88f  test    eax, eax
0x18007f891  jnz     short loc_18007F8B8
0x18007f893  mov     rcx, [rsp+248h+String]; String
0x18007f898  test    rcx, rcx
0x18007f89b  jz      short loc_18007F8B8
0x18007f89d  call    cs:__imp__wtoi
0x18007f8a4  nop     dword ptr [rax+rax+00h]
0x18007f8a9  mov     [rsp+248h+var_F0], eax
0x18007f8b0  mov     [rsp+248h+var_EC], r12b
0x18007f8b8  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007f8bd  lea     rdx, aDogroupid; "DOGroupId"
0x18007f8c4  mov     rcx, rdi; this
0x18007f8c7  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007f8cc  test    eax, eax
0x18007f8ce  jnz     short loc_18007F8E7
0x18007f8d0  mov     rdx, [rsp+248h+String]
0x18007f8d5  test    rdx, rdx
0x18007f8d8  jz      short loc_18007F8E7
0x18007f8da  lea     rcx, [rsp+248h+instance]
0x18007f8e2  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList
0x18007f8e7  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007f8ec  lea     rdx, aDogroupidsourc; "DOGroupIdSource"
0x18007f8f3  mov     rcx, rdi; this
0x18007f8f6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007f8fb  test    eax, eax
0x18007f8fd  jnz     short loc_18007F924
0x18007f8ff  mov     rcx, [rsp+248h+String]; String
0x18007f904  test    rcx, rcx
0x18007f907  jz      short loc_18007F924
0x18007f909  call    cs:__imp__wtoi
0x18007f910  nop     dword ptr [rax+rax+00h]
0x18007f915  mov     [rsp+248h+var_D8], eax
0x18007f91c  mov     [rsp+248h+var_D4], r12b
0x18007f924  lea     r8, [rsp+248h+String]; unsigned __int16 **
0x18007f929  lea     rdx, aDomaxbackgroun; "DOMaxBackgroundDownloadBandwidth"
0x18007f930  mov     rcx, rdi; this
0x18007f933  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007f938  test    eax, eax
0x18007f93a  jnz     short loc_18007F961
0x18007f93c  mov     rcx, [rsp+248h+String]; String
0x18007f941  test    rcx, rcx
0x18007f944  jz      short loc_18007F961
0x18007f946  call    cs:__imp__wtoi
0x18007f94d  nop     dword ptr [rax+rax+00h]
0x18007f952  mov     [rsp+248h+var_D0], eax
0x18007f959  mov     [rsp+248h+var_CC], r12b
0x18007f961  lea     r8, [rsp+248h+String]; unsigned __int16 **
  ... truncated ...
```
