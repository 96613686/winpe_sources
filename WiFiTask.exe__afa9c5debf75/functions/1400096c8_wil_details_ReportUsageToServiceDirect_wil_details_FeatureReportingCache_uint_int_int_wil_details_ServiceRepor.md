# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1400096c8`
- end: `0x140009867`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140009590`

## callees

- `0x140008074`
- `0x1400096c8`
- `0x14000c420`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009793`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009793`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400097df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400097df`

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
    if ( !qword_1400193C8 )
    {
      qword_1400193C8 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_1400193C8, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x1400096c8  mov     rax, rsp
0x1400096cb  mov     [rax+8], rbx
0x1400096cf  mov     [rax+20h], r9d
0x1400096d3  mov     [rax+18h], r8d
0x1400096d7  push    rbp
0x1400096d8  push    rsi
0x1400096d9  push    rdi
0x1400096da  push    r12
0x1400096dc  push    r13
0x1400096de  push    r14
0x1400096e0  push    r15
0x1400096e2  sub     rsp, 50h
0x1400096e6  mov     edi, edx
0x1400096e8  mov     r14, rcx
0x1400096eb  mov     ebx, [rsp+88h+arg_20]
0x1400096f2  mov     r8d, ebx
0x1400096f5  mov     rdx, rcx
0x1400096f8  lea     rcx, [rax-58h]
0x1400096fc  call    wil_details_FeatureReporting_RecordUsageInCache
0x140009701  mov     r15d, [rax]
0x140009704  mov     esi, [rax+4]
0x140009707  mov     r12d, [rax+8]
0x14000970b  mov     r13d, [rax+10h]
0x14000970f  mov     ebp, 1
0x140009714  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x14000971b  test    rax, rax
0x14000971e  jz      short loc_140009738
0x140009720  test    ebx, ebx
0x140009722  jz      short loc_14000972C
0x140009724  lea     ecx, [rbx-64h]
0x140009727  cmp     ecx, 31h ; '1'
0x14000972a  ja      short loc_140009738
0x14000972c  mov     r8d, ebp
0x14000972f  mov     edx, ebx
0x140009731  mov     ecx, edi
0x140009733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009738  test    r15d, r15d
0x14000973b  jz      short loc_14000974E
0x14000973d  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x140009740  mov     edx, edi; unsigned int
0x140009742  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x140009749  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x14000974e  xor     r14d, r14d
0x140009751  test    esi, esi
0x140009753  jz      short loc_14000977D
0x140009755  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000975c  test    rax, rax
0x14000975f  jnz     short loc_14000976D
0x140009761  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x140009768  test    rax, rax
0x14000976b  jz      short loc_14000977D
0x14000976d  xor     r9d, r9d
0x140009770  mov     r8d, esi
0x140009773  mov     edx, r12d
0x140009776  mov     ecx, edi
0x140009778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000977d  test    r13d, r13d
0x140009780  jnz     short loc_1400097E6
0x140009782  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140009788  test    eax, eax
0x14000978a  jz      short loc_1400097E6
0x14000978c  lea     rcx, SRWLock; SRWLock
0x140009793  call    cs:__imp_AcquireSRWLockExclusive
0x140009799  cmp     cs:qword_1400193C8, r14
0x1400097a0  jnz     short loc_1400097D8
0x1400097a2  mov     cs:qword_1400193C8, r14
0x1400097a9  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1400097b0  test    rax, rax
0x1400097b3  jnz     short loc_1400097C1
0x1400097b5  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1400097bc  test    rax, rax
0x1400097bf  jz      short loc_1400097D8
0x1400097c1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400097c5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x1400097cc  lea     rcx, qword_1400193C8
0x1400097d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400097d8  lea     rcx, SRWLock; SRWLock
0x1400097df  call    cs:__imp_ReleaseSRWLockExclusive
0x1400097e5  nop
0x1400097e6  cmp     [rsp+88h+arg_10], r14d
0x1400097ee  jz      short loc_140009826
0x1400097f0  mov     edx, ebx
0x1400097f2  bts     edx, 1Fh
0x1400097f6  cmp     [rsp+88h+arg_18], r14d
0x1400097fe  cmovz   edx, ebx
0x140009801  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x140009808  test    rax, rax
0x14000980b  jnz     short loc_140009819
0x14000980d  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x140009814  test    rax, rax
0x140009817  jz      short loc_140009826
0x140009819  xor     r9d, r9d
0x14000981c  xor     r8d, r8d
0x14000981f  mov     ecx, edi
0x140009821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009826  test    r13d, r13d
0x140009829  jnz     short loc_14000984A
0x14000982b  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x140009832  test    rax, rax
0x140009835  jz      short loc_14000984D
0x140009837  mov     r8b, [rsp+88h+arg_38]
0x14000983f  mov     edx, ebx
0x140009841  mov     ecx, edi
0x140009843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009848  jmp     short loc_14000984D
0x14000984a  mov     ebp, r14d
0x14000984d  mov     eax, ebp
0x14000984f  mov     rbx, [rsp+88h+arg_0]
0x140009857  add     rsp, 50h
0x14000985b  pop     r15
0x14000985d  pop     r14
0x14000985f  pop     r13
0x140009861  pop     r12
0x140009863  pop     rdi
0x140009864  pop     rsi
0x140009865  pop     rbp
0x140009866  retn
```
