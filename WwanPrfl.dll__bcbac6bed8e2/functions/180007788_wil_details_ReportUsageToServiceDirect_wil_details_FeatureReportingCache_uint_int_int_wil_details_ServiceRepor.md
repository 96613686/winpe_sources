# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180007788`
- end: `0x18000791b`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `403`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, __int64, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800076b0`

## callees

- `0x18000624c`
- `0x180007788`
- `0x18000e8f0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000789b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000789b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000784f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000784f`

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
  void (__fastcall *v19)(__int64 *, void (*)(), __int64); // rax
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
    g_wil_details_RecordSRUMFeatureUsage(60900037, a5, 1);
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
      v18(60900037, v15, v14, 0);
    }
  }
  if ( !v16 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_18001F468 )
    {
      qword_18001F468 = 0;
      v19 = (void (__fastcall *)(__int64 *, void (*)(), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v19 = (void (__fastcall *)(__int64 *, void (*)(), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v19(&qword_18001F468, `wil::details::RecordFeatureUsageCallback'::`17'::_lambda_1_::_lambda_invoker_cdecl_, -1);
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
      v21(60900037, v20, 0, 0);
    }
  }
  if ( v16 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(60900037, a5, v12);
  }
  return v17;
}

```

## disassembly

```asm
0x180007788  mov     [rsp+arg_18], r9d
0x18000778d  push    rbx
0x18000778e  push    rbp
0x18000778f  push    rsi
0x180007790  push    rdi
0x180007791  push    r12
0x180007793  push    r13
0x180007795  push    r14
0x180007797  push    r15
0x180007799  sub     rsp, 58h
0x18000779d  mov     r13d, r8d
0x1800077a0  mov     rbp, rcx
0x1800077a3  mov     ebx, [rsp+98h+arg_20]
0x1800077aa  mov     r8d, ebx
0x1800077ad  mov     rdx, rcx
0x1800077b0  lea     rcx, [rsp+98h+var_68]
0x1800077b5  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800077ba  mov     r14d, [rax]
0x1800077bd  mov     edi, [rax+4]
0x1800077c0  mov     r15d, [rax+8]
0x1800077c4  mov     r12d, [rax+10h]
0x1800077c8  mov     esi, 1
0x1800077cd  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800077d4  test    rax, rax
0x1800077d7  jz      short loc_1800077F4
0x1800077d9  test    ebx, ebx
0x1800077db  jz      short loc_1800077E5
0x1800077dd  lea     ecx, [rbx-64h]
0x1800077e0  cmp     ecx, 31h ; '1'
0x1800077e3  ja      short loc_1800077F4
0x1800077e5  mov     r8d, esi
0x1800077e8  mov     edx, ebx
0x1800077ea  mov     ecx, 3A142C5h
0x1800077ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077f4  test    r14d, r14d
0x1800077f7  jz      short loc_180007808
0x1800077f9  mov     r8, rbp; struct wil_details_FeatureReportingCache *
0x1800077fc  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180007803  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180007808  xor     ebp, ebp
0x18000780a  test    edi, edi
0x18000780c  jz      short loc_180007839
0x18000780e  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180007815  test    rax, rax
0x180007818  jnz     short loc_180007826
0x18000781a  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180007821  test    rax, rax
0x180007824  jz      short loc_180007839
0x180007826  xor     r9d, r9d
0x180007829  mov     r8d, edi
0x18000782c  mov     edx, r15d
0x18000782f  mov     ecx, 3A142C5h
0x180007834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007839  test    r12d, r12d
0x18000783c  jnz     short loc_1800078A2
0x18000783e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180007844  test    eax, eax
0x180007846  jz      short loc_1800078A2
0x180007848  lea     rcx, SRWLock; SRWLock
0x18000784f  call    cs:__imp_AcquireSRWLockExclusive
0x180007855  cmp     cs:qword_18001F468, rbp
0x18000785c  jnz     short loc_180007894
0x18000785e  mov     cs:qword_18001F468, rbp
0x180007865  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000786c  test    rax, rax
0x18000786f  jnz     short loc_18000787D
0x180007871  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180007878  test    rax, rax
0x18000787b  jz      short loc_180007894
0x18000787d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007881  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z; `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x180007888  lea     rcx, qword_18001F468
0x18000788f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007894  lea     rcx, SRWLock; SRWLock
0x18000789b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800078a1  nop
0x1800078a2  test    r13d, r13d
0x1800078a5  jz      short loc_1800078DF
0x1800078a7  mov     edx, ebx
0x1800078a9  bts     edx, 1Fh
0x1800078ad  cmp     [rsp+98h+arg_18], ebp
0x1800078b4  cmovz   edx, ebx
0x1800078b7  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800078be  test    rax, rax
0x1800078c1  jnz     short loc_1800078CF
0x1800078c3  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800078ca  test    rax, rax
0x1800078cd  jz      short loc_1800078DF
0x1800078cf  xor     r9d, r9d
0x1800078d2  xor     r8d, r8d
0x1800078d5  mov     ecx, 3A142C5h
0x1800078da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078df  test    r12d, r12d
0x1800078e2  jnz     short loc_180007906
0x1800078e4  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800078eb  test    rax, rax
0x1800078ee  jz      short loc_180007908
0x1800078f0  mov     r8b, [rsp+98h+arg_38]
0x1800078f8  mov     edx, ebx
0x1800078fa  mov     ecx, 3A142C5h
0x1800078ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007904  jmp     short loc_180007908
0x180007906  mov     esi, ebp
0x180007908  mov     eax, esi
0x18000790a  add     rsp, 58h
0x18000790e  pop     r15
0x180007910  pop     r14
0x180007912  pop     r13
0x180007914  pop     r12
0x180007916  pop     rdi
0x180007917  pop     rsi
0x180007918  pop     rbp
0x180007919  pop     rbx
0x18000791a  retn
```
