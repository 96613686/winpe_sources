# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180008784`
- end: `0x1800089f1`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `621`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180008650`

## callees

- `0x180004aa8`
- `0x180008784`
- `0x18000af9c`
- `0x18000bb20`
- `0x18000d010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800088b8`
- `msvcrt!memcpy_s` at `0x1800088b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000883a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008925`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000883a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008925`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800088d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008971`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800088d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008971`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        __int64 a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  int *v10; // rax
  __int64 v11; // r8
  int v12; // esi
  unsigned int v13; // ebp
  unsigned int v14; // r12d
  int v15; // r13d
  unsigned int v16; // r14d
  void (__fastcall *v17)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v19; // rdx
  void (__fastcall *v20)(_QWORD, __int64, _QWORD, _QWORD); // rax
  _DWORD Source[2]; // [rsp+38h] [rbp-60h] BYREF
  __int64 v25; // [rsp+40h] [rbp-58h]
  _BYTE v26[80]; // [rsp+48h] [rbp-50h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v26, a1, a5);
  v12 = *v10;
  v13 = v10[1];
  v14 = v10[2];
  v15 = v10[4];
  v16 = 1;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v12
    && wil::details::g_enabledStateManager
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( wil::details::g_enabledStateManager
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      Source[0] = a2;
      Source[1] = 0;
      v25 = a1;
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180015718, 0x10u) )
      {
        memcpy_s(
          Destination,
          (qword_180015728 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_180015728),
          Source,
          0x10u);
        Destination = (char *)Destination + 16;
      }
      wil::details::EnabledStateManager::EnsureTimerUnderLock((struct _TP_TIMER **)&wil::details::g_enabledStateManager);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( v13 )
  {
    v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v17(a2, v14, v13, 0);
    }
  }
  if ( !v15 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_180015760 )
    {
      qword_180015760 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180015760, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v19 = a5;
    if ( a4 )
      LODWORD(v19) = a5 | 0x80000000;
    v20 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v20 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v20(a2, v19, 0, 0);
    }
  }
  if ( v15 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v11) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v11);
  }
  return v16;
}

