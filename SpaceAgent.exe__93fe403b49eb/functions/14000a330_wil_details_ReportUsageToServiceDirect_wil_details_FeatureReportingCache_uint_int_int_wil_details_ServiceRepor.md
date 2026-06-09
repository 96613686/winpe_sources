# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x14000a330`
- end: `0x14000a438`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `264`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, __int64, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x14000a258`

## callees

- `0x140008fd4`
- `0x140009eb4`
- `0x14000a174`
- `0x14000a330`
- `0x14000be58`
- `0x140020010`

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
  unsigned int v13; // r9d
  unsigned int v14; // edi
  int v15; // r15d
  unsigned int v16; // ebp
  unsigned int v17; // r13d
  int v18; // esi
  unsigned int v19; // edx
  const char *v21; // [rsp+20h] [rbp-78h]
  _BYTE v22[104]; // [rsp+30h] [rbp-68h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v22, a1, a5);
  v14 = 1;
  v15 = *v10;
  v16 = v10[1];
  v17 = v10[2];
  v18 = v10[4];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(59117474, a5, 1);
  if ( v15 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (char *)&wil::details::g_enabledStateManager,
      v11,
      a1);
  if ( v16 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x3860FA2, v17, v16, v13, v21);
  if ( !v18 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( a3 )
  {
    v19 = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x3860FA2, v19, 0, v13, v21);
  }
  if ( v18 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(59117474, a5, v12);
  }
  return v14;
}

```

## disassembly

```asm
0x14000a330  mov     [rsp+arg_18], r9d
0x14000a335  push    rbx
0x14000a336  push    rbp
0x14000a337  push    rsi
0x14000a338  push    rdi
0x14000a339  push    r12
0x14000a33b  push    r13
0x14000a33d  push    r14
0x14000a33f  push    r15
0x14000a341  sub     rsp, 58h
0x14000a345  mov     ebx, [rsp+98h+arg_20]
0x14000a34c  mov     r12d, r8d
0x14000a34f  mov     r14, rcx
0x14000a352  mov     rdx, rcx
0x14000a355  mov     r8d, ebx
0x14000a358  lea     rcx, [rsp+98h+var_68]
0x14000a35d  call    wil_details_FeatureReporting_RecordUsageInCache
0x14000a362  mov     edi, 1
0x14000a367  mov     r15d, [rax]
0x14000a36a  mov     ebp, [rax+4]
0x14000a36d  mov     r13d, [rax+8]
0x14000a371  mov     esi, [rax+10h]
0x14000a374  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x14000a37b  test    rax, rax
0x14000a37e  jz      short loc_14000A39B
0x14000a380  test    ebx, ebx
0x14000a382  jz      short loc_14000A38C
0x14000a384  lea     ecx, [rbx-64h]
0x14000a387  cmp     ecx, 31h ; '1'
0x14000a38a  ja      short loc_14000A39B
0x14000a38c  mov     r8d, edi
0x14000a38f  mov     edx, ebx
0x14000a391  mov     ecx, 3860FA2h
0x14000a396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a39b  test    r15d, r15d
0x14000a39e  jz      short loc_14000A3AF
0x14000a3a0  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x14000a3a3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x14000a3aa  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x14000a3af  test    ebp, ebp
0x14000a3b1  jz      short loc_14000A3C3
0x14000a3b3  mov     r8d, ebp; unsigned int
0x14000a3b6  mov     edx, r13d; unsigned int
0x14000a3b9  mov     ecx, 3860FA2h; this
0x14000a3be  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x14000a3c3  test    esi, esi
0x14000a3c5  jnz     short loc_14000A3DA
0x14000a3c7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x14000a3ce  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x14000a3d5  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x14000a3da  test    r12d, r12d
0x14000a3dd  jz      short loc_14000A3FD
0x14000a3df  mov     edx, ebx
0x14000a3e1  mov     ecx, 3860FA2h; this
0x14000a3e6  bts     edx, 1Fh
0x14000a3ea  cmp     [rsp+98h+arg_18], 0
0x14000a3f2  cmovz   edx, ebx; unsigned int
0x14000a3f5  xor     r8d, r8d; unsigned int
0x14000a3f8  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x14000a3fd  test    esi, esi
0x14000a3ff  jnz     short loc_14000A423
0x14000a401  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x14000a408  test    rax, rax
0x14000a40b  jz      short loc_14000A425
0x14000a40d  mov     r8b, [rsp+98h+arg_38]
0x14000a415  mov     edx, ebx
0x14000a417  mov     ecx, 3860FA2h
0x14000a41c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a421  jmp     short loc_14000A425
0x14000a423  xor     edi, edi
0x14000a425  mov     eax, edi
0x14000a427  add     rsp, 58h
0x14000a42b  pop     r15
0x14000a42d  pop     r14
0x14000a42f  pop     r13
0x14000a431  pop     r12
0x14000a433  pop     rdi
0x14000a434  pop     rsi
0x14000a435  pop     rbp
0x14000a436  pop     rbx
0x14000a437  retn
```
