# MDM_Policy_Config01_MixedReality02_InvokeGetInstance

- ea: `0x1800bafe0`
- end: `0x1800bb5d5`
- name: `MDM_Policy_Config01_MixedReality02_InvokeGetInstance`
- size: `1525`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b9fa0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800bafe0`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800bb27d`
- `msvcrt!_wtoi` at `0x1800bb2b4`
- `msvcrt!_wtoi` at `0x1800bb2eb`
- `msvcrt!_wtoi` at `0x1800bb322`
- `msvcrt!_wtoi` at `0x1800bb359`
- `msvcrt!_wtoi` at `0x1800bb390`
- `msvcrt!_wtoi` at `0x1800bb3c7`
- `msvcrt!_wtoi` at `0x1800bb3fe`
- `msvcrt!_wtoi` at `0x1800bb435`
- `msvcrt!_wtoi` at `0x1800bb46c`
- `msvcrt!_wtoi` at `0x1800bb4a3`
- `msvcrt!_wtoi` at `0x1800bb4da`
- `msvcrt!_wtoi` at `0x1800bb27d`
- `msvcrt!_wtoi` at `0x1800bb2b4`
- `msvcrt!_wtoi` at `0x1800bb2eb`
- `msvcrt!_wtoi` at `0x1800bb322`
- `msvcrt!_wtoi` at `0x1800bb359`
- `msvcrt!_wtoi` at `0x1800bb390`
- `msvcrt!_wtoi` at `0x1800bb3c7`
- `msvcrt!_wtoi` at `0x1800bb3fe`
- `msvcrt!_wtoi` at `0x1800bb435`
- `msvcrt!_wtoi` at `0x1800bb46c`
- `msvcrt!_wtoi` at `0x1800bb4a3`
- `msvcrt!_wtoi` at `0x1800bb4da`

## string_xrefs

- `0x1800bb260`: `AADGroupMembershipCacheValidityInDays`
- `0x1800bb297`: `AllowLaunchUriInSingleAppKiosk`
- `0x1800bb33c`: `ConfigureMovingPlatform`
- `0x1800bb04f`: `MDM_Policy_Config01_MixedReality02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_MixedReality02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // esi
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
    v5 = 4;
    goto LABEL_65;
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
         (struct WmiNodeInfo *)&MDM_Policy_Config01_MixedReality02_NodeList,
         0xEu,
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
      goto LABEL_65;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_MixedReality02_NodeList,
      0xEu);
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_65;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_65;
    }
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AADGroupMembershipCacheValidityInDays",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowLaunchUriInSingleAppKiosk",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AutomaticDisplayAdjustment",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"BrightnessButtonDisabled",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureMovingPlatform",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"EyeTrackingCalibrationPrompt",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"FallbackDiagnostics",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"HeadTrackingMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ManualDownDirectionDisabled",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v34 = _wtoi(String);
      v35 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"MicrophoneDisabled",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v36 = _wtoi(String);
      v37 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"VisitorAutoLogon",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v38 = _wtoi(String);
      v39 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"VolumeButtonDisabled",
                          (const unsigned __int16 **)&String)
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
  return v5;
}

```

## disassembly

