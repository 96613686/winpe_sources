# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180048ed8`
- end: `0x180048ff2`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180048d90`

## callees

- `0x180048ed8`
- `0x180048ff8`
- `0x18005946c`
- `0x18005bd50`
- `0x18005c95c`
- `0x1800960c0`

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
      (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
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
0x180048ed8  mov     [rsp+arg_0], rbx
0x180048edd  mov     [rsp+arg_18], r9d
0x180048ee2  push    rbp
0x180048ee3  push    rsi
0x180048ee4  push    rdi
0x180048ee5  push    r12
0x180048ee7  push    r13
0x180048ee9  push    r14
0x180048eeb  push    r15
0x180048eed  sub     rsp, 50h
0x180048ef1  mov     ebx, [rsp+88h+arg_20]
0x180048ef8  mov     edi, edx
0x180048efa  mov     rdx, rcx
0x180048efd  mov     r13d, r8d
0x180048f00  mov     r15, rcx
0x180048f03  mov     r8d, ebx
0x180048f06  lea     rcx, [rsp+88h+var_58]
0x180048f0b  call    wil_details_FeatureReporting_RecordUsageInCache
0x180048f10  mov     esi, 1
0x180048f15  mov     ecx, [rax+8]
0x180048f18  mov     r12d, [rax]
0x180048f1b  mov     r14d, [rax+4]
0x180048f1f  mov     ebp, [rax+10h]
0x180048f22  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180048f29  mov     [rsp+88h+arg_10], ecx
0x180048f30  test    rax, rax
0x180048f33  jz      short loc_180048F4E
0x180048f35  test    ebx, ebx
0x180048f37  jz      short loc_180048F41
0x180048f39  lea     ecx, [rbx-64h]
0x180048f3c  cmp     ecx, 31h ; '1'
0x180048f3f  ja      short loc_180048F4E
0x180048f41  mov     r8d, esi
0x180048f44  mov     edx, ebx
0x180048f46  mov     ecx, edi
0x180048f48  call    cs:__guard_dispatch_icall_fptr
0x180048f4e  test    r12d, r12d
0x180048f51  jz      short loc_180048F64
0x180048f53  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x180048f56  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180048f5d  mov     edx, edi; unsigned int
0x180048f5f  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180048f64  test    r14d, r14d
0x180048f67  jz      short loc_180048F7A
0x180048f69  mov     edx, [rsp+88h+arg_10]; unsigned int
0x180048f70  mov     r8d, r14d; unsigned int
0x180048f73  mov     ecx, edi; this
0x180048f75  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180048f7a  test    ebp, ebp
0x180048f7c  jnz     short loc_180048F91
0x180048f7e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180048f85  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180048f8c  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180048f91  test    r13d, r13d
0x180048f94  jz      short loc_180048FB1
0x180048f96  mov     edx, ebx
0x180048f98  mov     ecx, edi; this
0x180048f9a  bts     edx, 1Fh
0x180048f9e  cmp     [rsp+88h+arg_18], 0
0x180048fa6  cmovz   edx, ebx; unsigned int
0x180048fa9  xor     r8d, r8d; unsigned int
0x180048fac  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180048fb1  test    ebp, ebp
0x180048fb3  jnz     short loc_180048FD5
0x180048fb5  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180048fbc  test    rax, rax
0x180048fbf  jz      short loc_180048FD7
0x180048fc1  mov     r8b, [rsp+88h+arg_38]
0x180048fc9  mov     edx, ebx
0x180048fcb  mov     ecx, edi
0x180048fcd  call    cs:__guard_dispatch_icall_fptr
0x180048fd3  jmp     short loc_180048FD7
0x180048fd5  xor     esi, esi
0x180048fd7  mov     rbx, [rsp+88h+arg_0]
0x180048fdf  mov     eax, esi
0x180048fe1  add     rsp, 50h
0x180048fe5  pop     r15
0x180048fe7  pop     r14
0x180048fe9  pop     r13
0x180048feb  pop     r12
0x180048fed  pop     rdi
0x180048fee  pop     rsi
0x180048fef  pop     rbp
0x180048ff0  retn
```
