# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18001ec00`
- end: `0x18001eda3`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `419`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001ead8`

## callees

- `0x18001cfe4`
- `0x18001ec00`
- `0x180021ebc`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ecd5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ecd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ed21`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ed21`

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
  __int64 v24; // [rsp+40h] [rbp-58h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(&v24, a1, a5);
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
    if ( !qword_18004C500 )
    {
      qword_18004C500 = 0;
      v18 = (void (__fastcall *)(__int64 *, void (*)(), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, void (*)(), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_18004C500, `wil::details::RecordFeatureUsageCallback'::`17'::_lambda_1_::_lambda_invoker_cdecl_, -1);
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
0x18001ec00  mov     rax, rsp
0x18001ec03  push    rbp
0x18001ec04  push    rsi
0x18001ec05  push    rdi
0x18001ec06  push    r12
0x18001ec08  push    r13
0x18001ec0a  push    r14
0x18001ec0c  push    r15
0x18001ec0e  sub     rsp, 60h
0x18001ec12  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x18001ec1a  mov     [rax+18h], rbx
0x18001ec1e  mov     [rsp+98h+var_64], r9d
0x18001ec23  mov     [rsp+98h+var_68], r8d
0x18001ec28  mov     ebx, edx
0x18001ec2a  mov     r14, rcx
0x18001ec2d  mov     edi, [rsp+98h+arg_20]
0x18001ec34  mov     r8d, edi
0x18001ec37  mov     rdx, rcx
0x18001ec3a  lea     rcx, [rax-58h]
0x18001ec3e  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001ec43  mov     r15d, [rax]
0x18001ec46  mov     esi, [rax+4]
0x18001ec49  mov     r12d, [rax+8]
0x18001ec4d  mov     r13d, [rax+10h]
0x18001ec51  mov     ebp, 1
0x18001ec56  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18001ec5d  test    rax, rax
0x18001ec60  jz      short loc_18001EC7A
0x18001ec62  test    edi, edi
0x18001ec64  jz      short loc_18001EC6E
0x18001ec66  lea     ecx, [rdi-64h]
0x18001ec69  cmp     ecx, 31h ; '1'
0x18001ec6c  ja      short loc_18001EC7A
0x18001ec6e  mov     r8d, ebp
0x18001ec71  mov     edx, edi
0x18001ec73  mov     ecx, ebx
0x18001ec75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec7a  test    r15d, r15d
0x18001ec7d  jz      short loc_18001EC90
0x18001ec7f  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18001ec82  mov     edx, ebx; unsigned int
0x18001ec84  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18001ec8b  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001ec90  xor     r14d, r14d
0x18001ec93  test    esi, esi
0x18001ec95  jz      short loc_18001ECBF
0x18001ec97  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001ec9e  test    rax, rax
0x18001eca1  jnz     short loc_18001ECAF
0x18001eca3  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001ecaa  test    rax, rax
0x18001ecad  jz      short loc_18001ECBF
0x18001ecaf  xor     r9d, r9d
0x18001ecb2  mov     r8d, esi
0x18001ecb5  mov     edx, r12d
0x18001ecb8  mov     ecx, ebx
0x18001ecba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecbf  test    r13d, r13d
0x18001ecc2  jnz     short loc_18001ED28
0x18001ecc4  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001ecca  test    eax, eax
0x18001eccc  jz      short loc_18001ED28
0x18001ecce  lea     rcx, SRWLock; SRWLock
0x18001ecd5  call    cs:__imp_AcquireSRWLockExclusive
0x18001ecdb  cmp     cs:qword_18004C500, r14
0x18001ece2  jnz     short loc_18001ED1A
0x18001ece4  mov     cs:qword_18004C500, r14
0x18001eceb  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001ecf2  test    rax, rax
0x18001ecf5  jnz     short loc_18001ED03
0x18001ecf7  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001ecfe  test    rax, rax
0x18001ed01  jz      short loc_18001ED1A
0x18001ed03  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001ed07  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z; `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18001ed0e  lea     rcx, qword_18004C500
0x18001ed15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed1a  lea     rcx, SRWLock; SRWLock
0x18001ed21  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ed27  nop
0x18001ed28  cmp     [rsp+98h+var_68], r14d
0x18001ed2d  jz      short loc_18001ED62
0x18001ed2f  mov     edx, edi
0x18001ed31  bts     edx, 1Fh
0x18001ed35  cmp     [rsp+98h+var_64], r14d
0x18001ed3a  cmovz   edx, edi
0x18001ed3d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001ed44  test    rax, rax
0x18001ed47  jnz     short loc_18001ED55
0x18001ed49  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001ed50  test    rax, rax
0x18001ed53  jz      short loc_18001ED62
0x18001ed55  xor     r9d, r9d
0x18001ed58  xor     r8d, r8d
0x18001ed5b  mov     ecx, ebx
0x18001ed5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed62  test    r13d, r13d
0x18001ed65  jnz     short loc_18001ED86
0x18001ed67  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18001ed6e  test    rax, rax
0x18001ed71  jz      short loc_18001ED89
0x18001ed73  mov     r8b, [rsp+98h+arg_38]
0x18001ed7b  mov     edx, edi
0x18001ed7d  mov     ecx, ebx
0x18001ed7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed84  jmp     short loc_18001ED89
0x18001ed86  mov     ebp, r14d
0x18001ed89  mov     eax, ebp
0x18001ed8b  mov     rbx, [rsp+98h+arg_10]
0x18001ed93  add     rsp, 60h
0x18001ed97  pop     r15
0x18001ed99  pop     r14
0x18001ed9b  pop     r13
0x18001ed9d  pop     r12
0x18001ed9f  pop     rdi
0x18001eda0  pop     rsi
0x18001eda1  pop     rbp
0x18001eda2  retn
```
