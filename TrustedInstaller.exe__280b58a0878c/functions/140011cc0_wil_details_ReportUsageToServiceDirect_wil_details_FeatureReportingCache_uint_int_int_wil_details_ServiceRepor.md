# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x140011cc0`
- end: `0x140011dd7`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140011c1c`

## callees

- `0x14000abb4`
- `0x14000f6c0`
- `0x14001191c`
- `0x140011cc0`
- `0x140012ecc`
- `0x14002b010`

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
      (char *)wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v16 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v22, v16, v13, v20);
  if ( !v17 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)wil::details::g_enabledStateManager,
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
0x140011cc0  mov     [rsp+arg_0], rbx
0x140011cc5  mov     [rsp+arg_18], r9d
0x140011cca  push    rbp
0x140011ccb  push    rsi
0x140011ccc  push    rdi
0x140011ccd  push    r12
0x140011ccf  push    r13
0x140011cd1  push    r14
0x140011cd3  push    r15
0x140011cd5  sub     rsp, 50h
0x140011cd9  mov     ebx, [rsp+88h+arg_20]
0x140011ce0  mov     edi, edx
0x140011ce2  mov     rdx, rcx
0x140011ce5  mov     r13d, r8d
0x140011ce8  mov     r15, rcx
0x140011ceb  mov     r8d, ebx
0x140011cee  lea     rcx, [rsp+88h+var_58]
0x140011cf3  call    wil_details_FeatureReporting_RecordUsageInCache
0x140011cf8  mov     esi, 1
0x140011cfd  mov     ecx, [rax+8]
0x140011d00  mov     r12d, [rax]
0x140011d03  mov     r14d, [rax+4]
0x140011d07  mov     ebp, [rax+10h]
0x140011d0a  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x140011d11  mov     [rsp+88h+arg_10], ecx
0x140011d18  test    rax, rax
0x140011d1b  jz      short loc_140011D35
0x140011d1d  test    ebx, ebx
0x140011d1f  jz      short loc_140011D29
0x140011d21  lea     ecx, [rbx-64h]
0x140011d24  cmp     ecx, 31h ; '1'
0x140011d27  ja      short loc_140011D35
0x140011d29  mov     r8d, esi
0x140011d2c  mov     edx, ebx
0x140011d2e  mov     ecx, edi
0x140011d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011d35  test    r12d, r12d
0x140011d38  jz      short loc_140011D4B
0x140011d3a  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x140011d3d  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x140011d44  mov     edx, edi; unsigned int
0x140011d46  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x140011d4b  test    r14d, r14d
0x140011d4e  jz      short loc_140011D61
0x140011d50  mov     edx, [rsp+88h+arg_10]; unsigned int
0x140011d57  mov     r8d, r14d; unsigned int
0x140011d5a  mov     ecx, edi; this
0x140011d5c  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x140011d61  test    ebp, ebp
0x140011d63  jnz     short loc_140011D78
0x140011d65  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x140011d6c  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x140011d73  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x140011d78  test    r13d, r13d
0x140011d7b  jz      short loc_140011D98
0x140011d7d  mov     edx, ebx
0x140011d7f  mov     ecx, edi; this
0x140011d81  bts     edx, 1Fh
0x140011d85  cmp     [rsp+88h+arg_18], 0
0x140011d8d  cmovz   edx, ebx; unsigned int
0x140011d90  xor     r8d, r8d; unsigned int
0x140011d93  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x140011d98  test    ebp, ebp
0x140011d9a  jnz     short loc_140011DBB
0x140011d9c  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x140011da3  test    rax, rax
0x140011da6  jz      short loc_140011DBD
0x140011da8  mov     r8b, [rsp+88h+arg_38]
0x140011db0  mov     edx, ebx
0x140011db2  mov     ecx, edi
0x140011db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011db9  jmp     short loc_140011DBD
0x140011dbb  xor     esi, esi
0x140011dbd  mov     rbx, [rsp+88h+arg_0]
0x140011dc5  mov     eax, esi
0x140011dc7  add     rsp, 50h
0x140011dcb  pop     r15
0x140011dcd  pop     r14
0x140011dcf  pop     r13
0x140011dd1  pop     r12
0x140011dd3  pop     rdi
0x140011dd4  pop     rsi
0x140011dd5  pop     rbp
0x140011dd6  retn
```
