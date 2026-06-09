# MDM_Policy_Config01_DeliveryOptimization02_InvokeCreateInstance

- ea: `0x18007e36c`
- end: `0x18007ed8e`
- name: `MDM_Policy_Config01_DeliveryOptimization02_InvokeCreateInstance`
- size: `2594`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting`

## callers

- `0x18007e270`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18007e36c`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x18007e535`: `DOAbsoluteMaxCacheSize`
- `0x18007e5af`: `DOCacheHost`
- `0x18007e5ef`: `DOCacheHostSource`
- `0x18007e66f`: `DODelayCacheServerFallbackBackground`
- `0x18007e6af`: `DODelayCacheServerFallbackForeground`
- `0x18007e82f`: `DOMaxCacheAge`
- `0x18007e86f`: `DOMaxCacheSize`
- `0x18007e9af`: `DOMinFileSizeToCache`
- `0x18007ea2f`: `DOModifyCacheDrive`
- `0x18007e495`: `CreateInstanceStart`
- `0x18007ecf5`: `CreateInstanceEnd`
- `0x18007e3dc`: `MDM_Policy_Config01_DeliveryOptimization02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_DeliveryOptimization02_InvokeCreateInstance(
        MI_Context *self,
        struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-1F8h] BYREF
  char v9; // [rsp+48h] [rbp-1F0h]
  _QWORD v10[5]; // [rsp+50h] [rbp-1E8h] BYREF
  char v11; // [rsp+78h] [rbp-1C0h]
  int v12; // [rsp+80h] [rbp-1B8h] BYREF
  char v13; // [rsp+84h] [rbp-1B4h]
  _BYTE v14[16]; // [rsp+88h] [rbp-1B0h] BYREF
  _DWORD v15[6]; // [rsp+98h] [rbp-1A0h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-188h] BYREF

  memset_0(&instance, 0, 0x160u);
  v12 = 0;
  v13 = 0;
  v10[0] = &TelemetryEventWriter::`vftable';
  v10[1] = &v12;
  v10[2] = "MDM_Policy_Config01_DeliveryOptimization02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_180354924,
      v14,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    inserted = 4;
    goto LABEL_137;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v10,
    "CreateInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v8 = 0;
  inserted = CreateRequestHandlerInstance(
               (__int64)self,
               (wchar_t *)a2[1].serverName,
               (const unsigned __int16 *)a2[1].ft,
               (struct WmiNodeInfo *)&MDM_Policy_Config01_DeliveryOptimization02_NodeList,
               0x1Du,
               4,
               &v8);
  if ( !inserted )
  {
    v10[4] = &v8;
    v11 = 1;
    v6 = v8;
    if ( !v8 )
    {
      inserted = 1;
      goto LABEL_137;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v8,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_DeliveryOptimization02_NodeList,
      0x1Du);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOAbsoluteMaxCacheSize", (LONG *)a2[1].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
LABEL_132:
        (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        goto LABEL_137;
      }
    }
    if ( BYTE4(a2[1].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOAllowVPNPeerCaching", (LONG *)&a2[1].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( LOBYTE(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOCacheHost", (LONG *)&a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[2].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOCacheHostSource", (LONG *)&a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DODelayBackgroundDownloadFromHttp",
                   (LONG *)&a2[2].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[2].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DODelayCacheServerFallbackBackground",
                   (LONG *)&a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DODelayCacheServerFallbackForeground",
                   (LONG *)&a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DODelayForegroundDownloadFromHttp",
                   (LONG *)a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DODownloadMode", (LONG *)&a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( LOBYTE(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOGroupId", (LONG *)&a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOGroupIdSource", (LONG *)&a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[3].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DOMaxBackgroundDownloadBandwidth",
                   (LONG *)&a2[3].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[3].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMaxCacheAge", (LONG *)&a2[3].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[3].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMaxCacheSize", (LONG *)&a2[3].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[3].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DOMaxForegroundDownloadBandwidth",
                   (LONG *)a2[3].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[3].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMinBackgroundQos", (LONG *)&a2[3].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[3].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DOMinBatteryPercentageAllowedToUpload",
                   (LONG *)&a2[3].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[3].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMinDiskSizeAllowedToPeer", (LONG *)&a2[3].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMinFileSizeToCache", (LONG *)&a2[4]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[4].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMinRAMAllowedToPeer", (LONG *)&a2[4].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( LOBYTE(a2[4].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOModifyCacheDrive", (LONG *)&a2[4].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[4].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMonthlyUploadDataCap", (LONG *)a2[4].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[4].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DOPercentageMaxBackgroundBandwidth",
                   (LONG *)&a2[4].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[4].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DOPercentageMaxForegroundBandwidth",
                   (LONG *)&a2[4].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DORestrictPeerSelectionBy", (LONG *)&a2[4].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( LOBYTE(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DOSetHoursToLimitBackgroundDownloadBandwidth",
                   (LONG *)&a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( LOBYTE(a2[5].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"DOSetHoursToLimitForegroundDownloadBandwidth",
                   (LONG *)&a2[5].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_137;
      goto LABEL_132;
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_137;
      goto LABEL_132;
    }
    inserted = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_DeliveryOptimization02_rtti, &instance);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_137;
      goto LABEL_132;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v8 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_137:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "CreateInstanceEnd", inserted);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18036F899,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return inserted;
}

```

