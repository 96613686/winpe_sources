# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180018918`
- end: `0x180018a2f`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180018874`

## callees

- `0x180014568`
- `0x180017130`
- `0x180018918`
- `0x18001bba0`
- `0x180020e18`
- `0x180025010`

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
  int *v11; // rax
  __int64 v12; // r8
  unsigned int v13; // r9d
  unsigned int v14; // esi
  int v15; // r12d
  unsigned int v16; // r14d
  int v17; // ebp
  unsigned int v18; // edx
  const char *v20; // [rsp+20h] [rbp-68h]
  _BYTE v21[88]; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v22; // [rsp+A0h] [rbp+18h]

  v11 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v21, a1, a5);
  v14 = 1;
  v15 = *v11;
  v16 = v11[1];
  v17 = v11[4];
  v22 = v11[2];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v15 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v16 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v22, v16, v13, v20);
  if ( !v17 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( a3 )
  {
    v18 = a5 | 0x80000000;
    if ( !a4 )
      v18 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v18, 0, v13, v20);
  }
  if ( v17 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v12);
  }
  return v14;
}

```

## disassembly

```asm
0x180018918  mov     [rsp+arg_0], rbx
0x18001891d  mov     [rsp+arg_18], r9d
0x180018922  push    rbp
0x180018923  push    rsi
0x180018924  push    rdi
0x180018925  push    r12
0x180018927  push    r13
0x180018929  push    r14
0x18001892b  push    r15
0x18001892d  sub     rsp, 50h
0x180018931  mov     ebx, [rsp+88h+arg_20]
0x180018938  mov     edi, edx
0x18001893a  mov     rdx, rcx
0x18001893d  mov     r13d, r8d
0x180018940  mov     r15, rcx
0x180018943  mov     r8d, ebx
0x180018946  lea     rcx, [rsp+88h+var_58]
0x18001894b  call    wil_details_FeatureReporting_RecordUsageInCache
0x180018950  mov     esi, 1
0x180018955  mov     ecx, [rax+8]
0x180018958  mov     r12d, [rax]
0x18001895b  mov     r14d, [rax+4]
0x18001895f  mov     ebp, [rax+10h]
0x180018962  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180018969  mov     [rsp+88h+arg_10], ecx
0x180018970  test    rax, rax
0x180018973  jz      short loc_18001898D
0x180018975  test    ebx, ebx
0x180018977  jz      short loc_180018981
0x180018979  lea     ecx, [rbx-64h]
0x18001897c  cmp     ecx, 31h ; '1'
0x18001897f  ja      short loc_18001898D
0x180018981  mov     r8d, esi
0x180018984  mov     edx, ebx
0x180018986  mov     ecx, edi
0x180018988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001898d  test    r12d, r12d
0x180018990  jz      short loc_1800189A3
0x180018992  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x180018995  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18001899c  mov     edx, edi; unsigned int
0x18001899e  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800189a3  test    r14d, r14d
0x1800189a6  jz      short loc_1800189B9
0x1800189a8  mov     edx, [rsp+88h+arg_10]; unsigned int
0x1800189af  mov     r8d, r14d; unsigned int
0x1800189b2  mov     ecx, edi; this
0x1800189b4  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800189b9  test    ebp, ebp
0x1800189bb  jnz     short loc_1800189D0
0x1800189bd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x1800189c4  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800189cb  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x1800189d0  test    r13d, r13d
0x1800189d3  jz      short loc_1800189F0
0x1800189d5  mov     edx, ebx
0x1800189d7  mov     ecx, edi; this
0x1800189d9  bts     edx, 1Fh
0x1800189dd  cmp     [rsp+88h+arg_18], 0
0x1800189e5  cmovz   edx, ebx; unsigned int
0x1800189e8  xor     r8d, r8d; unsigned int
0x1800189eb  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800189f0  test    ebp, ebp
0x1800189f2  jnz     short loc_180018A13
0x1800189f4  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800189fb  test    rax, rax
0x1800189fe  jz      short loc_180018A15
0x180018a00  mov     r8b, [rsp+88h+arg_38]
0x180018a08  mov     edx, ebx
0x180018a0a  mov     ecx, edi
0x180018a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a11  jmp     short loc_180018A15
0x180018a13  xor     esi, esi
0x180018a15  mov     rbx, [rsp+88h+arg_0]
0x180018a1d  mov     eax, esi
0x180018a1f  add     rsp, 50h
0x180018a23  pop     r15
0x180018a25  pop     r14
0x180018a27  pop     r13
0x180018a29  pop     r12
0x180018a2b  pop     rdi
0x180018a2c  pop     rsi
0x180018a2d  pop     rbp
0x180018a2e  retn
```
