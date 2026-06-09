# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000f894`
- end: `0x18000f9ab`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000f75c`

## callees

- `0x180009964`
- `0x18000f0f4`
- `0x18000f5e4`
- `0x18000f894`
- `0x180011864`
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
0x18000f894  mov     [rsp+arg_0], rbx
0x18000f899  mov     [rsp+arg_18], r9d
0x18000f89e  push    rbp
0x18000f89f  push    rsi
0x18000f8a0  push    rdi
0x18000f8a1  push    r12
0x18000f8a3  push    r13
0x18000f8a5  push    r14
0x18000f8a7  push    r15
0x18000f8a9  sub     rsp, 50h
0x18000f8ad  mov     ebx, [rsp+88h+arg_20]
0x18000f8b4  mov     edi, edx
0x18000f8b6  mov     rdx, rcx
0x18000f8b9  mov     r13d, r8d
0x18000f8bc  mov     r15, rcx
0x18000f8bf  mov     r8d, ebx
0x18000f8c2  lea     rcx, [rsp+88h+var_58]
0x18000f8c7  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000f8cc  mov     esi, 1
0x18000f8d1  mov     ecx, [rax+8]
0x18000f8d4  mov     r12d, [rax]
0x18000f8d7  mov     r14d, [rax+4]
0x18000f8db  mov     ebp, [rax+10h]
0x18000f8de  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000f8e5  mov     [rsp+88h+arg_10], ecx
0x18000f8ec  test    rax, rax
0x18000f8ef  jz      short loc_18000F909
0x18000f8f1  test    ebx, ebx
0x18000f8f3  jz      short loc_18000F8FD
0x18000f8f5  lea     ecx, [rbx-64h]
0x18000f8f8  cmp     ecx, 31h ; '1'
0x18000f8fb  ja      short loc_18000F909
0x18000f8fd  mov     r8d, esi
0x18000f900  mov     edx, ebx
0x18000f902  mov     ecx, edi
0x18000f904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f909  test    r12d, r12d
0x18000f90c  jz      short loc_18000F91F
0x18000f90e  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x18000f911  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000f918  mov     edx, edi; unsigned int
0x18000f91a  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000f91f  test    r14d, r14d
0x18000f922  jz      short loc_18000F935
0x18000f924  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18000f92b  mov     r8d, r14d; unsigned int
0x18000f92e  mov     ecx, edi; this
0x18000f930  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000f935  test    ebp, ebp
0x18000f937  jnz     short loc_18000F94C
0x18000f939  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18000f940  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000f947  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18000f94c  test    r13d, r13d
0x18000f94f  jz      short loc_18000F96C
0x18000f951  mov     edx, ebx
0x18000f953  mov     ecx, edi; this
0x18000f955  bts     edx, 1Fh
0x18000f959  cmp     [rsp+88h+arg_18], 0
0x18000f961  cmovz   edx, ebx; unsigned int
0x18000f964  xor     r8d, r8d; unsigned int
0x18000f967  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000f96c  test    ebp, ebp
0x18000f96e  jnz     short loc_18000F98F
0x18000f970  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000f977  test    rax, rax
0x18000f97a  jz      short loc_18000F991
0x18000f97c  mov     r8b, [rsp+88h+arg_38]
0x18000f984  mov     edx, ebx
0x18000f986  mov     ecx, edi
0x18000f988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f98d  jmp     short loc_18000F991
0x18000f98f  xor     esi, esi
0x18000f991  mov     rbx, [rsp+88h+arg_0]
0x18000f999  mov     eax, esi
0x18000f99b  add     rsp, 50h
0x18000f99f  pop     r15
0x18000f9a1  pop     r14
0x18000f9a3  pop     r13
0x18000f9a5  pop     r12
0x18000f9a7  pop     rdi
0x18000f9a8  pop     rsi
0x18000f9a9  pop     rbp
0x18000f9aa  retn
```
