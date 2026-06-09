# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1400090c0`
- end: `0x14000925e`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140009024`

## callees

- `0x140007930`
- `0x1400090c0`
- `0x14000aec0`
- `0x140017010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400091d7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400091d7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000918b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000918b`

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
    if ( !qword_140020A90 )
    {
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_140020A90 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_140020A90, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x1400090c0  mov     rax, rsp
0x1400090c3  mov     [rax+8], rbx
0x1400090c7  mov     [rax+20h], r9d
0x1400090cb  mov     [rax+18h], r8d
0x1400090cf  push    rbp
0x1400090d0  push    rsi
0x1400090d1  push    rdi
0x1400090d2  push    r12
0x1400090d4  push    r13
0x1400090d6  push    r14
0x1400090d8  push    r15
0x1400090da  sub     rsp, 50h
0x1400090de  mov     ebx, [rsp+88h+arg_20]
0x1400090e5  mov     edi, edx
0x1400090e7  mov     rdx, rcx
0x1400090ea  mov     r14, rcx
0x1400090ed  lea     rcx, [rax-58h]
0x1400090f1  mov     r8d, ebx
0x1400090f4  call    wil_details_FeatureReporting_RecordUsageInCache
0x1400090f9  mov     ebp, 1
0x1400090fe  mov     r15d, [rax]
0x140009101  mov     esi, [rax+4]
0x140009104  mov     r13d, [rax+8]
0x140009108  mov     r12d, [rax+10h]
0x14000910c  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x140009113  test    rax, rax
0x140009116  jz      short loc_140009130
0x140009118  test    ebx, ebx
0x14000911a  jz      short loc_140009124
0x14000911c  lea     ecx, [rbx-64h]
0x14000911f  cmp     ecx, 31h ; '1'
0x140009122  ja      short loc_140009130
0x140009124  mov     r8d, ebp
0x140009127  mov     edx, ebx
0x140009129  mov     ecx, edi
0x14000912b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009130  test    r15d, r15d
0x140009133  jz      short loc_140009146
0x140009135  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x140009138  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x14000913f  mov     edx, edi; unsigned int
0x140009141  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x140009146  xor     r14d, r14d
0x140009149  test    esi, esi
0x14000914b  jz      short loc_140009175
0x14000914d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x140009154  test    rax, rax
0x140009157  jnz     short loc_140009165
0x140009159  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x140009160  test    rax, rax
0x140009163  jz      short loc_140009175
0x140009165  xor     r9d, r9d
0x140009168  mov     r8d, esi
0x14000916b  mov     edx, r13d
0x14000916e  mov     ecx, edi
0x140009170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009175  test    r12d, r12d
0x140009178  jnz     short loc_1400091DD
0x14000917a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140009180  test    eax, eax
0x140009182  jz      short loc_1400091DD
0x140009184  lea     rcx, SRWLock; SRWLock
0x14000918b  call    cs:__imp_AcquireSRWLockExclusive
0x140009191  cmp     cs:qword_140020A90, r14
0x140009198  jnz     short loc_1400091D0
0x14000919a  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1400091a1  mov     cs:qword_140020A90, r14
0x1400091a8  test    rax, rax
0x1400091ab  jnz     short loc_1400091B9
0x1400091ad  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1400091b4  test    rax, rax
0x1400091b7  jz      short loc_1400091D0
0x1400091b9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400091bd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x1400091c4  lea     rcx, qword_140020A90
0x1400091cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400091d0  lea     rcx, SRWLock; SRWLock
0x1400091d7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400091dd  cmp     [rsp+88h+arg_10], r14d
0x1400091e5  jz      short loc_14000921D
0x1400091e7  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1400091ee  mov     edx, ebx
0x1400091f0  bts     edx, 1Fh
0x1400091f4  cmp     [rsp+88h+arg_18], r14d
0x1400091fc  cmovz   edx, ebx
0x1400091ff  test    rax, rax
0x140009202  jnz     short loc_140009210
0x140009204  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000920b  test    rax, rax
0x14000920e  jz      short loc_14000921D
0x140009210  xor     r9d, r9d
0x140009213  xor     r8d, r8d
0x140009216  mov     ecx, edi
0x140009218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000921d  test    r12d, r12d
0x140009220  jnz     short loc_140009241
0x140009222  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x140009229  test    rax, rax
0x14000922c  jz      short loc_140009244
0x14000922e  mov     r8b, [rsp+88h+arg_38]
0x140009236  mov     edx, ebx
0x140009238  mov     ecx, edi
0x14000923a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000923f  jmp     short loc_140009244
0x140009241  mov     ebp, r14d
0x140009244  mov     rbx, [rsp+88h+arg_0]
0x14000924c  mov     eax, ebp
0x14000924e  add     rsp, 50h
0x140009252  pop     r15
0x140009254  pop     r14
0x140009256  pop     r13
0x140009258  pop     r12
0x14000925a  pop     rdi
0x14000925b  pop     rsi
0x14000925c  pop     rbp
0x14000925d  retn
```
