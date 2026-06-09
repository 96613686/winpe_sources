# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180021274`
- end: `0x18002138b`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800211d0`

## callees

- `0x18001f4a8`
- `0x1800206a0`
- `0x180021274`
- `0x1800225fc`
- `0x180026784`
- `0x180031010`

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
0x180021274  mov     [rsp+arg_0], rbx
0x180021279  mov     [rsp+arg_18], r9d
0x18002127e  push    rbp
0x18002127f  push    rsi
0x180021280  push    rdi
0x180021281  push    r12
0x180021283  push    r13
0x180021285  push    r14
0x180021287  push    r15
0x180021289  sub     rsp, 50h
0x18002128d  mov     ebx, [rsp+88h+arg_20]
0x180021294  mov     edi, edx
0x180021296  mov     rdx, rcx
0x180021299  mov     r13d, r8d
0x18002129c  mov     r15, rcx
0x18002129f  mov     r8d, ebx
0x1800212a2  lea     rcx, [rsp+88h+var_58]
0x1800212a7  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800212ac  mov     esi, 1
0x1800212b1  mov     ecx, [rax+8]
0x1800212b4  mov     r12d, [rax]
0x1800212b7  mov     r14d, [rax+4]
0x1800212bb  mov     ebp, [rax+10h]
0x1800212be  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800212c5  mov     [rsp+88h+arg_10], ecx
0x1800212cc  test    rax, rax
0x1800212cf  jz      short loc_1800212E9
0x1800212d1  test    ebx, ebx
0x1800212d3  jz      short loc_1800212DD
0x1800212d5  lea     ecx, [rbx-64h]
0x1800212d8  cmp     ecx, 31h ; '1'
0x1800212db  ja      short loc_1800212E9
0x1800212dd  mov     r8d, esi
0x1800212e0  mov     edx, ebx
0x1800212e2  mov     ecx, edi
0x1800212e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212e9  test    r12d, r12d
0x1800212ec  jz      short loc_1800212FF
0x1800212ee  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x1800212f1  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800212f8  mov     edx, edi; unsigned int
0x1800212fa  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800212ff  test    r14d, r14d
0x180021302  jz      short loc_180021315
0x180021304  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18002130b  mov     r8d, r14d; unsigned int
0x18002130e  mov     ecx, edi; this
0x180021310  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180021315  test    ebp, ebp
0x180021317  jnz     short loc_18002132C
0x180021319  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180021320  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180021327  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18002132c  test    r13d, r13d
0x18002132f  jz      short loc_18002134C
0x180021331  mov     edx, ebx
0x180021333  mov     ecx, edi; this
0x180021335  bts     edx, 1Fh
0x180021339  cmp     [rsp+88h+arg_18], 0
0x180021341  cmovz   edx, ebx; unsigned int
0x180021344  xor     r8d, r8d; unsigned int
0x180021347  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18002134c  test    ebp, ebp
0x18002134e  jnz     short loc_18002136F
0x180021350  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180021357  test    rax, rax
0x18002135a  jz      short loc_180021371
0x18002135c  mov     r8b, [rsp+88h+arg_38]
0x180021364  mov     edx, ebx
0x180021366  mov     ecx, edi
0x180021368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002136d  jmp     short loc_180021371
0x18002136f  xor     esi, esi
0x180021371  mov     rbx, [rsp+88h+arg_0]
0x180021379  mov     eax, esi
0x18002137b  add     rsp, 50h
0x18002137f  pop     r15
0x180021381  pop     r14
0x180021383  pop     r13
0x180021385  pop     r12
0x180021387  pop     rdi
0x180021388  pop     rsi
0x180021389  pop     rbp
0x18002138a  retn
```
