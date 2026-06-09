# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18001c5d8`
- end: `0x18001c777`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001c4a0`

## callees

- `0x18001c27c`
- `0x18001c5d8`
- `0x18001d840`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c6a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c6a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c6ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c6ef`

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
    if ( !qword_18003AAC0 )
    {
      qword_18003AAC0 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_18003AAC0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18001c5d8  mov     rax, rsp
0x18001c5db  mov     [rax+8], rbx
0x18001c5df  mov     [rax+20h], r9d
0x18001c5e3  mov     [rax+18h], r8d
0x18001c5e7  push    rbp
0x18001c5e8  push    rsi
0x18001c5e9  push    rdi
0x18001c5ea  push    r12
0x18001c5ec  push    r13
0x18001c5ee  push    r14
0x18001c5f0  push    r15
0x18001c5f2  sub     rsp, 50h
0x18001c5f6  mov     edi, edx
0x18001c5f8  mov     r14, rcx
0x18001c5fb  mov     ebx, [rsp+88h+arg_20]
0x18001c602  mov     r8d, ebx
0x18001c605  mov     rdx, rcx
0x18001c608  lea     rcx, [rax-58h]
0x18001c60c  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001c611  mov     r15d, [rax]
0x18001c614  mov     esi, [rax+4]
0x18001c617  mov     r12d, [rax+8]
0x18001c61b  mov     r13d, [rax+10h]
0x18001c61f  mov     ebp, 1
0x18001c624  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18001c62b  test    rax, rax
0x18001c62e  jz      short loc_18001C648
0x18001c630  test    ebx, ebx
0x18001c632  jz      short loc_18001C63C
0x18001c634  lea     ecx, [rbx-64h]
0x18001c637  cmp     ecx, 31h ; '1'
0x18001c63a  ja      short loc_18001C648
0x18001c63c  mov     r8d, ebp
0x18001c63f  mov     edx, ebx
0x18001c641  mov     ecx, edi
0x18001c643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c648  test    r15d, r15d
0x18001c64b  jz      short loc_18001C65E
0x18001c64d  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18001c650  mov     edx, edi; unsigned int
0x18001c652  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18001c659  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001c65e  xor     r14d, r14d
0x18001c661  test    esi, esi
0x18001c663  jz      short loc_18001C68D
0x18001c665  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001c66c  test    rax, rax
0x18001c66f  jnz     short loc_18001C67D
0x18001c671  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001c678  test    rax, rax
0x18001c67b  jz      short loc_18001C68D
0x18001c67d  xor     r9d, r9d
0x18001c680  mov     r8d, esi
0x18001c683  mov     edx, r12d
0x18001c686  mov     ecx, edi
0x18001c688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c68d  test    r13d, r13d
0x18001c690  jnz     short loc_18001C6F6
0x18001c692  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001c698  test    eax, eax
0x18001c69a  jz      short loc_18001C6F6
0x18001c69c  lea     rcx, SRWLock; SRWLock
0x18001c6a3  call    cs:__imp_AcquireSRWLockExclusive
0x18001c6a9  cmp     cs:qword_18003AAC0, r14
0x18001c6b0  jnz     short loc_18001C6E8
0x18001c6b2  mov     cs:qword_18003AAC0, r14
0x18001c6b9  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001c6c0  test    rax, rax
0x18001c6c3  jnz     short loc_18001C6D1
0x18001c6c5  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001c6cc  test    rax, rax
0x18001c6cf  jz      short loc_18001C6E8
0x18001c6d1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c6d5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18001c6dc  lea     rcx, qword_18003AAC0
0x18001c6e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6e8  lea     rcx, SRWLock; SRWLock
0x18001c6ef  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c6f5  nop
0x18001c6f6  cmp     [rsp+88h+arg_10], r14d
0x18001c6fe  jz      short loc_18001C736
0x18001c700  mov     edx, ebx
0x18001c702  bts     edx, 1Fh
0x18001c706  cmp     [rsp+88h+arg_18], r14d
0x18001c70e  cmovz   edx, ebx
0x18001c711  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001c718  test    rax, rax
0x18001c71b  jnz     short loc_18001C729
0x18001c71d  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001c724  test    rax, rax
0x18001c727  jz      short loc_18001C736
0x18001c729  xor     r9d, r9d
0x18001c72c  xor     r8d, r8d
0x18001c72f  mov     ecx, edi
0x18001c731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c736  test    r13d, r13d
0x18001c739  jnz     short loc_18001C75A
0x18001c73b  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18001c742  test    rax, rax
0x18001c745  jz      short loc_18001C75D
0x18001c747  mov     r8b, [rsp+88h+arg_38]
0x18001c74f  mov     edx, ebx
0x18001c751  mov     ecx, edi
0x18001c753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c758  jmp     short loc_18001C75D
0x18001c75a  mov     ebp, r14d
0x18001c75d  mov     eax, ebp
0x18001c75f  mov     rbx, [rsp+88h+arg_0]
0x18001c767  add     rsp, 50h
0x18001c76b  pop     r15
0x18001c76d  pop     r14
0x18001c76f  pop     r13
0x18001c771  pop     r12
0x18001c773  pop     rdi
0x18001c774  pop     rsi
0x18001c775  pop     rbp
0x18001c776  retn
```
