# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000bc10`
- end: `0x18000bdaf`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000bad8`

## callees

- `0x18000a1bc`
- `0x18000bc10`
- `0x18000fe80`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bd27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bd27`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bcdb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bcdb`

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
    if ( !qword_180019720 )
    {
      qword_180019720 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180019720, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18000bc10  mov     rax, rsp
0x18000bc13  mov     [rax+8], rbx
0x18000bc17  mov     [rax+20h], r9d
0x18000bc1b  mov     [rax+18h], r8d
0x18000bc1f  push    rbp
0x18000bc20  push    rsi
0x18000bc21  push    rdi
0x18000bc22  push    r12
0x18000bc24  push    r13
0x18000bc26  push    r14
0x18000bc28  push    r15
0x18000bc2a  sub     rsp, 50h
0x18000bc2e  mov     edi, edx
0x18000bc30  mov     r14, rcx
0x18000bc33  mov     ebx, [rsp+88h+arg_20]
0x18000bc3a  mov     r8d, ebx
0x18000bc3d  mov     rdx, rcx
0x18000bc40  lea     rcx, [rax-58h]
0x18000bc44  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000bc49  mov     r15d, [rax]
0x18000bc4c  mov     esi, [rax+4]
0x18000bc4f  mov     r12d, [rax+8]
0x18000bc53  mov     r13d, [rax+10h]
0x18000bc57  mov     ebp, 1
0x18000bc5c  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000bc63  test    rax, rax
0x18000bc66  jz      short loc_18000BC80
0x18000bc68  test    ebx, ebx
0x18000bc6a  jz      short loc_18000BC74
0x18000bc6c  lea     ecx, [rbx-64h]
0x18000bc6f  cmp     ecx, 31h ; '1'
0x18000bc72  ja      short loc_18000BC80
0x18000bc74  mov     r8d, ebp
0x18000bc77  mov     edx, ebx
0x18000bc79  mov     ecx, edi
0x18000bc7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc80  test    r15d, r15d
0x18000bc83  jz      short loc_18000BC96
0x18000bc85  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18000bc88  mov     edx, edi; unsigned int
0x18000bc8a  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000bc91  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000bc96  xor     r14d, r14d
0x18000bc99  test    esi, esi
0x18000bc9b  jz      short loc_18000BCC5
0x18000bc9d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000bca4  test    rax, rax
0x18000bca7  jnz     short loc_18000BCB5
0x18000bca9  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000bcb0  test    rax, rax
0x18000bcb3  jz      short loc_18000BCC5
0x18000bcb5  xor     r9d, r9d
0x18000bcb8  mov     r8d, esi
0x18000bcbb  mov     edx, r12d
0x18000bcbe  mov     ecx, edi
0x18000bcc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcc5  test    r13d, r13d
0x18000bcc8  jnz     short loc_18000BD2E
0x18000bcca  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000bcd0  test    eax, eax
0x18000bcd2  jz      short loc_18000BD2E
0x18000bcd4  lea     rcx, SRWLock; SRWLock
0x18000bcdb  call    cs:__imp_AcquireSRWLockExclusive
0x18000bce1  cmp     cs:qword_180019720, r14
0x18000bce8  jnz     short loc_18000BD20
0x18000bcea  mov     cs:qword_180019720, r14
0x18000bcf1  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000bcf8  test    rax, rax
0x18000bcfb  jnz     short loc_18000BD09
0x18000bcfd  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000bd04  test    rax, rax
0x18000bd07  jz      short loc_18000BD20
0x18000bd09  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000bd0d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000bd14  lea     rcx, qword_180019720
0x18000bd1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd20  lea     rcx, SRWLock; SRWLock
0x18000bd27  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bd2d  nop
0x18000bd2e  cmp     [rsp+88h+arg_10], r14d
0x18000bd36  jz      short loc_18000BD6E
0x18000bd38  mov     edx, ebx
0x18000bd3a  bts     edx, 1Fh
0x18000bd3e  cmp     [rsp+88h+arg_18], r14d
0x18000bd46  cmovz   edx, ebx
0x18000bd49  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000bd50  test    rax, rax
0x18000bd53  jnz     short loc_18000BD61
0x18000bd55  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000bd5c  test    rax, rax
0x18000bd5f  jz      short loc_18000BD6E
0x18000bd61  xor     r9d, r9d
0x18000bd64  xor     r8d, r8d
0x18000bd67  mov     ecx, edi
0x18000bd69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd6e  test    r13d, r13d
0x18000bd71  jnz     short loc_18000BD92
0x18000bd73  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000bd7a  test    rax, rax
0x18000bd7d  jz      short loc_18000BD95
0x18000bd7f  mov     r8b, [rsp+88h+arg_38]
0x18000bd87  mov     edx, ebx
0x18000bd89  mov     ecx, edi
0x18000bd8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd90  jmp     short loc_18000BD95
0x18000bd92  mov     ebp, r14d
0x18000bd95  mov     eax, ebp
0x18000bd97  mov     rbx, [rsp+88h+arg_0]
0x18000bd9f  add     rsp, 50h
0x18000bda3  pop     r15
0x18000bda5  pop     r14
0x18000bda7  pop     r13
0x18000bda9  pop     r12
0x18000bdab  pop     rdi
0x18000bdac  pop     rsi
0x18000bdad  pop     rbp
0x18000bdae  retn
```
