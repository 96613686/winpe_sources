# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x14000ad84`
- end: `0x14000af23`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000ac4c`

## callees

- `0x14000aa8c`
- `0x14000ad84`
- `0x14000b4e0`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ae4f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ae4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ae9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ae9b`

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
  void (__fastcall *v18)(__int64 *, void (*)(), __int64); // rax
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
    if ( !qword_1400116E8 )
    {
      qword_1400116E8 = 0;
      v18 = (void (__fastcall *)(__int64 *, void (*)(), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, void (*)(), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_1400116E8, `wil::details::RecordFeatureUsageCallback'::`17'::_lambda_1_::_lambda_invoker_cdecl_, -1);
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
0x14000ad84  mov     rax, rsp
0x14000ad87  mov     [rax+8], rbx
0x14000ad8b  mov     [rax+20h], r9d
0x14000ad8f  mov     [rax+18h], r8d
0x14000ad93  push    rbp
0x14000ad94  push    rsi
0x14000ad95  push    rdi
0x14000ad96  push    r12
0x14000ad98  push    r13
0x14000ad9a  push    r14
0x14000ad9c  push    r15
0x14000ad9e  sub     rsp, 50h
0x14000ada2  mov     edi, edx
0x14000ada4  mov     r14, rcx
0x14000ada7  mov     ebx, [rsp+88h+arg_20]
0x14000adae  mov     r8d, ebx
0x14000adb1  mov     rdx, rcx
0x14000adb4  lea     rcx, [rax-58h]
0x14000adb8  call    wil_details_FeatureReporting_RecordUsageInCache
0x14000adbd  mov     r15d, [rax]
0x14000adc0  mov     esi, [rax+4]
0x14000adc3  mov     r12d, [rax+8]
0x14000adc7  mov     r13d, [rax+10h]
0x14000adcb  mov     ebp, 1
0x14000add0  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x14000add7  test    rax, rax
0x14000adda  jz      short loc_14000ADF4
0x14000addc  test    ebx, ebx
0x14000adde  jz      short loc_14000ADE8
0x14000ade0  lea     ecx, [rbx-64h]
0x14000ade3  cmp     ecx, 31h ; '1'
0x14000ade6  ja      short loc_14000ADF4
0x14000ade8  mov     r8d, ebp
0x14000adeb  mov     edx, ebx
0x14000aded  mov     ecx, edi
0x14000adef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000adf4  test    r15d, r15d
0x14000adf7  jz      short loc_14000AE0A
0x14000adf9  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x14000adfc  mov     edx, edi; unsigned int
0x14000adfe  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x14000ae05  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x14000ae0a  xor     r14d, r14d
0x14000ae0d  test    esi, esi
0x14000ae0f  jz      short loc_14000AE39
0x14000ae11  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000ae18  test    rax, rax
0x14000ae1b  jnz     short loc_14000AE29
0x14000ae1d  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000ae24  test    rax, rax
0x14000ae27  jz      short loc_14000AE39
0x14000ae29  xor     r9d, r9d
0x14000ae2c  mov     r8d, esi
0x14000ae2f  mov     edx, r12d
0x14000ae32  mov     ecx, edi
0x14000ae34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae39  test    r13d, r13d
0x14000ae3c  jnz     short loc_14000AEA2
0x14000ae3e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000ae44  test    eax, eax
0x14000ae46  jz      short loc_14000AEA2
0x14000ae48  lea     rcx, SRWLock; SRWLock
0x14000ae4f  call    cs:__imp_AcquireSRWLockExclusive
0x14000ae55  cmp     cs:qword_1400116E8, r14
0x14000ae5c  jnz     short loc_14000AE94
0x14000ae5e  mov     cs:qword_1400116E8, r14
0x14000ae65  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x14000ae6c  test    rax, rax
0x14000ae6f  jnz     short loc_14000AE7D
0x14000ae71  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x14000ae78  test    rax, rax
0x14000ae7b  jz      short loc_14000AE94
0x14000ae7d  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000ae81  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z; `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x14000ae88  lea     rcx, qword_1400116E8
0x14000ae8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae94  lea     rcx, SRWLock; SRWLock
0x14000ae9b  call    cs:__imp_ReleaseSRWLockExclusive
0x14000aea1  nop
0x14000aea2  cmp     [rsp+88h+arg_10], r14d
0x14000aeaa  jz      short loc_14000AEE2
0x14000aeac  mov     edx, ebx
0x14000aeae  bts     edx, 1Fh
0x14000aeb2  cmp     [rsp+88h+arg_18], r14d
0x14000aeba  cmovz   edx, ebx
0x14000aebd  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000aec4  test    rax, rax
0x14000aec7  jnz     short loc_14000AED5
0x14000aec9  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000aed0  test    rax, rax
0x14000aed3  jz      short loc_14000AEE2
0x14000aed5  xor     r9d, r9d
0x14000aed8  xor     r8d, r8d
0x14000aedb  mov     ecx, edi
0x14000aedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aee2  test    r13d, r13d
0x14000aee5  jnz     short loc_14000AF06
0x14000aee7  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x14000aeee  test    rax, rax
0x14000aef1  jz      short loc_14000AF09
0x14000aef3  mov     r8b, [rsp+88h+arg_38]
0x14000aefb  mov     edx, ebx
0x14000aefd  mov     ecx, edi
0x14000aeff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000af04  jmp     short loc_14000AF09
0x14000af06  mov     ebp, r14d
0x14000af09  mov     eax, ebp
0x14000af0b  mov     rbx, [rsp+88h+arg_0]
0x14000af13  add     rsp, 50h
0x14000af17  pop     r15
0x14000af19  pop     r14
0x14000af1b  pop     r13
0x14000af1d  pop     r12
0x14000af1f  pop     rdi
0x14000af20  pop     rsi
0x14000af21  pop     rbp
0x14000af22  retn
```
