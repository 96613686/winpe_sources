# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x140010260`
- end: `0x140010377`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1400101bc`

## callees

- `0x14000b430`
- `0x14000f0b8`
- `0x140010260`
- `0x140011478`
- `0x140013778`
- `0x14001c010`

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
0x140010260  mov     [rsp+arg_0], rbx
0x140010265  mov     [rsp+arg_18], r9d
0x14001026a  push    rbp
0x14001026b  push    rsi
0x14001026c  push    rdi
0x14001026d  push    r12
0x14001026f  push    r13
0x140010271  push    r14
0x140010273  push    r15
0x140010275  sub     rsp, 50h
0x140010279  mov     ebx, [rsp+88h+arg_20]
0x140010280  mov     edi, edx
0x140010282  mov     rdx, rcx
0x140010285  mov     r13d, r8d
0x140010288  mov     r15, rcx
0x14001028b  mov     r8d, ebx
0x14001028e  lea     rcx, [rsp+88h+var_58]
0x140010293  call    wil_details_FeatureReporting_RecordUsageInCache
0x140010298  mov     esi, 1
0x14001029d  mov     ecx, [rax+8]
0x1400102a0  mov     r12d, [rax]
0x1400102a3  mov     r14d, [rax+4]
0x1400102a7  mov     ebp, [rax+10h]
0x1400102aa  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1400102b1  mov     [rsp+88h+arg_10], ecx
0x1400102b8  test    rax, rax
0x1400102bb  jz      short loc_1400102D5
0x1400102bd  test    ebx, ebx
0x1400102bf  jz      short loc_1400102C9
0x1400102c1  lea     ecx, [rbx-64h]
0x1400102c4  cmp     ecx, 31h ; '1'
0x1400102c7  ja      short loc_1400102D5
0x1400102c9  mov     r8d, esi
0x1400102cc  mov     edx, ebx
0x1400102ce  mov     ecx, edi
0x1400102d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102d5  test    r12d, r12d
0x1400102d8  jz      short loc_1400102EB
0x1400102da  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x1400102dd  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1400102e4  mov     edx, edi; unsigned int
0x1400102e6  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1400102eb  test    r14d, r14d
0x1400102ee  jz      short loc_140010301
0x1400102f0  mov     edx, [rsp+88h+arg_10]; unsigned int
0x1400102f7  mov     r8d, r14d; unsigned int
0x1400102fa  mov     ecx, edi; this
0x1400102fc  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x140010301  test    ebp, ebp
0x140010303  jnz     short loc_140010318
0x140010305  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x14001030c  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x140010313  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x140010318  test    r13d, r13d
0x14001031b  jz      short loc_140010338
0x14001031d  mov     edx, ebx
0x14001031f  mov     ecx, edi; this
0x140010321  bts     edx, 1Fh
0x140010325  cmp     [rsp+88h+arg_18], 0
0x14001032d  cmovz   edx, ebx; unsigned int
0x140010330  xor     r8d, r8d; unsigned int
0x140010333  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x140010338  test    ebp, ebp
0x14001033a  jnz     short loc_14001035B
0x14001033c  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x140010343  test    rax, rax
0x140010346  jz      short loc_14001035D
0x140010348  mov     r8b, [rsp+88h+arg_38]
0x140010350  mov     edx, ebx
0x140010352  mov     ecx, edi
0x140010354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010359  jmp     short loc_14001035D
0x14001035b  xor     esi, esi
0x14001035d  mov     rbx, [rsp+88h+arg_0]
0x140010365  mov     eax, esi
0x140010367  add     rsp, 50h
0x14001036b  pop     r15
0x14001036d  pop     r14
0x14001036f  pop     r13
0x140010371  pop     r12
0x140010373  pop     rdi
0x140010374  pop     rsi
0x140010375  pop     rbp
0x140010376  retn
```
