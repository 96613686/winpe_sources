# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1800089dc`
- end: `0x180008c49`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `621`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1800088a8`

## callees

- `0x180005028`
- `0x1800089dc`
- `0x18000bf6c`
- `0x18000caf0`
- `0x180012010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008b10`
- `msvcrt!memcpy_s` at `0x180008b10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008bc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008bc9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008a92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b7d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008a92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b7d`

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
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18001B718, 0x10u) )
      {
        memcpy_s(
          Destination,
          (qword_18001B728 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_18001B728),
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
    if ( !qword_18001B760 )
    {
      qword_18001B760 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_18001B760, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x1800089dc  mov     [rsp+arg_10], rbx
0x1800089e1  push    rbp
0x1800089e2  push    rsi
0x1800089e3  push    rdi
0x1800089e4  push    r12
0x1800089e6  push    r13
0x1800089e8  push    r14
0x1800089ea  push    r15
0x1800089ec  sub     rsp, 60h
0x1800089f0  mov     [rsp+98h+var_64], r9d
0x1800089f5  mov     [rsp+98h+var_68], r8d
0x1800089fa  mov     edi, edx
0x1800089fc  mov     r15, rcx
0x1800089ff  mov     ebx, [rsp+98h+arg_20]
0x180008a06  mov     r8d, ebx
0x180008a09  mov     rdx, rcx
0x180008a0c  lea     rcx, [rsp+98h+var_50]
0x180008a11  call    wil_details_FeatureReporting_RecordUsageInCache
0x180008a16  mov     esi, [rax]
0x180008a18  mov     ebp, [rax+4]
0x180008a1b  mov     r12d, [rax+8]
0x180008a1f  mov     r13d, [rax+10h]
0x180008a23  mov     r14d, 1
0x180008a29  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180008a30  test    rax, rax
0x180008a33  jz      short loc_180008A4D
0x180008a35  test    ebx, ebx
0x180008a37  jz      short loc_180008A41
0x180008a39  lea     ecx, [rbx-64h]
0x180008a3c  cmp     ecx, 31h ; '1'
0x180008a3f  ja      short loc_180008A4D
0x180008a41  mov     r8d, r14d
0x180008a44  mov     edx, ebx
0x180008a46  mov     ecx, edi
0x180008a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a4d  test    esi, esi
0x180008a4f  jz      loc_180008B39
0x180008a55  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008a5b  xor     esi, esi
0x180008a5d  test    eax, eax
0x180008a5f  jz      loc_180008B37
0x180008a65  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, sil; bool wil::details::g_processShutdownInProgress
0x180008a6c  jnz     loc_180008B37
0x180008a72  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008a79  test    rax, rax
0x180008a7c  jz      short loc_180008A8B
0x180008a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a83  test    al, al
0x180008a85  jnz     loc_180008B37
0x180008a8b  lea     rcx, SRWLock; SRWLock
0x180008a92  call    cs:__imp_AcquireSRWLockExclusive
0x180008a98  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008a9e  test    eax, eax
0x180008aa0  jz      loc_180008B29
0x180008aa6  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, sil; bool wil::details::g_processShutdownInProgress
0x180008aad  jnz     short loc_180008B29
0x180008aaf  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008ab6  test    rax, rax
0x180008ab9  jz      short loc_180008AC4
0x180008abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ac0  test    al, al
0x180008ac2  jnz     short loc_180008B29
0x180008ac4  mov     [rsp+98h+Source], edi
0x180008ac8  xor     eax, eax
0x180008aca  mov     [rsp+98h+var_5C], eax
0x180008ace  mov     [rsp+98h+var_58], r15
0x180008ad3  lea     r15d, [rax+10h]
0x180008ad7  mov     edx, r15d; unsigned __int64
0x180008ada  lea     rcx, qword_18001B718; this
0x180008ae1  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008ae6  test    al, al
0x180008ae8  jz      short loc_180008B1D
0x180008aea  mov     rcx, cs:Destination; Destination
0x180008af1  mov     rax, cs:qword_18001B728
0x180008af8  sub     rax, rcx
0x180008afb  cmp     rcx, cs:qword_18001B728
0x180008b02  sbb     rdx, rdx
0x180008b05  and     rdx, rax; DestinationSize
0x180008b08  mov     r9d, r15d; SourceSize
0x180008b0b  lea     r8, [rsp+98h+Source]; Source
0x180008b10  call    cs:__imp_memcpy_s
0x180008b16  add     cs:Destination, r15
0x180008b1d  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180008b24  call    ?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::EnsureTimerUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180008b29  lea     rcx, SRWLock; SRWLock
0x180008b30  call    cs:__imp_ReleaseSRWLockExclusive
0x180008b36  nop
0x180008b37  jmp     short loc_180008B3B
0x180008b39  xor     esi, esi
0x180008b3b  test    ebp, ebp
0x180008b3d  jz      short loc_180008B67
0x180008b3f  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180008b46  test    rax, rax
0x180008b49  jnz     short loc_180008B57
0x180008b4b  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180008b52  test    rax, rax
0x180008b55  jz      short loc_180008B67
0x180008b57  xor     r9d, r9d
0x180008b5a  mov     r8d, ebp
0x180008b5d  mov     edx, r12d
0x180008b60  mov     ecx, edi
0x180008b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b67  test    r13d, r13d
0x180008b6a  jnz     short loc_180008BD0
0x180008b6c  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008b72  test    eax, eax
0x180008b74  jz      short loc_180008BD0
0x180008b76  lea     rcx, SRWLock; SRWLock
0x180008b7d  call    cs:__imp_AcquireSRWLockExclusive
0x180008b83  cmp     cs:qword_18001B760, rsi
0x180008b8a  jnz     short loc_180008BC2
0x180008b8c  mov     cs:qword_18001B760, rsi
0x180008b93  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180008b9a  test    rax, rax
0x180008b9d  jnz     short loc_180008BAB
0x180008b9f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180008ba6  test    rax, rax
0x180008ba9  jz      short loc_180008BC2
0x180008bab  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008baf  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180008bb6  lea     rcx, qword_18001B760
0x180008bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bc2  lea     rcx, SRWLock; SRWLock
0x180008bc9  call    cs:__imp_ReleaseSRWLockExclusive
0x180008bcf  nop
0x180008bd0  cmp     [rsp+98h+var_68], esi
0x180008bd4  jz      short loc_180008C07
0x180008bd6  mov     edx, ebx
0x180008bd8  cmp     [rsp+98h+var_64], esi
0x180008bdc  jz      short loc_180008BE2
0x180008bde  bts     edx, 1Fh
0x180008be2  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180008be9  test    rax, rax
0x180008bec  jnz     short loc_180008BFA
0x180008bee  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180008bf5  test    rax, rax
0x180008bf8  jz      short loc_180008C07
0x180008bfa  xor     r9d, r9d
0x180008bfd  xor     r8d, r8d
0x180008c00  mov     ecx, edi
0x180008c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c07  test    r13d, r13d
0x180008c0a  jnz     short loc_180008C2B
0x180008c0c  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180008c13  test    rax, rax
0x180008c16  jz      short loc_180008C2E
0x180008c18  mov     r8b, [rsp+98h+arg_38]
0x180008c20  mov     edx, ebx
0x180008c22  mov     ecx, edi
0x180008c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c29  jmp     short loc_180008C2E
0x180008c2b  mov     r14d, esi
0x180008c2e  mov     eax, r14d
0x180008c31  mov     rbx, [rsp+98h+arg_10]
0x180008c39  add     rsp, 60h
0x180008c3d  pop     r15
0x180008c3f  pop     r14
0x180008c41  pop     r13
0x180008c43  pop     r12
0x180008c45  pop     rdi
0x180008c46  pop     rsi
0x180008c47  pop     rbp
0x180008c48  retn
```
