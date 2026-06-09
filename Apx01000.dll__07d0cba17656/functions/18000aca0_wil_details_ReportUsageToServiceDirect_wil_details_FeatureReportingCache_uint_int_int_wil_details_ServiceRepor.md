# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000aca0`
- end: `0x18000ae3f`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000ab68`

## callees

- `0x18000a9a8`
- `0x18000aca0`
- `0x18000b070`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000adb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000adb7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ad6b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ad6b`

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
    if ( !qword_180033380 )
    {
      qword_180033380 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180033380, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18000aca0  mov     rax, rsp
0x18000aca3  mov     [rax+8], rbx
0x18000aca7  mov     [rax+20h], r9d
0x18000acab  mov     [rax+18h], r8d
0x18000acaf  push    rbp
0x18000acb0  push    rsi
0x18000acb1  push    rdi
0x18000acb2  push    r12
0x18000acb4  push    r13
0x18000acb6  push    r14
0x18000acb8  push    r15
0x18000acba  sub     rsp, 50h
0x18000acbe  mov     edi, edx
0x18000acc0  mov     r14, rcx
0x18000acc3  mov     ebx, [rsp+88h+arg_20]
0x18000acca  mov     r8d, ebx
0x18000accd  mov     rdx, rcx
0x18000acd0  lea     rcx, [rax-58h]
0x18000acd4  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000acd9  mov     r15d, [rax]
0x18000acdc  mov     esi, [rax+4]
0x18000acdf  mov     r12d, [rax+8]
0x18000ace3  mov     r13d, [rax+10h]
0x18000ace7  mov     ebp, 1
0x18000acec  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000acf3  test    rax, rax
0x18000acf6  jz      short loc_18000AD10
0x18000acf8  test    ebx, ebx
0x18000acfa  jz      short loc_18000AD04
0x18000acfc  lea     ecx, [rbx-64h]
0x18000acff  cmp     ecx, 31h ; '1'
0x18000ad02  ja      short loc_18000AD10
0x18000ad04  mov     r8d, ebp
0x18000ad07  mov     edx, ebx
0x18000ad09  mov     ecx, edi
0x18000ad0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad10  test    r15d, r15d
0x18000ad13  jz      short loc_18000AD26
0x18000ad15  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18000ad18  mov     edx, edi; unsigned int
0x18000ad1a  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000ad21  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000ad26  xor     r14d, r14d
0x18000ad29  test    esi, esi
0x18000ad2b  jz      short loc_18000AD55
0x18000ad2d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000ad34  test    rax, rax
0x18000ad37  jnz     short loc_18000AD45
0x18000ad39  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000ad40  test    rax, rax
0x18000ad43  jz      short loc_18000AD55
0x18000ad45  xor     r9d, r9d
0x18000ad48  mov     r8d, esi
0x18000ad4b  mov     edx, r12d
0x18000ad4e  mov     ecx, edi
0x18000ad50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad55  test    r13d, r13d
0x18000ad58  jnz     short loc_18000ADBE
0x18000ad5a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ad60  test    eax, eax
0x18000ad62  jz      short loc_18000ADBE
0x18000ad64  lea     rcx, SRWLock; SRWLock
0x18000ad6b  call    cs:__imp_AcquireSRWLockExclusive
0x18000ad71  cmp     cs:qword_180033380, r14
0x18000ad78  jnz     short loc_18000ADB0
0x18000ad7a  mov     cs:qword_180033380, r14
0x18000ad81  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000ad88  test    rax, rax
0x18000ad8b  jnz     short loc_18000AD99
0x18000ad8d  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000ad94  test    rax, rax
0x18000ad97  jz      short loc_18000ADB0
0x18000ad99  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ad9d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000ada4  lea     rcx, qword_180033380
0x18000adab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adb0  lea     rcx, SRWLock; SRWLock
0x18000adb7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000adbd  nop
0x18000adbe  cmp     [rsp+88h+arg_10], r14d
0x18000adc6  jz      short loc_18000ADFE
0x18000adc8  mov     edx, ebx
0x18000adca  bts     edx, 1Fh
0x18000adce  cmp     [rsp+88h+arg_18], r14d
0x18000add6  cmovz   edx, ebx
0x18000add9  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000ade0  test    rax, rax
0x18000ade3  jnz     short loc_18000ADF1
0x18000ade5  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000adec  test    rax, rax
0x18000adef  jz      short loc_18000ADFE
0x18000adf1  xor     r9d, r9d
0x18000adf4  xor     r8d, r8d
0x18000adf7  mov     ecx, edi
0x18000adf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adfe  test    r13d, r13d
0x18000ae01  jnz     short loc_18000AE22
0x18000ae03  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000ae0a  test    rax, rax
0x18000ae0d  jz      short loc_18000AE25
0x18000ae0f  mov     r8b, [rsp+88h+arg_38]
0x18000ae17  mov     edx, ebx
0x18000ae19  mov     ecx, edi
0x18000ae1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae20  jmp     short loc_18000AE25
0x18000ae22  mov     ebp, r14d
0x18000ae25  mov     eax, ebp
0x18000ae27  mov     rbx, [rsp+88h+arg_0]
0x18000ae2f  add     rsp, 50h
0x18000ae33  pop     r15
0x18000ae35  pop     r14
0x18000ae37  pop     r13
0x18000ae39  pop     r12
0x18000ae3b  pop     rdi
0x18000ae3c  pop     rsi
0x18000ae3d  pop     rbp
0x18000ae3e  retn
```
