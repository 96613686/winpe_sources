# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18001f2b8`
- end: `0x18001f457`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001f180`

## callees

- `0x18001ed48`
- `0x18001f2b8`
- `0x180020564`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f3cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f3cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f383`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f383`

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
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(), __int64); // rax
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
    if ( !qword_1800718E0 )
    {
      qword_1800718E0 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_1800718E0, `wil::details::RecordFeatureUsageCallback'::`17'::_lambda_1_::_lambda_invoker_cdecl_, -1);
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
0x18001f2b8  mov     rax, rsp
0x18001f2bb  mov     [rax+8], rbx
0x18001f2bf  mov     [rax+20h], r9d
0x18001f2c3  mov     [rax+18h], r8d
0x18001f2c7  push    rbp
0x18001f2c8  push    rsi
0x18001f2c9  push    rdi
0x18001f2ca  push    r12
0x18001f2cc  push    r13
0x18001f2ce  push    r14
0x18001f2d0  push    r15
0x18001f2d2  sub     rsp, 50h
0x18001f2d6  mov     edi, edx
0x18001f2d8  mov     r14, rcx
0x18001f2db  mov     ebx, [rsp+88h+arg_20]
0x18001f2e2  mov     r8d, ebx
0x18001f2e5  mov     rdx, rcx
0x18001f2e8  lea     rcx, [rax-58h]
0x18001f2ec  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001f2f1  mov     r15d, [rax]
0x18001f2f4  mov     esi, [rax+4]
0x18001f2f7  mov     r12d, [rax+8]
0x18001f2fb  mov     r13d, [rax+10h]
0x18001f2ff  mov     ebp, 1
0x18001f304  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18001f30b  test    rax, rax
0x18001f30e  jz      short loc_18001F328
0x18001f310  test    ebx, ebx
0x18001f312  jz      short loc_18001F31C
0x18001f314  lea     ecx, [rbx-64h]
0x18001f317  cmp     ecx, 31h ; '1'
0x18001f31a  ja      short loc_18001F328
0x18001f31c  mov     r8d, ebp
0x18001f31f  mov     edx, ebx
0x18001f321  mov     ecx, edi
0x18001f323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f328  test    r15d, r15d
0x18001f32b  jz      short loc_18001F33E
0x18001f32d  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18001f330  mov     edx, edi; unsigned int
0x18001f332  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18001f339  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001f33e  xor     r14d, r14d
0x18001f341  test    esi, esi
0x18001f343  jz      short loc_18001F36D
0x18001f345  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001f34c  test    rax, rax
0x18001f34f  jnz     short loc_18001F35D
0x18001f351  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001f358  test    rax, rax
0x18001f35b  jz      short loc_18001F36D
0x18001f35d  xor     r9d, r9d
0x18001f360  mov     r8d, esi
0x18001f363  mov     edx, r12d
0x18001f366  mov     ecx, edi
0x18001f368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f36d  test    r13d, r13d
0x18001f370  jnz     short loc_18001F3D6
0x18001f372  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001f378  test    eax, eax
0x18001f37a  jz      short loc_18001F3D6
0x18001f37c  lea     rcx, SRWLock; SRWLock
0x18001f383  call    cs:__imp_AcquireSRWLockExclusive
0x18001f389  cmp     cs:qword_1800718E0, r14
0x18001f390  jnz     short loc_18001F3C8
0x18001f392  mov     cs:qword_1800718E0, r14
0x18001f399  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001f3a0  test    rax, rax
0x18001f3a3  jnz     short loc_18001F3B1
0x18001f3a5  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001f3ac  test    rax, rax
0x18001f3af  jz      short loc_18001F3C8
0x18001f3b1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f3b5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z; `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18001f3bc  lea     rcx, qword_1800718E0
0x18001f3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3c8  lea     rcx, SRWLock; SRWLock
0x18001f3cf  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f3d5  nop
0x18001f3d6  cmp     [rsp+88h+arg_10], r14d
0x18001f3de  jz      short loc_18001F416
0x18001f3e0  mov     edx, ebx
0x18001f3e2  bts     edx, 1Fh
0x18001f3e6  cmp     [rsp+88h+arg_18], r14d
0x18001f3ee  cmovz   edx, ebx
0x18001f3f1  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001f3f8  test    rax, rax
0x18001f3fb  jnz     short loc_18001F409
0x18001f3fd  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001f404  test    rax, rax
0x18001f407  jz      short loc_18001F416
0x18001f409  xor     r9d, r9d
0x18001f40c  xor     r8d, r8d
0x18001f40f  mov     ecx, edi
0x18001f411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f416  test    r13d, r13d
0x18001f419  jnz     short loc_18001F43A
0x18001f41b  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18001f422  test    rax, rax
0x18001f425  jz      short loc_18001F43D
0x18001f427  mov     r8b, [rsp+88h+arg_38]
0x18001f42f  mov     edx, ebx
0x18001f431  mov     ecx, edi
0x18001f433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f438  jmp     short loc_18001F43D
0x18001f43a  mov     ebp, r14d
0x18001f43d  mov     eax, ebp
0x18001f43f  mov     rbx, [rsp+88h+arg_0]
0x18001f447  add     rsp, 50h
0x18001f44b  pop     r15
0x18001f44d  pop     r14
0x18001f44f  pop     r13
0x18001f451  pop     r12
0x18001f453  pop     rdi
0x18001f454  pop     rsi
0x18001f455  pop     rbp
0x18001f456  retn
```
