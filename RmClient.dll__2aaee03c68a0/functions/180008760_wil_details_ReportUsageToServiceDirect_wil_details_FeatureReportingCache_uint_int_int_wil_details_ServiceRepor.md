# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180008760`
- end: `0x1800089e0`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `640`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, __int64, unsigned int, unsigned int, __int64, __int64, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007ce8`

## callees

- `0x180008760`
- `0x1800089e8`
- `0x180008ad0`
- `0x180008c64`
- `0x180009020`
- `0x180017988`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        unsigned __int8 a8)
{
  int v9; // r14d
  BOOL v11; // edi
  unsigned int v12; // ebp
  signed __int32 v14; // r8d
  signed __int32 v15; // eax
  signed __int32 i; // ecx
  unsigned __int32 v17; // eax
  unsigned __int32 v18; // ett
  unsigned int v19; // r8d
  unsigned int v20; // edx
  char *v21[2]; // [rsp+20h] [rbp-58h] BYREF
  _BOOL8 v22; // [rsp+30h] [rbp-48h]

  v22 = 0;
  v9 = a3;
  *(_OWORD *)v21 = 0;
  if ( a5 != 4 )
  {
    switch ( a5 )
    {
      case 0u:
        break;
      case 1u:
      case 5u:
        wil_details_FeatureReporting_IncrementOpportunityInCache(a1, a5, a3, v21);
        goto LABEL_3;
      case 2u:
      case 3u:
      case 6u:
      case 7u:
        a2 = 0;
        switch ( a5 )
        {
          case 2u:
            a2 = 2;
            break;
          case 3u:
            a2 = 8;
            break;
          case 6u:
            a2 = 4;
            break;
          case 7u:
            a2 = 16;
            break;
        }
        for ( i = *a1; ; i = v15 )
        {
          v11 = (i | (unsigned int)a2) == i;
          v14 = i | a2 | 1;
          if ( (i | (unsigned int)a2) == i )
            v14 = i | a2;
          v15 = _InterlockedCompareExchange(a1, v14, i);
          if ( i == v15 )
            break;
        }
        LOBYTE(a2) = (v14 & 1) != 0;
        LODWORD(v21[0]) = ((unsigned __int8)a2 & ((i & 1) == 0)) != 0;
        goto LABEL_4;
      default:
        v19 = a5 - 320;
        if ( (int)(a5 - 320) >= 64 )
        {
          v11 = v22;
        }
        else
        {
          v17 = *((_DWORD *)a1 + 1);
          a2 = 32 * v19;
          do
          {
            v11 = (v17 & 0x10) != 0 && ((v17 >> 5) & 0x3F) == v19;
            v18 = v17;
            v17 = _InterlockedCompareExchange(
                    a1 + 1,
                    v17 ^ ((unsigned __int16)v17 ^ (unsigned __int16)(32 * v19)) & 0x7E0 | 0x10,
                    v17);
          }
          while ( v18 != v17 );
          if ( v11 )
            goto LABEL_4;
        }
        LODWORD(v21[1]) = a5;
        HIDWORD(v21[0]) = 1;
        goto LABEL_4;
    }
  }
  wil_details_FeatureReporting_IncrementUsageInCache(a1, a5, a3, v21);
LABEL_3:
  v11 = v22;
LABEL_4:
  v12 = HIDWORD(v21[0]);
  if ( g_wil_details_RecordSRUMFeatureUsage && (a5 - 100 <= 0x31 || !a5) )
    g_wil_details_RecordSRUMFeatureUsage(31261443, a5, 1);
  if ( LODWORD(v21[0]) )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
      a2,
      (struct wil_details_FeatureReportingCache *)a1);
  if ( v12 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x1DD0303, (unsigned int)v21[1], v12, a4, v21[0]);
  if ( !v11 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( v9 )
  {
    v20 = a5 | 0x80000000;
    if ( !a4 )
      v20 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x1DD0303, v20, 0, a4, v21[0]);
  }
  if ( v11 )
    return 0;
  if ( g_wil_details_realtimeFeatureUsageHook )
    g_wil_details_realtimeFeatureUsageHook(31261443, a5, a8);
  return 1;
}

```

