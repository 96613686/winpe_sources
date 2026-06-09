# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x140005238`
- end: `0x140005340`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140005164`

## callees

- `0x140005238`
- `0x140007474`
- `0x1400076cc`
- `0x140007d2c`
- `0x14000d824`
- `0x140010010`

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
    g_wil_details_RecordSRUMFeatureUsage(8482243, a5, 1);
  if ( v15 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
      v11,
      a1);
  if ( v16 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x816DC3, v17, v16, v13, v21);
  if ( !v18 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( a3 )
  {
    v19 = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x816DC3, v19, 0, v13, v21);
  }
  if ( v18 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(8482243, a5, v12);
  }
  return v14;
}

```

## disassembly

```asm
0x140005238  mov     [rsp+arg_18], r9d
0x14000523d  push    rbx
0x14000523e  push    rbp
0x14000523f  push    rsi
0x140005240  push    rdi
0x140005241  push    r12
0x140005243  push    r13
0x140005245  push    r14
0x140005247  push    r15
0x140005249  sub     rsp, 58h
0x14000524d  mov     ebx, [rsp+98h+arg_20]
0x140005254  mov     r12d, r8d
0x140005257  mov     r14, rcx
0x14000525a  mov     rdx, rcx
0x14000525d  mov     r8d, ebx
0x140005260  lea     rcx, [rsp+98h+var_68]
0x140005265  call    wil_details_FeatureReporting_RecordUsageInCache
0x14000526a  mov     edi, 1
0x14000526f  mov     r15d, [rax]
0x140005272  mov     ebp, [rax+4]
0x140005275  mov     r13d, [rax+8]
0x140005279  mov     esi, [rax+10h]
0x14000527c  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x140005283  test    rax, rax
0x140005286  jz      short loc_1400052A3
0x140005288  test    ebx, ebx
0x14000528a  jz      short loc_140005294
0x14000528c  lea     ecx, [rbx-64h]
0x14000528f  cmp     ecx, 31h ; '1'
0x140005292  ja      short loc_1400052A3
0x140005294  mov     r8d, edi
0x140005297  mov     edx, ebx
0x140005299  mov     ecx, 816DC3h
0x14000529e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052a3  test    r15d, r15d
0x1400052a6  jz      short loc_1400052B7
0x1400052a8  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x1400052ab  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1400052b2  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1400052b7  test    ebp, ebp
0x1400052b9  jz      short loc_1400052CB
0x1400052bb  mov     r8d, ebp; unsigned int
0x1400052be  mov     edx, r13d; unsigned int
0x1400052c1  mov     ecx, 816DC3h; this
0x1400052c6  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1400052cb  test    esi, esi
0x1400052cd  jnz     short loc_1400052E2
0x1400052cf  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x1400052d6  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1400052dd  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x1400052e2  test    r12d, r12d
0x1400052e5  jz      short loc_140005305
0x1400052e7  mov     edx, ebx
0x1400052e9  mov     ecx, 816DC3h; this
0x1400052ee  bts     edx, 1Fh
0x1400052f2  cmp     [rsp+98h+arg_18], 0
0x1400052fa  cmovz   edx, ebx; unsigned int
0x1400052fd  xor     r8d, r8d; unsigned int
0x140005300  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x140005305  test    esi, esi
0x140005307  jnz     short loc_14000532B
0x140005309  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x140005310  test    rax, rax
0x140005313  jz      short loc_14000532D
0x140005315  mov     r8b, [rsp+98h+arg_38]
0x14000531d  mov     edx, ebx
0x14000531f  mov     ecx, 816DC3h
0x140005324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005329  jmp     short loc_14000532D
0x14000532b  xor     edi, edi
0x14000532d  mov     eax, edi
0x14000532f  add     rsp, 58h
0x140005333  pop     r15
0x140005335  pop     r14
0x140005337  pop     r13
0x140005339  pop     r12
0x14000533b  pop     rdi
0x14000533c  pop     rsi
0x14000533d  pop     rbp
0x14000533e  pop     rbx
0x14000533f  retn
```
