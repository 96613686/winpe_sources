# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180011570`
- end: `0x1800117ac`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `572`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018a50`

## callees

- `0x180011570`
- `0x180014624`
- `0x180017fe0`
- `0x18001fee8`
- `0x180027f54`
- `0x18002b97c`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        volatile signed __int32 *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        unsigned __int8 a8)
{
  int v9; // ebp
  BOOL v12; // ebx
  int v13; // edx
  unsigned int v14; // r8d
  unsigned __int32 v15; // eax
  unsigned __int32 v16; // ett
  signed __int32 i; // ecx
  signed __int32 v18; // r8d
  signed __int32 v19; // eax
  unsigned int v20; // edx
  char *v22[2]; // [rsp+20h] [rbp-58h] BYREF
  _BOOL8 v23; // [rsp+30h] [rbp-48h]

  v23 = 0;
  v9 = a3;
  *(_OWORD *)v22 = 0;
  if ( a5 == 7 )
  {
LABEL_18:
    v13 = 0;
    switch ( a5 )
    {
      case 2u:
        v13 = 2;
        break;
      case 3u:
        v13 = 8;
        break;
      case 7u:
        v13 = 16;
        break;
    }
LABEL_24:
    for ( i = *a1; ; i = v19 )
    {
      v12 = (i | v13) == i;
      v18 = i | v13 | 1;
      if ( (i | v13) == i )
        v18 = i | v13;
      v19 = _InterlockedCompareExchange(a1, v18, i);
      if ( i == v19 )
        break;
    }
    if ( (v18 & 1) == 0 || (LODWORD(v22[0]) = 1, (i & 1) != 0) )
      LODWORD(v22[0]) = 0;
  }
  else
  {
    switch ( a5 )
    {
      case 0u:
      case 4u:
        wil_details_FeatureReporting_IncrementUsageInCache(a1, a5, a3, v22);
        v12 = v23;
        break;
      case 1u:
      case 5u:
        wil_details_FeatureReporting_IncrementOpportunityInCache(a1, a5, a3, v22);
        v12 = v23;
        break;
      case 2u:
      case 3u:
      case 6u:
        if ( a5 != 6 )
          goto LABEL_18;
        v13 = 4;
        goto LABEL_24;
      default:
        v14 = a5 - 320;
        if ( (int)(a5 - 320) >= 64 )
        {
          v12 = v23;
LABEL_17:
          LODWORD(v22[1]) = a5;
          HIDWORD(v22[0]) = 1;
          break;
        }
        v15 = *((_DWORD *)a1 + 1);
        do
        {
          v12 = (v15 & 0x10) != 0 && ((v15 >> 5) & 0x3F) == v14;
          v16 = v15;
          v15 = _InterlockedCompareExchange(
                  a1 + 1,
                  v15 ^ ((unsigned __int16)v15 ^ (unsigned __int16)(32 * v14)) & 0x7E0 | 0x10,
                  v15);
        }
        while ( v16 != v15 );
        if ( !v12 )
          goto LABEL_17;
        break;
    }
  }
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( LODWORD(v22[0]) )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (char *)&wil::details::g_enabledStateManager,
      a2,
      (struct wil_details_FeatureReportingCache *)a1);
  if ( HIDWORD(v22[0]) )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, (unsigned int)v22[1], HIDWORD(v22[0]), a4, v22[0]);
  if ( !v12 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( v9 )
  {
    v20 = a5 | 0x80000000;
    if ( !a4 )
      v20 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v20, 0, a4, v22[0]);
  }
  if ( v12 )
    return 0;
  if ( g_wil_details_realtimeFeatureUsageHook )
    g_wil_details_realtimeFeatureUsageHook(a2, a5, a8);
  return 1;
}

```

## disassembly

