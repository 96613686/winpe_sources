# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18001b218`
- end: `0x18001b3b5`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `413`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001b0f0`

## callees

- `0x180019878`
- `0x18001b218`
- `0x180023940`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b333`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b333`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b2e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b2e7`

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
  int v12; // r15d
  unsigned int v13; // esi
  unsigned int v14; // r12d
  int v15; // r13d
  unsigned int v16; // ebp
  void (__fastcall *v17)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v19; // rdx
  void (__fastcall *v20)(_QWORD, __int64, _QWORD, _QWORD); // rax
  _BYTE v24[80]; // [rsp+38h] [rbp-50h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v24, a1, a5, 0);
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
    if ( !qword_1800374E0 )
    {
      qword_1800374E0 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_1800374E0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18001b218  mov     [rsp+arg_10], rbx
0x18001b21d  push    rbp
0x18001b21e  push    rsi
0x18001b21f  push    rdi
0x18001b220  push    r12
0x18001b222  push    r13
0x18001b224  push    r14
0x18001b226  push    r15
0x18001b228  sub     rsp, 50h
0x18001b22c  mov     [rsp+88h+var_54], r9d
0x18001b231  mov     [rsp+88h+var_58], r8d
0x18001b236  mov     ebx, edx
0x18001b238  mov     r14, rcx
0x18001b23b  mov     edi, [rsp+88h+arg_20]
0x18001b242  xor     r9d, r9d
0x18001b245  mov     r8d, edi
0x18001b248  mov     rdx, rcx
0x18001b24b  lea     rcx, [rsp+88h+var_50]
0x18001b250  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001b255  mov     r15d, [rax]
0x18001b258  mov     esi, [rax+4]
0x18001b25b  mov     r12d, [rax+8]
0x18001b25f  mov     r13d, [rax+10h]
0x18001b263  mov     ebp, 1
0x18001b268  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18001b26f  test    rax, rax
0x18001b272  jz      short loc_18001B28C
0x18001b274  test    edi, edi
0x18001b276  jz      short loc_18001B280
0x18001b278  lea     ecx, [rdi-64h]
0x18001b27b  cmp     ecx, 31h ; '1'
0x18001b27e  ja      short loc_18001B28C
0x18001b280  mov     r8d, ebp
0x18001b283  mov     edx, edi
0x18001b285  mov     ecx, ebx
0x18001b287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b28c  test    r15d, r15d
0x18001b28f  jz      short loc_18001B2A2
0x18001b291  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18001b294  mov     edx, ebx; unsigned int
0x18001b296  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18001b29d  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001b2a2  xor     r14d, r14d
0x18001b2a5  test    esi, esi
0x18001b2a7  jz      short loc_18001B2D1
0x18001b2a9  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001b2b0  test    rax, rax
0x18001b2b3  jnz     short loc_18001B2C1
0x18001b2b5  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001b2bc  test    rax, rax
0x18001b2bf  jz      short loc_18001B2D1
0x18001b2c1  xor     r9d, r9d
0x18001b2c4  mov     r8d, esi
0x18001b2c7  mov     edx, r12d
0x18001b2ca  mov     ecx, ebx
0x18001b2cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2d1  test    r13d, r13d
0x18001b2d4  jnz     short loc_18001B33A
0x18001b2d6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001b2dc  test    eax, eax
0x18001b2de  jz      short loc_18001B33A
0x18001b2e0  lea     rcx, SRWLock; SRWLock
0x18001b2e7  call    cs:__imp_AcquireSRWLockExclusive
0x18001b2ed  cmp     cs:qword_1800374E0, r14
0x18001b2f4  jnz     short loc_18001B32C
0x18001b2f6  mov     cs:qword_1800374E0, r14
0x18001b2fd  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001b304  test    rax, rax
0x18001b307  jnz     short loc_18001B315
0x18001b309  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001b310  test    rax, rax
0x18001b313  jz      short loc_18001B32C
0x18001b315  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001b319  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18001b320  lea     rcx, qword_1800374E0
0x18001b327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b32c  lea     rcx, SRWLock; SRWLock
0x18001b333  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b339  nop
0x18001b33a  cmp     [rsp+88h+var_58], r14d
0x18001b33f  jz      short loc_18001B374
0x18001b341  mov     edx, edi
0x18001b343  bts     edx, 1Fh
0x18001b347  cmp     [rsp+88h+var_54], r14d
0x18001b34c  cmovz   edx, edi
0x18001b34f  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001b356  test    rax, rax
0x18001b359  jnz     short loc_18001B367
0x18001b35b  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001b362  test    rax, rax
0x18001b365  jz      short loc_18001B374
0x18001b367  xor     r9d, r9d
0x18001b36a  xor     r8d, r8d
0x18001b36d  mov     ecx, ebx
0x18001b36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b374  test    r13d, r13d
0x18001b377  jnz     short loc_18001B398
0x18001b379  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18001b380  test    rax, rax
0x18001b383  jz      short loc_18001B39B
0x18001b385  mov     r8b, [rsp+88h+arg_38]
0x18001b38d  mov     edx, edi
0x18001b38f  mov     ecx, ebx
0x18001b391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b396  jmp     short loc_18001B39B
0x18001b398  mov     ebp, r14d
0x18001b39b  mov     eax, ebp
0x18001b39d  mov     rbx, [rsp+88h+arg_10]
0x18001b3a5  add     rsp, 50h
0x18001b3a9  pop     r15
0x18001b3ab  pop     r14
0x18001b3ad  pop     r13
0x18001b3af  pop     r12
0x18001b3b1  pop     rdi
0x18001b3b2  pop     rsi
0x18001b3b3  pop     rbp
0x18001b3b4  retn
```
