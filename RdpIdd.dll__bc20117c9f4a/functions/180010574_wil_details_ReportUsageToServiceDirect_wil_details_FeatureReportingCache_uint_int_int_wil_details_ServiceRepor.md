# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180010574`
- end: `0x180010688`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800104d0`

## callees

- `0x18000bad4`
- `0x18000ee4c`
- `0x18000f22c`
- `0x180010574`
- `0x180010a7c`
- `0x18003f010`

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
  void (*v12)(void *); // rdx
  __int64 v13; // r8
  unsigned int v14; // r9d
  unsigned int v15; // esi
  int v16; // r12d
  unsigned int v17; // r14d
  int v18; // ebp
  unsigned int v19; // edx
  const char *v21; // [rsp+20h] [rbp-68h]
  _BYTE v22[88]; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v23; // [rsp+A0h] [rbp+18h]

  v11 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v22, a1, a5, 0);
  v15 = 1;
  v16 = *v11;
  v17 = v11[1];
  v18 = v11[4];
  v23 = v11[2];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v16 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v17 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v23, v17, v14, v21);
  if ( !v18 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
      v12);
  if ( a3 )
  {
    v19 = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v19, 0, v14, v21);
  }
  if ( v18 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v13) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v13);
  }
  return v15;
}

```

## disassembly

```asm
0x180010574  mov     [rsp+arg_0], rbx
0x180010579  mov     [rsp+arg_18], r9d
0x18001057e  push    rbp
0x18001057f  push    rsi
0x180010580  push    rdi
0x180010581  push    r12
0x180010583  push    r13
0x180010585  push    r14
0x180010587  push    r15
0x180010589  sub     rsp, 50h
0x18001058d  mov     ebx, [rsp+88h+arg_20]
0x180010594  mov     edi, edx
0x180010596  mov     rdx, rcx
0x180010599  mov     r13d, r8d
0x18001059c  mov     r15, rcx
0x18001059f  xor     r9d, r9d
0x1800105a2  lea     rcx, [rsp+88h+var_58]
0x1800105a7  mov     r8d, ebx
0x1800105aa  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800105af  mov     esi, 1
0x1800105b4  mov     ecx, [rax+8]
0x1800105b7  mov     r12d, [rax]
0x1800105ba  mov     r14d, [rax+4]
0x1800105be  mov     ebp, [rax+10h]
0x1800105c1  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800105c8  mov     [rsp+88h+arg_10], ecx
0x1800105cf  test    rax, rax
0x1800105d2  jz      short loc_1800105EC
0x1800105d4  test    ebx, ebx
0x1800105d6  jz      short loc_1800105E0
0x1800105d8  lea     ecx, [rbx-64h]
0x1800105db  cmp     ecx, 31h ; '1'
0x1800105de  ja      short loc_1800105EC
0x1800105e0  mov     r8d, esi
0x1800105e3  mov     edx, ebx
0x1800105e5  mov     ecx, edi
0x1800105e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105ec  test    r12d, r12d
0x1800105ef  jz      short loc_180010602
0x1800105f1  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x1800105f4  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800105fb  mov     edx, edi; unsigned int
0x1800105fd  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180010602  test    r14d, r14d
0x180010605  jz      short loc_180010618
0x180010607  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18001060e  mov     r8d, r14d; unsigned int
0x180010611  mov     ecx, edi; this
0x180010613  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180010618  test    ebp, ebp
0x18001061a  jnz     short loc_180010628
0x18001061c  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180010623  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180010628  test    r13d, r13d
0x18001062b  jz      short loc_180010648
0x18001062d  mov     edx, ebx
0x18001062f  mov     ecx, edi; this
0x180010631  bts     edx, 1Fh
0x180010635  cmp     [rsp+88h+arg_18], 0
0x18001063d  cmovz   edx, ebx; unsigned int
0x180010640  xor     r8d, r8d; unsigned int
0x180010643  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180010648  test    ebp, ebp
0x18001064a  jnz     short loc_18001066B
0x18001064c  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180010653  test    rax, rax
0x180010656  jz      short loc_18001066D
0x180010658  mov     r8b, [rsp+88h+arg_38]
0x180010660  mov     edx, ebx
0x180010662  mov     ecx, edi
0x180010664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010669  jmp     short loc_18001066D
0x18001066b  xor     esi, esi
0x18001066d  mov     rbx, [rsp+88h+arg_0]
0x180010675  mov     eax, esi
0x180010677  add     rsp, 50h
0x18001067b  pop     r15
0x18001067d  pop     r14
0x18001067f  pop     r13
0x180010681  pop     r12
0x180010683  pop     rdi
0x180010684  pop     rsi
0x180010685  pop     rbp
0x180010686  retn
```
