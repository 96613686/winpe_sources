# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000fd0c`
- end: `0x18000feab`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000fbd4`

## callees

- `0x18000f870`
- `0x18000fd0c`
- `0x18001068c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fdd7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fdd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fe23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fe23`

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
    if ( !qword_18001A3A0 )
    {
      qword_18001A3A0 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_18001A3A0, `wil::details::RecordFeatureUsageCallback'::`17'::_lambda_1_::_lambda_invoker_cdecl_, -1);
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
0x18000fd0c  mov     rax, rsp
0x18000fd0f  mov     [rax+8], rbx
0x18000fd13  mov     [rax+20h], r9d
0x18000fd17  mov     [rax+18h], r8d
0x18000fd1b  push    rbp
0x18000fd1c  push    rsi
0x18000fd1d  push    rdi
0x18000fd1e  push    r12
0x18000fd20  push    r13
0x18000fd22  push    r14
0x18000fd24  push    r15
0x18000fd26  sub     rsp, 50h
0x18000fd2a  mov     edi, edx
0x18000fd2c  mov     r14, rcx
0x18000fd2f  mov     ebx, [rsp+88h+arg_20]
0x18000fd36  mov     r8d, ebx
0x18000fd39  mov     rdx, rcx
0x18000fd3c  lea     rcx, [rax-58h]
0x18000fd40  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000fd45  mov     r15d, [rax]
0x18000fd48  mov     esi, [rax+4]
0x18000fd4b  mov     r12d, [rax+8]
0x18000fd4f  mov     r13d, [rax+10h]
0x18000fd53  mov     ebp, 1
0x18000fd58  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000fd5f  test    rax, rax
0x18000fd62  jz      short loc_18000FD7C
0x18000fd64  test    ebx, ebx
0x18000fd66  jz      short loc_18000FD70
0x18000fd68  lea     ecx, [rbx-64h]
0x18000fd6b  cmp     ecx, 31h ; '1'
0x18000fd6e  ja      short loc_18000FD7C
0x18000fd70  mov     r8d, ebp
0x18000fd73  mov     edx, ebx
0x18000fd75  mov     ecx, edi
0x18000fd77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd7c  test    r15d, r15d
0x18000fd7f  jz      short loc_18000FD92
0x18000fd81  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18000fd84  mov     edx, edi; unsigned int
0x18000fd86  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000fd8d  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000fd92  xor     r14d, r14d
0x18000fd95  test    esi, esi
0x18000fd97  jz      short loc_18000FDC1
0x18000fd99  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000fda0  test    rax, rax
0x18000fda3  jnz     short loc_18000FDB1
0x18000fda5  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000fdac  test    rax, rax
0x18000fdaf  jz      short loc_18000FDC1
0x18000fdb1  xor     r9d, r9d
0x18000fdb4  mov     r8d, esi
0x18000fdb7  mov     edx, r12d
0x18000fdba  mov     ecx, edi
0x18000fdbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdc1  test    r13d, r13d
0x18000fdc4  jnz     short loc_18000FE2A
0x18000fdc6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000fdcc  test    eax, eax
0x18000fdce  jz      short loc_18000FE2A
0x18000fdd0  lea     rcx, SRWLock; SRWLock
0x18000fdd7  call    cs:__imp_AcquireSRWLockExclusive
0x18000fddd  cmp     cs:qword_18001A3A0, r14
0x18000fde4  jnz     short loc_18000FE1C
0x18000fde6  mov     cs:qword_18001A3A0, r14
0x18000fded  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000fdf4  test    rax, rax
0x18000fdf7  jnz     short loc_18000FE05
0x18000fdf9  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000fe00  test    rax, rax
0x18000fe03  jz      short loc_18000FE1C
0x18000fe05  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000fe09  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z; `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18000fe10  lea     rcx, qword_18001A3A0
0x18000fe17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe1c  lea     rcx, SRWLock; SRWLock
0x18000fe23  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fe29  nop
0x18000fe2a  cmp     [rsp+88h+arg_10], r14d
0x18000fe32  jz      short loc_18000FE6A
0x18000fe34  mov     edx, ebx
0x18000fe36  bts     edx, 1Fh
0x18000fe3a  cmp     [rsp+88h+arg_18], r14d
0x18000fe42  cmovz   edx, ebx
0x18000fe45  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000fe4c  test    rax, rax
0x18000fe4f  jnz     short loc_18000FE5D
0x18000fe51  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000fe58  test    rax, rax
0x18000fe5b  jz      short loc_18000FE6A
0x18000fe5d  xor     r9d, r9d
0x18000fe60  xor     r8d, r8d
0x18000fe63  mov     ecx, edi
0x18000fe65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe6a  test    r13d, r13d
0x18000fe6d  jnz     short loc_18000FE8E
0x18000fe6f  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000fe76  test    rax, rax
0x18000fe79  jz      short loc_18000FE91
0x18000fe7b  mov     r8b, [rsp+88h+arg_38]
0x18000fe83  mov     edx, ebx
0x18000fe85  mov     ecx, edi
0x18000fe87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe8c  jmp     short loc_18000FE91
0x18000fe8e  mov     ebp, r14d
0x18000fe91  mov     eax, ebp
0x18000fe93  mov     rbx, [rsp+88h+arg_0]
0x18000fe9b  add     rsp, 50h
0x18000fe9f  pop     r15
0x18000fea1  pop     r14
0x18000fea3  pop     r13
0x18000fea5  pop     r12
0x18000fea7  pop     rdi
0x18000fea8  pop     rsi
0x18000fea9  pop     rbp
0x18000feaa  retn
```
