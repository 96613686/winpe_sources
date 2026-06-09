# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000cc58`
- end: `0x18000cd6f`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000cbb4`

## callees

- `0x180009af8`
- `0x18000b894`
- `0x18000cc58`
- `0x18000d6f0`
- `0x18000e3d8`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x18000cc58  mov     [rsp+arg_0], rbx
0x18000cc5d  mov     [rsp+arg_18], r9d
0x18000cc62  push    rbp
0x18000cc63  push    rsi
0x18000cc64  push    rdi
0x18000cc65  push    r12
0x18000cc67  push    r13
0x18000cc69  push    r14
0x18000cc6b  push    r15
0x18000cc6d  sub     rsp, 50h
0x18000cc71  mov     ebx, [rsp+88h+arg_20]
0x18000cc78  mov     edi, edx
0x18000cc7a  mov     rdx, rcx
0x18000cc7d  mov     r13d, r8d
0x18000cc80  mov     r15, rcx
0x18000cc83  mov     r8d, ebx
0x18000cc86  lea     rcx, [rsp+88h+var_58]
0x18000cc8b  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000cc90  mov     esi, 1
0x18000cc95  mov     ecx, [rax+8]
0x18000cc98  mov     r12d, [rax]
0x18000cc9b  mov     r14d, [rax+4]
0x18000cc9f  mov     ebp, [rax+10h]
0x18000cca2  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000cca9  mov     [rsp+88h+arg_10], ecx
0x18000ccb0  test    rax, rax
0x18000ccb3  jz      short loc_18000CCCD
0x18000ccb5  test    ebx, ebx
0x18000ccb7  jz      short loc_18000CCC1
0x18000ccb9  lea     ecx, [rbx-64h]
0x18000ccbc  cmp     ecx, 31h ; '1'
0x18000ccbf  ja      short loc_18000CCCD
0x18000ccc1  mov     r8d, esi
0x18000ccc4  mov     edx, ebx
0x18000ccc6  mov     ecx, edi
0x18000ccc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cccd  test    r12d, r12d
0x18000ccd0  jz      short loc_18000CCE3
0x18000ccd2  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x18000ccd5  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000ccdc  mov     edx, edi; unsigned int
0x18000ccde  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000cce3  test    r14d, r14d
0x18000cce6  jz      short loc_18000CCF9
0x18000cce8  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18000ccef  mov     r8d, r14d; unsigned int
0x18000ccf2  mov     ecx, edi; this
0x18000ccf4  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000ccf9  test    ebp, ebp
0x18000ccfb  jnz     short loc_18000CD10
0x18000ccfd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18000cd04  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000cd0b  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18000cd10  test    r13d, r13d
0x18000cd13  jz      short loc_18000CD30
0x18000cd15  mov     edx, ebx
0x18000cd17  mov     ecx, edi; this
0x18000cd19  bts     edx, 1Fh
0x18000cd1d  cmp     [rsp+88h+arg_18], 0
0x18000cd25  cmovz   edx, ebx; unsigned int
0x18000cd28  xor     r8d, r8d; unsigned int
0x18000cd2b  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000cd30  test    ebp, ebp
0x18000cd32  jnz     short loc_18000CD53
0x18000cd34  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000cd3b  test    rax, rax
0x18000cd3e  jz      short loc_18000CD55
0x18000cd40  mov     r8b, [rsp+88h+arg_38]
0x18000cd48  mov     edx, ebx
0x18000cd4a  mov     ecx, edi
0x18000cd4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd51  jmp     short loc_18000CD55
0x18000cd53  xor     esi, esi
0x18000cd55  mov     rbx, [rsp+88h+arg_0]
0x18000cd5d  mov     eax, esi
0x18000cd5f  add     rsp, 50h
0x18000cd63  pop     r15
0x18000cd65  pop     r14
0x18000cd67  pop     r13
0x18000cd69  pop     r12
0x18000cd6b  pop     rdi
0x18000cd6c  pop     rsi
0x18000cd6d  pop     rbp
0x18000cd6e  retn
```
