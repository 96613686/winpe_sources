# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000dda0`
- end: `0x18000df3f`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000dc68`

## callees

- `0x18000c84c`
- `0x18000dda0`
- `0x180012510`
- `0x180015010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000de6b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000de6b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000deb7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000deb7`

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
    if ( !qword_180023770 )
    {
      qword_180023770 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180023770, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18000dda0  mov     rax, rsp
0x18000dda3  mov     [rax+8], rbx
0x18000dda7  mov     [rax+20h], r9d
0x18000ddab  mov     [rax+18h], r8d
0x18000ddaf  push    rbp
0x18000ddb0  push    rsi
0x18000ddb1  push    rdi
0x18000ddb2  push    r12
0x18000ddb4  push    r13
0x18000ddb6  push    r14
0x18000ddb8  push    r15
0x18000ddba  sub     rsp, 50h
0x18000ddbe  mov     edi, edx
0x18000ddc0  mov     r14, rcx
0x18000ddc3  mov     ebx, [rsp+88h+arg_20]
0x18000ddca  mov     r8d, ebx
0x18000ddcd  mov     rdx, rcx
0x18000ddd0  lea     rcx, [rax-58h]
0x18000ddd4  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000ddd9  mov     r15d, [rax]
0x18000dddc  mov     esi, [rax+4]
0x18000dddf  mov     r12d, [rax+8]
0x18000dde3  mov     r13d, [rax+10h]
0x18000dde7  mov     ebp, 1
0x18000ddec  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000ddf3  test    rax, rax
0x18000ddf6  jz      short loc_18000DE10
0x18000ddf8  test    ebx, ebx
0x18000ddfa  jz      short loc_18000DE04
0x18000ddfc  lea     ecx, [rbx-64h]
0x18000ddff  cmp     ecx, 31h ; '1'
0x18000de02  ja      short loc_18000DE10
0x18000de04  mov     r8d, ebp
0x18000de07  mov     edx, ebx
0x18000de09  mov     ecx, edi
0x18000de0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de10  test    r15d, r15d
0x18000de13  jz      short loc_18000DE26
0x18000de15  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18000de18  mov     edx, edi; unsigned int
0x18000de1a  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000de21  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000de26  xor     r14d, r14d
0x18000de29  test    esi, esi
0x18000de2b  jz      short loc_18000DE55
0x18000de2d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000de34  test    rax, rax
0x18000de37  jnz     short loc_18000DE45
0x18000de39  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000de40  test    rax, rax
0x18000de43  jz      short loc_18000DE55
0x18000de45  xor     r9d, r9d
0x18000de48  mov     r8d, esi
0x18000de4b  mov     edx, r12d
0x18000de4e  mov     ecx, edi
0x18000de50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de55  test    r13d, r13d
0x18000de58  jnz     short loc_18000DEBE
0x18000de5a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000de60  test    eax, eax
0x18000de62  jz      short loc_18000DEBE
0x18000de64  lea     rcx, SRWLock; SRWLock
0x18000de6b  call    cs:__imp_AcquireSRWLockExclusive
0x18000de71  cmp     cs:qword_180023770, r14
0x18000de78  jnz     short loc_18000DEB0
0x18000de7a  mov     cs:qword_180023770, r14
0x18000de81  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000de88  test    rax, rax
0x18000de8b  jnz     short loc_18000DE99
0x18000de8d  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000de94  test    rax, rax
0x18000de97  jz      short loc_18000DEB0
0x18000de99  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000de9d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000dea4  lea     rcx, qword_180023770
0x18000deab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deb0  lea     rcx, SRWLock; SRWLock
0x18000deb7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000debd  nop
0x18000debe  cmp     [rsp+88h+arg_10], r14d
0x18000dec6  jz      short loc_18000DEFE
0x18000dec8  mov     edx, ebx
0x18000deca  bts     edx, 1Fh
0x18000dece  cmp     [rsp+88h+arg_18], r14d
0x18000ded6  cmovz   edx, ebx
0x18000ded9  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000dee0  test    rax, rax
0x18000dee3  jnz     short loc_18000DEF1
0x18000dee5  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000deec  test    rax, rax
0x18000deef  jz      short loc_18000DEFE
0x18000def1  xor     r9d, r9d
0x18000def4  xor     r8d, r8d
0x18000def7  mov     ecx, edi
0x18000def9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000defe  test    r13d, r13d
0x18000df01  jnz     short loc_18000DF22
0x18000df03  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000df0a  test    rax, rax
0x18000df0d  jz      short loc_18000DF25
0x18000df0f  mov     r8b, [rsp+88h+arg_38]
0x18000df17  mov     edx, ebx
0x18000df19  mov     ecx, edi
0x18000df1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df20  jmp     short loc_18000DF25
0x18000df22  mov     ebp, r14d
0x18000df25  mov     eax, ebp
0x18000df27  mov     rbx, [rsp+88h+arg_0]
0x18000df2f  add     rsp, 50h
0x18000df33  pop     r15
0x18000df35  pop     r14
0x18000df37  pop     r13
0x18000df39  pop     r12
0x18000df3b  pop     rdi
0x18000df3c  pop     rsi
0x18000df3d  pop     rbp
0x18000df3e  retn
```