## disassembly

```asm
0x18007e36c  mov     [rsp+arg_10], rsi
0x18007e371  mov     [rsp+arg_18], rdi
0x18007e376  push    r12
0x18007e378  push    r14
0x18007e37a  push    r15
0x18007e37c  sub     rsp, 220h
0x18007e383  mov     rax, cs:__security_cookie
0x18007e38a  xor     rax, rsp
0x18007e38d  mov     [rsp+238h+var_28], rax
0x18007e395  mov     rsi, rdx
0x18007e398  mov     r15, rcx
0x18007e39b  xor     edx, edx; Val
0x18007e39d  mov     r8d, 160h; Size
0x18007e3a3  lea     rcx, [rsp+238h+instance]; void *
0x18007e3ab  call    memset_0
0x18007e3b0  mov     [rsp+238h+var_1B8], 0
0x18007e3bb  mov     [rsp+238h+var_1B4], 0
0x18007e3c3  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18007e3ca  mov     [rsp+238h+var_1E8], rax
0x18007e3cf  lea     rax, [rsp+238h+var_1B8]
0x18007e3d7  mov     [rsp+238h+var_1E0], rax
0x18007e3dc  lea     rax, aMdmPolicyConfi_34; "MDM_Policy_Config01_DeliveryOptimizatio"...
0x18007e3e3  mov     [rsp+238h+var_1D8], rax
0x18007e3e8  lea     rcx, [rsp+238h+var_1B8]
0x18007e3f0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007e3f5  mov     eax, cs:dword_180380B68
0x18007e3fb  cmp     eax, 5
0x18007e3fe  jbe     short loc_18007E474
0x18007e400  mov     rdx, 200000000000h
0x18007e40a  lea     rcx, dword_180380B68
0x18007e411  call    _tlgKeywordOn
0x18007e416  test    al, al
0x18007e418  jz      short loc_18007E474
0x18007e41a  cmp     [rsp+238h+var_1B4], 0
0x18007e422  jz      short loc_18007E456
0x18007e424  cmp     [rsp+238h+var_1A0], 0
0x18007e42c  jnz     short loc_18007E44C
0x18007e42e  cmp     [rsp+238h+var_19C], 0
0x18007e436  jnz     short loc_18007E44C
0x18007e438  cmp     [rsp+238h+var_198], 0
0x18007e440  jnz     short loc_18007E44C
0x18007e442  cmp     [rsp+238h+var_194], 0
0x18007e44a  jz      short loc_18007E456
0x18007e44c  lea     r9, [rsp+238h+var_1A0]
0x18007e454  jmp     short loc_18007E459
0x18007e456  xor     r9d, r9d
0x18007e459  lea     r8, [rsp+238h+var_1B0]
0x18007e461  lea     rdx, dword_180354924
0x18007e468  lea     rcx, dword_180380B68
0x18007e46f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007e474  cmp     byte ptr [rsi+48h], 0
0x18007e478  jz      loc_18007ECED
0x18007e47e  mov     [rsp+238h+var_1F0], 0
0x18007e483  cmp     byte ptr [rsi+58h], 0
0x18007e487  jz      loc_18007ECED
0x18007e48d  mov     r9, [rsi+40h]; unsigned __int16 *
0x18007e491  mov     r8, [rsi+50h]; unsigned __int16 *
0x18007e495  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x18007e49c  lea     rcx, [rsp+238h+var_1E8]; this
0x18007e4a1  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18007e4a6  nop
0x18007e4a7  mov     [rsp+238h+var_1F8], 0
0x18007e4b0  lea     rax, [rsp+238h+var_1F8]
0x18007e4b5  mov     [rsp+238h+var_208], rax
0x18007e4ba  mov     [rsp+238h+var_210], 4
0x18007e4c2  mov     [rsp+238h+var_218], 1Dh
0x18007e4ca  lea     r9, ?MDM_Policy_Config01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_DeliveryOptimization02_NodeList
0x18007e4d1  mov     r8, [rsi+40h]
0x18007e4d5  mov     rdx, [rsi+50h]
0x18007e4d9  mov     rcx, r15
0x18007e4dc  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18007e4e1  mov     edi, eax
0x18007e4e3  test    eax, eax
0x18007e4e5  jz      short loc_18007E4EC
0x18007e4e7  jmp     loc_18007ECF2
0x18007e4ec  lea     rax, [rsp+238h+var_1F8]
0x18007e4f1  mov     [rsp+238h+var_1C8], rax
0x18007e4f6  mov     r12d, 1
0x18007e4fc  mov     [rsp+238h+var_1C0], r12b
0x18007e501  mov     r14, [rsp+238h+var_1F8]
0x18007e506  test    r14, r14
0x18007e509  jnz     short loc_18007E513
0x18007e50b  mov     edi, r12d
0x18007e50e  jmp     loc_18007ECF2
0x18007e513  mov     r9d, 1Dh; unsigned int
0x18007e519  lea     r8, ?MDM_Policy_Config01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18007e520  mov     rdx, rsi; struct _MI_Instance *
0x18007e523  mov     rcx, r14; this
0x18007e526  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18007e52b  lea     r8, [rsi+60h]; void *
0x18007e52f  cmp     [r8+4], r12b
0x18007e533  jnz     short loc_18007E568
0x18007e535  lea     rdx, aDoabsolutemaxc; "DOAbsoluteMaxCacheSize"
0x18007e53c  mov     rcx, r14; this
0x18007e53f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007e544  mov     edi, eax
0x18007e546  test    eax, eax
0x18007e548  jz      short loc_18007E568
0x18007e54a  mov     rcx, [rsp+238h+var_1F8]
0x18007e54f  test    rcx, rcx
0x18007e552  jz      short loc_18007E563
0x18007e554  mov     rax, [rcx]
0x18007e557  mov     edx, r12d
0x18007e55a  mov     rax, [rax]
0x18007e55d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e562  nop
0x18007e563  jmp     loc_18007ECF2
0x18007e568  lea     r8, [rsi+68h]; void *
0x18007e56c  cmp     [r8+4], r12b
0x18007e570  jnz     short loc_18007E5A5
0x18007e572  lea     rdx, aDoallowvpnpeer; "DOAllowVPNPeerCaching"
0x18007e579  mov     rcx, r14; this
0x18007e57c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007e581  mov     edi, eax
0x18007e583  test    eax, eax
0x18007e585  jz      short loc_18007E5A5
0x18007e587  mov     rcx, [rsp+238h+var_1F8]
0x18007e58c  test    rcx, rcx
0x18007e58f  jz      short loc_18007E5A0
0x18007e591  mov     rax, [rcx]
0x18007e594  mov     edx, r12d
0x18007e597  mov     rax, [rax]
0x18007e59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e59f  nop
0x18007e5a0  jmp     loc_18007ECF2
0x18007e5a5  lea     r8, [rsi+70h]; void *
0x18007e5a9  cmp     [r8+8], r12b
0x18007e5ad  jnz     short loc_18007E5E2
0x18007e5af  lea     rdx, aDocachehost; "DOCacheHost"
0x18007e5b6  mov     rcx, r14; this
0x18007e5b9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007e5be  mov     edi, eax
0x18007e5c0  test    eax, eax
0x18007e5c2  jz      short loc_18007E5E2
0x18007e5c4  mov     rcx, [rsp+238h+var_1F8]
0x18007e5c9  test    rcx, rcx
0x18007e5cc  jz      short loc_18007E5DD
0x18007e5ce  mov     rax, [rcx]
0x18007e5d1  mov     edx, r12d
0x18007e5d4  mov     rax, [rax]
0x18007e5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e5dc  nop
0x18007e5dd  jmp     loc_18007ECF2
0x18007e5e2  lea     r8, [rsi+80h]; void *
0x18007e5e9  cmp     [r8+4], r12b
0x18007e5ed  jnz     short loc_18007E622
0x18007e5ef  lea     rdx, aDocachehostsou; "DOCacheHostSource"
0x18007e5f6  mov     rcx, r14; this
0x18007e5f9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007e5fe  mov     edi, eax
0x18007e600  test    eax, eax
0x18007e602  jz      short loc_18007E622
0x18007e604  mov     rcx, [rsp+238h+var_1F8]
0x18007e609  test    rcx, rcx
0x18007e60c  jz      short loc_18007E61D
0x18007e60e  mov     rax, [rcx]
0x18007e611  mov     edx, r12d
0x18007e614  mov     rax, [rax]
0x18007e617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e61c  nop
0x18007e61d  jmp     loc_18007ECF2
0x18007e622  lea     r8, [rsi+88h]; void *
0x18007e629  cmp     [r8+4], r12b
0x18007e62d  jnz     short loc_18007E662
0x18007e62f  lea     rdx, aDodelaybackgro; "DODelayBackgroundDownloadFromHttp"
0x18007e636  mov     rcx, r14; this
0x18007e639  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007e63e  mov     edi, eax
0x18007e640  test    eax, eax
0x18007e642  jz      short loc_18007E662
0x18007e644  mov     rcx, [rsp+238h+var_1F8]
0x18007e649  test    rcx, rcx
0x18007e64c  jz      short loc_18007E65D
0x18007e64e  mov     rax, [rcx]
0x18007e651  mov     edx, r12d
0x18007e654  mov     rax, [rax]
0x18007e657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e65c  nop
0x18007e65d  jmp     loc_18007ECF2
0x18007e662  lea     r8, [rsi+90h]; void *
0x18007e669  cmp     [r8+4], r12b
0x18007e66d  jnz     short loc_18007E6A2
0x18007e66f  lea     rdx, aDodelaycachese; "DODelayCacheServerFallbackBackground"
0x18007e676  mov     rcx, r14; this
0x18007e679  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007e67e  mov     edi, eax
0x18007e680  test    eax, eax
0x18007e682  jz      short loc_18007E6A2
0x18007e684  mov     rcx, [rsp+238h+var_1F8]
0x18007e689  test    rcx, rcx
0x18007e68c  jz      short loc_18007E69D
0x18007e68e  mov     rax, [rcx]
0x18007e691  mov     edx, r12d
0x18007e694  mov     rax, [rax]
0x18007e697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e69c  nop
0x18007e69d  jmp     loc_18007ECF2
0x18007e6a2  lea     r8, [rsi+98h]; void *
0x18007e6a9  cmp     [r8+4], r12b
0x18007e6ad  jnz     short loc_18007E6E2
0x18007e6af  lea     rdx, aDodelaycachese_0; "DODelayCacheServerFallbackForeground"
0x18007e6b6  mov     rcx, r14; this
0x18007e6b9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007e6be  mov     edi, eax
0x18007e6c0  test    eax, eax
0x18007e6c2  jz      short loc_18007E6E2
0x18007e6c4  mov     rcx, [rsp+238h+var_1F8]
0x18007e6c9  test    rcx, rcx
0x18007e6cc  jz      short loc_18007E6DD
0x18007e6ce  mov     rax, [rcx]
0x18007e6d1  mov     edx, r12d
0x18007e6d4  mov     rax, [rax]
0x18007e6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e6dc  nop
0x18007e6dd  jmp     loc_18007ECF2
0x18007e6e2  lea     r8, [rsi+0A0h]; void *
0x18007e6e9  cmp     [r8+4], r12b
0x18007e6ed  jnz     short loc_18007E722
0x18007e6ef  lea     rdx, aDodelayforegro; "DODelayForegroundDownloadFromHttp"
0x18007e6f6  mov     rcx, r14; this
0x18007e6f9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007e6fe  mov     edi, eax
0x18007e700  test    eax, eax
0x18007e702  jz      short loc_18007E722
0x18007e704  mov     rcx, [rsp+238h+var_1F8]
0x18007e709  test    rcx, rcx
0x18007e70c  jz      short loc_18007E71D
0x18007e70e  mov     rax, [rcx]
0x18007e711  mov     edx, r12d
0x18007e714  mov     rax, [rax]
0x18007e717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e71c  nop
0x18007e71d  jmp     loc_18007ECF2
0x18007e722  lea     r8, [rsi+0A8h]; void *
0x18007e729  cmp     [r8+4], r12b
0x18007e72d  jnz     short loc_18007E762
0x18007e72f  lea     rdx, aDodownloadmode; "DODownloadMode"
0x18007e736  mov     rcx, r14; this
0x18007e739  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007e73e  mov     edi, eax
0x18007e740  test    eax, eax
0x18007e742  jz      short loc_18007E762
0x18007e744  mov     rcx, [rsp+238h+var_1F8]
0x18007e749  test    rcx, rcx
0x18007e74c  jz      short loc_18007E75D
0x18007e74e  mov     rax, [rcx]
0x18007e751  mov     edx, r12d
0x18007e754  mov     rax, [rax]
0x18007e757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e75c  nop
0x18007e75d  jmp     loc_18007ECF2
0x18007e762  lea     r8, [rsi+0B0h]; void *
0x18007e769  cmp     [r8+8], r12b
0x18007e76d  jnz     short loc_18007E7A2
0x18007e76f  lea     rdx, aDogroupid; "DOGroupId"
0x18007e776  mov     rcx, r14; this
0x18007e779  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007e77e  mov     edi, eax
0x18007e780  test    eax, eax
0x18007e782  jz      short loc_18007E7A2
0x18007e784  mov     rcx, [rsp+238h+var_1F8]
0x18007e789  test    rcx, rcx
0x18007e78c  jz      short loc_18007E79D
0x18007e78e  mov     rax, [rcx]
0x18007e791  mov     edx, r12d
0x18007e794  mov     rax, [rax]
0x18007e797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e79c  nop
0x18007e79d  jmp     loc_18007ECF2
0x18007e7a2  lea     r8, [rsi+0C0h]; void *
0x18007e7a9  cmp     [r8+4], r12b
0x18007e7ad  jnz     short loc_18007E7E2
0x18007e7af  lea     rdx, aDogroupidsourc; "DOGroupIdSource"
0x18007e7b6  mov     rcx, r14; this
0x18007e7b9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007e7be  mov     edi, eax
0x18007e7c0  test    eax, eax
0x18007e7c2  jz      short loc_18007E7E2
0x18007e7c4  mov     rcx, [rsp+238h+var_1F8]
0x18007e7c9  test    rcx, rcx
0x18007e7cc  jz      short loc_18007E7DD
0x18007e7ce  mov     rax, [rcx]
0x18007e7d1  mov     edx, r12d
0x18007e7d4  mov     rax, [rax]
0x18007e7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e7dc  nop
0x18007e7dd  jmp     loc_18007ECF2
0x18007e7e2  lea     r8, [rsi+0C8h]; void *
0x18007e7e9  cmp     [r8+4], r12b
0x18007e7ed  jnz     short loc_18007E822
0x18007e7ef  lea     rdx, aDomaxbackgroun; "DOMaxBackgroundDownloadBandwidth"
0x18007e7f6  mov     rcx, r14; this
0x18007e7f9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007e7fe  mov     edi, eax
0x18007e800  test    eax, eax
0x18007e802  jz      short loc_18007E822
0x18007e804  mov     rcx, [rsp+238h+var_1F8]
0x18007e809  test    rcx, rcx
0x18007e80c  jz      short loc_18007E81D
0x18007e80e  mov     rax, [rcx]
  ... truncated ...
```
