# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18001d7cc`
- end: `0x18001d994`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001d680`

## callees

- `0x18001d4bc`
- `0x18001d7cc`
- `0x18001eac8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d90f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d90f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d8bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d8bb`

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
  __int64 v12; // rax
  __m128i v13; // xmm1
  unsigned int v14; // ebp
  __int64 v15; // r8
  void (__fastcall *v16)(_QWORD, _QWORD, __int64, _QWORD); // rax
  void (__fastcall *v17)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v18; // rdx
  void (__fastcall *v19)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __m128i v21; // [rsp+30h] [rbp-58h]
  __int64 v22; // [rsp+50h] [rbp-38h]
  __int64 v23; // [rsp+58h] [rbp-30h] BYREF

  v12 = wil_details_FeatureReporting_RecordUsageInCache(&v23, a1, a5);
  v13 = *(__m128i *)v12;
  v21 = *(__m128i *)v12;
  v22 = *(_QWORD *)(v12 + 16);
  v14 = 1;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
  {
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
    v13 = v21;
  }
  if ( _mm_cvtsi128_si32(v13) )
  {
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      a2,
      a1);
    v13 = v21;
  }
  v15 = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v13, 4));
  if ( (_DWORD)v15 )
  {
    v16 = (void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v16 = (void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v16(a2, (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v13, 8)), v15, 0);
    }
  }
  if ( !(_DWORD)v22 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_18003CAB0 )
    {
      qword_18003CAB0 = 0;
      v17 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v17 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v17(&qword_18003CAB0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v18 = a5;
    LODWORD(v18) = a5 | 0x80000000;
    if ( !a4 )
      v18 = a5;
    v19 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v19 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v19(a2, v18, 0, 0);
    }
  }
  if ( (_DWORD)v22 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v15) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v15);
  }
  return v14;
}

```

## disassembly

```asm
0x18001d7cc  mov     rax, rsp
0x18001d7cf  mov     [rax+8], rbx
0x18001d7d3  mov     [rax+10h], rbp
0x18001d7d7  mov     [rax+18h], rsi
0x18001d7db  push    rdi
0x18001d7dc  push    r14
0x18001d7de  push    r15
0x18001d7e0  sub     rsp, 70h
0x18001d7e4  mov     r15d, r9d
0x18001d7e7  mov     r14d, r8d
0x18001d7ea  mov     edi, edx
0x18001d7ec  mov     rsi, rcx
0x18001d7ef  mov     ebx, [rsp+88h+arg_20]
0x18001d7f6  mov     r8d, ebx
0x18001d7f9  mov     rdx, rcx
0x18001d7fc  lea     rcx, [rax-30h]
0x18001d800  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001d805  movups  xmm1, xmmword ptr [rax]
0x18001d808  movups  [rsp+88h+var_58], xmm1
0x18001d80d  movsd   xmm0, qword ptr [rax+10h]
0x18001d812  movsd   [rsp+88h+var_38], xmm0
0x18001d818  mov     ebp, 1
0x18001d81d  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18001d824  test    rax, rax
0x18001d827  jz      short loc_18001D846
0x18001d829  test    ebx, ebx
0x18001d82b  jz      short loc_18001D835
0x18001d82d  lea     ecx, [rbx-64h]
0x18001d830  cmp     ecx, 31h ; '1'
0x18001d833  ja      short loc_18001D846
0x18001d835  mov     r8d, ebp
0x18001d838  mov     edx, ebx
0x18001d83a  mov     ecx, edi
0x18001d83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d841  movups  xmm1, [rsp+88h+var_58]
0x18001d846  movd    eax, xmm1
0x18001d84a  test    eax, eax
0x18001d84c  jz      short loc_18001D864
0x18001d84e  mov     r8, rsi; struct wil_details_FeatureReportingCache *
0x18001d851  mov     edx, edi; unsigned int
0x18001d853  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18001d85a  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001d85f  movups  xmm1, [rsp+88h+var_58]
0x18001d864  movdqa  xmm0, xmm1
0x18001d868  psrldq  xmm0, 4
0x18001d86d  movd    r8d, xmm0
0x18001d872  test    r8d, r8d
0x18001d875  jz      short loc_18001D8A2
0x18001d877  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001d87e  test    rax, rax
0x18001d881  jnz     short loc_18001D88F
0x18001d883  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001d88a  test    rax, rax
0x18001d88d  jz      short loc_18001D8A2
0x18001d88f  psrldq  xmm1, 8
0x18001d894  xor     r9d, r9d
0x18001d897  movd    edx, xmm1
0x18001d89b  mov     ecx, edi
0x18001d89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8a2  mov     esi, dword ptr [rsp+88h+var_38]
0x18001d8a6  test    esi, esi
0x18001d8a8  jnz     short loc_18001D91C
0x18001d8aa  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001d8b0  test    eax, eax
0x18001d8b2  jz      short loc_18001D91C
0x18001d8b4  lea     rcx, SRWLock; SRWLock
0x18001d8bb  call    cs:__imp_AcquireSRWLockExclusive
0x18001d8c2  nop     dword ptr [rax+rax+00h]
0x18001d8c7  cmp     cs:qword_18003CAB0, 0
0x18001d8cf  jnz     short loc_18001D908
0x18001d8d1  and     cs:qword_18003CAB0, 0
0x18001d8d9  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001d8e0  test    rax, rax
0x18001d8e3  jnz     short loc_18001D8F1
0x18001d8e5  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001d8ec  test    rax, rax
0x18001d8ef  jz      short loc_18001D908
0x18001d8f1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d8f5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18001d8fc  lea     rcx, qword_18003CAB0
0x18001d903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d908  lea     rcx, SRWLock; SRWLock
0x18001d90f  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d916  nop     dword ptr [rax+rax+00h]
0x18001d91b  nop
0x18001d91c  test    r14d, r14d
0x18001d91f  jz      short loc_18001D952
0x18001d921  mov     edx, ebx
0x18001d923  bts     edx, 1Fh
0x18001d927  test    r15d, r15d
0x18001d92a  cmovz   edx, ebx
0x18001d92d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001d934  test    rax, rax
0x18001d937  jnz     short loc_18001D945
0x18001d939  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001d940  test    rax, rax
0x18001d943  jz      short loc_18001D952
0x18001d945  xor     r9d, r9d
0x18001d948  xor     r8d, r8d
0x18001d94b  mov     ecx, edi
0x18001d94d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d952  test    esi, esi
0x18001d954  jnz     short loc_18001D975
0x18001d956  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18001d95d  test    rax, rax
0x18001d960  jz      short loc_18001D977
0x18001d962  mov     r8b, [rsp+88h+arg_38]
0x18001d96a  mov     edx, ebx
0x18001d96c  mov     ecx, edi
0x18001d96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d973  jmp     short loc_18001D977
0x18001d975  xor     ebp, ebp
0x18001d977  mov     eax, ebp
0x18001d979  lea     r11, [rsp+88h+var_18]
0x18001d97e  mov     rbx, [r11+20h]
0x18001d982  mov     rbp, [r11+28h]
0x18001d986  mov     rsi, [r11+30h]
0x18001d98a  mov     rsp, r11
0x18001d98d  pop     r15
0x18001d98f  pop     r14
0x18001d991  pop     rdi
0x18001d992  retn
```
