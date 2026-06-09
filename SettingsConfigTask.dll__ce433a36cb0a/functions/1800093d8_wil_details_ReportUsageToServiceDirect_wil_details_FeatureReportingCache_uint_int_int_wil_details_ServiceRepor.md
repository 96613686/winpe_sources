# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1800093d8`
- end: `0x1800094ef`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800092a0`

## callees

- `0x180005b88`
- `0x1800081a0`
- `0x1800093d8`
- `0x18000aa88`
- `0x18000bdc8`
- `0x180024010`

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
0x1800093d8  mov     [rsp+arg_0], rbx
0x1800093dd  mov     [rsp+arg_18], r9d
0x1800093e2  push    rbp
0x1800093e3  push    rsi
0x1800093e4  push    rdi
0x1800093e5  push    r12
0x1800093e7  push    r13
0x1800093e9  push    r14
0x1800093eb  push    r15
0x1800093ed  sub     rsp, 50h
0x1800093f1  mov     ebx, [rsp+88h+arg_20]
0x1800093f8  mov     edi, edx
0x1800093fa  mov     rdx, rcx
0x1800093fd  mov     r13d, r8d
0x180009400  mov     r15, rcx
0x180009403  mov     r8d, ebx
0x180009406  lea     rcx, [rsp+88h+var_58]
0x18000940b  call    wil_details_FeatureReporting_RecordUsageInCache
0x180009410  mov     esi, 1
0x180009415  mov     ecx, [rax+8]
0x180009418  mov     r12d, [rax]
0x18000941b  mov     r14d, [rax+4]
0x18000941f  mov     ebp, [rax+10h]
0x180009422  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180009429  mov     [rsp+88h+arg_10], ecx
0x180009430  test    rax, rax
0x180009433  jz      short loc_18000944D
0x180009435  test    ebx, ebx
0x180009437  jz      short loc_180009441
0x180009439  lea     ecx, [rbx-64h]
0x18000943c  cmp     ecx, 31h ; '1'
0x18000943f  ja      short loc_18000944D
0x180009441  mov     r8d, esi
0x180009444  mov     edx, ebx
0x180009446  mov     ecx, edi
0x180009448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000944d  test    r12d, r12d
0x180009450  jz      short loc_180009463
0x180009452  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x180009455  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000945c  mov     edx, edi; unsigned int
0x18000945e  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180009463  test    r14d, r14d
0x180009466  jz      short loc_180009479
0x180009468  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18000946f  mov     r8d, r14d; unsigned int
0x180009472  mov     ecx, edi; this
0x180009474  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180009479  test    ebp, ebp
0x18000947b  jnz     short loc_180009490
0x18000947d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180009484  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000948b  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180009490  test    r13d, r13d
0x180009493  jz      short loc_1800094B0
0x180009495  mov     edx, ebx
0x180009497  mov     ecx, edi; this
0x180009499  bts     edx, 1Fh
0x18000949d  cmp     [rsp+88h+arg_18], 0
0x1800094a5  cmovz   edx, ebx; unsigned int
0x1800094a8  xor     r8d, r8d; unsigned int
0x1800094ab  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800094b0  test    ebp, ebp
0x1800094b2  jnz     short loc_1800094D3
0x1800094b4  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800094bb  test    rax, rax
0x1800094be  jz      short loc_1800094D5
0x1800094c0  mov     r8b, [rsp+88h+arg_38]
0x1800094c8  mov     edx, ebx
0x1800094ca  mov     ecx, edi
0x1800094cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094d1  jmp     short loc_1800094D5
0x1800094d3  xor     esi, esi
0x1800094d5  mov     rbx, [rsp+88h+arg_0]
0x1800094dd  mov     eax, esi
0x1800094df  add     rsp, 50h
0x1800094e3  pop     r15
0x1800094e5  pop     r14
0x1800094e7  pop     r13
0x1800094e9  pop     r12
0x1800094eb  pop     rdi
0x1800094ec  pop     rsi
0x1800094ed  pop     rbp
0x1800094ee  retn
```
