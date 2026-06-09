# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1800158f8`
- end: `0x180015a0f`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180015854`

## callees

- `0x180014100`
- `0x180015564`
- `0x1800158f8`
- `0x180016328`
- `0x180016cb0`
- `0x180021010`

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
0x1800158f8  mov     [rsp+arg_0], rbx
0x1800158fd  mov     [rsp+arg_18], r9d
0x180015902  push    rbp
0x180015903  push    rsi
0x180015904  push    rdi
0x180015905  push    r12
0x180015907  push    r13
0x180015909  push    r14
0x18001590b  push    r15
0x18001590d  sub     rsp, 50h
0x180015911  mov     ebx, [rsp+88h+arg_20]
0x180015918  mov     edi, edx
0x18001591a  mov     rdx, rcx
0x18001591d  mov     r13d, r8d
0x180015920  mov     r15, rcx
0x180015923  mov     r8d, ebx
0x180015926  lea     rcx, [rsp+88h+var_58]
0x18001592b  call    wil_details_FeatureReporting_RecordUsageInCache
0x180015930  mov     esi, 1
0x180015935  mov     ecx, [rax+8]
0x180015938  mov     r12d, [rax]
0x18001593b  mov     r14d, [rax+4]
0x18001593f  mov     ebp, [rax+10h]
0x180015942  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180015949  mov     [rsp+88h+arg_10], ecx
0x180015950  test    rax, rax
0x180015953  jz      short loc_18001596D
0x180015955  test    ebx, ebx
0x180015957  jz      short loc_180015961
0x180015959  lea     ecx, [rbx-64h]
0x18001595c  cmp     ecx, 31h ; '1'
0x18001595f  ja      short loc_18001596D
0x180015961  mov     r8d, esi
0x180015964  mov     edx, ebx
0x180015966  mov     ecx, edi
0x180015968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001596d  test    r12d, r12d
0x180015970  jz      short loc_180015983
0x180015972  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x180015975  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18001597c  mov     edx, edi; unsigned int
0x18001597e  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180015983  test    r14d, r14d
0x180015986  jz      short loc_180015999
0x180015988  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18001598f  mov     r8d, r14d; unsigned int
0x180015992  mov     ecx, edi; this
0x180015994  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180015999  test    ebp, ebp
0x18001599b  jnz     short loc_1800159B0
0x18001599d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x1800159a4  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800159ab  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x1800159b0  test    r13d, r13d
0x1800159b3  jz      short loc_1800159D0
0x1800159b5  mov     edx, ebx
0x1800159b7  mov     ecx, edi; this
0x1800159b9  bts     edx, 1Fh
0x1800159bd  cmp     [rsp+88h+arg_18], 0
0x1800159c5  cmovz   edx, ebx; unsigned int
0x1800159c8  xor     r8d, r8d; unsigned int
0x1800159cb  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800159d0  test    ebp, ebp
0x1800159d2  jnz     short loc_1800159F3
0x1800159d4  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800159db  test    rax, rax
0x1800159de  jz      short loc_1800159F5
0x1800159e0  mov     r8b, [rsp+88h+arg_38]
0x1800159e8  mov     edx, ebx
0x1800159ea  mov     ecx, edi
0x1800159ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159f1  jmp     short loc_1800159F5
0x1800159f3  xor     esi, esi
0x1800159f5  mov     rbx, [rsp+88h+arg_0]
0x1800159fd  mov     eax, esi
0x1800159ff  add     rsp, 50h
0x180015a03  pop     r15
0x180015a05  pop     r14
0x180015a07  pop     r13
0x180015a09  pop     r12
0x180015a0b  pop     rdi
0x180015a0c  pop     rsi
0x180015a0d  pop     rbp
0x180015a0e  retn
```
