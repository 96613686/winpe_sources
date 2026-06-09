# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1400110ac`
- end: `0x14001124a`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `414`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140011010`

## callees

- `0x14000fda8`
- `0x1400110ac`
- `0x1400124e0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400111c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400111c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011177`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011177`

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
    if ( !qword_140019448 )
    {
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_140019448 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_140019448, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x1400110ac  mov     rax, rsp
0x1400110af  mov     [rax+8], rbx
0x1400110b3  mov     [rax+20h], r9d
0x1400110b7  mov     [rax+18h], r8d
0x1400110bb  push    rbp
0x1400110bc  push    rsi
0x1400110bd  push    rdi
0x1400110be  push    r12
0x1400110c0  push    r13
0x1400110c2  push    r14
0x1400110c4  push    r15
0x1400110c6  sub     rsp, 50h
0x1400110ca  mov     ebx, [rsp+88h+arg_20]
0x1400110d1  mov     edi, edx
0x1400110d3  mov     rdx, rcx
0x1400110d6  mov     r14, rcx
0x1400110d9  lea     rcx, [rax-58h]
0x1400110dd  mov     r8d, ebx
0x1400110e0  call    wil_details_FeatureReporting_RecordUsageInCache
0x1400110e5  mov     ebp, 1
0x1400110ea  mov     r15d, [rax]
0x1400110ed  mov     esi, [rax+4]
0x1400110f0  mov     r13d, [rax+8]
0x1400110f4  mov     r12d, [rax+10h]
0x1400110f8  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1400110ff  test    rax, rax
0x140011102  jz      short loc_14001111C
0x140011104  test    ebx, ebx
0x140011106  jz      short loc_140011110
0x140011108  lea     ecx, [rbx-64h]
0x14001110b  cmp     ecx, 31h ; '1'
0x14001110e  ja      short loc_14001111C
0x140011110  mov     r8d, ebp
0x140011113  mov     edx, ebx
0x140011115  mov     ecx, edi
0x140011117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001111c  test    r15d, r15d
0x14001111f  jz      short loc_140011132
0x140011121  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x140011124  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x14001112b  mov     edx, edi; unsigned int
0x14001112d  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x140011132  xor     r14d, r14d
0x140011135  test    esi, esi
0x140011137  jz      short loc_140011161
0x140011139  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x140011140  test    rax, rax
0x140011143  jnz     short loc_140011151
0x140011145  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14001114c  test    rax, rax
0x14001114f  jz      short loc_140011161
0x140011151  xor     r9d, r9d
0x140011154  mov     r8d, esi
0x140011157  mov     edx, r13d
0x14001115a  mov     ecx, edi
0x14001115c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011161  test    r12d, r12d
0x140011164  jnz     short loc_1400111C9
0x140011166  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14001116c  test    eax, eax
0x14001116e  jz      short loc_1400111C9
0x140011170  lea     rcx, SRWLock; SRWLock
0x140011177  call    cs:__imp_AcquireSRWLockExclusive
0x14001117d  cmp     cs:qword_140019448, r14
0x140011184  jnz     short loc_1400111BC
0x140011186  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x14001118d  mov     cs:qword_140019448, r14
0x140011194  test    rax, rax
0x140011197  jnz     short loc_1400111A5
0x140011199  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1400111a0  test    rax, rax
0x1400111a3  jz      short loc_1400111BC
0x1400111a5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400111a9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x1400111b0  lea     rcx, qword_140019448
0x1400111b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400111bc  lea     rcx, SRWLock; SRWLock
0x1400111c3  call    cs:__imp_ReleaseSRWLockExclusive
0x1400111c9  cmp     [rsp+88h+arg_10], r14d
0x1400111d1  jz      short loc_140011209
0x1400111d3  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1400111da  mov     edx, ebx
0x1400111dc  bts     edx, 1Fh
0x1400111e0  cmp     [rsp+88h+arg_18], r14d
0x1400111e8  cmovz   edx, ebx
0x1400111eb  test    rax, rax
0x1400111ee  jnz     short loc_1400111FC
0x1400111f0  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1400111f7  test    rax, rax
0x1400111fa  jz      short loc_140011209
0x1400111fc  xor     r9d, r9d
0x1400111ff  xor     r8d, r8d
0x140011202  mov     ecx, edi
0x140011204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011209  test    r12d, r12d
0x14001120c  jnz     short loc_14001122D
0x14001120e  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x140011215  test    rax, rax
0x140011218  jz      short loc_140011230
0x14001121a  mov     r8b, [rsp+88h+arg_38]
0x140011222  mov     edx, ebx
0x140011224  mov     ecx, edi
0x140011226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001122b  jmp     short loc_140011230
0x14001122d  mov     ebp, r14d
0x140011230  mov     rbx, [rsp+88h+arg_0]
0x140011238  mov     eax, ebp
0x14001123a  add     rsp, 50h
0x14001123e  pop     r15
0x140011240  pop     r14
0x140011242  pop     r13
0x140011244  pop     r12
0x140011246  pop     rdi
0x140011247  pop     rsi
0x140011248  pop     rbp
0x140011249  retn
```
