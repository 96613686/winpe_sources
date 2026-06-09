# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x14000462c`
- end: `0x14000472d`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140004254`

## callees

- `0x14000462c`
- `0x14000b564`
- `0x14000ced4`
- `0x14000d124`
- `0x14000d3b4`
- `0x140010010`

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
  void (*v11)(void *); // rdx
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
    g_wil_details_RecordSRUMFeatureUsage(24159631, a5, 1);
  if ( v15 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
      (__int64)v11,
      a1);
  if ( v16 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x170A58F, v17, v16, v13, v21);
  if ( !v18 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)wil::details::g_enabledStateManager,
      v11);
  if ( a3 )
  {
    v19 = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x170A58F, v19, 0, v13, v21);
  }
  if ( v18 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(24159631, a5, v12);
  }
  return v14;
}

```

## disassembly

```asm
0x14000462c  mov     [rsp+arg_18], r9d
0x140004631  push    rbx
0x140004632  push    rbp
0x140004633  push    rsi
0x140004634  push    rdi
0x140004635  push    r12
0x140004637  push    r13
0x140004639  push    r14
0x14000463b  push    r15
0x14000463d  sub     rsp, 58h
0x140004641  mov     ebx, [rsp+98h+arg_20]
0x140004648  mov     r12d, r8d
0x14000464b  mov     r14, rcx
0x14000464e  mov     rdx, rcx
0x140004651  mov     r8d, ebx
0x140004654  lea     rcx, [rsp+98h+var_68]
0x140004659  call    wil_details_FeatureReporting_RecordUsageInCache
0x14000465e  mov     edi, 1
0x140004663  mov     r15d, [rax]
0x140004666  mov     ebp, [rax+4]
0x140004669  mov     r13d, [rax+8]
0x14000466d  mov     esi, [rax+10h]
0x140004670  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x140004677  test    rax, rax
0x14000467a  jz      short loc_140004697
0x14000467c  test    ebx, ebx
0x14000467e  jz      short loc_140004688
0x140004680  lea     ecx, [rbx-64h]
0x140004683  cmp     ecx, 31h ; '1'
0x140004686  ja      short loc_140004697
0x140004688  mov     r8d, edi
0x14000468b  mov     edx, ebx
0x14000468d  mov     ecx, 170A58Fh
0x140004692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004697  test    r15d, r15d
0x14000469a  jz      short loc_1400046AB
0x14000469c  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x14000469f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1400046a6  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1400046ab  test    ebp, ebp
0x1400046ad  jz      short loc_1400046BF
0x1400046af  mov     r8d, ebp; unsigned int
0x1400046b2  mov     edx, r13d; unsigned int
0x1400046b5  mov     ecx, 170A58Fh; this
0x1400046ba  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1400046bf  test    esi, esi
0x1400046c1  jnz     short loc_1400046CF
0x1400046c3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1400046ca  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x1400046cf  test    r12d, r12d
0x1400046d2  jz      short loc_1400046F2
0x1400046d4  mov     edx, ebx
0x1400046d6  mov     ecx, 170A58Fh; this
0x1400046db  bts     edx, 1Fh
0x1400046df  cmp     [rsp+98h+arg_18], 0
0x1400046e7  cmovz   edx, ebx; unsigned int
0x1400046ea  xor     r8d, r8d; unsigned int
0x1400046ed  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1400046f2  test    esi, esi
0x1400046f4  jnz     short loc_140004718
0x1400046f6  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1400046fd  test    rax, rax
0x140004700  jz      short loc_14000471A
0x140004702  mov     r8b, [rsp+98h+arg_38]
0x14000470a  mov     edx, ebx
0x14000470c  mov     ecx, 170A58Fh
0x140004711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004716  jmp     short loc_14000471A
0x140004718  xor     edi, edi
0x14000471a  mov     eax, edi
0x14000471c  add     rsp, 58h
0x140004720  pop     r15
0x140004722  pop     r14
0x140004724  pop     r13
0x140004726  pop     r12
0x140004728  pop     rdi
0x140004729  pop     rsi
0x14000472a  pop     rbp
0x14000472b  pop     rbx
0x14000472c  retn
```
