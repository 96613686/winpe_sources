# KSMidiInDevice::Initialize(ushort const *,void *,uint,_MidiTransport,ulong,ulong *,IMidiCallback *,__int64,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004)

- ea: `0x180049100`
- end: `0x1800494cb`
- name: `?Initialize@KSMidiInDevice@@QEAAJPEBGPEAXIW4_MidiTransport@@KPEAKPEAUIMidiCallback@@_JW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@@Z`
- size: `971`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180043eb4`

## callees

- `0x180005044`
- `0x18000b374`
- `0x18000b394`
- `0x180010b10`
- `0x180043a74`
- `0x180047b58`
- `0x180048b80`
- `0x180048e60`
- `0x180049100`
- `0x18005813c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800492d2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180049499`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800492d2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180049499`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049293`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004946e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049293`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004946e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004945b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004945b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180049266`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180049441`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180049266`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180049441`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004928b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049466`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004928b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049466`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KSMidiInDevice::Initialize(
        __int64 a1,
        const unsigned __int16 *a2,
        void *a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        _DWORD *a7,
        void *Block,
        __int64 a9)
{
  void *v13; // rbx
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 v17; // r13
  _DWORD *v18; // r14
  int v19; // ebp
  __int64 v20; // rdx
  __int64 v21; // rsi
  HANDLE Thread; // rsi
  const char *v23; // r9
  char *v24; // rbp
  DWORD LastError; // ebx
  __int64 v26; // rdx
  void *v27; // rcx
  int v28; // eax
  unsigned int v29; // edi
  void *v30; // rbx
  void *v31; // rbx
  __int64 v32; // rsi
  HANDLE v33; // rsi
  char *v34; // rbp
  DWORD v35; // ebx
  int dwCreationFlags; // [rsp+20h] [rbp-88h]
  int dwCreationFlagsa; // [rsp+20h] [rbp-88h]
  int dwCreationFlagsb; // [rsp+20h] [rbp-88h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v13 = Block;
  if ( !Block )
  {
    v14 = -2147024809;
    v15 = 876;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
      (const char *)v14,
      dwCreationFlags);
    return v14;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl) )
  {
    v17 = a9;
    v18 = a7;
    v19 = KSMidiDevice::Initialize(a1, a2, a3, a4, 1, &a6, a7, 0, 0, (__int64)v13, a9);
    if ( v19 < 0 )
    {
      v20 = 880;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
        (const char *)(unsigned int)v19,
        dwCreationFlagsa);
      return (unsigned int)v19;
    }
    if ( *(_DWORD *)(a1 + 76) != 1 )
      return 0;
    *(_DWORD *)(a1 + 104) = *v18;
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      a1 + 128,
      1);
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      a1 + 136,
      1);
    v21 = *(_QWORD *)(a1 + 112);
    *(_QWORD *)(a1 + 112) = v13;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 8LL))(v13);
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    *(_QWORD *)(a1 + 120) = v17;
    Thread = CreateThread(0, 0, KSMidiInDevice::MidiInWorker, (LPVOID)a1, 0, 0);
    v24 = *(char **)(a1 + 144);
    if ( (unsigned __int64)(v24 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v24);
      SetLastError(LastError);
    }
    *(_QWORD *)(a1 + 144) = Thread;
    if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v26 = 895;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v26,
               (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
               v23);
    }
    if ( WaitForSingleObject(*(HANDLE *)(a1 + 136), 0x7530u) )
    {
      v15 = 897;
LABEL_35:
      v14 = -2147467259;
      goto LABEL_3;
    }
    goto LABEL_36;
  }
  v19 = KSMidiDevice::Initialize(a1, a2, a3, a4, 1, &a6, 0);
  if ( v19 < 0 )
  {
    v20 = 904;
    goto LABEL_7;
  }
  v27 = *(void **)(a1 + 88);
  if ( !v27 )
  {
    v18 = a7;
    *(_DWORD *)(a1 + 104) = *a7;
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      a1 + 128,
      1);
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      a1 + 136,
      1);
    v32 = *(_QWORD *)(a1 + 112);
    *(_QWORD *)(a1 + 112) = v13;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 8LL))(v13);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    *(_QWORD *)(a1 + 120) = a9;
    v33 = CreateThread(0, 0, KSMidiInDevice::MidiInWorker, (LPVOID)a1, 0, 0);
    v34 = *(char **)(a1 + 144);
    if ( (unsigned __int64)(v34 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v35 = GetLastError();
      CloseHandle(v34);
      SetLastError(v35);
    }
    *(_QWORD *)(a1 + 144) = v33;
    if ( (((unsigned __int64)v33 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v26 = 924;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v26,
               (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
               v23);
    }
    if ( WaitForSingleObject(*(HANDLE *)(a1 + 136), 0x7530u) )
    {
      v15 = 926;
      goto LABEL_35;
    }
LABEL_36:
    *v18 = *(_DWORD *)(a1 + 104);
    return 0;
  }
  Block = 0;
  v28 = CMidiXProc::Initialize(v27, (__int64)v13, a9);
  v29 = v28;
  if ( v28 >= 0 )
  {
    v31 = Block;
    if ( Block )
    {
      MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE((MEMORY_MAPPED_PIPE *)Block);
      operator delete(v31);
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x38E,
    (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
    (const char *)(unsigned int)v28,
    dwCreationFlagsb);
  v30 = Block;
  if ( Block )
  {
    MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE((MEMORY_MAPPED_PIPE *)Block);
    operator delete(v30);
  }
  return v29;
}

```

## disassembly

```asm
0x180049100  push    rbx
0x180049102  push    rbp
0x180049103  push    rsi
0x180049104  push    rdi
0x180049105  push    r12
0x180049107  push    r13
0x180049109  push    r14
0x18004910b  push    r15
0x18004910d  sub     rsp, 68h
0x180049111  mov     ebp, r9d
0x180049114  mov     r15, r8
0x180049117  mov     r12, rdx
0x18004911a  mov     rdi, rcx
0x18004911d  mov     rbx, [rsp+0A8h+Block]
0x180049125  xor     r13d, r13d
0x180049128  test    rbx, rbx
0x18004912b  jnz     short loc_180049155
0x18004912d  mov     ebx, 80070057h
0x180049132  mov     edx, 36Ch; void *
0x180049137  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x18004913e  mov     r9d, ebx; char *
0x180049141  mov     rcx, [rsp+0A8h]; this
0x180049149  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004914e  mov     eax, ebx
0x180049150  jmp     loc_1800494BA
0x180049155  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x18004915c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x180049161  mov     esi, 1
0x180049166  mov     r9d, ebp
0x180049169  mov     r8, r15
0x18004916c  mov     rdx, r12
0x18004916f  mov     rcx, rdi
0x180049172  test    al, al
0x180049174  lea     rax, [rsp+0A8h+arg_28]
0x18004917c  jz      loc_1800492EA
0x180049182  mov     r13, [rsp+0A8h+arg_40]
0x18004918a  mov     [rsp+0A8h+var_58], r13
0x18004918f  mov     [rsp+0A8h+var_60], rbx
0x180049194  mov     [rsp+0A8h+var_68], 0
0x18004919c  mov     [rsp+0A8h+var_70], 0
0x1800491a4  mov     r14, [rsp+0A8h+arg_30]
0x1800491ac  mov     [rsp+0A8h+var_78], r14
0x1800491b1  mov     [rsp+0A8h+lpThreadId], rax
0x1800491b6  mov     [rsp+0A8h+dwCreationFlags], esi; int
0x1800491ba  call    ?Initialize@KSMidiDevice@@MEAAJPEBGPEAXIW4_MidiTransport@@AEAKPEAKW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@W4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@PEAUIMidiCallback@@_J@Z; KSMidiDevice::Initialize(ushort const *,void *,uint,_MidiTransport,ulong &,ulong *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,IMidiCallback *,__int64)
0x1800491bf  mov     ebp, eax
0x1800491c1  test    eax, eax
0x1800491c3  jns     short loc_1800491E8
0x1800491c5  mov     edx, 370h; void *
0x1800491ca  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x1800491d1  mov     r9d, ebp; char *
0x1800491d4  mov     rcx, [rsp+0A8h]; this
0x1800491dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800491e1  mov     eax, ebp
0x1800491e3  jmp     loc_1800494BA
0x1800491e8  cmp     [rdi+4Ch], esi
0x1800491eb  jnz     loc_1800494B8
0x1800491f1  mov     eax, [r14]
0x1800491f4  mov     [rdi+68h], eax
0x1800491f7  lea     rcx, [rdi+80h]
0x1800491fe  mov     edx, esi
0x180049200  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180049205  lea     r15, [rdi+88h]
0x18004920c  mov     edx, esi
0x18004920e  mov     rcx, r15
0x180049211  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180049216  nop
0x180049217  mov     rsi, [rdi+70h]
0x18004921b  mov     [rdi+70h], rbx
0x18004921f  mov     rax, [rbx]
0x180049222  mov     rcx, rbx
0x180049225  mov     rax, [rax+8]
0x180049229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004922e  test    rsi, rsi
0x180049231  jz      short loc_180049243
0x180049233  mov     rax, [rsi]
0x180049236  mov     rcx, rsi
0x180049239  mov     rax, [rax+10h]
0x18004923d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049242  nop
0x180049243  mov     [rdi+78h], r13
0x180049247  mov     [rsp+0A8h+lpThreadId], 0; lpThreadId
0x180049250  mov     [rsp+0A8h+dwCreationFlags], 0; dwCreationFlags
0x180049258  mov     r9, rdi; lpParameter
0x18004925b  lea     r8, ?MidiInWorker@KSMidiInDevice@@CAKPEAX@Z; lpStartAddress
0x180049262  xor     edx, edx; dwStackSize
0x180049264  xor     ecx, ecx; lpThreadAttributes
0x180049266  call    cs:__imp_CreateThread
0x18004926c  mov     rsi, rax
0x18004926f  mov     rbp, [rdi+90h]
0x180049276  lea     rdx, [rbp-1]
0x18004927a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18004927e  ja      short loc_180049299
0x180049280  call    cs:__imp_GetLastError
0x180049286  mov     ebx, eax
0x180049288  mov     rcx, rbp; hObject
0x18004928b  call    cs:__imp_CloseHandle
0x180049291  mov     ecx, ebx; dwErrCode
0x180049293  call    cs:__imp_SetLastError
0x180049299  mov     [rdi+90h], rsi
0x1800492a0  lea     rax, [rsi+1]
0x1800492a4  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800492aa  jnz     short loc_1800492CA
0x1800492ac  mov     edx, 37Fh; void *
0x1800492b1  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x1800492b8  mov     rcx, [rsp+0A8h]; this
0x1800492c0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800492c5  jmp     loc_1800494BA
0x1800492ca  mov     edx, 7530h; dwMilliseconds
0x1800492cf  mov     rcx, [r15]; hHandle
0x1800492d2  call    cs:__imp_WaitForSingleObject
0x1800492d8  test    eax, eax
0x1800492da  jz      loc_1800494B2
0x1800492e0  mov     edx, 381h
0x1800492e5  jmp     loc_1800494A8
0x1800492ea  mov     dword ptr [rsp+0A8h+var_78], r13d
0x1800492ef  mov     [rsp+0A8h+lpThreadId], rax
0x1800492f4  mov     [rsp+0A8h+dwCreationFlags], esi
0x1800492f8  call    ?Initialize@KSMidiDevice@@MEAAJPEBGPEAXIW4_MidiTransport@@AEAKW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@@Z; KSMidiDevice::Initialize(ushort const *,void *,uint,_MidiTransport,ulong &,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004)
0x1800492fd  mov     ebp, eax
0x1800492ff  test    eax, eax
0x180049301  jns     short loc_18004930D
0x180049303  mov     edx, 388h
0x180049308  jmp     loc_1800491CA
0x18004930d  mov     rcx, [rdi+58h]; lpParameter
0x180049311  test    rcx, rcx
0x180049314  jz      loc_1800493C3
0x18004931a  mov     [rsp+0A8h+Block], r13
0x180049322  lea     r8, [rdi+50h]
0x180049326  mov     rax, [rsp+0A8h+arg_40]
0x18004932e  mov     [rsp+0A8h+lpThreadId], rax; __int64
0x180049333  mov     qword ptr [rsp+0A8h+dwCreationFlags], rbx; int
0x180049338  lea     r9, [rsp+0A8h+Block]
0x180049340  mov     rdx, [rsp+0A8h+arg_30]
0x180049348  call    ?Initialize@CMidiXProc@@QEAAJPEAKAEAV?$unique_ptr@UMEMORY_MAPPED_PIPE@@U?$default_delete@UMEMORY_MAPPED_PIPE@@@std@@@std@@1PEAUIMidiCallback@@_JH@Z; CMidiXProc::Initialize(ulong *,std::unique_ptr<MEMORY_MAPPED_PIPE> &,std::unique_ptr<MEMORY_MAPPED_PIPE> &,IMidiCallback *,__int64,int)
0x18004934d  mov     edi, eax
0x18004934f  test    eax, eax
0x180049351  jns     short loc_180049398
0x180049353  mov     rcx, [rsp+0A8h]; this
0x18004935b  mov     r9d, eax; char *
0x18004935e  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180049365  mov     edx, 38Eh; void *
0x18004936a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004936f  mov     rbx, [rsp+0A8h+Block]
0x180049377  test    rbx, rbx
0x18004937a  jz      short loc_180049391
0x18004937c  mov     rcx, rbx; this
0x18004937f  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x180049384  mov     edx, 68h ; 'h'
0x180049389  mov     rcx, rbx; Block
0x18004938c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180049391  mov     eax, edi
0x180049393  jmp     loc_1800494BA
0x180049398  mov     rbx, [rsp+0A8h+Block]
0x1800493a0  test    rbx, rbx
0x1800493a3  jz      loc_1800494B8
0x1800493a9  mov     rcx, rbx; this
0x1800493ac  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x1800493b1  mov     edx, 68h ; 'h'
0x1800493b6  mov     rcx, rbx; Block
0x1800493b9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800493be  jmp     loc_1800494B8
0x1800493c3  mov     r14, [rsp+0A8h+arg_30]
0x1800493cb  mov     eax, [r14]
0x1800493ce  mov     [rdi+68h], eax
0x1800493d1  lea     rcx, [rdi+80h]
0x1800493d8  mov     edx, esi
0x1800493da  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800493df  lea     r15, [rdi+88h]
0x1800493e6  mov     edx, esi
0x1800493e8  mov     rcx, r15
0x1800493eb  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800493f0  nop
0x1800493f1  mov     rsi, [rdi+70h]
0x1800493f5  mov     [rdi+70h], rbx
0x1800493f9  mov     rax, [rbx]
0x1800493fc  mov     rcx, rbx
0x1800493ff  mov     rax, [rax+8]
0x180049403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049408  test    rsi, rsi
0x18004940b  jz      short loc_18004941D
0x18004940d  mov     rax, [rsi]
0x180049410  mov     rcx, rsi
0x180049413  mov     rax, [rax+10h]
0x180049417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004941c  nop
0x18004941d  mov     rax, [rsp+0A8h+arg_40]
0x180049425  mov     [rdi+78h], rax
0x180049429  mov     [rsp+0A8h+lpThreadId], r13; lpThreadId
0x18004942e  mov     [rsp+0A8h+dwCreationFlags], r13d; dwCreationFlags
0x180049433  mov     r9, rdi; lpParameter
0x180049436  lea     r8, ?MidiInWorker@KSMidiInDevice@@CAKPEAX@Z; lpStartAddress
0x18004943d  xor     edx, edx; dwStackSize
0x18004943f  xor     ecx, ecx; lpThreadAttributes
0x180049441  call    cs:__imp_CreateThread
0x180049447  mov     rsi, rax
0x18004944a  mov     rbp, [rdi+90h]
0x180049451  lea     rdx, [rbp-1]
0x180049455  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180049459  ja      short loc_180049474
0x18004945b  call    cs:__imp_GetLastError
0x180049461  mov     ebx, eax
0x180049463  mov     rcx, rbp; hObject
0x180049466  call    cs:__imp_CloseHandle
0x18004946c  mov     ecx, ebx; dwErrCode
0x18004946e  call    cs:__imp_SetLastError
0x180049474  mov     [rdi+90h], rsi
0x18004947b  lea     rax, [rsi+1]
0x18004947f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180049485  jnz     short loc_180049491
0x180049487  mov     edx, 39Ch
0x18004948c  jmp     loc_1800492B1
0x180049491  mov     edx, 7530h; dwMilliseconds
0x180049496  mov     rcx, [r15]; hHandle
0x180049499  call    cs:__imp_WaitForSingleObject
0x18004949f  test    eax, eax
0x1800494a1  jz      short loc_1800494B2
0x1800494a3  mov     edx, 39Eh
0x1800494a8  mov     ebx, 80004005h
0x1800494ad  jmp     loc_180049137
0x1800494b2  mov     eax, [rdi+68h]
0x1800494b5  mov     [r14], eax
0x1800494b8  xor     eax, eax
0x1800494ba  add     rsp, 68h
0x1800494be  pop     r15
0x1800494c0  pop     r14
0x1800494c2  pop     r13
0x1800494c4  pop     r12
0x1800494c6  pop     rdi
0x1800494c7  pop     rsi
0x1800494c8  pop     rbp
0x1800494c9  pop     rbx
0x1800494ca  retn
```
