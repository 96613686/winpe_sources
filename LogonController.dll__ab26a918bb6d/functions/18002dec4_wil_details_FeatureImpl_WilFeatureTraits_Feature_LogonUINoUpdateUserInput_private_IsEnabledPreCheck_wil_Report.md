# wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonUINoUpdateUserInput>::__private_IsEnabledPreCheck(wil::ReportingKind)

- ea: `0x18002dec4`
- end: `0x18002e186`
- name: `?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_LogonUINoUpdateUserInput@@@details@wil@@QEAA_NW4ReportingKind@3@@Z`
- size: `706`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800268e0`
- `0x18002d7f0`
- `0x18002d920`
- `0x18002d9d0`

## callees

- `0x18000b290`
- `0x18000ba40`
- `0x18000ba60`
- `0x18000baa4`
- `0x18000bac8`
- `0x18000bd70`
- `0x180025948`
- `0x18002dec4`
- `0x180043c64`
- `0x18009d010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18002e01a`
- `KERNEL32!CreateThreadpoolTimer` at `0x18002e01a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002e058`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002e0b3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002e058`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002e0b3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002e06a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002e11d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002e06a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002e11d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonUINoUpdateUserInput>::__private_IsEnabledPreCheck(
        __int64 a1,
        char a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned int v5; // ebx
  volatile signed __int32 *v6; // rdi
  wil *i; // rcx
  signed __int32 v8; // edx
  BOOL v9; // r14d
  unsigned __int32 v10; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  void (__fastcall *v13)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  wil *v14; // rcx
  const char *v15; // [rsp+20h] [rbp-29h]
  _QWORD v16[2]; // [rsp+50h] [rbp+7h] BYREF
  unsigned int v17[4]; // [rsp+60h] [rbp+17h]
  int v18; // [rsp+B0h] [rbp+67h] BYREF
  __int16 v19; // [rsp+B4h] [rbp+6Bh]
  int v20; // [rsp+B8h] [rbp+6Fh] BYREF
  __int64 v21; // [rsp+C0h] [rbp+77h] BYREF
  char v22; // [rsp+C8h] [rbp+7Fh] BYREF

  LOBYTE(v20) = a2;
  v5 = *(_DWORD *)Feature_LogonUINoUpdateUserInput__descriptor;
  if ( (*(_DWORD *)Feature_LogonUINoUpdateUserInput__descriptor & 4) == 0 )
  {
    v21 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonUINoUpdateUserInput>::GetCachedFeatureEnabledState(
                       a1,
                       &v22);
    v5 = v21;
  }
  v18 = 0;
  v19 = 3;
  v20 = 3;
  v6 = (volatile signed __int32 *)(a1 + 8);
  *(_OWORD *)v17 = 0;
  for ( i = (wil *)*(unsigned int *)v6; ; i = (wil *)v10 )
  {
    v8 = (unsigned int)i | 2;
    v9 = ((unsigned int)i | 2) == (_DWORD)i;
    if ( ((unsigned int)i | 2) != (_DWORD)i )
      v8 = (unsigned int)i | 3;
    v10 = _InterlockedCompareExchange(v6, v8, (signed __int32)i);
    if ( (_DWORD)i == v10 )
      break;
  }
  LOBYTE(i) = ((unsigned __int8)i & 1) == 0;
  if ( ((unsigned __int8)i & ((v8 & 1) != 0)) != 0
    && wil::details::g_enabledStateManager
    && !wil::ProcessShutdownInProgress(i) )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( wil::details::g_enabledStateManager )
    {
      if ( !wil::ProcessShutdownInProgress(v14) )
      {
        v16[0] = 30723191;
        v16[1] = v6;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800D35D8, v16, 0x10u);
        if ( !byte_1800D35D0 )
        {
          if ( !qword_1800D35C8 )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v21);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                &wil::details::g_enabledStateManager,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &qword_1800D35C8,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v21);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&qword_1800D35C8, &byte_1800D35D0, 300000);
        }
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( v17[1] )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x1D4CC77, v17[2], v17[1], a4, v15);
  if ( !v9 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_1800D3620 )
    {
      qword_1800D3620 = 0;
      v13 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v13 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v13(&qword_1800D3620, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( (v5 & 0x400) != 0 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x1D4CC77, (v5 >> 11 << 31) + 2, 0, a4, v15);
  if ( !v9 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(a3) = 3;
      g_wil_details_realtimeFeatureUsageHook(30723191, 2, a3);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(30723191, &v18, 0, 1, &v20, 0, 0, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x18002dec4  mov     byte ptr [rsp-8+arg_8], dl
0x18002dec8  push    rbp
0x18002dec9  push    rbx
0x18002deca  push    rdi
0x18002decb  push    r14
0x18002decd  lea     rbp, [rsp-3Fh]
0x18002ded2  sub     rsp, 88h
0x18002ded9  mov     rdi, rcx
0x18002dedc  mov     rax, cs:Feature_LogonUINoUpdateUserInput__descriptor
0x18002dee3  mov     ebx, [rax]
0x18002dee5  test    bl, 4
0x18002dee8  jz      loc_18002E0F2
0x18002deee  xor     eax, eax
0x18002def0  mov     [rbp+57h+arg_0], eax
0x18002def3  mov     [rbp+57h+arg_4], 3
0x18002def9  mov     [rbp+57h+arg_8], 3
0x18002df00  add     rdi, 8
0x18002df04  xorps   xmm0, xmm0
0x18002df07  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18002df0b  mov     ecx, [rdi]
0x18002df0d  mov     edx, ecx
0x18002df0f  or      edx, 2
0x18002df12  xor     r14d, r14d
0x18002df15  cmp     edx, ecx
0x18002df17  setz    r14b
0x18002df1b  mov     eax, edx
0x18002df1d  or      eax, 1
0x18002df20  cmp     edx, ecx
0x18002df22  cmovnz  edx, eax
0x18002df25  mov     eax, ecx
0x18002df27  lock cmpxchg [rdi], edx
0x18002df2b  jz      short loc_18002DF31
0x18002df2d  mov     ecx, eax
0x18002df2f  jmp     short loc_18002DF0D
0x18002df31  test    cl, 1
0x18002df34  setz    cl; this
0x18002df37  test    dl, 1
0x18002df3a  setnz   al
0x18002df3d  test    al, cl
0x18002df3f  mov     eax, 0
0x18002df44  setnz   al
0x18002df47  test    eax, eax
0x18002df49  jz      short loc_18002DF59
0x18002df4b  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002df51  test    eax, eax
0x18002df53  jnz     loc_18002E109
0x18002df59  mov     edi, 1D4CC77h
0x18002df5e  cmp     [rbp+57h+var_40+4], 0
0x18002df62  ja      loc_18002E143
0x18002df68  test    r14d, r14d
0x18002df6b  jnz     short loc_18002DF7B
0x18002df6d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002df73  test    eax, eax
0x18002df75  jnz     loc_18002E063
0x18002df7b  bt      ebx, 0Ah
0x18002df7f  jb      loc_18002E16B
0x18002df85  test    r14d, r14d
0x18002df88  jz      short loc_18002DF99
0x18002df8a  mov     al, 1
0x18002df8c  add     rsp, 88h
0x18002df93  pop     r14
0x18002df95  pop     rdi
0x18002df96  pop     rbx
0x18002df97  pop     rbp
0x18002df98  retn
0x18002df99  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18002dfa0  test    rax, rax
0x18002dfa3  jz      short loc_18002DFB4
0x18002dfa5  mov     r8b, 3
0x18002dfa8  mov     edx, 2
0x18002dfad  mov     ecx, edi
0x18002dfaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfb4  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18002dfbb  test    rax, rax
0x18002dfbe  jz      short loc_18002DF8A
0x18002dfc0  mov     [rsp+0A0h+var_68], 1
0x18002dfc9  mov     [rsp+0A0h+var_70], 0
0x18002dfce  mov     [rsp+0A0h+var_78], 0
0x18002dfd7  lea     rdx, [rbp+57h+arg_8]
0x18002dfdb  mov     [rsp+0A0h+var_80], rdx
0x18002dfe0  mov     r9d, 1
0x18002dfe6  xor     r8d, r8d
0x18002dfe9  lea     rdx, [rbp+57h+arg_0]
0x18002dfed  mov     ecx, edi
0x18002dfef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dff4  jmp     short loc_18002DF8A
0x18002dff6  cmp     cs:qword_1800D35C8, 0
0x18002dffe  jnz     short loc_18002E038
0x18002e000  lea     rcx, [rbp+57h+arg_10]; this
0x18002e004  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002e009  xor     r8d, r8d; pcbe
0x18002e00c  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18002e013  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002e01a  call    cs:__imp_CreateThreadpoolTimer
0x18002e020  mov     rdx, rax
0x18002e023  lea     rcx, qword_1800D35C8
0x18002e02a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002e02f  lea     rcx, [rbp+57h+arg_10]; this
0x18002e033  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002e038  mov     r8d, 493E0h
0x18002e03e  lea     rdx, byte_1800D35D0
0x18002e045  lea     rcx, qword_1800D35C8
0x18002e04c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002e051  lea     rcx, SRWLock; SRWLock
0x18002e058  call    cs:__imp_ReleaseSRWLockExclusive
0x18002e05e  jmp     loc_18002DF59
0x18002e063  lea     rcx, SRWLock; SRWLock
0x18002e06a  call    cs:__imp_AcquireSRWLockExclusive
0x18002e070  cmp     cs:qword_1800D3620, 0
0x18002e078  jnz     short loc_18002E0AC
0x18002e07a  mov     cs:qword_1800D3620, 0
0x18002e085  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18002e08c  test    rax, rax
0x18002e08f  jz      loc_18002E156
0x18002e095  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002e099  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18002e0a0  lea     rcx, qword_1800D3620
0x18002e0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0ac  lea     rcx, SRWLock; SRWLock
0x18002e0b3  call    cs:__imp_ReleaseSRWLockExclusive
0x18002e0b9  jmp     loc_18002DF7B
0x18002e0be  mov     [rbp+57h+var_50], 1D4CC77h
0x18002e0c6  mov     [rbp+57h+var_48], rdi
0x18002e0ca  mov     r8d, 10h; unsigned __int64
0x18002e0d0  lea     rdx, [rbp+57h+var_50]; void *
0x18002e0d4  lea     rcx, qword_1800D35D8; this
0x18002e0db  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002e0e0  cmp     cs:byte_1800D35D0, 0
0x18002e0e7  jnz     loc_18002E051
0x18002e0ed  jmp     loc_18002DFF6
0x18002e0f2  lea     rdx, [rbp+57h+arg_18]
0x18002e0f6  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_LogonUINoUpdateUserInput@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonUINoUpdateUserInput>::GetCachedFeatureEnabledState(void)
0x18002e0fb  mov     rdx, [rax]
0x18002e0fe  mov     [rbp+57h+arg_10], rdx
0x18002e102  mov     ebx, edx
0x18002e104  jmp     loc_18002DEEE
0x18002e109  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002e10e  test    al, al
0x18002e110  jnz     loc_18002DF59
0x18002e116  lea     rcx, SRWLock; SRWLock
0x18002e11d  call    cs:__imp_AcquireSRWLockExclusive
0x18002e123  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002e129  test    eax, eax
0x18002e12b  jz      loc_18002E051
0x18002e131  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002e136  test    al, al
0x18002e138  jnz     loc_18002E051
0x18002e13e  jmp     loc_18002E0BE
0x18002e143  mov     r8d, [rbp+57h+var_40+4]; unsigned int
0x18002e147  mov     edx, [rbp+57h+var_40+8]; unsigned int
0x18002e14a  mov     ecx, edi; this
0x18002e14c  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18002e151  jmp     loc_18002DF68
0x18002e156  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18002e15d  test    rax, rax
0x18002e160  jz      loc_18002E0AC
0x18002e166  jmp     loc_18002E095
0x18002e16b  shr     ebx, 0Bh
0x18002e16e  and     ebx, 1
0x18002e171  shl     ebx, 1Fh
0x18002e174  lea     edx, [rbx+2]; unsigned int
0x18002e177  xor     r8d, r8d; unsigned int
0x18002e17a  mov     ecx, edi; this
0x18002e17c  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18002e181  jmp     loc_18002DF85
```
