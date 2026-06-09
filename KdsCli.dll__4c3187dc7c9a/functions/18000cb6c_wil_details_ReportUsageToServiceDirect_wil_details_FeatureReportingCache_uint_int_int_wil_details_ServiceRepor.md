# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000cb6c`
- end: `0x18000ccfe`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000ca94`

## callees

- `0x18000c740`
- `0x18000cb6c`
- `0x18000d35c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cc33`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cc33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc7f`

## pseudocode

```c
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
  unsigned int v13; // esi
  int v14; // r14d
  unsigned int v15; // edi
  unsigned int v16; // r12d
  int v17; // r15d
  void (__fastcall *v18)(__int64, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v19)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  void (__fastcall *v20)(__int64, __int64, _QWORD, _QWORD); // rax
  __int64 v21; // rdx
  _BYTE v23[104]; // [rsp+30h] [rbp-68h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v23, a1, a5);
  v13 = 1;
  v14 = *v10;
  v15 = v10[1];
  v16 = v10[2];
  v17 = v10[4];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(22235952, a5, 1);
  if ( v14 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      v11,
      a1);
  if ( v15 )
  {
    v18 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v18 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v18(22235952, v16, v15, 0);
    }
  }
  if ( !v17 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&stru_180023208);
    if ( !qword_180023268 )
    {
      v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_180023268 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v19(&qword_180023268, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&stru_180023208);
  }
  if ( a3 )
  {
    v20 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    v21 = a5;
    LODWORD(v21) = a5 | 0x80000000;
    if ( !a4 )
      v21 = a5;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v20 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v20(22235952, v21, 0, 0);
    }
  }
  if ( v17 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(22235952, a5, v12);
  }
  return v13;
}

```

## disassembly

```asm
0x18000cb6c  mov     [rsp+arg_18], r9d
0x18000cb71  push    rbx
0x18000cb72  push    rbp
0x18000cb73  push    rsi
0x18000cb74  push    rdi
0x18000cb75  push    r12
0x18000cb77  push    r13
0x18000cb79  push    r14
0x18000cb7b  push    r15
0x18000cb7d  sub     rsp, 58h
0x18000cb81  mov     ebx, [rsp+98h+arg_20]
0x18000cb88  mov     r13d, r8d
0x18000cb8b  mov     rbp, rcx
0x18000cb8e  mov     rdx, rcx
0x18000cb91  mov     r8d, ebx
0x18000cb94  lea     rcx, [rsp+98h+var_68]
0x18000cb99  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000cb9e  mov     esi, 1
0x18000cba3  mov     r14d, [rax]
0x18000cba6  mov     edi, [rax+4]
0x18000cba9  mov     r12d, [rax+8]
0x18000cbad  mov     r15d, [rax+10h]
0x18000cbb1  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000cbb8  test    rax, rax
0x18000cbbb  jz      short loc_18000CBD8
0x18000cbbd  test    ebx, ebx
0x18000cbbf  jz      short loc_18000CBC9
0x18000cbc1  lea     ecx, [rbx-64h]
0x18000cbc4  cmp     ecx, 31h ; '1'
0x18000cbc7  ja      short loc_18000CBD8
0x18000cbc9  mov     r8d, esi
0x18000cbcc  mov     edx, ebx
0x18000cbce  mov     ecx, 1534B30h
0x18000cbd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbd8  test    r14d, r14d
0x18000cbdb  jz      short loc_18000CBEC
0x18000cbdd  mov     r8, rbp; struct wil_details_FeatureReportingCache *
0x18000cbe0  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000cbe7  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000cbec  xor     ebp, ebp
0x18000cbee  test    edi, edi
0x18000cbf0  jz      short loc_18000CC1D
0x18000cbf2  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000cbf9  test    rax, rax
0x18000cbfc  jnz     short loc_18000CC0A
0x18000cbfe  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000cc05  test    rax, rax
0x18000cc08  jz      short loc_18000CC1D
0x18000cc0a  xor     r9d, r9d
0x18000cc0d  mov     r8d, edi
0x18000cc10  mov     edx, r12d
0x18000cc13  mov     ecx, 1534B30h
0x18000cc18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc1d  test    r15d, r15d
0x18000cc20  jnz     short loc_18000CC85
0x18000cc22  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000cc28  test    eax, eax
0x18000cc2a  jz      short loc_18000CC85
0x18000cc2c  lea     rcx, stru_180023208; SRWLock
0x18000cc33  call    cs:__imp_AcquireSRWLockExclusive
0x18000cc39  cmp     cs:qword_180023268, rbp
0x18000cc40  jnz     short loc_18000CC78
0x18000cc42  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000cc49  mov     cs:qword_180023268, rbp
0x18000cc50  test    rax, rax
0x18000cc53  jnz     short loc_18000CC61
0x18000cc55  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000cc5c  test    rax, rax
0x18000cc5f  jz      short loc_18000CC78
0x18000cc61  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000cc65  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000cc6c  lea     rcx, qword_180023268
0x18000cc73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc78  lea     rcx, stru_180023208; SRWLock
0x18000cc7f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cc85  test    r13d, r13d
0x18000cc88  jz      short loc_18000CCC2
0x18000cc8a  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000cc91  mov     edx, ebx
0x18000cc93  bts     edx, 1Fh
0x18000cc97  cmp     [rsp+98h+arg_18], ebp
0x18000cc9e  cmovz   edx, ebx
0x18000cca1  test    rax, rax
0x18000cca4  jnz     short loc_18000CCB2
0x18000cca6  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000ccad  test    rax, rax
0x18000ccb0  jz      short loc_18000CCC2
0x18000ccb2  xor     r9d, r9d
0x18000ccb5  xor     r8d, r8d
0x18000ccb8  mov     ecx, 1534B30h
0x18000ccbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccc2  test    r15d, r15d
0x18000ccc5  jnz     short loc_18000CCE9
0x18000ccc7  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000ccce  test    rax, rax
0x18000ccd1  jz      short loc_18000CCEB
0x18000ccd3  mov     r8b, [rsp+98h+arg_38]
0x18000ccdb  mov     edx, ebx
0x18000ccdd  mov     ecx, 1534B30h
0x18000cce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cce7  jmp     short loc_18000CCEB
0x18000cce9  mov     esi, ebp
0x18000cceb  mov     eax, esi
0x18000cced  add     rsp, 58h
0x18000ccf1  pop     r15
0x18000ccf3  pop     r14
0x18000ccf5  pop     r13
0x18000ccf7  pop     r12
0x18000ccf9  pop     rdi
0x18000ccfa  pop     rsi
0x18000ccfb  pop     rbp
0x18000ccfc  pop     rbx
0x18000ccfd  retn
```
