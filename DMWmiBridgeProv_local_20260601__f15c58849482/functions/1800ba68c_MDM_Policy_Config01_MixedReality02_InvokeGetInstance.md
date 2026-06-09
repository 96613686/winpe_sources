# MDM_Policy_Config01_MixedReality02_InvokeGetInstance

- ea: `0x1800ba68c`
- end: `0x1800bacca`
- name: `MDM_Policy_Config01_MixedReality02_InvokeGetInstance`
- size: `1598`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b9610`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800ba68c`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800ba929`
- `msvcrt!_wtoi` at `0x1800ba966`
- `msvcrt!_wtoi` at `0x1800ba9a3`
- `msvcrt!_wtoi` at `0x1800ba9e0`
- `msvcrt!_wtoi` at `0x1800baa1d`
- `msvcrt!_wtoi` at `0x1800baa5a`
- `msvcrt!_wtoi` at `0x1800baa97`
- `msvcrt!_wtoi` at `0x1800baad4`
- `msvcrt!_wtoi` at `0x1800bab11`
- `msvcrt!_wtoi` at `0x1800bab4e`
- `msvcrt!_wtoi` at `0x1800bab8b`
- `msvcrt!_wtoi` at `0x1800babc8`
- `msvcrt!_wtoi` at `0x1800ba929`
- `msvcrt!_wtoi` at `0x1800ba966`
- `msvcrt!_wtoi` at `0x1800ba9a3`
- `msvcrt!_wtoi` at `0x1800ba9e0`
- `msvcrt!_wtoi` at `0x1800baa1d`
- `msvcrt!_wtoi` at `0x1800baa5a`
- `msvcrt!_wtoi` at `0x1800baa97`
- `msvcrt!_wtoi` at `0x1800baad4`
- `msvcrt!_wtoi` at `0x1800bab11`
- `msvcrt!_wtoi` at `0x1800bab4e`
- `msvcrt!_wtoi` at `0x1800bab8b`
- `msvcrt!_wtoi` at `0x1800babc8`

## string_xrefs

- `0x1800ba90c`: `AADGroupMembershipCacheValidityInDays`
- `0x1800ba949`: `AllowLaunchUriInSingleAppKiosk`
- `0x1800baa00`: `ConfigureMovingPlatform`
- `0x1800ba6fb`: `MDM_Policy_Config01_MixedReality02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_MixedReality02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  MI_Result v5; // esi
  WmiRequestHandler *v6; // rdi
  wchar_t *String; // [rsp+40h] [rbp-168h] BYREF
  char v9; // [rsp+48h] [rbp-160h]
  WmiRequestHandler *v10; // [rsp+50h] [rbp-158h] BYREF
  _QWORD v11[5]; // [rsp+58h] [rbp-150h] BYREF
  char v12; // [rsp+80h] [rbp-128h]
  int v13; // [rsp+88h] [rbp-120h] BYREF
  char v14; // [rsp+8Ch] [rbp-11Ch]
  _BYTE v15[16]; // [rsp+90h] [rbp-118h] BYREF
  _DWORD v16[4]; // [rsp+A0h] [rbp-108h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-F8h] BYREF
  int v18; // [rsp+110h] [rbp-98h]
  char v19; // [rsp+114h] [rbp-94h]
  int v20; // [rsp+118h] [rbp-90h]
  char v21; // [rsp+11Ch] [rbp-8Ch]
  int v22; // [rsp+120h] [rbp-88h]
  char v23; // [rsp+124h] [rbp-84h]
  int v24; // [rsp+128h] [rbp-80h]
  char v25; // [rsp+12Ch] [rbp-7Ch]
  int v26; // [rsp+130h] [rbp-78h]
  char v27; // [rsp+134h] [rbp-74h]
  int v28; // [rsp+138h] [rbp-70h]
  char v29; // [rsp+13Ch] [rbp-6Ch]
  int v30; // [rsp+140h] [rbp-68h]
  char v31; // [rsp+144h] [rbp-64h]
  int v32; // [rsp+148h] [rbp-60h]
  char v33; // [rsp+14Ch] [rbp-5Ch]
  int v34; // [rsp+150h] [rbp-58h]
  char v35; // [rsp+154h] [rbp-54h]
  int v36; // [rsp+158h] [rbp-50h]
  char v37; // [rsp+15Ch] [rbp-4Ch]
  int v38; // [rsp+160h] [rbp-48h]
  char v39; // [rsp+164h] [rbp-44h]
  int v40; // [rsp+168h] [rbp-40h]
  char v41; // [rsp+16Ch] [rbp-3Ch]

  String = 0;
  memset_0(&instance, 0, 0xC0u);
  v13 = 0;
  v14 = 0;
  v11[0] = &TelemetryEventWriter::`vftable';
  v11[1] = &v13;
  v11[2] = "MDM_Policy_Config01_MixedReality02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180338409,
      v15,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    v5 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_65;
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
                       &MDM_Policy_Config01_MixedReality02_NodeList,
                       14,
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
      goto LABEL_65;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_MixedReality02_NodeList,
      0xEu);
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_65;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_65;
    }
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_65;
      goto LABEL_24;
    }
    v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_MixedReality02_rtti, &instance);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_65;
      goto LABEL_24;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AADGroupMembershipCacheValidityInDays",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowLaunchUriInSingleAppKiosk",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AutomaticDisplayAdjustment", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"BrightnessButtonDisabled", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ConfigureMovingPlatform", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"EyeTrackingCalibrationPrompt",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"FallbackDiagnostics", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"HeadTrackingMode", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ManualDownDirectionDisabled",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v34 = _wtoi(String);
      v35 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"MicrophoneDisabled", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v36 = _wtoi(String);
      v37 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"VisitorAutoLogon", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v38 = _wtoi(String);
      v39 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"VolumeButtonDisabled", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v40 = _wtoi(String);
      v41 = 1;
    }
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v10 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_65:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180338EA5,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800ba68c  mov     [rsp+arg_10], rbx
0x1800ba691  push    rsi
0x1800ba692  push    rdi
0x1800ba693  push    r12
0x1800ba695  push    r14
0x1800ba697  push    r15
0x1800ba699  sub     rsp, 180h
0x1800ba6a0  mov     rax, cs:__security_cookie
0x1800ba6a7  xor     rax, rsp
0x1800ba6aa  mov     [rsp+1A8h+var_38], rax
0x1800ba6b2  mov     r14, rdx
0x1800ba6b5  mov     r15, rcx
0x1800ba6b8  xor     ebx, ebx
0x1800ba6ba  mov     [rsp+1A8h+String], rbx
0x1800ba6bf  xor     edx, edx; Val
0x1800ba6c1  mov     r8d, 0C0h; Size
0x1800ba6c7  lea     rcx, [rsp+1A8h+instance]; void *
0x1800ba6cf  call    memset_0
0x1800ba6d4  mov     [rsp+1A8h+var_120], ebx
0x1800ba6db  mov     [rsp+1A8h+var_11C], bl
0x1800ba6e2  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800ba6e9  mov     [rsp+1A8h+var_150], rax
0x1800ba6ee  lea     rax, [rsp+1A8h+var_120]
0x1800ba6f6  mov     [rsp+1A8h+var_148], rax
0x1800ba6fb  lea     rax, aMdmPolicyConfi_149; "MDM_Policy_Config01_MixedReality02"
0x1800ba702  mov     [rsp+1A8h+var_140], rax
0x1800ba707  lea     rcx, [rsp+1A8h+var_120]
0x1800ba70f  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800ba714  mov     eax, cs:dword_180380B68
0x1800ba71a  cmp     eax, 5
0x1800ba71d  jbe     short loc_1800BA78E
0x1800ba71f  mov     rdx, 200000000000h
0x1800ba729  lea     rcx, dword_180380B68
0x1800ba730  call    _tlgKeywordOn
0x1800ba735  test    al, al
0x1800ba737  jz      short loc_1800BA78E
0x1800ba739  cmp     [rsp+1A8h+var_11C], bl
0x1800ba740  jz      short loc_1800BA770
0x1800ba742  cmp     [rsp+1A8h+var_108], ebx
0x1800ba749  jnz     short loc_1800BA766
0x1800ba74b  cmp     [rsp+1A8h+var_104], ebx
0x1800ba752  jnz     short loc_1800BA766
0x1800ba754  cmp     [rsp+1A8h+var_100], ebx
0x1800ba75b  jnz     short loc_1800BA766
0x1800ba75d  cmp     [rsp+1A8h+var_FC], ebx
0x1800ba764  jz      short loc_1800BA770
0x1800ba766  lea     r9, [rsp+1A8h+var_108]
0x1800ba76e  jmp     short loc_1800BA773
0x1800ba770  mov     r9, rbx
0x1800ba773  lea     r8, [rsp+1A8h+var_118]
0x1800ba77b  lea     rdx, byte_180338409
0x1800ba782  lea     rcx, dword_180380B68
0x1800ba789  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800ba78e  cmp     [r14+48h], bl
0x1800ba792  jz      loc_1800BAC2A
0x1800ba798  mov     [rsp+1A8h+var_160], bl
0x1800ba79c  cmp     [r14+58h], bl
0x1800ba7a0  jz      loc_1800BAC2A
0x1800ba7a6  mov     r9, [r14+40h]; unsigned __int16 *
0x1800ba7aa  mov     r8, [r14+50h]; unsigned __int16 *
0x1800ba7ae  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800ba7b5  lea     rcx, [rsp+1A8h+var_150]; this
0x1800ba7ba  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800ba7bf  nop
0x1800ba7c0  mov     [rsp+1A8h+var_158], rbx
0x1800ba7c5  lea     rax, [rsp+1A8h+var_158]
0x1800ba7ca  mov     [rsp+1A8h+var_178], rax
0x1800ba7cf  mov     [rsp+1A8h+var_180], ebx
0x1800ba7d3  mov     [rsp+1A8h+var_188], 0Eh
0x1800ba7db  lea     r9, ?MDM_Policy_Config01_MixedReality02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_MixedReality02_NodeList
0x1800ba7e2  mov     r8, [r14+40h]
0x1800ba7e6  mov     rdx, [r14+50h]
0x1800ba7ea  mov     rcx, r15
0x1800ba7ed  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800ba7f2  mov     esi, eax
0x1800ba7f4  test    eax, eax
0x1800ba7f6  jz      short loc_1800BA7FD
0x1800ba7f8  jmp     loc_1800BAC2F
0x1800ba7fd  lea     rax, [rsp+1A8h+var_158]
0x1800ba802  mov     [rsp+1A8h+var_130], rax
0x1800ba807  mov     r12d, 1
0x1800ba80d  mov     [rsp+1A8h+var_128], r12b
0x1800ba815  mov     rdi, [rsp+1A8h+var_158]
0x1800ba81a  test    rdi, rdi
0x1800ba81d  jnz     short loc_1800BA827
0x1800ba81f  mov     esi, r12d
0x1800ba822  jmp     loc_1800BAC2F
0x1800ba827  mov     r9d, 0Eh; unsigned int
0x1800ba82d  lea     r8, ?MDM_Policy_Config01_MixedReality02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800ba834  mov     rdx, r14; struct _MI_Instance *
0x1800ba837  mov     rcx, rdi; this
0x1800ba83a  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800ba83f  mov     rax, [rdi]
0x1800ba842  mov     rcx, rdi
0x1800ba845  mov     rax, [rax+10h]
0x1800ba849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba84e  mov     esi, eax
0x1800ba850  test    eax, eax
0x1800ba852  jz      short loc_1800BA872
0x1800ba854  mov     rcx, [rsp+1A8h+var_158]
0x1800ba859  test    rcx, rcx
0x1800ba85c  jz      short loc_1800BA86D
0x1800ba85e  mov     rax, [rcx]
0x1800ba861  mov     edx, r12d
0x1800ba864  mov     rax, [rax]
0x1800ba867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba86c  nop
0x1800ba86d  jmp     loc_1800BAC2F
0x1800ba872  mov     rax, [rdi]
0x1800ba875  mov     rcx, rdi
0x1800ba878  mov     rax, [rax+8]
0x1800ba87c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba881  mov     esi, eax
0x1800ba883  test    eax, eax
0x1800ba885  jz      short loc_1800BA8A5
0x1800ba887  mov     rcx, [rsp+1A8h+var_158]
0x1800ba88c  test    rcx, rcx
0x1800ba88f  jz      short loc_1800BA8A0
0x1800ba891  mov     rax, [rcx]
0x1800ba894  mov     edx, r12d
0x1800ba897  mov     rax, [rax]
0x1800ba89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba89f  nop
0x1800ba8a0  jmp     loc_1800BAC2F
0x1800ba8a5  lea     r8, [rsp+1A8h+instance]; instance
0x1800ba8ad  lea     rdx, MDM_Policy_Config01_MixedReality02_rtti; classDecl
0x1800ba8b4  mov     rcx, r15; context
0x1800ba8b7  call    MI_Context_ConstructInstance
0x1800ba8bc  mov     esi, eax
0x1800ba8be  test    eax, eax
0x1800ba8c0  jz      short loc_1800BA8E0
0x1800ba8c2  mov     rcx, [rsp+1A8h+var_158]
0x1800ba8c7  test    rcx, rcx
0x1800ba8ca  jz      short loc_1800BA8DB
0x1800ba8cc  mov     rax, [rcx]
0x1800ba8cf  mov     edx, r12d
0x1800ba8d2  mov     rax, [rax]
0x1800ba8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba8da  nop
0x1800ba8db  jmp     loc_1800BAC2F
0x1800ba8e0  mov     [rsp+1A8h+var_160], r12b
0x1800ba8e5  mov     rdx, [r14+40h]
0x1800ba8e9  lea     rcx, [rsp+1A8h+instance]
0x1800ba8f1  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800ba8f6  mov     rdx, [r14+50h]
0x1800ba8fa  lea     rcx, [rsp+1A8h+instance]
0x1800ba902  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800ba907  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800ba90c  lea     rdx, aAadgroupmember; "AADGroupMembershipCacheValidityInDays"
0x1800ba913  mov     rcx, rdi; this
0x1800ba916  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ba91b  test    eax, eax
0x1800ba91d  jnz     short loc_1800BA944
0x1800ba91f  mov     rcx, [rsp+1A8h+String]; String
0x1800ba924  test    rcx, rcx
0x1800ba927  jz      short loc_1800BA944
0x1800ba929  call    cs:__imp__wtoi
0x1800ba930  nop     dword ptr [rax+rax+00h]
0x1800ba935  mov     [rsp+1A8h+var_98], eax
0x1800ba93c  mov     [rsp+1A8h+var_94], r12b
0x1800ba944  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800ba949  lea     rdx, aAllowlaunchuri; "AllowLaunchUriInSingleAppKiosk"
0x1800ba950  mov     rcx, rdi; this
0x1800ba953  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ba958  test    eax, eax
0x1800ba95a  jnz     short loc_1800BA981
0x1800ba95c  mov     rcx, [rsp+1A8h+String]; String
0x1800ba961  test    rcx, rcx
0x1800ba964  jz      short loc_1800BA981
0x1800ba966  call    cs:__imp__wtoi
0x1800ba96d  nop     dword ptr [rax+rax+00h]
0x1800ba972  mov     [rsp+1A8h+var_90], eax
0x1800ba979  mov     [rsp+1A8h+var_8C], r12b
0x1800ba981  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800ba986  lea     rdx, aAutomaticdispl; "AutomaticDisplayAdjustment"
0x1800ba98d  mov     rcx, rdi; this
0x1800ba990  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ba995  test    eax, eax
0x1800ba997  jnz     short loc_1800BA9BE
0x1800ba999  mov     rcx, [rsp+1A8h+String]; String
0x1800ba99e  test    rcx, rcx
0x1800ba9a1  jz      short loc_1800BA9BE
0x1800ba9a3  call    cs:__imp__wtoi
0x1800ba9aa  nop     dword ptr [rax+rax+00h]
0x1800ba9af  mov     [rsp+1A8h+var_88], eax
0x1800ba9b6  mov     [rsp+1A8h+var_84], r12b
0x1800ba9be  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800ba9c3  lea     rdx, aBrightnessbutt; "BrightnessButtonDisabled"
0x1800ba9ca  mov     rcx, rdi; this
0x1800ba9cd  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ba9d2  test    eax, eax
0x1800ba9d4  jnz     short loc_1800BA9FB
0x1800ba9d6  mov     rcx, [rsp+1A8h+String]; String
0x1800ba9db  test    rcx, rcx
0x1800ba9de  jz      short loc_1800BA9FB
0x1800ba9e0  call    cs:__imp__wtoi
0x1800ba9e7  nop     dword ptr [rax+rax+00h]
0x1800ba9ec  mov     [rsp+1A8h+var_80], eax
0x1800ba9f3  mov     [rsp+1A8h+var_7C], r12b
0x1800ba9fb  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800baa00  lea     rdx, aConfiguremovin; "ConfigureMovingPlatform"
0x1800baa07  mov     rcx, rdi; this
0x1800baa0a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800baa0f  test    eax, eax
0x1800baa11  jnz     short loc_1800BAA38
0x1800baa13  mov     rcx, [rsp+1A8h+String]; String
0x1800baa18  test    rcx, rcx
0x1800baa1b  jz      short loc_1800BAA38
0x1800baa1d  call    cs:__imp__wtoi
0x1800baa24  nop     dword ptr [rax+rax+00h]
0x1800baa29  mov     [rsp+1A8h+var_78], eax
0x1800baa30  mov     [rsp+1A8h+var_74], r12b
0x1800baa38  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800baa3d  lea     rdx, aEyetrackingcal; "EyeTrackingCalibrationPrompt"
0x1800baa44  mov     rcx, rdi; this
0x1800baa47  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800baa4c  test    eax, eax
0x1800baa4e  jnz     short loc_1800BAA75
0x1800baa50  mov     rcx, [rsp+1A8h+String]; String
0x1800baa55  test    rcx, rcx
0x1800baa58  jz      short loc_1800BAA75
0x1800baa5a  call    cs:__imp__wtoi
0x1800baa61  nop     dword ptr [rax+rax+00h]
0x1800baa66  mov     [rsp+1A8h+var_70], eax
0x1800baa6d  mov     [rsp+1A8h+var_6C], r12b
0x1800baa75  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800baa7a  lea     rdx, aFallbackdiagno; "FallbackDiagnostics"
0x1800baa81  mov     rcx, rdi; this
0x1800baa84  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800baa89  test    eax, eax
0x1800baa8b  jnz     short loc_1800BAAB2
0x1800baa8d  mov     rcx, [rsp+1A8h+String]; String
0x1800baa92  test    rcx, rcx
0x1800baa95  jz      short loc_1800BAAB2
0x1800baa97  call    cs:__imp__wtoi
0x1800baa9e  nop     dword ptr [rax+rax+00h]
0x1800baaa3  mov     [rsp+1A8h+var_68], eax
0x1800baaaa  mov     [rsp+1A8h+var_64], r12b
0x1800baab2  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800baab7  lea     rdx, aHeadtrackingmo; "HeadTrackingMode"
0x1800baabe  mov     rcx, rdi; this
0x1800baac1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800baac6  test    eax, eax
0x1800baac8  jnz     short loc_1800BAAEF
0x1800baaca  mov     rcx, [rsp+1A8h+String]; String
0x1800baacf  test    rcx, rcx
0x1800baad2  jz      short loc_1800BAAEF
0x1800baad4  call    cs:__imp__wtoi
0x1800baadb  nop     dword ptr [rax+rax+00h]
0x1800baae0  mov     [rsp+1A8h+var_60], eax
0x1800baae7  mov     [rsp+1A8h+var_5C], r12b
0x1800baaef  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800baaf4  lea     rdx, aManualdowndire; "ManualDownDirectionDisabled"
0x1800baafb  mov     rcx, rdi; this
0x1800baafe  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800bab03  test    eax, eax
0x1800bab05  jnz     short loc_1800BAB2C
0x1800bab07  mov     rcx, [rsp+1A8h+String]; String
0x1800bab0c  test    rcx, rcx
0x1800bab0f  jz      short loc_1800BAB2C
0x1800bab11  call    cs:__imp__wtoi
0x1800bab18  nop     dword ptr [rax+rax+00h]
0x1800bab1d  mov     [rsp+1A8h+var_58], eax
0x1800bab24  mov     [rsp+1A8h+var_54], r12b
0x1800bab2c  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800bab31  lea     rdx, aMicrophonedisa; "MicrophoneDisabled"
0x1800bab38  mov     rcx, rdi; this
0x1800bab3b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800bab40  test    eax, eax
0x1800bab42  jnz     short loc_1800BAB69
0x1800bab44  mov     rcx, [rsp+1A8h+String]; String
0x1800bab49  test    rcx, rcx
0x1800bab4c  jz      short loc_1800BAB69
0x1800bab4e  call    cs:__imp__wtoi
0x1800bab55  nop     dword ptr [rax+rax+00h]
0x1800bab5a  mov     [rsp+1A8h+var_50], eax
0x1800bab61  mov     [rsp+1A8h+var_4C], r12b
0x1800bab69  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800bab6e  lea     rdx, aVisitorautolog; "VisitorAutoLogon"
0x1800bab75  mov     rcx, rdi; this
0x1800bab78  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800bab7d  test    eax, eax
0x1800bab7f  jnz     short loc_1800BABA6
0x1800bab81  mov     rcx, [rsp+1A8h+String]; String
0x1800bab86  test    rcx, rcx
0x1800bab89  jz      short loc_1800BABA6
0x1800bab8b  call    cs:__imp__wtoi
0x1800bab92  nop     dword ptr [rax+rax+00h]
0x1800bab97  mov     [rsp+1A8h+var_48], eax
0x1800bab9e  mov     [rsp+1A8h+var_44], r12b
0x1800baba6  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800babab  lea     rdx, aVolumebuttondi; "VolumeButtonDisabled"
0x1800babb2  mov     rcx, rdi; this
0x1800babb5  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800babba  test    eax, eax
0x1800babbc  jnz     short loc_1800BABE3
0x1800babbe  mov     rcx, [rsp+1A8h+String]; String
0x1800babc3  test    rcx, rcx
0x1800babc6  jz      short loc_1800BABE3
0x1800babc8  call    cs:__imp__wtoi
  ... truncated ...
```
