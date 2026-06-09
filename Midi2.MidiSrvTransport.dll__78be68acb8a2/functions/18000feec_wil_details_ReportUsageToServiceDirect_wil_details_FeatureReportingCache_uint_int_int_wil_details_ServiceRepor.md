# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000feec`
- end: `0x18001008b`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000fdb4`

## callees

- `0x18000fa44`
- `0x18000feec`
- `0x1800117f8`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ffb7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ffb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010003`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010003`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(), __int64); // rax
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
    if ( !qword_18001E458 )
    {
      qword_18001E458 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_18001E458, `wil::details::RecordFeatureUsageCallback'::`17'::_lambda_1_::_lambda_invoker_cdecl_, -1);
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
0x18000feec  mov     rax, rsp
0x18000feef  mov     [rax+8], rbx
0x18000fef3  mov     [rax+20h], r9d
0x18000fef7  mov     [rax+18h], r8d
0x18000fefb  push    rbp
0x18000fefc  push    rsi
0x18000fefd  push    rdi
0x18000fefe  push    r12
0x18000ff00  push    r13
0x18000ff02  push    r14
0x18000ff04  push    r15
0x18000ff06  sub     rsp, 50h
0x18000ff0a  mov     edi, edx
0x18000ff0c  mov     r14, rcx
0x18000ff0f  mov     ebx, [rsp+88h+arg_20]
0x18000ff16  mov     r8d, ebx
0x18000ff19  mov     rdx, rcx
0x18000ff1c  lea     rcx, [rax-58h]
0x18000ff20  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000ff25  mov     r15d, [rax]
0x18000ff28  mov     esi, [rax+4]
0x18000ff2b  mov     r12d, [rax+8]
0x18000ff2f  mov     r13d, [rax+10h]
0x18000ff33  mov     ebp, 1
0x18000ff38  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000ff3f  test    rax, rax
0x18000ff42  jz      short loc_18000FF5C
0x18000ff44  test    ebx, ebx
0x18000ff46  jz      short loc_18000FF50
0x18000ff48  lea     ecx, [rbx-64h]
0x18000ff4b  cmp     ecx, 31h ; '1'
0x18000ff4e  ja      short loc_18000FF5C
0x18000ff50  mov     r8d, ebp
0x18000ff53  mov     edx, ebx
0x18000ff55  mov     ecx, edi
0x18000ff57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff5c  test    r15d, r15d
0x18000ff5f  jz      short loc_18000FF72
0x18000ff61  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18000ff64  mov     edx, edi; unsigned int
0x18000ff66  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000ff6d  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000ff72  xor     r14d, r14d
0x18000ff75  test    esi, esi
0x18000ff77  jz      short loc_18000FFA1
0x18000ff79  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000ff80  test    rax, rax
0x18000ff83  jnz     short loc_18000FF91
0x18000ff85  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000ff8c  test    rax, rax
0x18000ff8f  jz      short loc_18000FFA1
0x18000ff91  xor     r9d, r9d
0x18000ff94  mov     r8d, esi
0x18000ff97  mov     edx, r12d
0x18000ff9a  mov     ecx, edi
0x18000ff9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffa1  test    r13d, r13d
0x18000ffa4  jnz     short loc_18001000A
0x18000ffa6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ffac  test    eax, eax
0x18000ffae  jz      short loc_18001000A
0x18000ffb0  lea     rcx, SRWLock; SRWLock
0x18000ffb7  call    cs:__imp_AcquireSRWLockExclusive
0x18000ffbd  cmp     cs:qword_18001E458, r14
0x18000ffc4  jnz     short loc_18000FFFC
0x18000ffc6  mov     cs:qword_18001E458, r14
0x18000ffcd  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000ffd4  test    rax, rax
0x18000ffd7  jnz     short loc_18000FFE5
0x18000ffd9  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000ffe0  test    rax, rax
0x18000ffe3  jz      short loc_18000FFFC
0x18000ffe5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ffe9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z; `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18000fff0  lea     rcx, qword_18001E458
0x18000fff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fffc  lea     rcx, SRWLock; SRWLock
0x180010003  call    cs:__imp_ReleaseSRWLockExclusive
0x180010009  nop
0x18001000a  cmp     [rsp+88h+arg_10], r14d
0x180010012  jz      short loc_18001004A
0x180010014  mov     edx, ebx
0x180010016  bts     edx, 1Fh
0x18001001a  cmp     [rsp+88h+arg_18], r14d
0x180010022  cmovz   edx, ebx
0x180010025  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001002c  test    rax, rax
0x18001002f  jnz     short loc_18001003D
0x180010031  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180010038  test    rax, rax
0x18001003b  jz      short loc_18001004A
0x18001003d  xor     r9d, r9d
0x180010040  xor     r8d, r8d
0x180010043  mov     ecx, edi
0x180010045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001004a  test    r13d, r13d
0x18001004d  jnz     short loc_18001006E
0x18001004f  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180010056  test    rax, rax
0x180010059  jz      short loc_180010071
0x18001005b  mov     r8b, [rsp+88h+arg_38]
0x180010063  mov     edx, ebx
0x180010065  mov     ecx, edi
0x180010067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001006c  jmp     short loc_180010071
0x18001006e  mov     ebp, r14d
0x180010071  mov     eax, ebp
0x180010073  mov     rbx, [rsp+88h+arg_0]
0x18001007b  add     rsp, 50h
0x18001007f  pop     r15
0x180010081  pop     r14
0x180010083  pop     r13
0x180010085  pop     r12
0x180010087  pop     rdi
0x180010088  pop     rsi
0x180010089  pop     rbp
0x18001008a  retn
```
