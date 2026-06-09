# MDM_Policy_Config01_DeliveryOptimization02_InvokeCreateInstance

- ea: `0x18007dc2c`
- end: `0x18007e64f`
- name: `MDM_Policy_Config01_DeliveryOptimization02_InvokeCreateInstance`
- size: `2595`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting`

## callers

- `0x18007db70`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18007dc2c`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x18007ddf5`: `DOAbsoluteMaxCacheSize`
- `0x18007de6f`: `DOCacheHost`
- `0x18007deaf`: `DOCacheHostSource`
- `0x18007df2f`: `DODelayCacheServerFallbackBackground`
- `0x18007df6f`: `DODelayCacheServerFallbackForeground`
- `0x18007e0ef`: `DOMaxCacheAge`
- `0x18007e12f`: `DOMaxCacheSize`
- `0x18007e26f`: `DOMinFileSizeToCache`
- `0x18007e2ef`: `DOModifyCacheDrive`
- `0x18007dd55`: `CreateInstanceStart`
- `0x18007e5b5`: `CreateInstanceEnd`
- `0x18007dc9c`: `MDM_Policy_Config01_DeliveryOptimization02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_DeliveryOptimization02_InvokeCreateInstance(
        MI_Context *self,
        struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
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
    inserted = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_137;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v10,
    "CreateInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v8 = 0;
  inserted = (unsigned int)CreateRequestHandlerInstance(
                             self,
                             a2[1].serverName,
                             a2[1].ft,
                             &MDM_Policy_Config01_DeliveryOptimization02_NodeList,
                             29,
                             4,
                             &v8);
  if ( inserted == MI_RESULT_OK )
  {
    v10[4] = &v8;
    v11 = 1;
    v6 = v8;
    if ( !v8 )
    {
      inserted = MI_RESULT_FAILED;
      goto LABEL_137;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v8,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_DeliveryOptimization02_NodeList,
      0x1Du);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOAbsoluteMaxCacheSize", a2[1].reserved);
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
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOAllowVPNPeerCaching", &a2[1].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( LOBYTE(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOCacheHost", &a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[2].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOCacheHostSource", &a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DODelayBackgroundDownloadFromHttp", &a2[2].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[2].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DODelayCacheServerFallbackBackground", &a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DODelayCacheServerFallbackForeground", &a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DODelayForegroundDownloadFromHttp", a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DODownloadMode", &a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( LOBYTE(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOGroupId", &a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOGroupIdSource", &a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[3].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMaxBackgroundDownloadBandwidth", &a2[3].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[3].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMaxCacheAge", &a2[3].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[3].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMaxCacheSize", &a2[3].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[3].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMaxForegroundDownloadBandwidth", a2[3].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[3].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMinBackgroundQos", &a2[3].reserved[1]);
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
                   &a2[3].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[3].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMinDiskSizeAllowedToPeer", &a2[3].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMinFileSizeToCache", &a2[4]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[4].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMinRAMAllowedToPeer", &a2[4].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( LOBYTE(a2[4].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOModifyCacheDrive", &a2[4].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[4].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOMonthlyUploadDataCap", a2[4].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[4].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOPercentageMaxBackgroundBandwidth", &a2[4].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[4].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOPercentageMaxForegroundBandwidth", &a2[4].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( BYTE4(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DORestrictPeerSelectionBy", &a2[4].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    if ( LOBYTE(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DOSetHoursToLimitBackgroundDownloadBandwidth", &a2[5]);
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
                   &a2[5].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_137;
        goto LABEL_132;
      }
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_137;
      goto LABEL_132;
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18007dc2c  mov     [rsp+arg_10], rsi
0x18007dc31  mov     [rsp+arg_18], rdi
0x18007dc36  push    r12
0x18007dc38  push    r14
0x18007dc3a  push    r15
0x18007dc3c  sub     rsp, 220h
0x18007dc43  mov     rax, cs:__security_cookie
0x18007dc4a  xor     rax, rsp
0x18007dc4d  mov     [rsp+238h+var_28], rax
0x18007dc55  mov     rsi, rdx
0x18007dc58  mov     r15, rcx
0x18007dc5b  xor     edx, edx; Val
0x18007dc5d  mov     r8d, 160h; Size
0x18007dc63  lea     rcx, [rsp+238h+instance]; void *
0x18007dc6b  call    memset_0
0x18007dc70  mov     [rsp+238h+var_1B8], 0
0x18007dc7b  mov     [rsp+238h+var_1B4], 0
0x18007dc83  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18007dc8a  mov     [rsp+238h+var_1E8], rax
0x18007dc8f  lea     rax, [rsp+238h+var_1B8]
0x18007dc97  mov     [rsp+238h+var_1E0], rax
0x18007dc9c  lea     rax, aMdmPolicyConfi_34; "MDM_Policy_Config01_DeliveryOptimizatio"...
0x18007dca3  mov     [rsp+238h+var_1D8], rax
0x18007dca8  lea     rcx, [rsp+238h+var_1B8]
0x18007dcb0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007dcb5  mov     eax, cs:dword_180380B68
0x18007dcbb  cmp     eax, 5
0x18007dcbe  jbe     short loc_18007DD34
0x18007dcc0  mov     rdx, 200000000000h
0x18007dcca  lea     rcx, dword_180380B68
0x18007dcd1  call    _tlgKeywordOn
0x18007dcd6  test    al, al
0x18007dcd8  jz      short loc_18007DD34
0x18007dcda  cmp     [rsp+238h+var_1B4], 0
0x18007dce2  jz      short loc_18007DD16
0x18007dce4  cmp     [rsp+238h+var_1A0], 0
0x18007dcec  jnz     short loc_18007DD0C
0x18007dcee  cmp     [rsp+238h+var_19C], 0
0x18007dcf6  jnz     short loc_18007DD0C
0x18007dcf8  cmp     [rsp+238h+var_198], 0
0x18007dd00  jnz     short loc_18007DD0C
0x18007dd02  cmp     [rsp+238h+var_194], 0
0x18007dd0a  jz      short loc_18007DD16
0x18007dd0c  lea     r9, [rsp+238h+var_1A0]
0x18007dd14  jmp     short loc_18007DD19
0x18007dd16  xor     r9d, r9d
0x18007dd19  lea     r8, [rsp+238h+var_1B0]
0x18007dd21  lea     rdx, dword_180354924
0x18007dd28  lea     rcx, dword_180380B68
0x18007dd2f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007dd34  cmp     byte ptr [rsi+48h], 0
0x18007dd38  jz      loc_18007E5AD
0x18007dd3e  mov     [rsp+238h+var_1F0], 0
0x18007dd43  cmp     byte ptr [rsi+58h], 0
0x18007dd47  jz      loc_18007E5AD
0x18007dd4d  mov     r9, [rsi+40h]; unsigned __int16 *
0x18007dd51  mov     r8, [rsi+50h]; unsigned __int16 *
0x18007dd55  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x18007dd5c  lea     rcx, [rsp+238h+var_1E8]; this
0x18007dd61  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18007dd66  nop
0x18007dd67  mov     [rsp+238h+var_1F8], 0
0x18007dd70  lea     rax, [rsp+238h+var_1F8]
0x18007dd75  mov     [rsp+238h+var_208], rax
0x18007dd7a  mov     [rsp+238h+var_210], 4
0x18007dd82  mov     [rsp+238h+var_218], 1Dh
0x18007dd8a  lea     r9, ?MDM_Policy_Config01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_DeliveryOptimization02_NodeList
0x18007dd91  mov     r8, [rsi+40h]
0x18007dd95  mov     rdx, [rsi+50h]
0x18007dd99  mov     rcx, r15
0x18007dd9c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18007dda1  mov     edi, eax
0x18007dda3  test    eax, eax
0x18007dda5  jz      short loc_18007DDAC
0x18007dda7  jmp     loc_18007E5B2
0x18007ddac  lea     rax, [rsp+238h+var_1F8]
0x18007ddb1  mov     [rsp+238h+var_1C8], rax
0x18007ddb6  mov     r12d, 1
0x18007ddbc  mov     [rsp+238h+var_1C0], r12b
0x18007ddc1  mov     r14, [rsp+238h+var_1F8]
0x18007ddc6  test    r14, r14
0x18007ddc9  jnz     short loc_18007DDD3
0x18007ddcb  mov     edi, r12d
0x18007ddce  jmp     loc_18007E5B2
0x18007ddd3  mov     r9d, 1Dh; unsigned int
0x18007ddd9  lea     r8, ?MDM_Policy_Config01_DeliveryOptimization02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18007dde0  mov     rdx, rsi; struct _MI_Instance *
0x18007dde3  mov     rcx, r14; this
0x18007dde6  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18007ddeb  lea     r8, [rsi+60h]; void *
0x18007ddef  cmp     [r8+4], r12b
0x18007ddf3  jnz     short loc_18007DE28
0x18007ddf5  lea     rdx, aDoabsolutemaxc; "DOAbsoluteMaxCacheSize"
0x18007ddfc  mov     rcx, r14; this
0x18007ddff  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007de04  mov     edi, eax
0x18007de06  test    eax, eax
0x18007de08  jz      short loc_18007DE28
0x18007de0a  mov     rcx, [rsp+238h+var_1F8]
0x18007de0f  test    rcx, rcx
0x18007de12  jz      short loc_18007DE23
0x18007de14  mov     rax, [rcx]
0x18007de17  mov     edx, r12d
0x18007de1a  mov     rax, [rax]
0x18007de1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007de22  nop
0x18007de23  jmp     loc_18007E5B2
0x18007de28  lea     r8, [rsi+68h]; void *
0x18007de2c  cmp     [r8+4], r12b
0x18007de30  jnz     short loc_18007DE65
0x18007de32  lea     rdx, aDoallowvpnpeer; "DOAllowVPNPeerCaching"
0x18007de39  mov     rcx, r14; this
0x18007de3c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007de41  mov     edi, eax
0x18007de43  test    eax, eax
0x18007de45  jz      short loc_18007DE65
0x18007de47  mov     rcx, [rsp+238h+var_1F8]
0x18007de4c  test    rcx, rcx
0x18007de4f  jz      short loc_18007DE60
0x18007de51  mov     rax, [rcx]
0x18007de54  mov     edx, r12d
0x18007de57  mov     rax, [rax]
0x18007de5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007de5f  nop
0x18007de60  jmp     loc_18007E5B2
0x18007de65  lea     r8, [rsi+70h]; void *
0x18007de69  cmp     [r8+8], r12b
0x18007de6d  jnz     short loc_18007DEA2
0x18007de6f  lea     rdx, aDocachehost; "DOCacheHost"
0x18007de76  mov     rcx, r14; this
0x18007de79  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007de7e  mov     edi, eax
0x18007de80  test    eax, eax
0x18007de82  jz      short loc_18007DEA2
0x18007de84  mov     rcx, [rsp+238h+var_1F8]
0x18007de89  test    rcx, rcx
0x18007de8c  jz      short loc_18007DE9D
0x18007de8e  mov     rax, [rcx]
0x18007de91  mov     edx, r12d
0x18007de94  mov     rax, [rax]
0x18007de97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007de9c  nop
0x18007de9d  jmp     loc_18007E5B2
0x18007dea2  lea     r8, [rsi+80h]; void *
0x18007dea9  cmp     [r8+4], r12b
0x18007dead  jnz     short loc_18007DEE2
0x18007deaf  lea     rdx, aDocachehostsou; "DOCacheHostSource"
0x18007deb6  mov     rcx, r14; this
0x18007deb9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007debe  mov     edi, eax
0x18007dec0  test    eax, eax
0x18007dec2  jz      short loc_18007DEE2
0x18007dec4  mov     rcx, [rsp+238h+var_1F8]
0x18007dec9  test    rcx, rcx
0x18007decc  jz      short loc_18007DEDD
0x18007dece  mov     rax, [rcx]
0x18007ded1  mov     edx, r12d
0x18007ded4  mov     rax, [rax]
0x18007ded7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dedc  nop
0x18007dedd  jmp     loc_18007E5B2
0x18007dee2  lea     r8, [rsi+88h]; void *
0x18007dee9  cmp     [r8+4], r12b
0x18007deed  jnz     short loc_18007DF22
0x18007deef  lea     rdx, aDodelaybackgro; "DODelayBackgroundDownloadFromHttp"
0x18007def6  mov     rcx, r14; this
0x18007def9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007defe  mov     edi, eax
0x18007df00  test    eax, eax
0x18007df02  jz      short loc_18007DF22
0x18007df04  mov     rcx, [rsp+238h+var_1F8]
0x18007df09  test    rcx, rcx
0x18007df0c  jz      short loc_18007DF1D
0x18007df0e  mov     rax, [rcx]
0x18007df11  mov     edx, r12d
0x18007df14  mov     rax, [rax]
0x18007df17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007df1c  nop
0x18007df1d  jmp     loc_18007E5B2
0x18007df22  lea     r8, [rsi+90h]; void *
0x18007df29  cmp     [r8+4], r12b
0x18007df2d  jnz     short loc_18007DF62
0x18007df2f  lea     rdx, aDodelaycachese; "DODelayCacheServerFallbackBackground"
0x18007df36  mov     rcx, r14; this
0x18007df39  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007df3e  mov     edi, eax
0x18007df40  test    eax, eax
0x18007df42  jz      short loc_18007DF62
0x18007df44  mov     rcx, [rsp+238h+var_1F8]
0x18007df49  test    rcx, rcx
0x18007df4c  jz      short loc_18007DF5D
0x18007df4e  mov     rax, [rcx]
0x18007df51  mov     edx, r12d
0x18007df54  mov     rax, [rax]
0x18007df57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007df5c  nop
0x18007df5d  jmp     loc_18007E5B2
0x18007df62  lea     r8, [rsi+98h]; void *
0x18007df69  cmp     [r8+4], r12b
0x18007df6d  jnz     short loc_18007DFA2
0x18007df6f  lea     rdx, aDodelaycachese_0; "DODelayCacheServerFallbackForeground"
0x18007df76  mov     rcx, r14; this
0x18007df79  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007df7e  mov     edi, eax
0x18007df80  test    eax, eax
0x18007df82  jz      short loc_18007DFA2
0x18007df84  mov     rcx, [rsp+238h+var_1F8]
0x18007df89  test    rcx, rcx
0x18007df8c  jz      short loc_18007DF9D
0x18007df8e  mov     rax, [rcx]
0x18007df91  mov     edx, r12d
0x18007df94  mov     rax, [rax]
0x18007df97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007df9c  nop
0x18007df9d  jmp     loc_18007E5B2
0x18007dfa2  lea     r8, [rsi+0A0h]; void *
0x18007dfa9  cmp     [r8+4], r12b
0x18007dfad  jnz     short loc_18007DFE2
0x18007dfaf  lea     rdx, aDodelayforegro; "DODelayForegroundDownloadFromHttp"
0x18007dfb6  mov     rcx, r14; this
0x18007dfb9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007dfbe  mov     edi, eax
0x18007dfc0  test    eax, eax
0x18007dfc2  jz      short loc_18007DFE2
0x18007dfc4  mov     rcx, [rsp+238h+var_1F8]
0x18007dfc9  test    rcx, rcx
0x18007dfcc  jz      short loc_18007DFDD
0x18007dfce  mov     rax, [rcx]
0x18007dfd1  mov     edx, r12d
0x18007dfd4  mov     rax, [rax]
0x18007dfd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dfdc  nop
0x18007dfdd  jmp     loc_18007E5B2
0x18007dfe2  lea     r8, [rsi+0A8h]; void *
0x18007dfe9  cmp     [r8+4], r12b
0x18007dfed  jnz     short loc_18007E022
0x18007dfef  lea     rdx, aDodownloadmode; "DODownloadMode"
0x18007dff6  mov     rcx, r14; this
0x18007dff9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007dffe  mov     edi, eax
0x18007e000  test    eax, eax
0x18007e002  jz      short loc_18007E022
0x18007e004  mov     rcx, [rsp+238h+var_1F8]
0x18007e009  test    rcx, rcx
0x18007e00c  jz      short loc_18007E01D
0x18007e00e  mov     rax, [rcx]
0x18007e011  mov     edx, r12d
0x18007e014  mov     rax, [rax]
0x18007e017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e01c  nop
0x18007e01d  jmp     loc_18007E5B2
0x18007e022  lea     r8, [rsi+0B0h]; void *
0x18007e029  cmp     [r8+8], r12b
0x18007e02d  jnz     short loc_18007E062
0x18007e02f  lea     rdx, aDogroupid; "DOGroupId"
0x18007e036  mov     rcx, r14; this
0x18007e039  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007e03e  mov     edi, eax
0x18007e040  test    eax, eax
0x18007e042  jz      short loc_18007E062
0x18007e044  mov     rcx, [rsp+238h+var_1F8]
0x18007e049  test    rcx, rcx
0x18007e04c  jz      short loc_18007E05D
0x18007e04e  mov     rax, [rcx]
0x18007e051  mov     edx, r12d
0x18007e054  mov     rax, [rax]
0x18007e057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e05c  nop
0x18007e05d  jmp     loc_18007E5B2
0x18007e062  lea     r8, [rsi+0C0h]; void *
0x18007e069  cmp     [r8+4], r12b
0x18007e06d  jnz     short loc_18007E0A2
0x18007e06f  lea     rdx, aDogroupidsourc; "DOGroupIdSource"
0x18007e076  mov     rcx, r14; this
0x18007e079  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007e07e  mov     edi, eax
0x18007e080  test    eax, eax
0x18007e082  jz      short loc_18007E0A2
0x18007e084  mov     rcx, [rsp+238h+var_1F8]
0x18007e089  test    rcx, rcx
0x18007e08c  jz      short loc_18007E09D
0x18007e08e  mov     rax, [rcx]
0x18007e091  mov     edx, r12d
0x18007e094  mov     rax, [rax]
0x18007e097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e09c  nop
0x18007e09d  jmp     loc_18007E5B2
0x18007e0a2  lea     r8, [rsi+0C8h]; void *
0x18007e0a9  cmp     [r8+4], r12b
0x18007e0ad  jnz     short loc_18007E0E2
0x18007e0af  lea     rdx, aDomaxbackgroun; "DOMaxBackgroundDownloadBandwidth"
0x18007e0b6  mov     rcx, r14; this
0x18007e0b9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18007e0be  mov     edi, eax
0x18007e0c0  test    eax, eax
0x18007e0c2  jz      short loc_18007E0E2
0x18007e0c4  mov     rcx, [rsp+238h+var_1F8]
0x18007e0c9  test    rcx, rcx
0x18007e0cc  jz      short loc_18007E0DD
0x18007e0ce  mov     rax, [rcx]
  ... truncated ...
```