## disassembly

```asm
0x180008760  push    rbx
0x180008762  push    rbp
0x180008763  push    rsi
0x180008764  push    rdi
0x180008765  push    r14
0x180008767  push    r15
0x180008769  sub     rsp, 48h
0x18000876d  movsxd  rbx, [rsp+78h+arg_20]
0x180008775  xor     eax, eax
0x180008777  mov     [rsp+78h+var_48], rax
0x18000877c  xorps   xmm0, xmm0
0x18000877f  mov     r15d, r9d
0x180008782  mov     r14d, r8d
0x180008785  mov     rsi, rcx
0x180008788  movups  xmmword ptr [rsp+78h+var_58], xmm0; char *
0x18000878d  cmp     ebx, 4
0x180008790  jnz     loc_1800088B3
0x180008796  lea     r9, [rsp+78h+var_58]; jumptable 00000001800088CD case 0
0x18000879b  mov     edx, ebx
0x18000879d  mov     rcx, rsi
0x1800087a0  call    wil_details_FeatureReporting_IncrementUsageInCache
0x1800087a5  mov     edi, dword ptr [rsp+78h+var_48]
0x1800087a9  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800087b0  mov     ebp, dword ptr [rsp+78h+var_58+4]
0x1800087b4  test    rax, rax
0x1800087b7  jz      short loc_1800087CD
0x1800087b9  lea     ecx, [rbx-64h]
0x1800087bc  cmp     ecx, 31h ; '1'
0x1800087bf  jbe     loc_180008989
0x1800087c5  test    ebx, ebx
0x1800087c7  jz      loc_180008989
0x1800087cd  cmp     dword ptr [rsp+78h+var_58], 0
0x1800087d2  jz      short loc_1800087E3
0x1800087d4  mov     r8, rsi; struct wil_details_FeatureReportingCache *
0x1800087d7  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800087de  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800087e3  test    ebp, ebp
0x1800087e5  jnz     short loc_18000884F
0x1800087e7  test    edi, edi
0x1800087e9  jz      short loc_18000883A
0x1800087eb  test    r14d, r14d
0x1800087ee  jnz     loc_1800089A0
0x1800087f4  test    edi, edi
0x1800087f6  jz      short loc_180008807
0x1800087f8  xor     eax, eax
0x1800087fa  add     rsp, 48h
0x1800087fe  pop     r15
0x180008800  pop     r14
0x180008802  pop     rdi
0x180008803  pop     rsi
0x180008804  pop     rbp
0x180008805  pop     rbx
0x180008806  retn
0x180008807  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000880e  test    rax, rax
0x180008811  jz      short loc_180008828
0x180008813  movzx   r8d, [rsp+78h+arg_38]
0x18000881c  mov     edx, ebx
0x18000881e  mov     ecx, 1DD0303h
0x180008823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008828  mov     eax, 1
0x18000882d  add     rsp, 48h
0x180008831  pop     r15
0x180008833  pop     r14
0x180008835  pop     rdi
0x180008836  pop     rsi
0x180008837  pop     rbp
0x180008838  pop     rbx
0x180008839  retn
0x18000883a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180008841  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180008848  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18000884d  jmp     short loc_1800087EB
0x18000884f  mov     edx, dword ptr [rsp+78h+var_58+8]; unsigned int
0x180008853  mov     r8d, ebp; unsigned int
0x180008856  mov     ecx, 1DD0303h; this
0x18000885b  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180008860  jmp     short loc_1800087E7
0x180008862  xor     edi, edi
0x180008864  mov     eax, edx
0x180008866  or      eax, ecx
0x180008868  cmp     eax, ecx
0x18000886a  mov     r8d, eax
0x18000886d  setz    dil
0x180008871  or      r8d, 1
0x180008875  test    edi, edi
0x180008877  cmovnz  r8d, eax
0x18000887b  mov     eax, ecx
0x18000887d  lock cmpxchg [rsi], r8d
0x180008882  jz      loc_180008908
0x180008888  mov     ecx, eax
0x18000888a  jmp     short loc_180008862
0x18000888c  mov     ecx, edx
0x18000888e  xor     ecx, eax
0x180008890  and     ecx, 7E0h
0x180008896  xor     ecx, eax
0x180008898  or      ecx, 10h
0x18000889b  lock cmpxchg [rsi+4], ecx
0x1800088a0  jnz     loc_180008952
0x1800088a6  test    edi, edi
0x1800088a8  jz      loc_180008978
0x1800088ae  jmp     loc_1800087A9
0x1800088b3  cmp     ebx, 7; switch 8 cases
0x1800088b6  ja      def_1800088CD; jumptable 00000001800088CD default case, case 4
0x1800088bc  lea     rdx, __ImageBase
0x1800088c3  mov     ecx, ds:(jpt_1800088CD - 180000000h)[rdx+rbx*4]
0x1800088ca  add     rcx, rdx
0x1800088cd  jmp     rcx; switch jump
0x1800088cf  xor     edx, edx; jumptable 00000001800088CD cases 2,3,6,7
0x1800088d1  mov     ecx, ebx
0x1800088d3  sub     ecx, 2
0x1800088d6  jz      short loc_1800088FC
0x1800088d8  sub     ecx, 1
0x1800088db  jz      short loc_1800088F5
0x1800088dd  sub     ecx, 3
0x1800088e0  jz      short loc_1800088EE
0x1800088e2  cmp     ecx, 1
0x1800088e5  jnz     short loc_180008901
0x1800088e7  mov     edx, 10h
0x1800088ec  jmp     short loc_180008901
0x1800088ee  mov     edx, 4
0x1800088f3  jmp     short loc_180008901
0x1800088f5  mov     edx, 8
0x1800088fa  jmp     short loc_180008901
0x1800088fc  mov     edx, 2
0x180008901  mov     ecx, [rsi]
0x180008903  jmp     loc_180008862
0x180008908  test    r8b, 1
0x18000890c  setnz   dl
0x18000890f  test    cl, 1
0x180008912  setz    al
0x180008915  test    al, dl
0x180008917  mov     eax, 0
0x18000891c  setnz   al
0x18000891f  mov     dword ptr [rsp+78h+var_58], eax
0x180008923  jmp     loc_1800087A9
0x180008928  lea     r9, [rsp+78h+var_58]; jumptable 00000001800088CD cases 1,5
0x18000892d  mov     edx, ebx
0x18000892f  mov     rcx, rsi
0x180008932  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180008937  jmp     loc_1800087A5
0x18000893c  lea     r8d, [rbx-140h]; jumptable 00000001800088CD default case, case 4
0x180008943  cmp     r8d, 40h ; '@'
0x180008947  jge     short loc_180008974
0x180008949  mov     eax, [rsi+4]
0x18000894c  mov     edx, r8d
0x18000894f  shl     edx, 5
0x180008952  test    al, 10h
0x180008954  jz      short loc_18000896D
0x180008956  mov     ecx, eax
0x180008958  shr     ecx, 5
0x18000895b  and     ecx, 3Fh
0x18000895e  cmp     ecx, r8d
0x180008961  jnz     short loc_18000896D
0x180008963  mov     edi, 1
0x180008968  jmp     loc_18000888C
0x18000896d  xor     edi, edi
0x18000896f  jmp     loc_18000888C
0x180008974  mov     edi, dword ptr [rsp+78h+var_48]
0x180008978  mov     dword ptr [rsp+78h+var_58+8], ebx
0x18000897c  mov     dword ptr [rsp+78h+var_58+4], 1
0x180008984  jmp     loc_1800087A9
0x180008989  mov     r8d, 1
0x18000898f  mov     edx, ebx
0x180008991  mov     ecx, 1DD0303h
0x180008996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000899b  jmp     loc_1800087CD
0x1800089a0  mov     edx, ebx
0x1800089a2  mov     ecx, 1DD0303h; this
0x1800089a7  bts     edx, 1Fh
0x1800089ab  test    r15d, r15d
0x1800089ae  cmovz   edx, ebx; unsigned int
0x1800089b1  xor     r8d, r8d; unsigned int
0x1800089b4  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800089b9  jmp     loc_1800087F4
```
