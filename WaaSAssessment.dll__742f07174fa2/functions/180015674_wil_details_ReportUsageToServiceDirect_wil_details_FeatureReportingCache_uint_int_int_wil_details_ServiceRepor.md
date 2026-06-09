# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180015674`
- end: `0x180015813`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001553c`

## callees

- `0x180014000`
- `0x180015674`
- `0x1800167d0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001578b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001578b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001573f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001573f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  int v12; // r15d
  unsigned int v13; // esi
  unsigned int v14; // r12d
  int v15; // r13d
  unsigned int v16; // ebp
  void (__fastcall *v17)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v19; // rdx
  void (__fastcall *v20)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __int64 v22; // [rsp+30h] [rbp-58h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(&v22, a1, a5);
  v12 = *v10;
  v13 = v10[1];
  v14 = v10[2];
  v15 = v10[4];
  v16 = 1;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v12 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      a2,
      a1);
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
    if ( !qword_1800274F0 )
    {
      qword_1800274F0 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_1800274F0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v19 = a5;
    LODWORD(v19) = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
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
0x180015674  mov     rax, rsp
0x180015677  mov     [rax+8], rbx
0x18001567b  mov     [rax+20h], r9d
0x18001567f  mov     [rax+18h], r8d
0x180015683  push    rbp
0x180015684  push    rsi
0x180015685  push    rdi
0x180015686  push    r12
0x180015688  push    r13
0x18001568a  push    r14
0x18001568c  push    r15
0x18001568e  sub     rsp, 50h
0x180015692  mov     edi, edx
0x180015694  mov     r14, rcx
0x180015697  mov     ebx, [rsp+88h+arg_20]
0x18001569e  mov     r8d, ebx
0x1800156a1  mov     rdx, rcx
0x1800156a4  lea     rcx, [rax-58h]
0x1800156a8  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800156ad  mov     r15d, [rax]
0x1800156b0  mov     esi, [rax+4]
0x1800156b3  mov     r12d, [rax+8]
0x1800156b7  mov     r13d, [rax+10h]
0x1800156bb  mov     ebp, 1
0x1800156c0  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800156c7  test    rax, rax
0x1800156ca  jz      short loc_1800156E4
0x1800156cc  test    ebx, ebx
0x1800156ce  jz      short loc_1800156D8
0x1800156d0  lea     ecx, [rbx-64h]
0x1800156d3  cmp     ecx, 31h ; '1'
0x1800156d6  ja      short loc_1800156E4
0x1800156d8  mov     r8d, ebp
0x1800156db  mov     edx, ebx
0x1800156dd  mov     ecx, edi
0x1800156df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156e4  test    r15d, r15d
0x1800156e7  jz      short loc_1800156FA
0x1800156e9  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x1800156ec  mov     edx, edi; unsigned int
0x1800156ee  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800156f5  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800156fa  xor     r14d, r14d
0x1800156fd  test    esi, esi
0x1800156ff  jz      short loc_180015729
0x180015701  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180015708  test    rax, rax
0x18001570b  jnz     short loc_180015719
0x18001570d  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180015714  test    rax, rax
0x180015717  jz      short loc_180015729
0x180015719  xor     r9d, r9d
0x18001571c  mov     r8d, esi
0x18001571f  mov     edx, r12d
0x180015722  mov     ecx, edi
0x180015724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015729  test    r13d, r13d
0x18001572c  jnz     short loc_180015792
0x18001572e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015734  test    eax, eax
0x180015736  jz      short loc_180015792
0x180015738  lea     rcx, SRWLock; SRWLock
0x18001573f  call    cs:__imp_AcquireSRWLockExclusive
0x180015745  cmp     cs:qword_1800274F0, r14
0x18001574c  jnz     short loc_180015784
0x18001574e  mov     cs:qword_1800274F0, r14
0x180015755  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001575c  test    rax, rax
0x18001575f  jnz     short loc_18001576D
0x180015761  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180015768  test    rax, rax
0x18001576b  jz      short loc_180015784
0x18001576d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015771  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180015778  lea     rcx, qword_1800274F0
0x18001577f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015784  lea     rcx, SRWLock; SRWLock
0x18001578b  call    cs:__imp_ReleaseSRWLockExclusive
0x180015791  nop
0x180015792  cmp     [rsp+88h+arg_10], r14d
0x18001579a  jz      short loc_1800157D2
0x18001579c  mov     edx, ebx
0x18001579e  bts     edx, 1Fh
0x1800157a2  cmp     [rsp+88h+arg_18], r14d
0x1800157aa  cmovz   edx, ebx
0x1800157ad  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800157b4  test    rax, rax
0x1800157b7  jnz     short loc_1800157C5
0x1800157b9  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800157c0  test    rax, rax
0x1800157c3  jz      short loc_1800157D2
0x1800157c5  xor     r9d, r9d
0x1800157c8  xor     r8d, r8d
0x1800157cb  mov     ecx, edi
0x1800157cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157d2  test    r13d, r13d
0x1800157d5  jnz     short loc_1800157F6
0x1800157d7  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800157de  test    rax, rax
0x1800157e1  jz      short loc_1800157F9
0x1800157e3  mov     r8b, [rsp+88h+arg_38]
0x1800157eb  mov     edx, ebx
0x1800157ed  mov     ecx, edi
0x1800157ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157f4  jmp     short loc_1800157F9
0x1800157f6  mov     ebp, r14d
0x1800157f9  mov     eax, ebp
0x1800157fb  mov     rbx, [rsp+88h+arg_0]
0x180015803  add     rsp, 50h
0x180015807  pop     r15
0x180015809  pop     r14
0x18001580b  pop     r13
0x18001580d  pop     r12
0x18001580f  pop     rdi
0x180015810  pop     rsi
0x180015811  pop     rbp
0x180015812  retn
```
