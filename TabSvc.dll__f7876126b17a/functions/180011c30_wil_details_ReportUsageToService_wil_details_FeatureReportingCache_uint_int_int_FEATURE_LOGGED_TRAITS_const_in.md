# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180011c30`
- end: `0x180012050`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `1056`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `18`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011ae0`
- `0x180019c78`
- `0x180019d04`
- `0x180021da0`
- `0x180021ef4`
- `0x180022048`
- `0x180022288`
- `0x1800223b4`
- `0x180025350`
- `0x1800253dc`
- `0x180025460`
- `0x1800254ec`
- `0x180025574`
- `0x1800255fc`
- `0x180025684`
- `0x18002570c`
- `0x180025794`
- `0x18002dec8`

## callees

- `0x180011c30`
- `0x180014624`
- `0x180017fe0`
- `0x18001fee8`
- `0x180027f54`
- `0x18002b97c`
- `0x180031010`

## pseudocode

```c
void __fastcall wil::details::ReportUsageToService(
        volatile signed __int32 *a1,
        unsigned int a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        unsigned __int8 a8)
{
  int v12; // r10d
  unsigned int v13; // r9d
  int v14; // r15d
  unsigned int v15; // r15d
  __int64 v16; // rcx
  unsigned __int8 v17; // dl
  BOOL v18; // r14d
  unsigned int v19; // r8d
  unsigned __int32 v20; // eax
  unsigned __int32 v21; // ett
  signed __int32 i; // ecx
  signed __int32 v23; // edx
  signed __int32 v24; // eax
  unsigned int v25; // edx
  const char *v26; // [rsp+20h] [rbp-68h]
  unsigned int v27[4]; // [rsp+50h] [rbp-38h] BYREF
  _BOOL8 v28; // [rsp+60h] [rbp-28h]

  if ( a7 )
  {
    v12 = 4;
    v13 = 2;
    switch ( a7 )
    {
      case 3:
        v15 = 6;
        if ( a6 )
          v15 = 2;
        break;
      case 1:
        v15 = 0;
        if ( !a6 )
          v15 = 4;
        break;
      case 2:
        v15 = 1;
        if ( !a6 )
          v15 = 5;
        break;
      case 4:
        v15 = 3;
        if ( !a6 )
          v15 = 7;
        break;
      case 5:
        v15 = 8;
        if ( !a6 )
          v15 = 10;
        break;
      case 6:
        v15 = 9;
        if ( !a6 )
          v15 = 11;
        break;
      default:
        if ( (unsigned __int8)(a7 - 100) > 0x31u )
        {
          v15 = 255;
        }
        else
        {
          v14 = 100;
          if ( !a6 )
            v14 = 150;
          v15 = (unsigned __int8)(a7 - 100) + v14;
        }
        break;
    }
    v16 = a5;
    v28 = 0;
    *(_OWORD *)v27 = 0;
    v17 = *(_BYTE *)(a5 + 4);
    a8 = v17;
    if ( v15 == 7 )
    {
LABEL_35:
      v12 = 0;
      switch ( v15 )
      {
        case 2u:
          v12 = 2;
          break;
        case 3u:
          v12 = 8;
          break;
        case 7u:
          v12 = 16;
          break;
      }
LABEL_52:
      for ( i = *a1; ; i = v24 )
      {
        v18 = (i | v12) == i;
        v23 = i | v12 | 1;
        if ( (i | v12) == i )
          v23 = i | v12;
        v24 = _InterlockedCompareExchange(a1, v23, i);
        if ( i == v24 )
          break;
      }
      if ( (v23 & 1) == 0 || (v27[0] = 1, (i & 1) != 0) )
        v27[0] = 0;
LABEL_60:
      v17 = a8;
      v16 = a5;
    }
    else
    {
      switch ( v15 )
      {
        case 0u:
        case 4u:
          wil_details_FeatureReporting_IncrementUsageInCache(a1, v15, &_ImageBase, v27);
          v18 = v28;
          goto LABEL_60;
        case 1u:
        case 5u:
          wil_details_FeatureReporting_IncrementOpportunityInCache(a1, v15, &_ImageBase, v27);
          v18 = v28;
          goto LABEL_60;
        case 2u:
        case 3u:
        case 6u:
          if ( v15 != 6 )
            goto LABEL_35;
          goto LABEL_52;
        default:
          v19 = v15 - 320;
          if ( (int)(v15 - 320) >= 64 )
          {
            v18 = v28;
LABEL_49:
            v27[2] = v15;
            v27[1] = 1;
            break;
          }
          v20 = *((_DWORD *)a1 + 1);
          do
          {
            v18 = (v20 & 0x10) != 0 && ((v20 >> 5) & 0x3F) == v19;
            v21 = v20;
            v20 = _InterlockedCompareExchange(
                    a1 + 1,
                    v20 ^ ((unsigned __int16)v20 ^ (unsigned __int16)(32 * v19)) & 0x7E0 | 0x10,
                    v20);
          }
          while ( v21 != v20 );
          v16 = a5;
          v17 = a8;
          if ( !v18 )
            goto LABEL_49;
          break;
      }
    }
    if ( g_wil_details_RecordSRUMFeatureUsage )
    {
      if ( !v15 || v15 - 100 <= 0x31 )
      {
        g_wil_details_RecordSRUMFeatureUsage(a2, v15, 1);
        v17 = a8;
      }
      v16 = a5;
    }
    if ( v27[0] )
    {
      wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        (char *)&wil::details::g_enabledStateManager,
        a2,
        (struct wil_details_FeatureReportingCache *)a1);
      v16 = a5;
      v17 = a8;
    }
    if ( v27[1] )
    {
      wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v27[2], v27[1], v13, v26);
      v16 = a5;
      v17 = a8;
    }
    if ( !v18 )
    {
      wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
        (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
        (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
      v16 = a5;
      v17 = a8;
    }
    if ( a3 )
    {
      v25 = v15 | 0x80000000;
      if ( !a4 )
        v25 = v15;
      wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v25, 0, v13, v26);
      v16 = a5;
      v17 = a8;
    }
    if ( !v18 )
    {
      if ( g_wil_details_realtimeFeatureUsageHook )
      {
        g_wil_details_realtimeFeatureUsageHook(a2, v15, v17);
        v16 = a5;
      }
      if ( g_wil_details_pfnFeatureLoggingHook )
        g_wil_details_pfnFeatureLoggingHook(a2, v16, 0, a6, &a7, 0, 0, 1);
    }
  }
}

