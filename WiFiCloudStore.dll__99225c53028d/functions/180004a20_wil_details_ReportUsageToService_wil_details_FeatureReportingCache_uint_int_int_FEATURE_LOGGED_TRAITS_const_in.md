# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180004a20`
- end: `0x180004ccc`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `684`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800263e8`
- `0x18003bd4c`

## callees

- `0x180004a20`
- `0x180005a30`
- `0x18001abb0`
- `0x180031280`
- `0x1800328e8`
- `0x180041010`

## pseudocode

```c
void __fastcall wil::details::ReportUsageToService(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        __int64 a5,
        int a6,
        int a7)
{
  unsigned int v10; // ebx
  int *v11; // rax
  unsigned int v12; // r9d
  unsigned int v13; // ecx
  int v14; // r13d
  unsigned int v15; // r12d
  int v16; // edi
  int v17; // ebx
  unsigned int v18; // edx
  const char *v19; // [rsp+20h] [rbp-78h]
  unsigned int v20; // [rsp+50h] [rbp-48h]
  _BYTE v21[24]; // [rsp+58h] [rbp-40h] BYREF
  unsigned __int8 v23; // [rsp+D8h] [rbp+40h]

  if ( a7 )
  {
    if ( a7 == 1 )
    {
      v10 = 4;
      if ( a6 )
        v10 = 0;
    }
    else
    {
      switch ( a7 )
      {
        case 0:
          goto LABEL_26;
        case 2:
          v10 = 1;
          if ( !a6 )
            v10 = 5;
          break;
        case 3:
          v10 = 2;
          if ( !a6 )
            v10 = 6;
          break;
        case 4:
          v10 = 3;
          if ( !a6 )
            v10 = 7;
          break;
        case 5:
          v10 = 8;
          if ( !a6 )
            v10 = 10;
          break;
        case 6:
          v10 = 9;
          if ( !a6 )
            v10 = 11;
          break;
        default:
          if ( (unsigned __int8)(a7 - 100) > 0x31u )
          {
LABEL_26:
            v10 = 255;
          }
          else
          {
            v17 = 100;
            if ( !a6 )
              v17 = 150;
            v10 = (unsigned __int8)(a7 - 100) + v17;
          }
          break;
      }
    }
    v23 = *(_BYTE *)(a5 + 4);
    v11 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v21, a1, v10);
    v13 = v11[2];
    v14 = *v11;
    v15 = v11[1];
    v16 = v11[4];
    v20 = v13;
    if ( g_wil_details_RecordSRUMFeatureUsage )
    {
      if ( !v10 || v10 - 100 <= 0x31 )
        g_wil_details_RecordSRUMFeatureUsage(a2, v10, 1);
      v13 = v20;
    }
    if ( v14 )
    {
      wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        a2,
        a1);
      v13 = v20;
    }
    if ( v15 )
      wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v13, v15, v12, v19);
    if ( !v16 )
      wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
        (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
        (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
    if ( a3 )
    {
      v18 = v10 | 0x80000000;
      if ( !a4 )
        v18 = v10;
      wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v18, 0, v12, v19);
    }
    if ( !v16 )
    {
      if ( g_wil_details_realtimeFeatureUsageHook )
        g_wil_details_realtimeFeatureUsageHook(a2, v10, v23);
      if ( g_wil_details_pfnFeatureLoggingHook )
        g_wil_details_pfnFeatureLoggingHook(a2, a5);
    }
  }
}