```asm
0x180011570  push    rbx
0x180011572  push    rbp
0x180011573  push    rdi
0x180011574  push    r12
0x180011576  push    r14
0x180011578  push    r15
0x18001157a  sub     rsp, 48h
0x18001157e  movsxd  rdi, [rsp+78h+arg_20]
0x180011586  xor     eax, eax
0x180011588  mov     [rsp+78h+var_48], rax
0x18001158d  xorps   xmm0, xmm0
0x180011590  mov     r15d, r9d
0x180011593  mov     ebp, r8d
0x180011596  mov     r12d, edx
0x180011599  mov     r14, rcx
0x18001159c  movups  xmmword ptr [rsp+78h+var_58], xmm0
0x1800115a1  cmp     edi, 7
0x1800115a4  jz      loc_180011661
0x1800115aa  cmp     edi, 6; switch 7 cases
0x1800115ad  ja      short def_1800115C0; jumptable 00000001800115C0 default case
0x1800115af  lea     rdx, __ImageBase
0x1800115b6  mov     ecx, ds:(jpt_1800115C0 - 180000000h)[rdx+rdi*4]
0x1800115bd  add     rcx, rdx
0x1800115c0  jmp     rcx; switch jump
0x1800115c2  lea     r9, [rsp+78h+var_58]; jumptable 00000001800115C0 cases 0,4
0x1800115c7  mov     edx, edi
0x1800115c9  mov     rcx, r14
0x1800115cc  call    wil_details_FeatureReporting_IncrementUsageInCache
0x1800115d1  mov     ebx, dword ptr [rsp+78h+var_48]
0x1800115d5  jmp     loc_1800116CA
0x1800115da  lea     r9, [rsp+78h+var_58]; jumptable 00000001800115C0 cases 1,5
0x1800115df  mov     edx, edi
0x1800115e1  mov     rcx, r14
0x1800115e4  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1800115e9  mov     ebx, dword ptr [rsp+78h+var_48]
0x1800115ed  jmp     loc_1800116CA
0x1800115f2  cmp     edi, 6; jumptable 00000001800115C0 cases 2,3,6
0x1800115f5  jnz     short loc_180011661
0x1800115f7  mov     edx, 4
0x1800115fc  jmp     loc_180011687
0x180011601  lea     r8d, [rdi-140h]; jumptable 00000001800115C0 default case
0x180011608  cmp     r8d, 40h ; '@'
0x18001160c  jge     short loc_18001164F
0x18001160e  mov     eax, [r14+4]
0x180011612  mov     edx, r8d
0x180011615  shl     edx, 5
0x180011618  test    al, 10h
0x18001161a  jz      short loc_180011630
0x18001161c  mov     ecx, eax
0x18001161e  shr     ecx, 5
0x180011621  and     ecx, 3Fh
0x180011624  cmp     ecx, r8d
0x180011627  jnz     short loc_180011630
0x180011629  mov     ebx, 1
0x18001162e  jmp     short loc_180011632
0x180011630  xor     ebx, ebx
0x180011632  mov     ecx, edx
0x180011634  xor     ecx, eax
0x180011636  and     ecx, 7E0h
0x18001163c  xor     ecx, eax
0x18001163e  or      ecx, 10h
0x180011641  lock cmpxchg [r14+4], ecx
0x180011647  jnz     short loc_180011618
0x180011649  test    ebx, ebx
0x18001164b  jnz     short loc_1800116CA
0x18001164d  jmp     short loc_180011653
0x18001164f  mov     ebx, dword ptr [rsp+78h+var_48]
0x180011653  mov     dword ptr [rsp+78h+var_58+8], edi
0x180011657  mov     dword ptr [rsp+78h+var_58+4], 1
0x18001165f  jmp     short loc_1800116CA
0x180011661  xor     edx, edx
0x180011663  mov     ecx, edi
0x180011665  sub     ecx, 2
0x180011668  jz      short loc_180011682
0x18001166a  sub     ecx, 1
0x18001166d  jz      short loc_18001167B
0x18001166f  cmp     ecx, 4
0x180011672  jnz     short loc_180011687
0x180011674  mov     edx, 10h
0x180011679  jmp     short loc_180011687
0x18001167b  mov     edx, 8
0x180011680  jmp     short loc_180011687
0x180011682  mov     edx, 2
0x180011687  mov     ecx, [r14]
0x18001168a  xor     ebx, ebx
0x18001168c  mov     eax, edx
0x18001168e  or      eax, ecx
0x180011690  cmp     eax, ecx
0x180011692  mov     r8d, eax
0x180011695  setz    bl
0x180011698  or      r8d, 1
0x18001169c  test    ebx, ebx
0x18001169e  cmovnz  r8d, eax
0x1800116a2  mov     eax, ecx
0x1800116a4  lock cmpxchg [r14], r8d
0x1800116a9  jz      short loc_1800116AF
0x1800116ab  mov     ecx, eax
0x1800116ad  jmp     short loc_18001168A
0x1800116af  test    r8b, 1
0x1800116b3  jz      short loc_1800116C2
0x1800116b5  mov     dword ptr [rsp+78h+var_58], 1
0x1800116bd  test    cl, 1
0x1800116c0  jz      short loc_1800116CA
0x1800116c2  mov     dword ptr [rsp+78h+var_58], 0; char *
0x1800116ca  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800116d1  test    rax, rax
0x1800116d4  jz      short loc_1800116F2
0x1800116d6  test    edi, edi
0x1800116d8  jz      short loc_1800116E2
0x1800116da  lea     ecx, [rdi-64h]
0x1800116dd  cmp     ecx, 31h ; '1'
0x1800116e0  ja      short loc_1800116F2
0x1800116e2  mov     r8d, 1
0x1800116e8  mov     edx, edi
0x1800116ea  mov     ecx, r12d
0x1800116ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116f2  cmp     dword ptr [rsp+78h+var_58], 0
0x1800116f7  jz      short loc_18001170B
0x1800116f9  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x1800116fc  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180011703  mov     edx, r12d; unsigned int
0x180011706  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001170b  cmp     dword ptr [rsp+78h+var_58+4], 0
0x180011710  jbe     short loc_180011723
0x180011712  mov     r8d, dword ptr [rsp+78h+var_58+4]; unsigned int
0x180011717  mov     ecx, r12d; this
0x18001171a  mov     edx, dword ptr [rsp+78h+var_58+8]; unsigned int
0x18001171e  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180011723  test    ebx, ebx
0x180011725  jnz     short loc_18001173A
0x180011727  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18001172e  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180011735  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18001173a  test    ebp, ebp
0x18001173c  jz      short loc_180011755
0x18001173e  mov     edx, edi
0x180011740  mov     ecx, r12d; this
0x180011743  bts     edx, 1Fh
0x180011747  test    r15d, r15d
0x18001174a  cmovz   edx, edi; unsigned int
0x18001174d  xor     r8d, r8d; unsigned int
0x180011750  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180011755  test    ebx, ebx
0x180011757  jnz     short loc_18001177F
0x180011759  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180011760  test    rax, rax
0x180011763  jz      short loc_180011778
0x180011765  movzx   r8d, [rsp+78h+arg_38]
0x18001176e  mov     edx, edi
0x180011770  mov     ecx, r12d
0x180011773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011778  mov     eax, 1
0x18001177d  jmp     short loc_180011781
0x18001177f  xor     eax, eax
0x180011781  add     rsp, 48h
0x180011785  pop     r15
0x180011787  pop     r14
0x180011789  pop     r12
0x18001178b  pop     rdi
0x18001178c  pop     rbp
0x18001178d  pop     rbx
0x18001178e  retn
```
