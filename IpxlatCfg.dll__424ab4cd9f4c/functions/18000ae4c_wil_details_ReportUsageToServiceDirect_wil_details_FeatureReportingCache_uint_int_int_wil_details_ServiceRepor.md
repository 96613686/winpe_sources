# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000ae4c`
- end: `0x18000afeb`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000ad14`

## callees

- `0x18000aabc`
- `0x18000ae4c`
- `0x18000b2b0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000af17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000af17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000af63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000af63`

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
    if ( !qword_180023480 )
    {
      qword_180023480 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180023480, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18000ae4c  mov     rax, rsp
0x18000ae4f  mov     [rax+8], rbx
0x18000ae53  mov     [rax+20h], r9d
0x18000ae57  mov     [rax+18h], r8d
0x18000ae5b  push    rbp
0x18000ae5c  push    rsi
0x18000ae5d  push    rdi
0x18000ae5e  push    r12
0x18000ae60  push    r13
0x18000ae62  push    r14
0x18000ae64  push    r15
0x18000ae66  sub     rsp, 50h
0x18000ae6a  mov     edi, edx
0x18000ae6c  mov     r14, rcx
0x18000ae6f  mov     ebx, [rsp+88h+arg_20]
0x18000ae76  mov     r8d, ebx
0x18000ae79  mov     rdx, rcx
0x18000ae7c  lea     rcx, [rax-58h]
0x18000ae80  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000ae85  mov     r15d, [rax]
0x18000ae88  mov     esi, [rax+4]
0x18000ae8b  mov     r12d, [rax+8]
0x18000ae8f  mov     r13d, [rax+10h]
0x18000ae93  mov     ebp, 1
0x18000ae98  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000ae9f  test    rax, rax
0x18000aea2  jz      short loc_18000AEBC
0x18000aea4  test    ebx, ebx
0x18000aea6  jz      short loc_18000AEB0
0x18000aea8  lea     ecx, [rbx-64h]
0x18000aeab  cmp     ecx, 31h ; '1'
0x18000aeae  ja      short loc_18000AEBC
0x18000aeb0  mov     r8d, ebp
0x18000aeb3  mov     edx, ebx
0x18000aeb5  mov     ecx, edi
0x18000aeb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aebc  test    r15d, r15d
0x18000aebf  jz      short loc_18000AED2
0x18000aec1  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18000aec4  mov     edx, edi; unsigned int
0x18000aec6  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000aecd  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000aed2  xor     r14d, r14d
0x18000aed5  test    esi, esi
0x18000aed7  jz      short loc_18000AF01
0x18000aed9  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000aee0  test    rax, rax
0x18000aee3  jnz     short loc_18000AEF1
0x18000aee5  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000aeec  test    rax, rax
0x18000aeef  jz      short loc_18000AF01
0x18000aef1  xor     r9d, r9d
0x18000aef4  mov     r8d, esi
0x18000aef7  mov     edx, r12d
0x18000aefa  mov     ecx, edi
0x18000aefc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af01  test    r13d, r13d
0x18000af04  jnz     short loc_18000AF6A
0x18000af06  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000af0c  test    eax, eax
0x18000af0e  jz      short loc_18000AF6A
0x18000af10  lea     rcx, SRWLock; SRWLock
0x18000af17  call    cs:__imp_AcquireSRWLockExclusive
0x18000af1d  cmp     cs:qword_180023480, r14
0x18000af24  jnz     short loc_18000AF5C
0x18000af26  mov     cs:qword_180023480, r14
0x18000af2d  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000af34  test    rax, rax
0x18000af37  jnz     short loc_18000AF45
0x18000af39  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000af40  test    rax, rax
0x18000af43  jz      short loc_18000AF5C
0x18000af45  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000af49  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000af50  lea     rcx, qword_180023480
0x18000af57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af5c  lea     rcx, SRWLock; SRWLock
0x18000af63  call    cs:__imp_ReleaseSRWLockExclusive
0x18000af69  nop
0x18000af6a  cmp     [rsp+88h+arg_10], r14d
0x18000af72  jz      short loc_18000AFAA
0x18000af74  mov     edx, ebx
0x18000af76  bts     edx, 1Fh
0x18000af7a  cmp     [rsp+88h+arg_18], r14d
0x18000af82  cmovz   edx, ebx
0x18000af85  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000af8c  test    rax, rax
0x18000af8f  jnz     short loc_18000AF9D
0x18000af91  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000af98  test    rax, rax
0x18000af9b  jz      short loc_18000AFAA
0x18000af9d  xor     r9d, r9d
0x18000afa0  xor     r8d, r8d
0x18000afa3  mov     ecx, edi
0x18000afa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afaa  test    r13d, r13d
0x18000afad  jnz     short loc_18000AFCE
0x18000afaf  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000afb6  test    rax, rax
0x18000afb9  jz      short loc_18000AFD1
0x18000afbb  mov     r8b, [rsp+88h+arg_38]
0x18000afc3  mov     edx, ebx
0x18000afc5  mov     ecx, edi
0x18000afc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afcc  jmp     short loc_18000AFD1
0x18000afce  mov     ebp, r14d
0x18000afd1  mov     eax, ebp
0x18000afd3  mov     rbx, [rsp+88h+arg_0]
0x18000afdb  add     rsp, 50h
0x18000afdf  pop     r15
0x18000afe1  pop     r14
0x18000afe3  pop     r13
0x18000afe5  pop     r12
0x18000afe7  pop     rdi
0x18000afe8  pop     rsi
0x18000afe9  pop     rbp
0x18000afea  retn
```
