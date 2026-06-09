# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18002107c`
- end: `0x180021184`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180020fa4`

## callees

- `0x18001e834`
- `0x18001ff58`
- `0x18002107c`
- `0x180022144`
- `0x180023938`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        __int64 a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  int *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // r9d
  unsigned int v14; // edi
  int v15; // r15d
  unsigned int v16; // ebp
  unsigned int v17; // r13d
  int v18; // esi
  unsigned int v19; // edx
  const char *v21; // [rsp+20h] [rbp-78h]
  _BYTE v22[104]; // [rsp+30h] [rbp-68h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v22, a1, a5);
  v14 = 1;
  v15 = *v10;
  v16 = v10[1];
  v17 = v10[2];
  v18 = v10[4];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(60475541, a5, 1);
  if ( v15 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      v11,
      a1);
  if ( v16 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x39AC895, v17, v16, v13, v21);
  if ( !v18 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( a3 )
  {
    v19 = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x39AC895, v19, 0, v13, v21);
  }
  if ( v18 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(60475541, a5, v12);
  }
  return v14;
}

```

## disassembly

```asm
0x18002107c  mov     [rsp+arg_18], r9d
0x180021081  push    rbx
0x180021082  push    rbp
0x180021083  push    rsi
0x180021084  push    rdi
0x180021085  push    r12
0x180021087  push    r13
0x180021089  push    r14
0x18002108b  push    r15
0x18002108d  sub     rsp, 58h
0x180021091  mov     ebx, [rsp+98h+arg_20]
0x180021098  mov     r12d, r8d
0x18002109b  mov     r14, rcx
0x18002109e  mov     rdx, rcx
0x1800210a1  mov     r8d, ebx
0x1800210a4  lea     rcx, [rsp+98h+var_68]
0x1800210a9  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800210ae  mov     edi, 1
0x1800210b3  mov     r15d, [rax]
0x1800210b6  mov     ebp, [rax+4]
0x1800210b9  mov     r13d, [rax+8]
0x1800210bd  mov     esi, [rax+10h]
0x1800210c0  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800210c7  test    rax, rax
0x1800210ca  jz      short loc_1800210E7
0x1800210cc  test    ebx, ebx
0x1800210ce  jz      short loc_1800210D8
0x1800210d0  lea     ecx, [rbx-64h]
0x1800210d3  cmp     ecx, 31h ; '1'
0x1800210d6  ja      short loc_1800210E7
0x1800210d8  mov     r8d, edi
0x1800210db  mov     edx, ebx
0x1800210dd  mov     ecx, 39AC895h
0x1800210e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210e7  test    r15d, r15d
0x1800210ea  jz      short loc_1800210FB
0x1800210ec  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x1800210ef  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800210f6  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800210fb  test    ebp, ebp
0x1800210fd  jz      short loc_18002110F
0x1800210ff  mov     r8d, ebp; unsigned int
0x180021102  mov     edx, r13d; unsigned int
0x180021105  mov     ecx, 39AC895h; this
0x18002110a  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18002110f  test    esi, esi
0x180021111  jnz     short loc_180021126
0x180021113  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18002111a  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180021121  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180021126  test    r12d, r12d
0x180021129  jz      short loc_180021149
0x18002112b  mov     edx, ebx
0x18002112d  mov     ecx, 39AC895h; this
0x180021132  bts     edx, 1Fh
0x180021136  cmp     [rsp+98h+arg_18], 0
0x18002113e  cmovz   edx, ebx; unsigned int
0x180021141  xor     r8d, r8d; unsigned int
0x180021144  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180021149  test    esi, esi
0x18002114b  jnz     short loc_18002116F
0x18002114d  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180021154  test    rax, rax
0x180021157  jz      short loc_180021171
0x180021159  mov     r8b, [rsp+98h+arg_38]
0x180021161  mov     edx, ebx
0x180021163  mov     ecx, 39AC895h
0x180021168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002116d  jmp     short loc_180021171
0x18002116f  xor     edi, edi
0x180021171  mov     eax, edi
0x180021173  add     rsp, 58h
0x180021177  pop     r15
0x180021179  pop     r14
0x18002117b  pop     r13
0x18002117d  pop     r12
0x18002117f  pop     rdi
0x180021180  pop     rsi
0x180021181  pop     rbp
0x180021182  pop     rbx
0x180021183  retn
```
