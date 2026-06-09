# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180020bdc`
- end: `0x180020d7b`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180020aa4`

## callees

- `0x18002073c`
- `0x180020bdc`
- `0x18002193c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020cf3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020cf3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020ca7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020ca7`

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
    if ( !qword_18005F7E0 )
    {
      qword_18005F7E0 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_18005F7E0, `wil::details::RecordFeatureUsageCallback'::`17'::_lambda_1_::_lambda_invoker_cdecl_, -1);
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
0x180020bdc  mov     rax, rsp
0x180020bdf  mov     [rax+8], rbx
0x180020be3  mov     [rax+20h], r9d
0x180020be7  mov     [rax+18h], r8d
0x180020beb  push    rbp
0x180020bec  push    rsi
0x180020bed  push    rdi
0x180020bee  push    r12
0x180020bf0  push    r13
0x180020bf2  push    r14
0x180020bf4  push    r15
0x180020bf6  sub     rsp, 50h
0x180020bfa  mov     edi, edx
0x180020bfc  mov     r14, rcx
0x180020bff  mov     ebx, [rsp+88h+arg_20]
0x180020c06  mov     r8d, ebx
0x180020c09  mov     rdx, rcx
0x180020c0c  lea     rcx, [rax-58h]
0x180020c10  call    wil_details_FeatureReporting_RecordUsageInCache
0x180020c15  mov     r15d, [rax]
0x180020c18  mov     esi, [rax+4]
0x180020c1b  mov     r12d, [rax+8]
0x180020c1f  mov     r13d, [rax+10h]
0x180020c23  mov     ebp, 1
0x180020c28  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180020c2f  test    rax, rax
0x180020c32  jz      short loc_180020C4C
0x180020c34  test    ebx, ebx
0x180020c36  jz      short loc_180020C40
0x180020c38  lea     ecx, [rbx-64h]
0x180020c3b  cmp     ecx, 31h ; '1'
0x180020c3e  ja      short loc_180020C4C
0x180020c40  mov     r8d, ebp
0x180020c43  mov     edx, ebx
0x180020c45  mov     ecx, edi
0x180020c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c4c  test    r15d, r15d
0x180020c4f  jz      short loc_180020C62
0x180020c51  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x180020c54  mov     edx, edi; unsigned int
0x180020c56  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180020c5d  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180020c62  xor     r14d, r14d
0x180020c65  test    esi, esi
0x180020c67  jz      short loc_180020C91
0x180020c69  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180020c70  test    rax, rax
0x180020c73  jnz     short loc_180020C81
0x180020c75  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180020c7c  test    rax, rax
0x180020c7f  jz      short loc_180020C91
0x180020c81  xor     r9d, r9d
0x180020c84  mov     r8d, esi
0x180020c87  mov     edx, r12d
0x180020c8a  mov     ecx, edi
0x180020c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c91  test    r13d, r13d
0x180020c94  jnz     short loc_180020CFA
0x180020c96  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180020c9c  test    eax, eax
0x180020c9e  jz      short loc_180020CFA
0x180020ca0  lea     rcx, SRWLock; SRWLock
0x180020ca7  call    cs:__imp_AcquireSRWLockExclusive
0x180020cad  cmp     cs:qword_18005F7E0, r14
0x180020cb4  jnz     short loc_180020CEC
0x180020cb6  mov     cs:qword_18005F7E0, r14
0x180020cbd  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180020cc4  test    rax, rax
0x180020cc7  jnz     short loc_180020CD5
0x180020cc9  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180020cd0  test    rax, rax
0x180020cd3  jz      short loc_180020CEC
0x180020cd5  or      r8, 0FFFFFFFFFFFFFFFFh
0x180020cd9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z; `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x180020ce0  lea     rcx, qword_18005F7E0
0x180020ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cec  lea     rcx, SRWLock; SRWLock
0x180020cf3  call    cs:__imp_ReleaseSRWLockExclusive
0x180020cf9  nop
0x180020cfa  cmp     [rsp+88h+arg_10], r14d
0x180020d02  jz      short loc_180020D3A
0x180020d04  mov     edx, ebx
0x180020d06  bts     edx, 1Fh
0x180020d0a  cmp     [rsp+88h+arg_18], r14d
0x180020d12  cmovz   edx, ebx
0x180020d15  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180020d1c  test    rax, rax
0x180020d1f  jnz     short loc_180020D2D
0x180020d21  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180020d28  test    rax, rax
0x180020d2b  jz      short loc_180020D3A
0x180020d2d  xor     r9d, r9d
0x180020d30  xor     r8d, r8d
0x180020d33  mov     ecx, edi
0x180020d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d3a  test    r13d, r13d
0x180020d3d  jnz     short loc_180020D5E
0x180020d3f  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180020d46  test    rax, rax
0x180020d49  jz      short loc_180020D61
0x180020d4b  mov     r8b, [rsp+88h+arg_38]
0x180020d53  mov     edx, ebx
0x180020d55  mov     ecx, edi
0x180020d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d5c  jmp     short loc_180020D61
0x180020d5e  mov     ebp, r14d
0x180020d61  mov     eax, ebp
0x180020d63  mov     rbx, [rsp+88h+arg_0]
0x180020d6b  add     rsp, 50h
0x180020d6f  pop     r15
0x180020d71  pop     r14
0x180020d73  pop     r13
0x180020d75  pop     r12
0x180020d77  pop     rdi
0x180020d78  pop     rsi
0x180020d79  pop     rbp
0x180020d7a  retn
```
