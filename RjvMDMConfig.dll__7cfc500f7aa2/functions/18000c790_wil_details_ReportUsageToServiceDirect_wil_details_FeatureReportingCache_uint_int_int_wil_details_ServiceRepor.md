# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000c790`
- end: `0x18000c8a8`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000c6ec`

## callees

- `0x18000a08c`
- `0x18000bb0c`
- `0x18000c790`
- `0x1800110c0`
- `0x18001249c`
- `0x18001e010`

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
0x18000c790  mov     [rsp+arg_0], rbx
0x18000c795  mov     [rsp+arg_18], r9d
0x18000c79a  push    rbp
0x18000c79b  push    rsi
0x18000c79c  push    rdi
0x18000c79d  push    r12
0x18000c79f  push    r13
0x18000c7a1  push    r14
0x18000c7a3  push    r15
0x18000c7a5  sub     rsp, 50h
0x18000c7a9  mov     ebx, [rsp+88h+arg_20]
0x18000c7b0  mov     edi, edx
0x18000c7b2  mov     rdx, rcx
0x18000c7b5  mov     r13d, r8d
0x18000c7b8  mov     r15, rcx
0x18000c7bb  mov     r8d, ebx
0x18000c7be  lea     rcx, [rsp+88h+var_58]
0x18000c7c3  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000c7c8  mov     esi, 1
0x18000c7cd  mov     ecx, [rax+8]
0x18000c7d0  mov     r12d, [rax]
0x18000c7d3  mov     r14d, [rax+4]
0x18000c7d7  mov     ebp, [rax+10h]
0x18000c7da  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000c7e1  mov     [rsp+88h+arg_10], ecx
0x18000c7e8  test    rax, rax
0x18000c7eb  jz      short loc_18000C805
0x18000c7ed  test    ebx, ebx
0x18000c7ef  jz      short loc_18000C7F9
0x18000c7f1  lea     ecx, [rbx-64h]
0x18000c7f4  cmp     ecx, 31h ; '1'
0x18000c7f7  ja      short loc_18000C805
0x18000c7f9  mov     r8d, esi
0x18000c7fc  mov     edx, ebx
0x18000c7fe  mov     ecx, edi
0x18000c800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c805  test    r12d, r12d
0x18000c808  jz      short loc_18000C81B
0x18000c80a  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x18000c80d  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000c814  mov     edx, edi; unsigned int
0x18000c816  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000c81b  test    r14d, r14d
0x18000c81e  jz      short loc_18000C831
0x18000c820  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18000c827  mov     r8d, r14d; unsigned int
0x18000c82a  mov     ecx, edi; this
0x18000c82c  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000c831  test    ebp, ebp
0x18000c833  jnz     short loc_18000C848
0x18000c835  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18000c83c  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000c843  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18000c848  test    r13d, r13d
0x18000c84b  jz      short loc_18000C868
0x18000c84d  mov     edx, ebx
0x18000c84f  mov     ecx, edi; this
0x18000c851  bts     edx, 1Fh
0x18000c855  cmp     [rsp+88h+arg_18], 0
0x18000c85d  cmovz   edx, ebx; unsigned int
0x18000c860  xor     r8d, r8d; unsigned int
0x18000c863  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000c868  test    ebp, ebp
0x18000c86a  jnz     short loc_18000C88B
0x18000c86c  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000c873  test    rax, rax
0x18000c876  jz      short loc_18000C88D
0x18000c878  mov     r8b, [rsp+88h+arg_38]
0x18000c880  mov     edx, ebx
0x18000c882  mov     ecx, edi
0x18000c884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c889  jmp     short loc_18000C88D
0x18000c88b  xor     esi, esi
0x18000c88d  mov     rbx, [rsp+88h+arg_0]
0x18000c895  mov     eax, esi
0x18000c897  add     rsp, 50h
0x18000c89b  pop     r15
0x18000c89d  pop     r14
0x18000c89f  pop     r13
0x18000c8a1  pop     r12
0x18000c8a3  pop     rdi
0x18000c8a4  pop     rsi
0x18000c8a5  pop     rbp
0x18000c8a6  retn
```
