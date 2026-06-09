# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000a768`
- end: `0x18000a87f`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000a6c4`

## callees

- `0x1800086f0`
- `0x1800098d4`
- `0x18000a768`
- `0x18000b0d0`
- `0x18000bad8`
- `0x180018010`

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
0x18000a768  mov     [rsp+arg_0], rbx
0x18000a76d  mov     [rsp+arg_18], r9d
0x18000a772  push    rbp
0x18000a773  push    rsi
0x18000a774  push    rdi
0x18000a775  push    r12
0x18000a777  push    r13
0x18000a779  push    r14
0x18000a77b  push    r15
0x18000a77d  sub     rsp, 50h
0x18000a781  mov     ebx, [rsp+88h+arg_20]
0x18000a788  mov     edi, edx
0x18000a78a  mov     rdx, rcx
0x18000a78d  mov     r13d, r8d
0x18000a790  mov     r15, rcx
0x18000a793  mov     r8d, ebx
0x18000a796  lea     rcx, [rsp+88h+var_58]
0x18000a79b  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000a7a0  mov     esi, 1
0x18000a7a5  mov     ecx, [rax+8]
0x18000a7a8  mov     r12d, [rax]
0x18000a7ab  mov     r14d, [rax+4]
0x18000a7af  mov     ebp, [rax+10h]
0x18000a7b2  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000a7b9  mov     [rsp+88h+arg_10], ecx
0x18000a7c0  test    rax, rax
0x18000a7c3  jz      short loc_18000A7DD
0x18000a7c5  test    ebx, ebx
0x18000a7c7  jz      short loc_18000A7D1
0x18000a7c9  lea     ecx, [rbx-64h]
0x18000a7cc  cmp     ecx, 31h ; '1'
0x18000a7cf  ja      short loc_18000A7DD
0x18000a7d1  mov     r8d, esi
0x18000a7d4  mov     edx, ebx
0x18000a7d6  mov     ecx, edi
0x18000a7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7dd  test    r12d, r12d
0x18000a7e0  jz      short loc_18000A7F3
0x18000a7e2  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x18000a7e5  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000a7ec  mov     edx, edi; unsigned int
0x18000a7ee  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000a7f3  test    r14d, r14d
0x18000a7f6  jz      short loc_18000A809
0x18000a7f8  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18000a7ff  mov     r8d, r14d; unsigned int
0x18000a802  mov     ecx, edi; this
0x18000a804  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000a809  test    ebp, ebp
0x18000a80b  jnz     short loc_18000A820
0x18000a80d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18000a814  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000a81b  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18000a820  test    r13d, r13d
0x18000a823  jz      short loc_18000A840
0x18000a825  mov     edx, ebx
0x18000a827  mov     ecx, edi; this
0x18000a829  bts     edx, 1Fh
0x18000a82d  cmp     [rsp+88h+arg_18], 0
0x18000a835  cmovz   edx, ebx; unsigned int
0x18000a838  xor     r8d, r8d; unsigned int
0x18000a83b  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000a840  test    ebp, ebp
0x18000a842  jnz     short loc_18000A863
0x18000a844  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000a84b  test    rax, rax
0x18000a84e  jz      short loc_18000A865
0x18000a850  mov     r8b, [rsp+88h+arg_38]
0x18000a858  mov     edx, ebx
0x18000a85a  mov     ecx, edi
0x18000a85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a861  jmp     short loc_18000A865
0x18000a863  xor     esi, esi
0x18000a865  mov     rbx, [rsp+88h+arg_0]
0x18000a86d  mov     eax, esi
0x18000a86f  add     rsp, 50h
0x18000a873  pop     r15
0x18000a875  pop     r14
0x18000a877  pop     r13
0x18000a879  pop     r12
0x18000a87b  pop     rdi
0x18000a87c  pop     rsi
0x18000a87d  pop     rbp
0x18000a87e  retn
```
