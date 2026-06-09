# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18002db04`
- end: `0x18002dc97`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `403`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, __int64, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002da2c`

## callees

- `0x18002c22c`
- `0x18002db04`
- `0x180030e70`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002dc17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002dc17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002dbcb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002dbcb`

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
    g_wil_details_RecordSRUMFeatureUsage(45690917, a5, 1);
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
      v18(45690917, v15, v14, 0);
    }
  }
  if ( !v16 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_1800464A0 )
    {
      qword_1800464A0 = 0;
      v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v19(&qword_1800464A0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
      v21(45690917, v20, 0, 0);
    }
  }
  if ( v16 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(45690917, a5, v12);
  }
  return v17;
}

```

## disassembly

```asm
0x18002db04  mov     [rsp+arg_18], r9d
0x18002db09  push    rbx
0x18002db0a  push    rbp
0x18002db0b  push    rsi
0x18002db0c  push    rdi
0x18002db0d  push    r12
0x18002db0f  push    r13
0x18002db11  push    r14
0x18002db13  push    r15
0x18002db15  sub     rsp, 58h
0x18002db19  mov     r13d, r8d
0x18002db1c  mov     rbp, rcx
0x18002db1f  mov     ebx, [rsp+98h+arg_20]
0x18002db26  mov     r8d, ebx
0x18002db29  mov     rdx, rcx
0x18002db2c  lea     rcx, [rsp+98h+var_68]
0x18002db31  call    wil_details_FeatureReporting_RecordUsageInCache
0x18002db36  mov     r14d, [rax]
0x18002db39  mov     edi, [rax+4]
0x18002db3c  mov     r15d, [rax+8]
0x18002db40  mov     r12d, [rax+10h]
0x18002db44  mov     esi, 1
0x18002db49  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18002db50  test    rax, rax
0x18002db53  jz      short loc_18002DB70
0x18002db55  test    ebx, ebx
0x18002db57  jz      short loc_18002DB61
0x18002db59  lea     ecx, [rbx-64h]
0x18002db5c  cmp     ecx, 31h ; '1'
0x18002db5f  ja      short loc_18002DB70
0x18002db61  mov     r8d, esi
0x18002db64  mov     edx, ebx
0x18002db66  mov     ecx, 2B93025h
0x18002db6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db70  test    r14d, r14d
0x18002db73  jz      short loc_18002DB84
0x18002db75  mov     r8, rbp; struct wil_details_FeatureReportingCache *
0x18002db78  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18002db7f  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18002db84  xor     ebp, ebp
0x18002db86  test    edi, edi
0x18002db88  jz      short loc_18002DBB5
0x18002db8a  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18002db91  test    rax, rax
0x18002db94  jnz     short loc_18002DBA2
0x18002db96  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18002db9d  test    rax, rax
0x18002dba0  jz      short loc_18002DBB5
0x18002dba2  xor     r9d, r9d
0x18002dba5  mov     r8d, edi
0x18002dba8  mov     edx, r15d
0x18002dbab  mov     ecx, 2B93025h
0x18002dbb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dbb5  test    r12d, r12d
0x18002dbb8  jnz     short loc_18002DC1E
0x18002dbba  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002dbc0  test    eax, eax
0x18002dbc2  jz      short loc_18002DC1E
0x18002dbc4  lea     rcx, SRWLock; SRWLock
0x18002dbcb  call    cs:__imp_AcquireSRWLockExclusive
0x18002dbd1  cmp     cs:qword_1800464A0, rbp
0x18002dbd8  jnz     short loc_18002DC10
0x18002dbda  mov     cs:qword_1800464A0, rbp
0x18002dbe1  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18002dbe8  test    rax, rax
0x18002dbeb  jnz     short loc_18002DBF9
0x18002dbed  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18002dbf4  test    rax, rax
0x18002dbf7  jz      short loc_18002DC10
0x18002dbf9  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002dbfd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18002dc04  lea     rcx, qword_1800464A0
0x18002dc0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc10  lea     rcx, SRWLock; SRWLock
0x18002dc17  call    cs:__imp_ReleaseSRWLockExclusive
0x18002dc1d  nop
0x18002dc1e  test    r13d, r13d
0x18002dc21  jz      short loc_18002DC5B
0x18002dc23  mov     edx, ebx
0x18002dc25  bts     edx, 1Fh
0x18002dc29  cmp     [rsp+98h+arg_18], ebp
0x18002dc30  cmovz   edx, ebx
0x18002dc33  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18002dc3a  test    rax, rax
0x18002dc3d  jnz     short loc_18002DC4B
0x18002dc3f  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18002dc46  test    rax, rax
0x18002dc49  jz      short loc_18002DC5B
0x18002dc4b  xor     r9d, r9d
0x18002dc4e  xor     r8d, r8d
0x18002dc51  mov     ecx, 2B93025h
0x18002dc56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc5b  test    r12d, r12d
0x18002dc5e  jnz     short loc_18002DC82
0x18002dc60  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18002dc67  test    rax, rax
0x18002dc6a  jz      short loc_18002DC84
0x18002dc6c  mov     r8b, [rsp+98h+arg_38]
0x18002dc74  mov     edx, ebx
0x18002dc76  mov     ecx, 2B93025h
0x18002dc7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc80  jmp     short loc_18002DC84
0x18002dc82  mov     esi, ebp
0x18002dc84  mov     eax, esi
0x18002dc86  add     rsp, 58h
0x18002dc8a  pop     r15
0x18002dc8c  pop     r14
0x18002dc8e  pop     r13
0x18002dc90  pop     r12
0x18002dc92  pop     rdi
0x18002dc93  pop     rsi
0x18002dc94  pop     rbp
0x18002dc95  pop     rbx
0x18002dc96  retn
```