```asm
0x1800bafe0  mov     [rsp+arg_10], rbx
0x1800bafe5  push    rsi
0x1800bafe6  push    rdi
0x1800bafe7  push    r12
0x1800bafe9  push    r14
0x1800bafeb  push    r15
0x1800bafed  sub     rsp, 180h
0x1800baff4  mov     rax, cs:__security_cookie
0x1800baffb  xor     rax, rsp
0x1800baffe  mov     [rsp+1A8h+var_38], rax
0x1800bb006  mov     r14, rdx
0x1800bb009  mov     r15, rcx
0x1800bb00c  xor     ebx, ebx
0x1800bb00e  mov     [rsp+1A8h+String], rbx
0x1800bb013  xor     edx, edx; Val
0x1800bb015  mov     r8d, 0C0h; Size
0x1800bb01b  lea     rcx, [rsp+1A8h+instance]; void *
0x1800bb023  call    memset_0
0x1800bb028  mov     [rsp+1A8h+var_120], ebx
0x1800bb02f  mov     [rsp+1A8h+var_11C], bl
0x1800bb036  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800bb03d  mov     [rsp+1A8h+var_150], rax
0x1800bb042  lea     rax, [rsp+1A8h+var_120]
0x1800bb04a  mov     [rsp+1A8h+var_148], rax
0x1800bb04f  lea     rax, aMdmPolicyConfi_149; "MDM_Policy_Config01_MixedReality02"
0x1800bb056  mov     [rsp+1A8h+var_140], rax
0x1800bb05b  lea     rcx, [rsp+1A8h+var_120]
0x1800bb063  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800bb068  mov     eax, cs:dword_180380B68
0x1800bb06e  cmp     eax, 5
0x1800bb071  jbe     short loc_1800BB0E2
0x1800bb073  mov     rdx, 200000000000h
0x1800bb07d  lea     rcx, dword_180380B68
0x1800bb084  call    _tlgKeywordOn
0x1800bb089  test    al, al
0x1800bb08b  jz      short loc_1800BB0E2
0x1800bb08d  cmp     [rsp+1A8h+var_11C], bl
0x1800bb094  jz      short loc_1800BB0C4
0x1800bb096  cmp     [rsp+1A8h+var_108], ebx
0x1800bb09d  jnz     short loc_1800BB0BA
0x1800bb09f  cmp     [rsp+1A8h+var_104], ebx
0x1800bb0a6  jnz     short loc_1800BB0BA
0x1800bb0a8  cmp     [rsp+1A8h+var_100], ebx
0x1800bb0af  jnz     short loc_1800BB0BA
0x1800bb0b1  cmp     [rsp+1A8h+var_FC], ebx
0x1800bb0b8  jz      short loc_1800BB0C4
0x1800bb0ba  lea     r9, [rsp+1A8h+var_108]
0x1800bb0c2  jmp     short loc_1800BB0C7
0x1800bb0c4  mov     r9, rbx
0x1800bb0c7  lea     r8, [rsp+1A8h+var_118]
0x1800bb0cf  lea     rdx, byte_180338409
0x1800bb0d6  lea     rcx, dword_180380B68
0x1800bb0dd  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800bb0e2  cmp     [r14+48h], bl
0x1800bb0e6  jz      loc_1800BB536
0x1800bb0ec  mov     [rsp+1A8h+var_160], bl
0x1800bb0f0  cmp     [r14+58h], bl
0x1800bb0f4  jz      loc_1800BB536
0x1800bb0fa  mov     r9, [r14+40h]; unsigned __int16 *
0x1800bb0fe  mov     r8, [r14+50h]; unsigned __int16 *
0x1800bb102  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800bb109  lea     rcx, [rsp+1A8h+var_150]; this
0x1800bb10e  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800bb113  nop
0x1800bb114  mov     [rsp+1A8h+var_158], rbx
0x1800bb119  lea     rax, [rsp+1A8h+var_158]
0x1800bb11e  mov     [rsp+1A8h+var_178], rax
0x1800bb123  mov     [rsp+1A8h+var_180], ebx
0x1800bb127  mov     [rsp+1A8h+var_188], 0Eh
0x1800bb12f  lea     r9, ?MDM_Policy_Config01_MixedReality02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_MixedReality02_NodeList
0x1800bb136  mov     r8, [r14+40h]
0x1800bb13a  mov     rdx, [r14+50h]
0x1800bb13e  mov     rcx, r15
0x1800bb141  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800bb146  mov     esi, eax
0x1800bb148  test    eax, eax
0x1800bb14a  jz      short loc_1800BB151
0x1800bb14c  jmp     loc_1800BB53B
0x1800bb151  lea     rax, [rsp+1A8h+var_158]
0x1800bb156  mov     [rsp+1A8h+var_130], rax
0x1800bb15b  mov     r12d, 1
0x1800bb161  mov     [rsp+1A8h+var_128], r12b
0x1800bb169  mov     rdi, [rsp+1A8h+var_158]
0x1800bb16e  test    rdi, rdi
0x1800bb171  jnz     short loc_1800BB17B
0x1800bb173  mov     esi, r12d
0x1800bb176  jmp     loc_1800BB53B
0x1800bb17b  mov     r9d, 0Eh; unsigned int
0x1800bb181  lea     r8, ?MDM_Policy_Config01_MixedReality02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800bb188  mov     rdx, r14; struct _MI_Instance *
0x1800bb18b  mov     rcx, rdi; this
0x1800bb18e  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800bb193  mov     rax, [rdi]
0x1800bb196  mov     rcx, rdi
0x1800bb199  mov     rax, [rax+10h]
0x1800bb19d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb1a2  mov     esi, eax
0x1800bb1a4  test    eax, eax
0x1800bb1a6  jz      short loc_1800BB1C6
0x1800bb1a8  mov     rcx, [rsp+1A8h+var_158]
0x1800bb1ad  test    rcx, rcx
0x1800bb1b0  jz      short loc_1800BB1C1
0x1800bb1b2  mov     rax, [rcx]
0x1800bb1b5  mov     edx, r12d
0x1800bb1b8  mov     rax, [rax]
0x1800bb1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb1c0  nop
0x1800bb1c1  jmp     loc_1800BB53B
0x1800bb1c6  mov     rax, [rdi]
0x1800bb1c9  mov     rcx, rdi
0x1800bb1cc  mov     rax, [rax+8]
0x1800bb1d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb1d5  mov     esi, eax
0x1800bb1d7  test    eax, eax
0x1800bb1d9  jz      short loc_1800BB1F9
0x1800bb1db  mov     rcx, [rsp+1A8h+var_158]
0x1800bb1e0  test    rcx, rcx
0x1800bb1e3  jz      short loc_1800BB1F4
0x1800bb1e5  mov     rax, [rcx]
0x1800bb1e8  mov     edx, r12d
0x1800bb1eb  mov     rax, [rax]
0x1800bb1ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb1f3  nop
0x1800bb1f4  jmp     loc_1800BB53B
0x1800bb1f9  lea     r8, [rsp+1A8h+instance]; instance
0x1800bb201  lea     rdx, MDM_Policy_Config01_MixedReality02_rtti; classDecl
0x1800bb208  mov     rcx, r15; context
0x1800bb20b  call    MI_Context_ConstructInstance
0x1800bb210  mov     esi, eax
0x1800bb212  test    eax, eax
0x1800bb214  jz      short loc_1800BB234
0x1800bb216  mov     rcx, [rsp+1A8h+var_158]
0x1800bb21b  test    rcx, rcx
0x1800bb21e  jz      short loc_1800BB22F
0x1800bb220  mov     rax, [rcx]
0x1800bb223  mov     edx, r12d
0x1800bb226  mov     rax, [rax]
0x1800bb229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb22e  nop
0x1800bb22f  jmp     loc_1800BB53B
0x1800bb234  mov     [rsp+1A8h+var_160], r12b
0x1800bb239  mov     rdx, [r14+40h]
0x1800bb23d  lea     rcx, [rsp+1A8h+instance]
0x1800bb245  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800bb24a  mov     rdx, [r14+50h]
0x1800bb24e  lea     rcx, [rsp+1A8h+instance]
0x1800bb256  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800bb25b  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800bb260  lea     rdx, aAadgroupmember; "AADGroupMembershipCacheValidityInDays"
0x1800bb267  mov     rcx, rdi; this
0x1800bb26a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800bb26f  test    eax, eax
0x1800bb271  jnz     short loc_1800BB292
0x1800bb273  mov     rcx, [rsp+1A8h+String]; String
0x1800bb278  test    rcx, rcx
0x1800bb27b  jz      short loc_1800BB292
0x1800bb27d  call    cs:__imp__wtoi
0x1800bb283  mov     [rsp+1A8h+var_98], eax
0x1800bb28a  mov     [rsp+1A8h+var_94], r12b
0x1800bb292  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800bb297  lea     rdx, aAllowlaunchuri; "AllowLaunchUriInSingleAppKiosk"
0x1800bb29e  mov     rcx, rdi; this
0x1800bb2a1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800bb2a6  test    eax, eax
0x1800bb2a8  jnz     short loc_1800BB2C9
0x1800bb2aa  mov     rcx, [rsp+1A8h+String]; String
0x1800bb2af  test    rcx, rcx
0x1800bb2b2  jz      short loc_1800BB2C9
0x1800bb2b4  call    cs:__imp__wtoi
0x1800bb2ba  mov     [rsp+1A8h+var_90], eax
0x1800bb2c1  mov     [rsp+1A8h+var_8C], r12b
0x1800bb2c9  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800bb2ce  lea     rdx, aAutomaticdispl; "AutomaticDisplayAdjustment"
0x1800bb2d5  mov     rcx, rdi; this
0x1800bb2d8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800bb2dd  test    eax, eax
0x1800bb2df  jnz     short loc_1800BB300
0x1800bb2e1  mov     rcx, [rsp+1A8h+String]; String
0x1800bb2e6  test    rcx, rcx
0x1800bb2e9  jz      short loc_1800BB300
0x1800bb2eb  call    cs:__imp__wtoi
0x1800bb2f1  mov     [rsp+1A8h+var_88], eax
0x1800bb2f8  mov     [rsp+1A8h+var_84], r12b
0x1800bb300  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800bb305  lea     rdx, aBrightnessbutt; "BrightnessButtonDisabled"
0x1800bb30c  mov     rcx, rdi; this
0x1800bb30f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800bb314  test    eax, eax
0x1800bb316  jnz     short loc_1800BB337
0x1800bb318  mov     rcx, [rsp+1A8h+String]; String
0x1800bb31d  test    rcx, rcx
0x1800bb320  jz      short loc_1800BB337
0x1800bb322  call    cs:__imp__wtoi
0x1800bb328  mov     [rsp+1A8h+var_80], eax
0x1800bb32f  mov     [rsp+1A8h+var_7C], r12b
0x1800bb337  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800bb33c  lea     rdx, aConfiguremovin; "ConfigureMovingPlatform"
0x1800bb343  mov     rcx, rdi; this
0x1800bb346  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800bb34b  test    eax, eax
0x1800bb34d  jnz     short loc_1800BB36E
0x1800bb34f  mov     rcx, [rsp+1A8h+String]; String
0x1800bb354  test    rcx, rcx
0x1800bb357  jz      short loc_1800BB36E
0x1800bb359  call    cs:__imp__wtoi
0x1800bb35f  mov     [rsp+1A8h+var_78], eax
0x1800bb366  mov     [rsp+1A8h+var_74], r12b
0x1800bb36e  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800bb373  lea     rdx, aEyetrackingcal; "EyeTrackingCalibrationPrompt"
0x1800bb37a  mov     rcx, rdi; this
0x1800bb37d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800bb382  test    eax, eax
0x1800bb384  jnz     short loc_1800BB3A5
0x1800bb386  mov     rcx, [rsp+1A8h+String]; String
0x1800bb38b  test    rcx, rcx
0x1800bb38e  jz      short loc_1800BB3A5
0x1800bb390  call    cs:__imp__wtoi
0x1800bb396  mov     [rsp+1A8h+var_70], eax
0x1800bb39d  mov     [rsp+1A8h+var_6C], r12b
0x1800bb3a5  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800bb3aa  lea     rdx, aFallbackdiagno; "FallbackDiagnostics"
0x1800bb3b1  mov     rcx, rdi; this
0x1800bb3b4  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800bb3b9  test    eax, eax
0x1800bb3bb  jnz     short loc_1800BB3DC
0x1800bb3bd  mov     rcx, [rsp+1A8h+String]; String
0x1800bb3c2  test    rcx, rcx
0x1800bb3c5  jz      short loc_1800BB3DC
0x1800bb3c7  call    cs:__imp__wtoi
0x1800bb3cd  mov     [rsp+1A8h+var_68], eax
0x1800bb3d4  mov     [rsp+1A8h+var_64], r12b
0x1800bb3dc  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800bb3e1  lea     rdx, aHeadtrackingmo; "HeadTrackingMode"
0x1800bb3e8  mov     rcx, rdi; this
0x1800bb3eb  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800bb3f0  test    eax, eax
0x1800bb3f2  jnz     short loc_1800BB413
0x1800bb3f4  mov     rcx, [rsp+1A8h+String]; String
0x1800bb3f9  test    rcx, rcx
0x1800bb3fc  jz      short loc_1800BB413
0x1800bb3fe  call    cs:__imp__wtoi
0x1800bb404  mov     [rsp+1A8h+var_60], eax
0x1800bb40b  mov     [rsp+1A8h+var_5C], r12b
0x1800bb413  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800bb418  lea     rdx, aManualdowndire; "ManualDownDirectionDisabled"
0x1800bb41f  mov     rcx, rdi; this
0x1800bb422  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800bb427  test    eax, eax
0x1800bb429  jnz     short loc_1800BB44A
0x1800bb42b  mov     rcx, [rsp+1A8h+String]; String
0x1800bb430  test    rcx, rcx
0x1800bb433  jz      short loc_1800BB44A
0x1800bb435  call    cs:__imp__wtoi
0x1800bb43b  mov     [rsp+1A8h+var_58], eax
0x1800bb442  mov     [rsp+1A8h+var_54], r12b
0x1800bb44a  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800bb44f  lea     rdx, aMicrophonedisa; "MicrophoneDisabled"
0x1800bb456  mov     rcx, rdi; this
0x1800bb459  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800bb45e  test    eax, eax
0x1800bb460  jnz     short loc_1800BB481
0x1800bb462  mov     rcx, [rsp+1A8h+String]; String
0x1800bb467  test    rcx, rcx
0x1800bb46a  jz      short loc_1800BB481
0x1800bb46c  call    cs:__imp__wtoi
0x1800bb472  mov     [rsp+1A8h+var_50], eax
0x1800bb479  mov     [rsp+1A8h+var_4C], r12b
0x1800bb481  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800bb486  lea     rdx, aVisitorautolog; "VisitorAutoLogon"
0x1800bb48d  mov     rcx, rdi; this
0x1800bb490  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800bb495  test    eax, eax
0x1800bb497  jnz     short loc_1800BB4B8
0x1800bb499  mov     rcx, [rsp+1A8h+String]; String
0x1800bb49e  test    rcx, rcx
0x1800bb4a1  jz      short loc_1800BB4B8
0x1800bb4a3  call    cs:__imp__wtoi
0x1800bb4a9  mov     [rsp+1A8h+var_48], eax
0x1800bb4b0  mov     [rsp+1A8h+var_44], r12b
0x1800bb4b8  lea     r8, [rsp+1A8h+String]; unsigned __int16 **
0x1800bb4bd  lea     rdx, aVolumebuttondi; "VolumeButtonDisabled"
0x1800bb4c4  mov     rcx, rdi; this
0x1800bb4c7  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800bb4cc  test    eax, eax
0x1800bb4ce  jnz     short loc_1800BB4EF
0x1800bb4d0  mov     rcx, [rsp+1A8h+String]; String
0x1800bb4d5  test    rcx, rcx
0x1800bb4d8  jz      short loc_1800BB4EF
0x1800bb4da  call    cs:__imp__wtoi
0x1800bb4e0  mov     [rsp+1A8h+var_40], eax
0x1800bb4e7  mov     [rsp+1A8h+var_3C], r12b
0x1800bb4ef  lea     rdx, [rsp+1A8h+instance]
0x1800bb4f7  mov     rcx, r15; self
0x1800bb4fa  call    MI_Instance_Destruct
0x1800bb4ff  nop
0x1800bb500  mov     rcx, [rsp+1A8h+var_158]
0x1800bb505  test    rcx, rcx
0x1800bb508  jz      short loc_1800BB519
0x1800bb50a  mov     rax, [rcx]
0x1800bb50d  mov     edx, r12d
  ... truncated ...
```
