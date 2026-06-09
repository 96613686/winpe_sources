# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18001ce40`
- end: `0x18001cfec`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `428`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001cd08`

## callees

- `0x18001c7d0`
- `0x18001ce40`
- `0x18001d578`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cf5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cf5d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cf0b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cf0b`

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
    if ( !qword_180043920 )
    {
      qword_180043920 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180043920, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18001ce40  mov     rax, rsp
0x18001ce43  mov     [rax+8], rbx
0x18001ce47  mov     [rax+20h], r9d
0x18001ce4b  mov     [rax+18h], r8d
0x18001ce4f  push    rbp
0x18001ce50  push    rsi
0x18001ce51  push    rdi
0x18001ce52  push    r12
0x18001ce54  push    r13
0x18001ce56  push    r14
0x18001ce58  push    r15
0x18001ce5a  sub     rsp, 50h
0x18001ce5e  mov     edi, edx
0x18001ce60  mov     r14, rcx
0x18001ce63  mov     ebx, [rsp+88h+arg_20]
0x18001ce6a  mov     r8d, ebx
0x18001ce6d  mov     rdx, rcx
0x18001ce70  lea     rcx, [rax-58h]
0x18001ce74  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001ce79  mov     r15d, [rax]
0x18001ce7c  mov     esi, [rax+4]
0x18001ce7f  mov     r12d, [rax+8]
0x18001ce83  mov     r13d, [rax+10h]
0x18001ce87  mov     ebp, 1
0x18001ce8c  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18001ce93  test    rax, rax
0x18001ce96  jz      short loc_18001CEB0
0x18001ce98  test    ebx, ebx
0x18001ce9a  jz      short loc_18001CEA4
0x18001ce9c  lea     ecx, [rbx-64h]
0x18001ce9f  cmp     ecx, 31h ; '1'
0x18001cea2  ja      short loc_18001CEB0
0x18001cea4  mov     r8d, ebp
0x18001cea7  mov     edx, ebx
0x18001cea9  mov     ecx, edi
0x18001ceab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ceb0  test    r15d, r15d
0x18001ceb3  jz      short loc_18001CEC6
0x18001ceb5  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18001ceb8  mov     edx, edi; unsigned int
0x18001ceba  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18001cec1  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001cec6  xor     r14d, r14d
0x18001cec9  test    esi, esi
0x18001cecb  jz      short loc_18001CEF5
0x18001cecd  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001ced4  test    rax, rax
0x18001ced7  jnz     short loc_18001CEE5
0x18001ced9  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001cee0  test    rax, rax
0x18001cee3  jz      short loc_18001CEF5
0x18001cee5  xor     r9d, r9d
0x18001cee8  mov     r8d, esi
0x18001ceeb  mov     edx, r12d
0x18001ceee  mov     ecx, edi
0x18001cef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cef5  test    r13d, r13d
0x18001cef8  jnz     short loc_18001CF6A
0x18001cefa  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001cf00  test    eax, eax
0x18001cf02  jz      short loc_18001CF6A
0x18001cf04  lea     rcx, SRWLock; SRWLock
0x18001cf0b  call    cs:__imp_AcquireSRWLockExclusive
0x18001cf12  nop     dword ptr [rax+rax+00h]
0x18001cf17  cmp     cs:qword_180043920, r14
0x18001cf1e  jnz     short loc_18001CF56
0x18001cf20  mov     cs:qword_180043920, r14
0x18001cf27  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001cf2e  test    rax, rax
0x18001cf31  jnz     short loc_18001CF3F
0x18001cf33  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001cf3a  test    rax, rax
0x18001cf3d  jz      short loc_18001CF56
0x18001cf3f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001cf43  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18001cf4a  lea     rcx, qword_180043920
0x18001cf51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf56  lea     rcx, SRWLock; SRWLock
0x18001cf5d  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cf64  nop     dword ptr [rax+rax+00h]
0x18001cf69  nop
0x18001cf6a  cmp     [rsp+88h+arg_10], r14d
0x18001cf72  jz      short loc_18001CFAA
0x18001cf74  mov     edx, ebx
0x18001cf76  bts     edx, 1Fh
0x18001cf7a  cmp     [rsp+88h+arg_18], r14d
0x18001cf82  cmovz   edx, ebx
0x18001cf85  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001cf8c  test    rax, rax
0x18001cf8f  jnz     short loc_18001CF9D
0x18001cf91  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001cf98  test    rax, rax
0x18001cf9b  jz      short loc_18001CFAA
0x18001cf9d  xor     r9d, r9d
0x18001cfa0  xor     r8d, r8d
0x18001cfa3  mov     ecx, edi
0x18001cfa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfaa  test    r13d, r13d
0x18001cfad  jnz     short loc_18001CFCE
0x18001cfaf  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18001cfb6  test    rax, rax
0x18001cfb9  jz      short loc_18001CFD1
0x18001cfbb  mov     r8b, [rsp+88h+arg_38]
0x18001cfc3  mov     edx, ebx
0x18001cfc5  mov     ecx, edi
0x18001cfc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfcc  jmp     short loc_18001CFD1
0x18001cfce  mov     ebp, r14d
0x18001cfd1  mov     eax, ebp
0x18001cfd3  mov     rbx, [rsp+88h+arg_0]
0x18001cfdb  add     rsp, 50h
0x18001cfdf  pop     r15
0x18001cfe1  pop     r14
0x18001cfe3  pop     r13
0x18001cfe5  pop     r12
0x18001cfe7  pop     rdi
0x18001cfe8  pop     rsi
0x18001cfe9  pop     rbp
0x18001cfea  retn
```
