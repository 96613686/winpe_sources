# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000ff48`
- end: `0x180010067`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `287`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000fe9c`
- `0x180013208`

## callees

- `0x18000a384`
- `0x18000ecf4`
- `0x18000fa68`
- `0x18000ff48`
- `0x180011d1c`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
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

  v11 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v21, a1, a5, a6);
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
0x18000ff48  mov     [rsp+arg_0], rbx
0x18000ff4d  mov     [rsp+arg_18], r9d
0x18000ff52  push    rbp
0x18000ff53  push    rsi
0x18000ff54  push    rdi
0x18000ff55  push    r12
0x18000ff57  push    r13
0x18000ff59  push    r14
0x18000ff5b  push    r15
0x18000ff5d  sub     rsp, 50h
0x18000ff61  mov     ebx, [rsp+88h+arg_20]
0x18000ff68  mov     edi, edx
0x18000ff6a  mov     r9d, [rsp+88h+arg_28]
0x18000ff72  mov     rdx, rcx
0x18000ff75  mov     r13d, r8d
0x18000ff78  mov     r15, rcx
0x18000ff7b  lea     rcx, [rsp+88h+var_58]
0x18000ff80  mov     r8d, ebx
0x18000ff83  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000ff88  mov     esi, 1
0x18000ff8d  mov     ecx, [rax+8]
0x18000ff90  mov     r12d, [rax]
0x18000ff93  mov     r14d, [rax+4]
0x18000ff97  mov     ebp, [rax+10h]
0x18000ff9a  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000ffa1  mov     [rsp+88h+arg_10], ecx
0x18000ffa8  test    rax, rax
0x18000ffab  jz      short loc_18000FFC5
0x18000ffad  test    ebx, ebx
0x18000ffaf  jz      short loc_18000FFB9
0x18000ffb1  lea     ecx, [rbx-64h]
0x18000ffb4  cmp     ecx, 31h ; '1'
0x18000ffb7  ja      short loc_18000FFC5
0x18000ffb9  mov     r8d, esi
0x18000ffbc  mov     edx, ebx
0x18000ffbe  mov     ecx, edi
0x18000ffc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffc5  test    r12d, r12d
0x18000ffc8  jz      short loc_18000FFDB
0x18000ffca  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x18000ffcd  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000ffd4  mov     edx, edi; unsigned int
0x18000ffd6  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000ffdb  test    r14d, r14d
0x18000ffde  jz      short loc_18000FFF1
0x18000ffe0  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18000ffe7  mov     r8d, r14d; unsigned int
0x18000ffea  mov     ecx, edi; this
0x18000ffec  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000fff1  test    ebp, ebp
0x18000fff3  jnz     short loc_180010008
0x18000fff5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18000fffc  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180010003  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180010008  test    r13d, r13d
0x18001000b  jz      short loc_180010028
0x18001000d  mov     edx, ebx
0x18001000f  mov     ecx, edi; this
0x180010011  bts     edx, 1Fh
0x180010015  cmp     [rsp+88h+arg_18], 0
0x18001001d  cmovz   edx, ebx; unsigned int
0x180010020  xor     r8d, r8d; unsigned int
0x180010023  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180010028  test    ebp, ebp
0x18001002a  jnz     short loc_18001004B
0x18001002c  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180010033  test    rax, rax
0x180010036  jz      short loc_18001004D
0x180010038  mov     r8b, [rsp+88h+arg_38]
0x180010040  mov     edx, ebx
0x180010042  mov     ecx, edi
0x180010044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010049  jmp     short loc_18001004D
0x18001004b  xor     esi, esi
0x18001004d  mov     rbx, [rsp+88h+arg_0]
0x180010055  mov     eax, esi
0x180010057  add     rsp, 50h
0x18001005b  pop     r15
0x18001005d  pop     r14
0x18001005f  pop     r13
0x180010061  pop     r12
0x180010063  pop     rdi
0x180010064  pop     rsi
0x180010065  pop     rbp
0x180010066  retn
```
