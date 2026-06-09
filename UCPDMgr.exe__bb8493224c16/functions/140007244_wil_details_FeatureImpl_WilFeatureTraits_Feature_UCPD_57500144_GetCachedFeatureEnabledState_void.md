# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_57500144>::GetCachedFeatureEnabledState(void)

- ea: `0x140007244`
- end: `0x1400073d4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_57500144@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000567c`
- `0x1400073dc`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140007244`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_57500144>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v5; // ebp
  __int64 (__fastcall *v6)(__int64, _QWORD, int *); // rax
  int v7; // eax
  unsigned int v8; // r8d
  int v9; // ecx
  int v10; // eax
  unsigned int v11; // eax
  int v12; // ebx
  signed __int32 v13; // eax
  bool v14; // zf
  signed __int32 v15; // edx
  signed __int32 v16; // ecx
  int v17; // ecx
  int v19; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v3 & 6) == 6 )
    return a2;
  v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v19 = 0;
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v7 = v6(57500144, 0, &v19);
    v8 = v7 & 0xFFFFFF3F;
    v9 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
    if ( (v7 & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
      v11 = v9 | v10;
      goto LABEL_10;
    }
  }
  else
  {
    v9 = 0;
  }
  v11 = v9;
LABEL_10:
  v12 = v11 | (v11 >> 6) & 1;
  if ( !v5 )
    v19 = 0;
  v13 = *(_DWORD *)a2;
  do
  {
    v14 = v19 == 0;
    v15 = v13;
    *(_DWORD *)a2 = v13;
    v16 = v13;
    if ( !v14 && (v13 & 2) == 0 )
    {
      v17 = v13
          ^ ((unsigned __int16)v13
           ^ (unsigned __int16)v12)
          & 0x180
          ^ (v12
           ^ v13
           ^ ((unsigned __int16)v13
            ^ (unsigned __int16)v12)
           & 0x180)
          & 0x40;
      v16 = v17
          ^ ((unsigned __int8)v12
           ^ (unsigned __int8)v17)
          & 1
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)(v17 ^ ((unsigned __int8)v12 ^ (unsigned __int8)v17) & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v16;
    }
    if ( (v13 & 4) == 0 )
    {
      v16 = ((unsigned __int16)v16 ^ (unsigned __int16)v12) & 0x400 ^ v16 | 4;
      *(_DWORD *)a2 = v16;
    }
    v13 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v16, v13);
  }
  while ( v15 != v13 );
  if ( (v15 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(a1, 0, v5);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (*(_DWORD *)a2
                    ^ v12)
                   & 0x180
                   ^ (v12
                    ^ *(_DWORD *)a2
                    ^ (*(_DWORD *)a2
                     ^ v12)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v12
                    ^ *(_BYTE *)a2
                    ^ (*(_BYTE *)a2
                     ^ (unsigned __int8)v12)
                    & 0x80
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v12)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v12
                    ^ *(_WORD *)a2
                    ^ (*(_WORD *)a2
                     ^ (unsigned __int16)v12)
                    & 0x180
                    ^ ((unsigned __int16)v12
                     ^ *(_WORD *)a2
                     ^ (*(_WORD *)a2
                      ^ (unsigned __int16)v12)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v12)
                     & 0x80
                     ^ ((unsigned __int8)v12
                      ^ *(_BYTE *)a2
                      ^ (*(_BYTE *)a2
                       ^ (unsigned __int8)v12)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x140007244  mov     [rsp+arg_10], rbx
0x140007249  mov     [rsp+arg_18], rbp
0x14000724e  push    rsi
0x14000724f  push    rdi
0x140007250  push    r15
0x140007252  sub     rsp, 30h
0x140007256  mov     rax, cs:__security_cookie
0x14000725d  xor     rax, rsp
0x140007260  mov     [rsp+48h+var_20], rax
0x140007265  mov     qword ptr [rdx], 0
0x14000726c  mov     rdi, rdx
0x14000726f  mov     eax, [rcx]
0x140007271  mov     rsi, rcx
0x140007274  mov     [rdx], eax
0x140007276  and     eax, 6
0x140007279  cmp     al, 6
0x14000727b  jz      loc_1400073B1
0x140007281  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140007286  mov     ebp, eax
0x140007288  mov     [rsp+48h+var_28], 0
0x140007290  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140007297  mov     r15d, 40h ; '@'
0x14000729d  test    rax, rax
0x1400072a0  jnz     short loc_1400072AE
0x1400072a2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1400072a9  test    rax, rax
0x1400072ac  jz      short loc_1400072FA
0x1400072ae  lea     r8, [rsp+48h+var_28]
0x1400072b3  xor     edx, edx
0x1400072b5  mov     ecx, 36D61F0h
0x1400072ba  call    _guard_dispatch_icall
0x1400072bf  mov     r8d, eax
0x1400072c2  mov     edx, eax
0x1400072c4  and     r8d, 0FFFFFF3Fh
0x1400072cb  and     eax, r15d
0x1400072ce  and     edx, 80h
0x1400072d4  mov     ecx, r8d
0x1400072d7  and     ecx, 3
0x1400072da  shl     ecx, 2
0x1400072dd  or      ecx, eax
0x1400072df  shl     ecx, 2
0x1400072e2  or      ecx, edx
0x1400072e4  shl     ecx, 3
0x1400072e7  test    r8d, r8d
0x1400072ea  jz      short loc_1400072FC
0x1400072ec  xor     eax, eax
0x1400072ee  cmp     r8d, 2
0x1400072f2  cmovz   eax, r15d
0x1400072f6  or      eax, ecx
0x1400072f8  jmp     short loc_1400072FE
0x1400072fa  xor     ecx, ecx
0x1400072fc  mov     eax, ecx
0x1400072fe  mov     ebx, eax
0x140007300  shr     ebx, 6
0x140007303  and     ebx, 1
0x140007306  or      ebx, eax
0x140007308  test    ebp, ebp
0x14000730a  jnz     short loc_140007310
0x14000730c  mov     [rsp+48h+var_28], ebp
0x140007310  mov     eax, [rdi]
0x140007312  cmp     [rsp+48h+var_28], 0
0x140007317  mov     edx, eax
0x140007319  mov     [rdi], eax
0x14000731b  mov     ecx, eax
0x14000731d  jz      short loc_140007352
0x14000731f  test    dl, 2
0x140007322  jnz     short loc_140007352
0x140007324  mov     eax, ebx
0x140007326  xor     eax, ecx
0x140007328  and     eax, 180h
0x14000732d  xor     eax, ecx
0x14000732f  mov     ecx, eax
0x140007331  xor     ecx, ebx
0x140007333  and     ecx, r15d
0x140007336  xor     ecx, eax
0x140007338  mov     eax, ecx
0x14000733a  xor     eax, ebx
0x14000733c  and     eax, 1
0x14000733f  xor     eax, ecx
0x140007341  mov     ecx, eax
0x140007343  xor     ecx, ebx
0x140007345  and     ecx, 800h
0x14000734b  xor     ecx, eax
0x14000734d  or      ecx, 2
0x140007350  mov     [rdi], ecx
0x140007352  test    dl, 4
0x140007355  jnz     short loc_140007367
0x140007357  mov     eax, ebx
0x140007359  xor     eax, ecx
0x14000735b  and     eax, 400h
0x140007360  xor     ecx, eax
0x140007362  or      ecx, 4
0x140007365  mov     [rdi], ecx
0x140007367  mov     eax, edx
0x140007369  lock cmpxchg [rsi], ecx
0x14000736d  jnz     short loc_140007312
0x14000736f  test    dl, 4
0x140007372  jnz     short loc_140007381
0x140007374  mov     r8d, ebp
0x140007377  xor     edx, edx
0x140007379  mov     rcx, rsi
0x14000737c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140007381  test    byte ptr [rdi], 2
0x140007384  jnz     short loc_1400073B1
0x140007386  mov     eax, ebx
0x140007388  xor     eax, [rdi]
0x14000738a  and     eax, 180h
0x14000738f  xor     eax, [rdi]
0x140007391  mov     ecx, eax
0x140007393  xor     ecx, ebx
0x140007395  and     ecx, r15d
0x140007398  xor     ecx, eax
0x14000739a  mov     edx, ecx
0x14000739c  xor     edx, ebx
0x14000739e  and     edx, 1
0x1400073a1  xor     edx, ecx
0x1400073a3  mov     ecx, edx
0x1400073a5  xor     ecx, ebx
0x1400073a7  and     ecx, 800h
0x1400073ad  xor     ecx, edx
0x1400073af  mov     [rdi], ecx
0x1400073b1  mov     rax, rdi
0x1400073b4  mov     rcx, [rsp+48h+var_20]
0x1400073b9  xor     rcx, rsp; StackCookie
0x1400073bc  call    __security_check_cookie
0x1400073c1  mov     rbx, [rsp+48h+arg_10]
0x1400073c6  mov     rbp, [rsp+48h+arg_18]
0x1400073cb  add     rsp, 30h
0x1400073cf  pop     r15
0x1400073d1  pop     rdi
0x1400073d2  pop     rsi
0x1400073d3  retn
```