```

## disassembly

```asm
0x180008784  mov     [rsp+arg_10], rbx
0x180008789  push    rbp
0x18000878a  push    rsi
0x18000878b  push    rdi
0x18000878c  push    r12
0x18000878e  push    r13
0x180008790  push    r14
0x180008792  push    r15
0x180008794  sub     rsp, 60h
0x180008798  mov     [rsp+98h+var_64], r9d
0x18000879d  mov     [rsp+98h+var_68], r8d
0x1800087a2  mov     edi, edx
0x1800087a4  mov     r15, rcx
0x1800087a7  mov     ebx, [rsp+98h+arg_20]
0x1800087ae  mov     r8d, ebx
0x1800087b1  mov     rdx, rcx
0x1800087b4  lea     rcx, [rsp+98h+var_50]
0x1800087b9  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800087be  mov     esi, [rax]
0x1800087c0  mov     ebp, [rax+4]
0x1800087c3  mov     r12d, [rax+8]
0x1800087c7  mov     r13d, [rax+10h]
0x1800087cb  mov     r14d, 1
0x1800087d1  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800087d8  test    rax, rax
0x1800087db  jz      short loc_1800087F5
0x1800087dd  test    ebx, ebx
0x1800087df  jz      short loc_1800087E9
0x1800087e1  lea     ecx, [rbx-64h]
0x1800087e4  cmp     ecx, 31h ; '1'
0x1800087e7  ja      short loc_1800087F5
0x1800087e9  mov     r8d, r14d
0x1800087ec  mov     edx, ebx
0x1800087ee  mov     ecx, edi
0x1800087f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087f5  test    esi, esi
0x1800087f7  jz      loc_1800088E1
0x1800087fd  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008803  xor     esi, esi
0x180008805  test    eax, eax
0x180008807  jz      loc_1800088DF
0x18000880d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, sil; bool wil::details::g_processShutdownInProgress
0x180008814  jnz     loc_1800088DF
0x18000881a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008821  test    rax, rax
0x180008824  jz      short loc_180008833
0x180008826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000882b  test    al, al
0x18000882d  jnz     loc_1800088DF
0x180008833  lea     rcx, SRWLock; SRWLock
0x18000883a  call    cs:__imp_AcquireSRWLockExclusive
0x180008840  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008846  test    eax, eax
0x180008848  jz      loc_1800088D1
0x18000884e  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, sil; bool wil::details::g_processShutdownInProgress
0x180008855  jnz     short loc_1800088D1
0x180008857  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000885e  test    rax, rax
0x180008861  jz      short loc_18000886C
0x180008863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008868  test    al, al
0x18000886a  jnz     short loc_1800088D1
0x18000886c  mov     [rsp+98h+Source], edi
0x180008870  xor     eax, eax
0x180008872  mov     [rsp+98h+var_5C], eax
0x180008876  mov     [rsp+98h+var_58], r15
0x18000887b  lea     r15d, [rax+10h]
0x18000887f  mov     edx, r15d; unsigned __int64
0x180008882  lea     rcx, qword_180015718; this
0x180008889  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000888e  test    al, al
0x180008890  jz      short loc_1800088C5
0x180008892  mov     rcx, cs:Destination; Destination
0x180008899  mov     rax, cs:qword_180015728
0x1800088a0  sub     rax, rcx
0x1800088a3  cmp     rcx, cs:qword_180015728
0x1800088aa  sbb     rdx, rdx
0x1800088ad  and     rdx, rax; DestinationSize
0x1800088b0  mov     r9d, r15d; SourceSize
0x1800088b3  lea     r8, [rsp+98h+Source]; Source
0x1800088b8  call    cs:__imp_memcpy_s
0x1800088be  add     cs:Destination, r15
0x1800088c5  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800088cc  call    ?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::EnsureTimerUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800088d1  lea     rcx, SRWLock; SRWLock
0x1800088d8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800088de  nop
0x1800088df  jmp     short loc_1800088E3
0x1800088e1  xor     esi, esi
0x1800088e3  test    ebp, ebp
0x1800088e5  jz      short loc_18000890F
0x1800088e7  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800088ee  test    rax, rax
0x1800088f1  jnz     short loc_1800088FF
0x1800088f3  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800088fa  test    rax, rax
0x1800088fd  jz      short loc_18000890F
0x1800088ff  xor     r9d, r9d
0x180008902  mov     r8d, ebp
0x180008905  mov     edx, r12d
0x180008908  mov     ecx, edi
0x18000890a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000890f  test    r13d, r13d
0x180008912  jnz     short loc_180008978
0x180008914  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000891a  test    eax, eax
0x18000891c  jz      short loc_180008978
0x18000891e  lea     rcx, SRWLock; SRWLock
0x180008925  call    cs:__imp_AcquireSRWLockExclusive
0x18000892b  cmp     cs:qword_180015760, rsi
0x180008932  jnz     short loc_18000896A
0x180008934  mov     cs:qword_180015760, rsi
0x18000893b  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180008942  test    rax, rax
0x180008945  jnz     short loc_180008953
0x180008947  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000894e  test    rax, rax
0x180008951  jz      short loc_18000896A
0x180008953  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008957  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000895e  lea     rcx, qword_180015760
0x180008965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000896a  lea     rcx, SRWLock; SRWLock
0x180008971  call    cs:__imp_ReleaseSRWLockExclusive
0x180008977  nop
0x180008978  cmp     [rsp+98h+var_68], esi
0x18000897c  jz      short loc_1800089AF
0x18000897e  mov     edx, ebx
0x180008980  cmp     [rsp+98h+var_64], esi
0x180008984  jz      short loc_18000898A
0x180008986  bts     edx, 1Fh
0x18000898a  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180008991  test    rax, rax
0x180008994  jnz     short loc_1800089A2
0x180008996  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000899d  test    rax, rax
0x1800089a0  jz      short loc_1800089AF
0x1800089a2  xor     r9d, r9d
0x1800089a5  xor     r8d, r8d
0x1800089a8  mov     ecx, edi
0x1800089aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089af  test    r13d, r13d
0x1800089b2  jnz     short loc_1800089D3
0x1800089b4  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800089bb  test    rax, rax
0x1800089be  jz      short loc_1800089D6
0x1800089c0  mov     r8b, [rsp+98h+arg_38]
0x1800089c8  mov     edx, ebx
0x1800089ca  mov     ecx, edi
0x1800089cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089d1  jmp     short loc_1800089D6
0x1800089d3  mov     r14d, esi
0x1800089d6  mov     eax, r14d
0x1800089d9  mov     rbx, [rsp+98h+arg_10]
0x1800089e1  add     rsp, 60h
0x1800089e5  pop     r15
0x1800089e7  pop     r14
0x1800089e9  pop     r13
0x1800089eb  pop     r12
0x1800089ed  pop     rdi
0x1800089ee  pop     rsi
0x1800089ef  pop     rbp
0x1800089f0  retn
```