```

## disassembly

```asm
0x180011c30  mov     rax, rsp
0x180011c33  mov     [rax+20h], rbx
0x180011c37  push    rbp
0x180011c38  push    rsi
0x180011c39  push    rdi
0x180011c3a  sub     rsp, 70h
0x180011c3e  mov     r11d, [rax+38h]
0x180011c42  mov     esi, r9d
0x180011c45  mov     edi, r8d
0x180011c48  mov     ebp, edx
0x180011c4a  mov     rbx, rcx
0x180011c4d  test    r11d, r11d
0x180011c50  jz      loc_180012024
0x180011c56  mov     [rax+8], r13
0x180011c5a  mov     r10d, 4
0x180011c60  mov     r13d, [rsp+88h+arg_28]
0x180011c68  mov     r9d, 2
0x180011c6e  mov     [rax+10h], r14
0x180011c72  mov     [rax+18h], r15
0x180011c76  cmp     r11d, 3
0x180011c7a  jz      loc_180011D32
0x180011c80  test    r11d, r11d
0x180011c83  jz      loc_180011D2A
0x180011c89  mov     ecx, r11d
0x180011c8c  sub     ecx, 1
0x180011c8f  jz      loc_180011D1E
0x180011c95  sub     ecx, 1
0x180011c98  jz      short loc_180011D0A
0x180011c9a  sub     ecx, r9d
0x180011c9d  jz      short loc_180011CF6
0x180011c9f  sub     ecx, 1
0x180011ca2  jz      short loc_180011CE2
0x180011ca4  cmp     ecx, 1
0x180011ca7  jz      short loc_180011CCE
0x180011ca9  sub     r11b, 64h ; 'd'
0x180011cad  cmp     r11b, 31h ; '1'
0x180011cb1  ja      short loc_180011D2A
0x180011cb3  test    r13d, r13d
0x180011cb6  mov     eax, 96h
0x180011cbb  mov     r15d, 64h ; 'd'
0x180011cc1  cmovz   r15d, eax
0x180011cc5  movzx   eax, r11b
0x180011cc9  add     r15d, eax
0x180011ccc  jmp     short loc_180011D3F
0x180011cce  test    r13d, r13d
0x180011cd1  mov     eax, 0Bh
0x180011cd6  mov     r15d, 9
0x180011cdc  cmovz   r15d, eax
0x180011ce0  jmp     short loc_180011D3F
0x180011ce2  test    r13d, r13d
0x180011ce5  mov     eax, 0Ah
0x180011cea  mov     r15d, 8
0x180011cf0  cmovz   r15d, eax
0x180011cf4  jmp     short loc_180011D3F
0x180011cf6  test    r13d, r13d
0x180011cf9  mov     eax, 7
0x180011cfe  mov     r15d, 3
0x180011d04  cmovz   r15d, eax
0x180011d08  jmp     short loc_180011D3F
0x180011d0a  test    r13d, r13d
0x180011d0d  mov     eax, 5
0x180011d12  mov     r15d, 1
0x180011d18  cmovz   r15d, eax
0x180011d1c  jmp     short loc_180011D3F
0x180011d1e  xor     r15d, r15d
0x180011d21  test    r13d, r13d
0x180011d24  cmovz   r15d, r10d
0x180011d28  jmp     short loc_180011D3F
0x180011d2a  mov     r15d, 0FFh
0x180011d30  jmp     short loc_180011D3F
0x180011d32  test    r13d, r13d
0x180011d35  mov     r15d, 6
0x180011d3b  cmovnz  r15d, r9d
0x180011d3f  mov     rcx, [rsp+88h+arg_20]
0x180011d47  xor     eax, eax
0x180011d49  mov     [rsp+88h+var_28], rax
0x180011d4e  xorps   xmm0, xmm0
0x180011d51  movups  xmmword ptr [rsp+88h+var_38], xmm0
0x180011d56  movzx   edx, byte ptr [rcx+4]
0x180011d5a  mov     [rsp+88h+arg_38], dl
0x180011d61  cmp     r15d, 7
0x180011d65  jz      short loc_180011DC6
0x180011d67  cmp     r15d, 6; switch 7 cases
0x180011d6b  ja      def_180011D86; jumptable 0000000180011D86 default case
0x180011d71  lea     r8, __ImageBase
0x180011d78  movsxd  rax, r15d
0x180011d7b  mov     ecx, ds:(jpt_180011D86 - 180000000h)[r8+rax*4]
0x180011d83  add     rcx, r8
0x180011d86  jmp     rcx; switch jump
0x180011d88  lea     r9, [rsp+88h+var_38]; jumptable 0000000180011D86 cases 0,4
0x180011d8d  mov     edx, r15d
0x180011d90  mov     rcx, rbx
0x180011d93  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180011d98  mov     r14d, dword ptr [rsp+88h+var_28]
0x180011d9d  jmp     loc_180011EB9
0x180011da2  lea     r9, [rsp+88h+var_38]; jumptable 0000000180011D86 cases 1,5
0x180011da7  mov     edx, r15d
0x180011daa  mov     rcx, rbx
0x180011dad  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180011db2  mov     r14d, dword ptr [rsp+88h+var_28]
0x180011db7  jmp     loc_180011EB9
0x180011dbc  cmp     r15d, 6; jumptable 0000000180011D86 cases 2,3,6
0x180011dc0  jz      loc_180011E78
0x180011dc6  xor     r10d, r10d
0x180011dc9  mov     ecx, r15d
0x180011dcc  sub     ecx, r9d
0x180011dcf  jz      loc_180011E75
0x180011dd5  sub     ecx, 1
0x180011dd8  jz      loc_180011E6D
0x180011dde  cmp     ecx, 4
0x180011de1  jnz     loc_180011E78
0x180011de7  mov     r10d, 10h
0x180011ded  jmp     loc_180011E78
0x180011df2  mov     rcx, [rsp+88h+arg_20]
0x180011dfa  lea     r8d, [r15-140h]; jumptable 0000000180011D86 default case
0x180011e01  cmp     r8d, 40h ; '@'
0x180011e05  jge     short loc_180011E59
0x180011e07  mov     eax, [rbx+4]
0x180011e0a  mov     edx, r8d
0x180011e0d  shl     edx, 5
0x180011e10  test    al, 10h
0x180011e12  jz      short loc_180011E29
0x180011e14  mov     ecx, eax
0x180011e16  shr     ecx, 5
0x180011e19  and     ecx, 3Fh
0x180011e1c  cmp     ecx, r8d
0x180011e1f  jnz     short loc_180011E29
0x180011e21  mov     r14d, 1
0x180011e27  jmp     short loc_180011E2C
0x180011e29  xor     r14d, r14d
0x180011e2c  mov     ecx, edx
0x180011e2e  xor     ecx, eax
0x180011e30  and     ecx, 7E0h
0x180011e36  xor     ecx, eax
0x180011e38  or      ecx, 10h
0x180011e3b  lock cmpxchg [rbx+4], ecx
0x180011e40  jnz     short loc_180011E10
0x180011e42  mov     rcx, [rsp+88h+arg_20]
0x180011e4a  movzx   edx, [rsp+88h+arg_38]
0x180011e52  test    r14d, r14d
0x180011e55  jnz     short loc_180011EC9
0x180011e57  jmp     short loc_180011E5E
0x180011e59  mov     r14d, dword ptr [rsp+88h+var_28]
0x180011e5e  mov     [rsp+88h+var_38+8], r15d
0x180011e63  mov     [rsp+88h+var_38+4], 1
0x180011e6b  jmp     short loc_180011EC9
0x180011e6d  mov     r10d, 8
0x180011e73  jmp     short loc_180011E78
0x180011e75  mov     r10d, r9d
0x180011e78  mov     ecx, [rbx]
0x180011e7a  xor     r14d, r14d
0x180011e7d  mov     eax, r10d
0x180011e80  or      eax, ecx
0x180011e82  cmp     eax, ecx
0x180011e84  mov     edx, eax
0x180011e86  setz    r14b
0x180011e8a  or      edx, 1
0x180011e8d  test    r14d, r14d
0x180011e90  cmovnz  edx, eax
0x180011e93  mov     eax, ecx
0x180011e95  lock cmpxchg [rbx], edx
0x180011e99  jz      short loc_180011E9F
0x180011e9b  mov     ecx, eax
0x180011e9d  jmp     short loc_180011E7A
0x180011e9f  test    dl, 1
0x180011ea2  jz      short loc_180011EB1
0x180011ea4  mov     [rsp+88h+var_38], 1
0x180011eac  test    cl, 1
0x180011eaf  jz      short loc_180011EB9
0x180011eb1  mov     [rsp+88h+var_38], 0
0x180011eb9  movzx   edx, [rsp+88h+arg_38]
0x180011ec1  mov     rcx, [rsp+88h+arg_20]
0x180011ec9  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180011ed0  test    rax, rax
0x180011ed3  jz      short loc_180011F03
0x180011ed5  test    r15d, r15d
0x180011ed8  jz      short loc_180011EE3
0x180011eda  lea     ecx, [r15-64h]
0x180011ede  cmp     ecx, 31h ; '1'
0x180011ee1  ja      short loc_180011EFB
0x180011ee3  mov     r8d, 1
0x180011ee9  mov     edx, r15d
0x180011eec  mov     ecx, ebp
0x180011eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ef3  movzx   edx, [rsp+88h+arg_38]
0x180011efb  mov     rcx, [rsp+88h+arg_20]
0x180011f03  cmp     [rsp+88h+var_38], 0
0x180011f08  jz      short loc_180011F2B
0x180011f0a  mov     r8, rbx; struct wil_details_FeatureReportingCache *
0x180011f0d  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180011f14  mov     edx, ebp; unsigned int
0x180011f16  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180011f1b  mov     rcx, [rsp+88h+arg_20]
0x180011f23  movzx   edx, [rsp+88h+arg_38]
0x180011f2b  cmp     [rsp+88h+var_38+4], 0
0x180011f30  jbe     short loc_180011F52
0x180011f32  mov     r8d, [rsp+88h+var_38+4]; unsigned int
0x180011f37  mov     ecx, ebp; this
0x180011f39  mov     edx, [rsp+88h+var_38+8]; unsigned int
0x180011f3d  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180011f42  mov     rcx, [rsp+88h+arg_20]
0x180011f4a  movzx   edx, [rsp+88h+arg_38]
0x180011f52  test    r14d, r14d
0x180011f55  jnz     short loc_180011F7A
0x180011f57  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180011f5e  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180011f65  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180011f6a  mov     rcx, [rsp+88h+arg_20]
0x180011f72  movzx   edx, [rsp+88h+arg_38]
0x180011f7a  test    edi, edi
0x180011f7c  jz      short loc_180011FA5
0x180011f7e  mov     edx, r15d
0x180011f81  mov     ecx, ebp; this
0x180011f83  bts     edx, 1Fh
0x180011f87  test    esi, esi
0x180011f89  cmovz   edx, r15d; unsigned int
0x180011f8d  xor     r8d, r8d; unsigned int
0x180011f90  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180011f95  mov     rcx, [rsp+88h+arg_20]
0x180011f9d  movzx   edx, [rsp+88h+arg_38]
0x180011fa5  test    r14d, r14d
0x180011fa8  mov     r14, [rsp+88h+arg_8]
0x180011fb0  jnz     short loc_180012014
0x180011fb2  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180011fb9  test    rax, rax
0x180011fbc  jz      short loc_180011FD4
0x180011fbe  movzx   r8d, dl
0x180011fc2  mov     ecx, ebp
0x180011fc4  mov     edx, r15d
0x180011fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fcc  mov     rcx, [rsp+88h+arg_20]
0x180011fd4  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180011fdb  test    rax, rax
0x180011fde  jz      short loc_180012014
0x180011fe0  mov     [rsp+88h+var_50], 1
0x180011fe9  lea     rdx, [rsp+88h+arg_30]
0x180011ff1  mov     [rsp+88h+var_58], 0
0x180011ff6  mov     r9d, r13d
0x180011ff9  mov     [rsp+88h+var_60], 0
0x180012002  xor     r8d, r8d
0x180012005  mov     [rsp+88h+var_68], rdx
0x18001200a  mov     rdx, rcx
0x18001200d  mov     ecx, ebp
0x18001200f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012014  mov     r13, [rsp+88h+arg_0]
0x18001201c  mov     r15, [rsp+88h+arg_10]
0x180012024  mov     rbx, [rsp+88h+arg_18]
0x18001202c  add     rsp, 70h
0x180012030  pop     rdi
0x180012031  pop     rsi
0x180012032  pop     rbp
0x180012033  retn
```
