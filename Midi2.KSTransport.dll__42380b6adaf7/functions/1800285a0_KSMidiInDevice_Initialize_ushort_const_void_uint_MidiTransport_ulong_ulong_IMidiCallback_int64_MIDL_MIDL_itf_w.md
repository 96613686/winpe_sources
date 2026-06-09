# KSMidiInDevice::Initialize(ushort const *,void *,uint,_MidiTransport,ulong,ulong *,IMidiCallback *,__int64,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004)

- ea: `0x1800285a0`
- end: `0x18002898c`
- name: `?Initialize@KSMidiInDevice@@QEAAJPEBGPEAXIW4_MidiTransport@@KPEAKPEAUIMidiCallback@@_JW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@@Z`
- size: `1004`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800124c8`

## callees

- `0x180004434`
- `0x18000a7f4`
- `0x18000a814`
- `0x18000d13c`
- `0x180010f30`
- `0x1800270a8`
- `0x180028020`
- `0x180028300`
- `0x1800285a0`
- `0x18003cb40`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028777`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002895c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028777`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002895c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028738`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028931`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028738`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028931`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002891e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002891e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002870b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180028904`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002870b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180028904`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028730`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028929`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028730`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028929`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KSMidiInDevice::Initialize(
        __int64 a1,
        const unsigned __int16 *a2,
        void *a3,
        int a4,
        int a5,
        int a6,
        _DWORD *a7,
        void *Block,
        __int64 a9,
        unsigned int a10)
{
  void *v14; // rbx
  unsigned int v15; // ebx
  __int64 v16; // rdx
  __int64 v18; // r12
  _DWORD *v19; // r14
  int v20; // esi
  __int64 v21; // rdx
  __int64 v22; // rsi
  HANDLE Thread; // rsi
  const char *v24; // r9
  char *v25; // rbp
  DWORD LastError; // ebx
  __int64 v27; // rdx
  void *v28; // rcx
  int v29; // eax
  unsigned int v30; // edi
  void *v31; // rbx
  void *v32; // rbx
  __int64 v33; // rsi
  HANDLE v34; // rsi
  char *v35; // rbp
  DWORD v36; // ebx
  int dwCreationFlags; // [rsp+20h] [rbp-78h]
  int dwCreationFlagsa; // [rsp+20h] [rbp-78h]
  int dwCreationFlagsb; // [rsp+20h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v14 = Block;
  if ( !Block )
  {
    v15 = -2147024809;
    v16 = 876;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
      (const char *)v15,
      dwCreationFlags);
    return v15;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl) )
  {
    v18 = a9;
    v19 = a7;
    v20 = KSMidiDevice::Initialize(a1, a2, a3, a4, a5, &a6, a7, a10, 0, (__int64)v14, a9);
    if ( v20 < 0 )
    {
      v21 = 880;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
        (const char *)(unsigned int)v20,
        dwCreationFlagsa);
      return (unsigned int)v20;
    }
    if ( *(_DWORD *)(a1 + 76) != 1 )
      return 0;
    *(_DWORD *)(a1 + 104) = *v19;
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      a1 + 128,
      1);
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      a1 + 136,
      1);
    v22 = *(_QWORD *)(a1 + 112);
    *(_QWORD *)(a1 + 112) = v14;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 8LL))(v14);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    *(_QWORD *)(a1 + 120) = v18;
    Thread = CreateThread(0, 0, KSMidiInDevice::MidiInWorker, (LPVOID)a1, 0, 0);
    v25 = *(char **)(a1 + 144);
    if ( (unsigned __int64)(v25 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v25);
      SetLastError(LastError);
    }
    *(_QWORD *)(a1 + 144) = Thread;
    if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v27 = 895;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v27,
               (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
               v24);
    }
    if ( WaitForSingleObject(*(HANDLE *)(a1 + 136), 0x7530u) )
    {
      v16 = 897;
LABEL_35:
      v15 = -2147467259;
      goto LABEL_3;
    }
    goto LABEL_36;
  }
  v20 = KSMidiDevice::Initialize(a1, a2, a3, a4, a5, (__int64)&a6, a10);
  if ( v20 < 0 )
  {
    v21 = 904;
    goto LABEL_7;
  }
  v28 = *(void **)(a1 + 88);
  if ( !v28 )
  {
    v19 = a7;
    *(_DWORD *)(a1 + 104) = *a7;
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      a1 + 128,
      1);
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      a1 + 136,
      1);
    v33 = *(_QWORD *)(a1 + 112);
    *(_QWORD *)(a1 + 112) = v14;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 8LL))(v14);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    *(_QWORD *)(a1 + 120) = a9;
    v34 = CreateThread(0, 0, KSMidiInDevice::MidiInWorker, (LPVOID)a1, 0, 0);
    v35 = *(char **)(a1 + 144);
    if ( (unsigned __int64)(v35 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v36 = GetLastError();
      CloseHandle(v35);
      SetLastError(v36);
    }
    *(_QWORD *)(a1 + 144) = v34;
    if ( (((unsigned __int64)v34 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v27 = 924;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v27,
               (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
               v24);
    }
    if ( WaitForSingleObject(*(HANDLE *)(a1 + 136), 0x7530u) )
    {
      v16 = 926;
      goto LABEL_35;
    }
LABEL_36:
    *v19 = *(_DWORD *)(a1 + 104);
    return 0;
  }
  Block = 0;
  v29 = CMidiXProc::Initialize(v28, (__int64)v14, a9);
  v30 = v29;
  if ( v29 >= 0 )
  {
    v32 = Block;
    if ( Block )
    {
      MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE((MEMORY_MAPPED_PIPE *)Block);
      operator delete(v32);
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x38E,
    (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
    (const char *)(unsigned int)v29,
    dwCreationFlagsb);
  v31 = Block;
  if ( Block )
  {
    MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE((MEMORY_MAPPED_PIPE *)Block);
    operator delete(v31);
  }
  return v30;
}

```