```

## disassembly

```asm
0x180004a20  mov     rax, rsp
0x180004a23  mov     [rax+20h], r9d
0x180004a27  push    rbp
0x180004a28  push    rsi
0x180004a29  push    r14
0x180004a2b  sub     rsp, 80h
0x180004a32  movsxd  r10, dword ptr [rax+38h]
0x180004a36  mov     esi, r8d
0x180004a39  mov     ebp, edx
0x180004a3b  mov     r14, rcx
0x180004a3e  test    r10d, r10d
0x180004a41  jz      loc_180004B2C
0x180004a47  mov     [rax+8], rbx
0x180004a4b  mov     [rax+10h], rdi
0x180004a4f  mov     [rax+18h], r12
0x180004a53  mov     [rax-20h], r13
0x180004a57  mov     [rax-28h], r15
0x180004a5b  mov     r15d, [rsp+98h+arg_28]
0x180004a63  cmp     r10d, 1
0x180004a67  jnz     loc_180004B9D
0x180004a6d  xor     eax, eax
0x180004a6f  mov     ebx, 4
0x180004a74  test    r15d, r15d
0x180004a77  cmovnz  ebx, eax
0x180004a7a  mov     rax, [rsp+98h+arg_20]
0x180004a82  lea     rcx, [rsp+98h+var_40]
0x180004a87  mov     r8d, ebx
0x180004a8a  mov     rdx, r14
0x180004a8d  movzx   eax, byte ptr [rax+4]
0x180004a91  mov     [rsp+98h+arg_38], al
0x180004a98  call    wil_details_FeatureReporting_RecordUsageInCache
0x180004a9d  mov     ecx, [rax+8]
0x180004aa0  mov     r13d, [rax]
0x180004aa3  mov     r12d, [rax+4]
0x180004aa7  mov     edi, [rax+10h]
0x180004aaa  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180004ab1  mov     [rsp+98h+var_48], ecx
0x180004ab5  test    rax, rax
0x180004ab8  jz      short loc_180004AD5
0x180004aba  test    ebx, ebx
0x180004abc  jnz     loc_180004C53
0x180004ac2  mov     r8d, 1
0x180004ac8  mov     edx, ebx
0x180004aca  mov     ecx, ebp
0x180004acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ad1  mov     ecx, [rsp+98h+var_48]
0x180004ad5  test    r13d, r13d
0x180004ad8  mov     r13, [rsp+98h+var_20]
0x180004add  jnz     loc_180004C64
0x180004ae3  test    r12d, r12d
0x180004ae6  jnz     loc_180004C7E
0x180004aec  mov     r12, [rsp+98h+arg_10]
0x180004af4  test    edi, edi
0x180004af6  jnz     short loc_180004B0B
0x180004af8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180004aff  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180004b06  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180004b0b  test    esi, esi
0x180004b0d  jnz     loc_180004C8F
0x180004b13  test    edi, edi
0x180004b15  mov     rdi, [rsp+98h+arg_8]
0x180004b1d  jz      short loc_180004B38
0x180004b1f  mov     rbx, [rsp+98h+arg_0]
0x180004b27  mov     r15, [rsp+98h+var_28]
0x180004b2c  add     rsp, 80h
0x180004b33  pop     r14
0x180004b35  pop     rsi
0x180004b36  pop     rbp
0x180004b37  retn
0x180004b38  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180004b3f  test    rax, rax
0x180004b42  jz      short loc_180004B56
0x180004b44  movzx   r8d, [rsp+98h+arg_38]
0x180004b4d  mov     edx, ebx
0x180004b4f  mov     ecx, ebp
0x180004b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b56  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180004b5d  test    rax, rax
0x180004b60  jz      short loc_180004B1F
0x180004b62  mov     rdx, [rsp+98h+arg_20]
0x180004b6a  lea     rcx, [rsp+98h+arg_30]
0x180004b72  mov     [rsp+98h+var_60], 1
0x180004b7b  mov     r9d, r15d
0x180004b7e  mov     [rsp+98h+var_68], 0
0x180004b83  xor     r8d, r8d
0x180004b86  mov     [rsp+98h+var_70], 0
0x180004b8f  mov     [rsp+98h+var_78], rcx
0x180004b94  mov     ecx, ebp
0x180004b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b9b  jmp     short loc_180004B1F
0x180004b9d  cmp     r10d, 6; switch 7 cases
0x180004ba1  ja      def_180004BB9; jumptable 0000000180004BB9 default case, case 1
0x180004ba7  lea     rdx, __ImageBase
0x180004bae  mov     ecx, ds:(jpt_180004BB9 - 180000000h)[rdx+r10*4]
0x180004bb6  add     rcx, rdx
0x180004bb9  jmp     rcx; switch jump
0x180004bbb  test    r15d, r15d; jumptable 0000000180004BB9 case 2
0x180004bbe  mov     ebx, 1
0x180004bc3  mov     eax, 5
0x180004bc8  cmovz   ebx, eax
0x180004bcb  jmp     loc_180004A7A
0x180004bd0  mov     ebx, 0FFh; jumptable 0000000180004BB9 case 0
0x180004bd5  jmp     loc_180004A7A
0x180004bda  test    r15d, r15d; jumptable 0000000180004BB9 case 3
0x180004bdd  mov     ebx, 2
0x180004be2  mov     eax, 6
0x180004be7  cmovz   ebx, eax
0x180004bea  jmp     loc_180004A7A
0x180004bef  test    r15d, r15d; jumptable 0000000180004BB9 case 4
0x180004bf2  mov     ebx, 3
0x180004bf7  mov     eax, 7
0x180004bfc  cmovz   ebx, eax
0x180004bff  jmp     loc_180004A7A
0x180004c04  test    r15d, r15d; jumptable 0000000180004BB9 case 5
0x180004c07  mov     ebx, 8
0x180004c0c  mov     eax, 0Ah
0x180004c11  cmovz   ebx, eax
0x180004c14  jmp     loc_180004A7A
0x180004c19  test    r15d, r15d; jumptable 0000000180004BB9 case 6
0x180004c1c  mov     ebx, 9
0x180004c21  mov     eax, 0Bh
0x180004c26  cmovz   ebx, eax
0x180004c29  jmp     loc_180004A7A
0x180004c2e  sub     r10b, 64h ; 'd'; jumptable 0000000180004BB9 default case, case 1
0x180004c32  cmp     r10b, 31h ; '1'
0x180004c36  ja      short loc_180004BD0; jumptable 0000000180004BB9 case 0
0x180004c38  test    r15d, r15d
0x180004c3b  mov     eax, 96h
0x180004c40  mov     ebx, 64h ; 'd'
0x180004c45  cmovz   ebx, eax
0x180004c48  movzx   eax, r10b
0x180004c4c  add     ebx, eax
0x180004c4e  jmp     loc_180004A7A
0x180004c53  lea     ecx, [rbx-64h]
0x180004c56  cmp     ecx, 31h ; '1'
0x180004c59  ja      loc_180004AD1
0x180004c5f  jmp     loc_180004AC2
0x180004c64  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x180004c67  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180004c6e  mov     edx, ebp; unsigned int
0x180004c70  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180004c75  mov     ecx, [rsp+98h+var_48]
0x180004c79  jmp     loc_180004AE3
0x180004c7e  mov     edx, ecx; unsigned int
0x180004c80  mov     r8d, r12d; unsigned int
0x180004c83  mov     ecx, ebp; this
0x180004c85  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180004c8a  jmp     loc_180004AEC
0x180004c8f  mov     edx, ebx
0x180004c91  mov     ecx, ebp; this
0x180004c93  bts     edx, 1Fh
0x180004c97  cmp     [rsp+98h+arg_18], 0
0x180004c9f  cmovz   edx, ebx; unsigned int
0x180004ca2  xor     r8d, r8d; unsigned int
0x180004ca5  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180004caa  jmp     loc_180004B13
```
