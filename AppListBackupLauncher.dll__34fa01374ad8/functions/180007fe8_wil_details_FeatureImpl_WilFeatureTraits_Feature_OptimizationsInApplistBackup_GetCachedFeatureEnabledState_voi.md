# wil::details::FeatureImpl<__WilFeatureTraits_Feature_OptimizationsInApplistBackup>::GetCachedFeatureEnabledState(void)

- ea: `0x180007fe8`
- end: `0x1800081b5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_OptimizationsInApplistBackup@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e9a0`

## callees

- `0x180007854`
- `0x180007fe8`
- `0x18000d31c`
- `0x18000e904`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_OptimizationsInApplistBackup>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // si
  char IsEnabled; // al
  BOOL v11; // esi
  signed __int32 v12; // eax
  int v13; // esi
  bool v14; // zf
  signed __int32 v15; // edx
  int v16; // r8d
  int v17; // r9d
  signed __int32 v18; // ecx
  wil::details *v20; // [rsp+60h] [rbp+8h] BYREF

  v20 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_OptimizationsInApplistBackup__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_OptimizationsInApplistBackup__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(46406346, 3, &v20);
  }
  else
  {
    v6 = 0;
  }
  if ( (v6 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (v6 & 0xFFFFFF3F) == 2 )
      v7 = 64;
  }
  else
  {
    v7 = 64;
  }
  v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
LABEL_13:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_MercuryADEPTAppBackup>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MercuryADEPTAppBackup>::GetImpl'::`2'::impl);
    if ( v9 && !IsEnabled )
      v8 &= ~0x400u;
    goto LABEL_17;
  }
  v9 = 0;
  if ( (v8 & 0x40) != 0 )
    goto LABEL_13;
  IsEnabled = 0;
