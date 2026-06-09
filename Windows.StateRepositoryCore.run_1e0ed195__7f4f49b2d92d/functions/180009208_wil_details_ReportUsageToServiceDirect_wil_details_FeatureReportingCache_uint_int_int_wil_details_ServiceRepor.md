# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180009208`
- end: `0x18000931f`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180009164`

## callees

- `0x180004a04`
- `0x180007d50`
- `0x180009208`
- `0x18000a570`
- `0x18000b8e8`
- `0x180011010`

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
      (char *)&wil::details::g_enabledStateManager,
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
0x180009208  mov     [rsp+arg_0], rbx
0x18000920d  mov     [rsp+arg_18], r9d
0x180009212  push    rbp
0x180009213  push    rsi
0x180009214  push    rdi
0x180009215  push    r12
0x180009217  push    r13
0x180009219  push    r14
0x18000921b  push    r15
0x18000921d  sub     rsp, 50h
0x180009221  mov     ebx, [rsp+88h+arg_20]
0x180009228  mov     edi, edx
0x18000922a  mov     rdx, rcx
0x18000922d  mov     r13d, r8d
0x180009230  mov     r15, rcx
0x180009233  mov     r8d, ebx
0x180009236  lea     rcx, [rsp+88h+var_58]
0x18000923b  call    wil_details_FeatureReporting_RecordUsageInCache
0x180009240  mov     esi, 1
0x180009245  mov     ecx, [rax+8]
0x180009248  mov     r12d, [rax]
0x18000924b  mov     r14d, [rax+4]
0x18000924f  mov     ebp, [rax+10h]
0x180009252  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180009259  mov     [rsp+88h+arg_10], ecx
0x180009260  test    rax, rax
0x180009263  jz      short loc_18000927D
0x180009265  test    ebx, ebx
0x180009267  jz      short loc_180009271
0x180009269  lea     ecx, [rbx-64h]
0x18000926c  cmp     ecx, 31h ; '1'
0x18000926f  ja      short loc_18000927D
0x180009271  mov     r8d, esi
0x180009274  mov     edx, ebx
0x180009276  mov     ecx, edi
0x180009278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000927d  test    r12d, r12d
0x180009280  jz      short loc_180009293
0x180009282  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x180009285  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000928c  mov     edx, edi; unsigned int
0x18000928e  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180009293  test    r14d, r14d
0x180009296  jz      short loc_1800092A9
0x180009298  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18000929f  mov     r8d, r14d; unsigned int
0x1800092a2  mov     ecx, edi; this
0x1800092a4  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800092a9  test    ebp, ebp
0x1800092ab  jnz     short loc_1800092C0
0x1800092ad  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x1800092b4  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800092bb  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x1800092c0  test    r13d, r13d
0x1800092c3  jz      short loc_1800092E0
0x1800092c5  mov     edx, ebx
0x1800092c7  mov     ecx, edi; this
0x1800092c9  bts     edx, 1Fh
0x1800092cd  cmp     [rsp+88h+arg_18], 0
0x1800092d5  cmovz   edx, ebx; unsigned int
0x1800092d8  xor     r8d, r8d; unsigned int
0x1800092db  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800092e0  test    ebp, ebp
0x1800092e2  jnz     short loc_180009303
0x1800092e4  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800092eb  test    rax, rax
0x1800092ee  jz      short loc_180009305
0x1800092f0  mov     r8b, [rsp+88h+arg_38]
0x1800092f8  mov     edx, ebx
0x1800092fa  mov     ecx, edi
0x1800092fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009301  jmp     short loc_180009305
0x180009303  xor     esi, esi
0x180009305  mov     rbx, [rsp+88h+arg_0]
0x18000930d  mov     eax, esi
0x18000930f  add     rsp, 50h
0x180009313  pop     r15
0x180009315  pop     r14
0x180009317  pop     r13
0x180009319  pop     r12
0x18000931b  pop     rdi
0x18000931c  pop     rsi
0x18000931d  pop     rbp
0x18000931e  retn
```
