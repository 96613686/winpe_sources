# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180009884`
- end: `0x180009a22`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `414`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000974c`

## callees

- `0x18000958c`
- `0x180009884`
- `0x180009c10`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000999b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000999b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000994f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000994f`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
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
  unsigned int v12; // ebp
  int v13; // r15d
  unsigned int v14; // esi
  unsigned int v15; // r13d
  int v16; // r12d
  void (__fastcall *v17)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  void (__fastcall *v19)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __int64 v20; // rdx
  __int64 v22; // [rsp+30h] [rbp-58h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(&v22, a1, a5);
  v12 = 1;
  v13 = *v10;
  v14 = v10[1];
  v15 = v10[2];
  v16 = v10[4];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v13 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v14 )
  {
    v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v17(a2, v15, v14, 0);
    }
  }
  if ( !v16 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_18002F768 )
    {
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_18002F768 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_18002F768, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v19 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    v20 = a5;
    LODWORD(v20) = a5 | 0x80000000;
    if ( !a4 )
      v20 = a5;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v19 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v19(a2, v20, 0, 0);
    }
  }
  if ( v16 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v11) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v11);
  }
  return v12;
}

```

## disassembly

```asm
0x180009884  mov     rax, rsp
0x180009887  mov     [rax+8], rbx
0x18000988b  mov     [rax+20h], r9d
0x18000988f  mov     [rax+18h], r8d
0x180009893  push    rbp
0x180009894  push    rsi
0x180009895  push    rdi
0x180009896  push    r12
0x180009898  push    r13
0x18000989a  push    r14
0x18000989c  push    r15
0x18000989e  sub     rsp, 50h
0x1800098a2  mov     ebx, [rsp+88h+arg_20]
0x1800098a9  mov     edi, edx
0x1800098ab  mov     rdx, rcx
0x1800098ae  mov     r14, rcx
0x1800098b1  lea     rcx, [rax-58h]
0x1800098b5  mov     r8d, ebx
0x1800098b8  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800098bd  mov     ebp, 1
0x1800098c2  mov     r15d, [rax]
0x1800098c5  mov     esi, [rax+4]
0x1800098c8  mov     r13d, [rax+8]
0x1800098cc  mov     r12d, [rax+10h]
0x1800098d0  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800098d7  test    rax, rax
0x1800098da  jz      short loc_1800098F4
0x1800098dc  test    ebx, ebx
0x1800098de  jz      short loc_1800098E8
0x1800098e0  lea     ecx, [rbx-64h]
0x1800098e3  cmp     ecx, 31h ; '1'
0x1800098e6  ja      short loc_1800098F4
0x1800098e8  mov     r8d, ebp
0x1800098eb  mov     edx, ebx
0x1800098ed  mov     ecx, edi
0x1800098ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098f4  test    r15d, r15d
0x1800098f7  jz      short loc_18000990A
0x1800098f9  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x1800098fc  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180009903  mov     edx, edi; unsigned int
0x180009905  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000990a  xor     r14d, r14d
0x18000990d  test    esi, esi
0x18000990f  jz      short loc_180009939
0x180009911  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180009918  test    rax, rax
0x18000991b  jnz     short loc_180009929
0x18000991d  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180009924  test    rax, rax
0x180009927  jz      short loc_180009939
0x180009929  xor     r9d, r9d
0x18000992c  mov     r8d, esi
0x18000992f  mov     edx, r13d
0x180009932  mov     ecx, edi
0x180009934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009939  test    r12d, r12d
0x18000993c  jnz     short loc_1800099A1
0x18000993e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180009944  test    eax, eax
0x180009946  jz      short loc_1800099A1
0x180009948  lea     rcx, SRWLock; SRWLock
0x18000994f  call    cs:__imp_AcquireSRWLockExclusive
0x180009955  cmp     cs:qword_18002F768, r14
0x18000995c  jnz     short loc_180009994
0x18000995e  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180009965  mov     cs:qword_18002F768, r14
0x18000996c  test    rax, rax
0x18000996f  jnz     short loc_18000997D
0x180009971  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180009978  test    rax, rax
0x18000997b  jz      short loc_180009994
0x18000997d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009981  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180009988  lea     rcx, qword_18002F768
0x18000998f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009994  lea     rcx, SRWLock; SRWLock
0x18000999b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800099a1  cmp     [rsp+88h+arg_10], r14d
0x1800099a9  jz      short loc_1800099E1
0x1800099ab  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800099b2  mov     edx, ebx
0x1800099b4  bts     edx, 1Fh
0x1800099b8  cmp     [rsp+88h+arg_18], r14d
0x1800099c0  cmovz   edx, ebx
0x1800099c3  test    rax, rax
0x1800099c6  jnz     short loc_1800099D4
0x1800099c8  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800099cf  test    rax, rax
0x1800099d2  jz      short loc_1800099E1
0x1800099d4  xor     r9d, r9d
0x1800099d7  xor     r8d, r8d
0x1800099da  mov     ecx, edi
0x1800099dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099e1  test    r12d, r12d
0x1800099e4  jnz     short loc_180009A05
0x1800099e6  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800099ed  test    rax, rax
0x1800099f0  jz      short loc_180009A08
0x1800099f2  mov     r8b, [rsp+88h+arg_38]
0x1800099fa  mov     edx, ebx
0x1800099fc  mov     ecx, edi
0x1800099fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a03  jmp     short loc_180009A08
0x180009a05  mov     ebp, r14d
0x180009a08  mov     rbx, [rsp+88h+arg_0]
0x180009a10  mov     eax, ebp
0x180009a12  add     rsp, 50h
0x180009a16  pop     r15
0x180009a18  pop     r14
0x180009a1a  pop     r13
0x180009a1c  pop     r12
0x180009a1e  pop     rdi
0x180009a1f  pop     rsi
0x180009a20  pop     rbp
0x180009a21  retn
```
