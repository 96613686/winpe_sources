# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180009d60`
- end: `0x180009efe`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180009c84`

## callees

- `0x180009988`
- `0x180009d60`
- `0x18000a3a4`
- `0x180017010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180009e77`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180009e77`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009e2b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009e2b`

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
    if ( !qword_1800204D8 )
    {
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1800204D8 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_1800204D8, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x180009d60  mov     rax, rsp
0x180009d63  mov     [rax+8], rbx
0x180009d67  mov     [rax+20h], r9d
0x180009d6b  mov     [rax+18h], r8d
0x180009d6f  push    rbp
0x180009d70  push    rsi
0x180009d71  push    rdi
0x180009d72  push    r12
0x180009d74  push    r13
0x180009d76  push    r14
0x180009d78  push    r15
0x180009d7a  sub     rsp, 50h
0x180009d7e  mov     ebx, [rsp+88h+arg_20]
0x180009d85  mov     edi, edx
0x180009d87  mov     rdx, rcx
0x180009d8a  mov     r14, rcx
0x180009d8d  lea     rcx, [rax-58h]
0x180009d91  mov     r8d, ebx
0x180009d94  call    wil_details_FeatureReporting_RecordUsageInCache
0x180009d99  mov     ebp, 1
0x180009d9e  mov     r15d, [rax]
0x180009da1  mov     esi, [rax+4]
0x180009da4  mov     r13d, [rax+8]
0x180009da8  mov     r12d, [rax+10h]
0x180009dac  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180009db3  test    rax, rax
0x180009db6  jz      short loc_180009DD0
0x180009db8  test    ebx, ebx
0x180009dba  jz      short loc_180009DC4
0x180009dbc  lea     ecx, [rbx-64h]
0x180009dbf  cmp     ecx, 31h ; '1'
0x180009dc2  ja      short loc_180009DD0
0x180009dc4  mov     r8d, ebp
0x180009dc7  mov     edx, ebx
0x180009dc9  mov     ecx, edi
0x180009dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dd0  test    r15d, r15d
0x180009dd3  jz      short loc_180009DE6
0x180009dd5  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x180009dd8  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180009ddf  mov     edx, edi; unsigned int
0x180009de1  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180009de6  xor     r14d, r14d
0x180009de9  test    esi, esi
0x180009deb  jz      short loc_180009E15
0x180009ded  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180009df4  test    rax, rax
0x180009df7  jnz     short loc_180009E05
0x180009df9  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180009e00  test    rax, rax
0x180009e03  jz      short loc_180009E15
0x180009e05  xor     r9d, r9d
0x180009e08  mov     r8d, esi
0x180009e0b  mov     edx, r13d
0x180009e0e  mov     ecx, edi
0x180009e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e15  test    r12d, r12d
0x180009e18  jnz     short loc_180009E7D
0x180009e1a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180009e20  test    eax, eax
0x180009e22  jz      short loc_180009E7D
0x180009e24  lea     rcx, SRWLock; SRWLock
0x180009e2b  call    cs:__imp_AcquireSRWLockExclusive
0x180009e31  cmp     cs:qword_1800204D8, r14
0x180009e38  jnz     short loc_180009E70
0x180009e3a  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180009e41  mov     cs:qword_1800204D8, r14
0x180009e48  test    rax, rax
0x180009e4b  jnz     short loc_180009E59
0x180009e4d  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180009e54  test    rax, rax
0x180009e57  jz      short loc_180009E70
0x180009e59  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009e5d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180009e64  lea     rcx, qword_1800204D8
0x180009e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e70  lea     rcx, SRWLock; SRWLock
0x180009e77  call    cs:__imp_ReleaseSRWLockExclusive
0x180009e7d  cmp     [rsp+88h+arg_10], r14d
0x180009e85  jz      short loc_180009EBD
0x180009e87  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180009e8e  mov     edx, ebx
0x180009e90  bts     edx, 1Fh
0x180009e94  cmp     [rsp+88h+arg_18], r14d
0x180009e9c  cmovz   edx, ebx
0x180009e9f  test    rax, rax
0x180009ea2  jnz     short loc_180009EB0
0x180009ea4  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180009eab  test    rax, rax
0x180009eae  jz      short loc_180009EBD
0x180009eb0  xor     r9d, r9d
0x180009eb3  xor     r8d, r8d
0x180009eb6  mov     ecx, edi
0x180009eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ebd  test    r12d, r12d
0x180009ec0  jnz     short loc_180009EE1
0x180009ec2  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180009ec9  test    rax, rax
0x180009ecc  jz      short loc_180009EE4
0x180009ece  mov     r8b, [rsp+88h+arg_38]
0x180009ed6  mov     edx, ebx
0x180009ed8  mov     ecx, edi
0x180009eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009edf  jmp     short loc_180009EE4
0x180009ee1  mov     ebp, r14d
0x180009ee4  mov     rbx, [rsp+88h+arg_0]
0x180009eec  mov     eax, ebp
0x180009eee  add     rsp, 50h
0x180009ef2  pop     r15
0x180009ef4  pop     r14
0x180009ef6  pop     r13
0x180009ef8  pop     r12
0x180009efa  pop     rdi
0x180009efb  pop     rsi
0x180009efc  pop     rbp
0x180009efd  retn
```