## disassembly

```asm
0x1800285a0  push    rbx
0x1800285a2  push    rbp
0x1800285a3  push    rsi
0x1800285a4  push    rdi
0x1800285a5  push    r12
0x1800285a7  push    r14
0x1800285a9  push    r15
0x1800285ab  sub     rsp, 60h
0x1800285af  mov     esi, r9d
0x1800285b2  mov     rbp, r8
0x1800285b5  mov     r15, rdx
0x1800285b8  mov     rdi, rcx
0x1800285bb  mov     rbx, [rsp+98h+Block]
0x1800285c3  test    rbx, rbx
0x1800285c6  jnz     short loc_1800285F0
0x1800285c8  mov     ebx, 80070057h
0x1800285cd  mov     edx, 36Ch; void *
0x1800285d2  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x1800285d9  mov     r9d, ebx; char *
0x1800285dc  mov     rcx, [rsp+98h]; this
0x1800285e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800285e9  mov     eax, ebx
0x1800285eb  jmp     loc_18002897D
0x1800285f0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x1800285f7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x1800285fc  mov     r9d, esi
0x1800285ff  mov     r8, rbp
0x180028602  mov     rdx, r15
0x180028605  mov     rcx, rdi
0x180028608  test    al, al
0x18002860a  mov     eax, [rsp+98h+arg_48]
0x180028611  jz      loc_18002878F
0x180028617  mov     r12, [rsp+98h+arg_40]
0x18002861f  mov     [rsp+98h+var_48], r12
0x180028624  mov     [rsp+98h+var_50], rbx
0x180028629  mov     [rsp+98h+var_58], 0
0x180028631  mov     [rsp+98h+var_60], eax
0x180028635  mov     r14, [rsp+98h+arg_30]
0x18002863d  mov     [rsp+98h+var_68], r14
0x180028642  lea     rax, [rsp+98h+arg_28]
0x18002864a  mov     [rsp+98h+lpThreadId], rax
0x18002864f  mov     eax, [rsp+98h+arg_20]
0x180028656  mov     [rsp+98h+dwCreationFlags], eax; int
0x18002865a  call    ?Initialize@KSMidiDevice@@MEAAJPEBGPEAXIW4_MidiTransport@@AEAKPEAKW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@W4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@PEAUIMidiCallback@@_J@Z; KSMidiDevice::Initialize(ushort const *,void *,uint,_MidiTransport,ulong &,ulong *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,IMidiCallback *,__int64)
0x18002865f  mov     esi, eax
0x180028661  test    eax, eax
0x180028663  jns     short loc_180028688
0x180028665  mov     edx, 370h; void *
0x18002866a  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180028671  mov     r9d, esi; char *
0x180028674  mov     rcx, [rsp+98h]; this
0x18002867c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028681  mov     eax, esi
0x180028683  jmp     loc_18002897D
0x180028688  mov     esi, 1
0x18002868d  cmp     [rdi+4Ch], esi
0x180028690  jnz     loc_18002897B
0x180028696  mov     eax, [r14]
0x180028699  mov     [rdi+68h], eax
0x18002869c  lea     rcx, [rdi+80h]
0x1800286a3  mov     edx, esi
0x1800286a5  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800286aa  lea     r15, [rdi+88h]
0x1800286b1  mov     edx, esi
0x1800286b3  mov     rcx, r15
0x1800286b6  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800286bb  nop
0x1800286bc  mov     rsi, [rdi+70h]
0x1800286c0  mov     [rdi+70h], rbx
0x1800286c4  mov     rax, [rbx]
0x1800286c7  mov     rcx, rbx
0x1800286ca  mov     rax, [rax+8]
0x1800286ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286d3  test    rsi, rsi
0x1800286d6  jz      short loc_1800286E8
0x1800286d8  mov     rax, [rsi]
0x1800286db  mov     rcx, rsi
0x1800286de  mov     rax, [rax+10h]
0x1800286e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286e7  nop
0x1800286e8  mov     [rdi+78h], r12
0x1800286ec  mov     [rsp+98h+lpThreadId], 0; lpThreadId
0x1800286f5  mov     [rsp+98h+dwCreationFlags], 0; dwCreationFlags
0x1800286fd  mov     r9, rdi; lpParameter
0x180028700  lea     r8, ?MidiInWorker@KSMidiInDevice@@CAKPEAX@Z; lpStartAddress
0x180028707  xor     edx, edx; dwStackSize
0x180028709  xor     ecx, ecx; lpThreadAttributes
0x18002870b  call    cs:__imp_CreateThread
0x180028711  mov     rsi, rax
0x180028714  mov     rbp, [rdi+90h]
0x18002871b  lea     rdx, [rbp-1]
0x18002871f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180028723  ja      short loc_18002873E
0x180028725  call    cs:__imp_GetLastError
0x18002872b  mov     ebx, eax
0x18002872d  mov     rcx, rbp; hObject
0x180028730  call    cs:__imp_CloseHandle
0x180028736  mov     ecx, ebx; dwErrCode
0x180028738  call    cs:__imp_SetLastError
0x18002873e  mov     [rdi+90h], rsi
0x180028745  lea     rax, [rsi+1]
0x180028749  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002874f  jnz     short loc_18002876F
0x180028751  mov     edx, 37Fh; void *
0x180028756  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x18002875d  mov     rcx, [rsp+98h]; this
0x180028765  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002876a  jmp     loc_18002897D
0x18002876f  mov     edx, 7530h; dwMilliseconds
0x180028774  mov     rcx, [r15]; hHandle
0x180028777  call    cs:__imp_WaitForSingleObject
0x18002877d  test    eax, eax
0x18002877f  jz      loc_180028975
0x180028785  mov     edx, 381h
0x18002878a  jmp     loc_18002896B
0x18002878f  mov     dword ptr [rsp+98h+var_68], eax
0x180028793  lea     rax, [rsp+98h+arg_28]
0x18002879b  mov     [rsp+98h+lpThreadId], rax
0x1800287a0  mov     eax, [rsp+98h+arg_20]
0x1800287a7  mov     [rsp+98h+dwCreationFlags], eax
0x1800287ab  call    ?Initialize@KSMidiDevice@@MEAAJPEBGPEAXIW4_MidiTransport@@AEAKW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@@Z; KSMidiDevice::Initialize(ushort const *,void *,uint,_MidiTransport,ulong &,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004)
0x1800287b0  mov     esi, eax
0x1800287b2  test    eax, eax
0x1800287b4  jns     short loc_1800287C0
0x1800287b6  mov     edx, 388h
0x1800287bb  jmp     loc_18002866A
0x1800287c0  mov     rcx, [rdi+58h]; lpParameter
0x1800287c4  test    rcx, rcx
0x1800287c7  jz      loc_18002887A
0x1800287cd  mov     [rsp+98h+Block], 0
0x1800287d9  lea     r8, [rdi+50h]
0x1800287dd  mov     rax, [rsp+98h+arg_40]
0x1800287e5  mov     [rsp+98h+lpThreadId], rax; __int64
0x1800287ea  mov     qword ptr [rsp+98h+dwCreationFlags], rbx; int
0x1800287ef  lea     r9, [rsp+98h+Block]
0x1800287f7  mov     rdx, [rsp+98h+arg_30]
0x1800287ff  call    ?Initialize@CMidiXProc@@QEAAJPEAKAEAV?$unique_ptr@UMEMORY_MAPPED_PIPE@@U?$default_delete@UMEMORY_MAPPED_PIPE@@@std@@@std@@1PEAUIMidiCallback@@_JH@Z; CMidiXProc::Initialize(ulong *,std::unique_ptr<MEMORY_MAPPED_PIPE> &,std::unique_ptr<MEMORY_MAPPED_PIPE> &,IMidiCallback *,__int64,int)
0x180028804  mov     edi, eax
0x180028806  test    eax, eax
0x180028808  jns     short loc_18002884F
0x18002880a  mov     rcx, [rsp+98h]; this
0x180028812  mov     r9d, eax; char *
0x180028815  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x18002881c  mov     edx, 38Eh; void *
0x180028821  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028826  mov     rbx, [rsp+98h+Block]
0x18002882e  test    rbx, rbx
0x180028831  jz      short loc_180028848
0x180028833  mov     rcx, rbx; this
0x180028836  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x18002883b  mov     edx, 68h ; 'h'
0x180028840  mov     rcx, rbx; Block
0x180028843  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028848  mov     eax, edi
0x18002884a  jmp     loc_18002897D
0x18002884f  mov     rbx, [rsp+98h+Block]
0x180028857  test    rbx, rbx
0x18002885a  jz      loc_18002897B
0x180028860  mov     rcx, rbx; this
0x180028863  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x180028868  mov     edx, 68h ; 'h'
0x18002886d  mov     rcx, rbx; Block
0x180028870  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028875  jmp     loc_18002897B
0x18002887a  mov     r14, [rsp+98h+arg_30]
0x180028882  mov     eax, [r14]
0x180028885  mov     [rdi+68h], eax
0x180028888  lea     rcx, [rdi+80h]
0x18002888f  mov     esi, 1
0x180028894  mov     edx, esi
0x180028896  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002889b  lea     r15, [rdi+88h]
0x1800288a2  mov     edx, esi
0x1800288a4  mov     rcx, r15
0x1800288a7  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800288ac  nop
0x1800288ad  mov     rsi, [rdi+70h]
0x1800288b1  mov     [rdi+70h], rbx
0x1800288b5  mov     rax, [rbx]
0x1800288b8  mov     rcx, rbx
0x1800288bb  mov     rax, [rax+8]
0x1800288bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288c4  test    rsi, rsi
0x1800288c7  jz      short loc_1800288D9
0x1800288c9  mov     rax, [rsi]
0x1800288cc  mov     rcx, rsi
0x1800288cf  mov     rax, [rax+10h]
0x1800288d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288d8  nop
0x1800288d9  mov     rax, [rsp+98h+arg_40]
0x1800288e1  mov     [rdi+78h], rax
0x1800288e5  mov     [rsp+98h+lpThreadId], 0; lpThreadId
0x1800288ee  mov     [rsp+98h+dwCreationFlags], 0; dwCreationFlags
0x1800288f6  mov     r9, rdi; lpParameter
0x1800288f9  lea     r8, ?MidiInWorker@KSMidiInDevice@@CAKPEAX@Z; lpStartAddress
0x180028900  xor     edx, edx; dwStackSize
0x180028902  xor     ecx, ecx; lpThreadAttributes
0x180028904  call    cs:__imp_CreateThread
0x18002890a  mov     rsi, rax
0x18002890d  mov     rbp, [rdi+90h]
0x180028914  lea     rdx, [rbp-1]
0x180028918  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002891c  ja      short loc_180028937
0x18002891e  call    cs:__imp_GetLastError
0x180028924  mov     ebx, eax
0x180028926  mov     rcx, rbp; hObject
0x180028929  call    cs:__imp_CloseHandle
0x18002892f  mov     ecx, ebx; dwErrCode
0x180028931  call    cs:__imp_SetLastError
0x180028937  mov     [rdi+90h], rsi
0x18002893e  lea     rax, [rsi+1]
0x180028942  test    rax, 0FFFFFFFFFFFFFFFEh
0x180028948  jnz     short loc_180028954
0x18002894a  mov     edx, 39Ch
0x18002894f  jmp     loc_180028756
0x180028954  mov     edx, 7530h; dwMilliseconds
0x180028959  mov     rcx, [r15]; hHandle
0x18002895c  call    cs:__imp_WaitForSingleObject
0x180028962  test    eax, eax
0x180028964  jz      short loc_180028975
0x180028966  mov     edx, 39Eh
0x18002896b  mov     ebx, 80004005h
0x180028970  jmp     loc_1800285D2
0x180028975  mov     eax, [rdi+68h]
0x180028978  mov     [r14], eax
0x18002897b  xor     eax, eax
0x18002897d  add     rsp, 60h
0x180028981  pop     r15
0x180028983  pop     r14
0x180028985  pop     r12
0x180028987  pop     rdi
0x180028988  pop     rsi
0x180028989  pop     rbp
0x18002898a  pop     rbx
0x18002898b  retn
```