LABEL_17:
  v11 = (v8 & 0x40) != 0 && IsEnabled;
  v12 = *(_DWORD *)a2;
  v13 = v8 | v11;
  do
  {
    v14 = (_DWORD)v20 == 0;
    v15 = v12;
    *(_DWORD *)a2 = v12;
    if ( v14 || (v12 & 2) != 0 )
    {
      v16 = v12;
    }
    else
    {
      v16 = v12
          ^ (v12
           ^ v13)
          & 0x180
          ^ (v13
           ^ v12
           ^ (v12
            ^ v13)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v13
           ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v13
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v13)
                              & 0x180
                              ^ (v13
                               ^ v12
                               ^ (v12
                                ^ v13)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v13
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v16;
    }
    v17 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v18 = v16;
    }
    else
    {
      v18 = v16 ^ ((unsigned __int16)v16 ^ (unsigned __int16)v13) & 0x400 | 4;
      *(_DWORD *)a2 = v18;
    }
    v12 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_OptimizationsInApplistBackup__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      Feature_OptimizationsInApplistBackup__descriptor,
      3,
      v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (v13
                    ^ *(_DWORD *)a2)
                   & 0x180
                   ^ (v13
                    ^ *(_DWORD *)a2
                    ^ (v13
                     ^ *(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v13
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v13
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v13
                     ^ *(_WORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v13
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v13
                      ^ *(_WORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v13
                       ^ *(_BYTE *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x180007fe8  mov     [rsp+arg_0], rcx
0x180007fed  push    rbx
0x180007fee  push    rbp
0x180007fef  push    rsi
0x180007ff0  push    rdi
0x180007ff1  push    r12
0x180007ff3  push    r14
0x180007ff5  sub     rsp, 28h
0x180007ff9  mov     r14, cs:Feature_OptimizationsInApplistBackup__descriptor
0x180008000  mov     rdi, rdx
0x180008003  mov     qword ptr [rdx], 0
0x18000800a  mov     eax, [r14]
0x18000800d  mov     [rdx], eax
0x18000800f  and     eax, 6
0x180008012  cmp     al, 6
0x180008014  jz      loc_1800081A5
0x18000801a  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000801f  mov     ebp, eax
0x180008021  mov     dword ptr [rsp+58h+arg_0], 0
0x180008029  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180008030  test    rax, rax
0x180008033  jz      short loc_18000804D
0x180008035  lea     r8, [rsp+58h+arg_0]
0x18000803a  mov     edx, 3
0x18000803f  mov     ecx, 2C41ACAh
0x180008044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008049  mov     edx, eax
0x18000804b  jmp     short loc_18000805B
0x18000804d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180008054  test    rax, rax
0x180008057  jnz     short loc_180008035
0x180008059  xor     edx, edx
0x18000805b  mov     r8d, edx
0x18000805e  mov     eax, edx
0x180008060  and     r8d, 0FFFFFF3Fh
0x180008067  and     edx, 80h
0x18000806d  mov     ecx, r8d
0x180008070  mov     r12d, 40h ; '@'
0x180008076  and     ecx, 3
0x180008079  and     eax, r12d
0x18000807c  shl     ecx, 2
0x18000807f  or      ecx, eax
0x180008081  shl     ecx, 2
0x180008084  or      ecx, edx
0x180008086  lea     ebx, ds:0[rcx*8]
0x18000808d  test    r8d, r8d
0x180008090  jnz     short loc_180008097
0x180008092  mov     eax, r12d
0x180008095  jmp     short loc_1800080A1
0x180008097  xor     eax, eax
0x180008099  cmp     r8d, 2
0x18000809d  cmovz   eax, r12d
0x1800080a1  or      ebx, eax
0x1800080a3  mov     ecx, 0C00h
0x1800080a8  mov     eax, ebx
0x1800080aa  and     eax, ecx
0x1800080ac  cmp     eax, ecx
0x1800080ae  jnz     short loc_1800080B5
0x1800080b0  mov     sil, 1
0x1800080b3  jmp     short loc_1800080BD
0x1800080b5  xor     sil, sil
0x1800080b8  test    r12b, bl
0x1800080bb  jz      short loc_1800080D8
0x1800080bd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MercuryADEPTAppBackup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MercuryADEPTAppBackup@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MercuryADEPTAppBackup> `wil::Feature<__WilFeatureTraits_Feature_MercuryADEPTAppBackup>::GetImpl(void)'::`2'::impl
0x1800080c4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MercuryADEPTAppBackup@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MercuryADEPTAppBackup>::__private_IsEnabled(wil::ReportingKind)
0x1800080c9  test    sil, sil
0x1800080cc  jz      short loc_1800080DA
0x1800080ce  test    al, al
0x1800080d0  jnz     short loc_1800080DA
0x1800080d2  btr     ebx, 0Ah
0x1800080d6  jmp     short loc_1800080DA
0x1800080d8  xor     al, al
0x1800080da  test    r12b, bl
0x1800080dd  jz      short loc_1800080EA
0x1800080df  test    al, al
0x1800080e1  jz      short loc_1800080EA
0x1800080e3  mov     esi, 1
0x1800080e8  jmp     short loc_1800080EC
0x1800080ea  xor     esi, esi
0x1800080ec  mov     eax, [rdi]
0x1800080ee  or      esi, ebx
0x1800080f0  mov     ebx, 180h
0x1800080f5  cmp     dword ptr [rsp+58h+arg_0], 0
0x1800080fa  mov     edx, eax
0x1800080fc  mov     [rdi], eax
0x1800080fe  jz      short loc_180008138
0x180008100  test    dl, 2
0x180008103  jnz     short loc_180008138
0x180008105  mov     eax, esi
0x180008107  xor     eax, edx
0x180008109  and     eax, ebx
0x18000810b  xor     eax, edx
0x18000810d  mov     ecx, eax
0x18000810f  xor     ecx, esi
0x180008111  and     ecx, r12d
0x180008114  xor     ecx, eax
0x180008116  mov     eax, ecx
0x180008118  xor     eax, esi
0x18000811a  and     eax, 1
0x18000811d  xor     eax, ecx
0x18000811f  mov     r8d, eax
0x180008122  xor     r8d, esi
0x180008125  and     r8d, 800h
0x18000812c  xor     r8d, eax
0x18000812f  or      r8d, 2
0x180008133  mov     [rdi], r8d
0x180008136  jmp     short loc_18000813B
0x180008138  mov     r8d, edx
0x18000813b  mov     r9d, edx
0x18000813e  and     r9d, 4
0x180008142  jnz     short loc_180008159
0x180008144  mov     ecx, esi
0x180008146  xor     ecx, r8d
0x180008149  and     ecx, 400h
0x18000814f  xor     ecx, r8d
0x180008152  or      ecx, 4
0x180008155  mov     [rdi], ecx
0x180008157  jmp     short loc_18000815C
0x180008159  mov     ecx, r8d
0x18000815c  mov     eax, edx
0x18000815e  lock cmpxchg [r14], ecx
0x180008163  jnz     short loc_1800080F5
0x180008165  test    r9d, r9d
0x180008168  jnz     short loc_180008179
0x18000816a  mov     r8d, ebp
0x18000816d  lea     edx, [r9+3]
0x180008171  mov     rcx, r14
0x180008174  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008179  test    byte ptr [rdi], 2
0x18000817c  jnz     short loc_1800081A5
0x18000817e  mov     eax, [rdi]
0x180008180  xor     eax, esi
0x180008182  and     eax, ebx
0x180008184  xor     eax, [rdi]
0x180008186  mov     ecx, eax
0x180008188  xor     ecx, esi
0x18000818a  and     ecx, r12d
0x18000818d  xor     ecx, eax
0x18000818f  mov     edx, ecx
0x180008191  xor     edx, esi
0x180008193  and     edx, 1
0x180008196  xor     edx, ecx
0x180008198  mov     eax, edx
0x18000819a  xor     eax, esi
0x18000819c  and     eax, 800h
0x1800081a1  xor     eax, edx
0x1800081a3  mov     [rdi], eax
0x1800081a5  mov     rax, rdi
0x1800081a8  add     rsp, 28h
0x1800081ac  pop     r14
0x1800081ae  pop     r12
0x1800081b0  pop     rdi
0x1800081b1  pop     rsi
0x1800081b2  pop     rbp
0x1800081b3  pop     rbx
0x1800081b4  retn
```
