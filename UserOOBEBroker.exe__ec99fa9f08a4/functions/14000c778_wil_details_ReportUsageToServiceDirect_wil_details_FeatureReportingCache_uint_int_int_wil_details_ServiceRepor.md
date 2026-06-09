# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x14000c778`
- end: `0x14000c90b`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000c6a0`

## callees

- `0x14000ad30`
- `0x14000c778`
- `0x14000dd00`
- `0x14000f010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c83f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c83f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000c88b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000c88b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        __int64 a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  int *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // r14d
  unsigned int v14; // edi
  unsigned int v15; // r15d
  int v16; // r12d
  unsigned int v17; // esi
  void (__fastcall *v18)(__int64, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v19)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v20; // rdx
  void (__fastcall *v21)(__int64, __int64, _QWORD, _QWORD); // rax
  _BYTE v23[104]; // [rsp+30h] [rbp-68h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v23, a1, a5);
  v13 = *v10;
  v14 = v10[1];
  v15 = v10[2];
  v16 = v10[4];
  v17 = 1;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(43788167, a5, 1);
  if ( v13 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      v11,
      a1);
  if ( v14 )
  {
    v18 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v18 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v18(43788167, v15, v14, 0);
    }
  }
  if ( !v16 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_140017420 )
    {
      qword_140017420 = 0;
      v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v19(&qword_140017420, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v20 = a5;
    LODWORD(v20) = a5 | 0x80000000;
    if ( !a4 )
      v20 = a5;
    v21 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v21 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v21(43788167, v20, 0, 0);
    }
  }
  if ( v16 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(43788167, a5, v12);
  }
  return v17;
}

```

## disassembly

```asm
0x14000c778  mov     [rsp+arg_18], r9d
0x14000c77d  push    rbx
0x14000c77e  push    rbp
0x14000c77f  push    rsi
0x14000c780  push    rdi
0x14000c781  push    r12
0x14000c783  push    r13
0x14000c785  push    r14
0x14000c787  push    r15
0x14000c789  sub     rsp, 58h
0x14000c78d  mov     r13d, r8d
0x14000c790  mov     rbp, rcx
0x14000c793  mov     ebx, [rsp+98h+arg_20]
0x14000c79a  mov     r8d, ebx
0x14000c79d  mov     rdx, rcx
0x14000c7a0  lea     rcx, [rsp+98h+var_68]
0x14000c7a5  call    wil_details_FeatureReporting_RecordUsageInCache
0x14000c7aa  mov     r14d, [rax]
0x14000c7ad  mov     edi, [rax+4]
0x14000c7b0  mov     r15d, [rax+8]
0x14000c7b4  mov     r12d, [rax+10h]
0x14000c7b8  mov     esi, 1
0x14000c7bd  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x14000c7c4  test    rax, rax
0x14000c7c7  jz      short loc_14000C7E4
0x14000c7c9  test    ebx, ebx
0x14000c7cb  jz      short loc_14000C7D5
0x14000c7cd  lea     ecx, [rbx-64h]
0x14000c7d0  cmp     ecx, 31h ; '1'
0x14000c7d3  ja      short loc_14000C7E4
0x14000c7d5  mov     r8d, esi
0x14000c7d8  mov     edx, ebx
0x14000c7da  mov     ecx, 29C2787h
0x14000c7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c7e4  test    r14d, r14d
0x14000c7e7  jz      short loc_14000C7F8
0x14000c7e9  mov     r8, rbp; struct wil_details_FeatureReportingCache *
0x14000c7ec  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x14000c7f3  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x14000c7f8  xor     ebp, ebp
0x14000c7fa  test    edi, edi
0x14000c7fc  jz      short loc_14000C829
0x14000c7fe  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000c805  test    rax, rax
0x14000c808  jnz     short loc_14000C816
0x14000c80a  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000c811  test    rax, rax
0x14000c814  jz      short loc_14000C829
0x14000c816  xor     r9d, r9d
0x14000c819  mov     r8d, edi
0x14000c81c  mov     edx, r15d
0x14000c81f  mov     ecx, 29C2787h
0x14000c824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c829  test    r12d, r12d
0x14000c82c  jnz     short loc_14000C892
0x14000c82e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000c834  test    eax, eax
0x14000c836  jz      short loc_14000C892
0x14000c838  lea     rcx, SRWLock; SRWLock
0x14000c83f  call    cs:__imp_AcquireSRWLockExclusive
0x14000c845  cmp     cs:qword_140017420, rbp
0x14000c84c  jnz     short loc_14000C884
0x14000c84e  mov     cs:qword_140017420, rbp
0x14000c855  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x14000c85c  test    rax, rax
0x14000c85f  jnz     short loc_14000C86D
0x14000c861  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x14000c868  test    rax, rax
0x14000c86b  jz      short loc_14000C884
0x14000c86d  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000c871  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x14000c878  lea     rcx, qword_140017420
0x14000c87f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c884  lea     rcx, SRWLock; SRWLock
0x14000c88b  call    cs:__imp_ReleaseSRWLockExclusive
0x14000c891  nop
0x14000c892  test    r13d, r13d
0x14000c895  jz      short loc_14000C8CF
0x14000c897  mov     edx, ebx
0x14000c899  bts     edx, 1Fh
0x14000c89d  cmp     [rsp+98h+arg_18], ebp
0x14000c8a4  cmovz   edx, ebx
0x14000c8a7  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000c8ae  test    rax, rax
0x14000c8b1  jnz     short loc_14000C8BF
0x14000c8b3  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000c8ba  test    rax, rax
0x14000c8bd  jz      short loc_14000C8CF
0x14000c8bf  xor     r9d, r9d
0x14000c8c2  xor     r8d, r8d
0x14000c8c5  mov     ecx, 29C2787h
0x14000c8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c8cf  test    r12d, r12d
0x14000c8d2  jnz     short loc_14000C8F6
0x14000c8d4  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x14000c8db  test    rax, rax
0x14000c8de  jz      short loc_14000C8F8
0x14000c8e0  mov     r8b, [rsp+98h+arg_38]
0x14000c8e8  mov     edx, ebx
0x14000c8ea  mov     ecx, 29C2787h
0x14000c8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c8f4  jmp     short loc_14000C8F8
0x14000c8f6  mov     esi, ebp
0x14000c8f8  mov     eax, esi
0x14000c8fa  add     rsp, 58h
0x14000c8fe  pop     r15
0x14000c900  pop     r14
0x14000c902  pop     r13
0x14000c904  pop     r12
0x14000c906  pop     rdi
0x14000c907  pop     rsi
0x14000c908  pop     rbp
0x14000c909  pop     rbx
0x14000c90a  retn
```
