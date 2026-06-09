# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_57302880>::GetCachedFeatureEnabledState(void)

- ea: `0x140007014`
- end: `0x1400071a4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_57302880@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005640`
- `0x1400071ac`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140007014`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_57302880>::GetCachedFeatureEnabledState(
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
    v7 = v6(57302880, 0, &v19);
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
0x140007014  mov     [rsp+arg_10], rbx
0x140007019  mov     [rsp+arg_18], rbp
0x14000701e  push    rsi
0x14000701f  push    rdi
0x140007020  push    r15
0x140007022  sub     rsp, 30h
0x140007026  mov     rax, cs:__security_cookie
0x14000702d  xor     rax, rsp
0x140007030  mov     [rsp+48h+var_20], rax
0x140007035  mov     qword ptr [rdx], 0
0x14000703c  mov     rdi, rdx
0x14000703f  mov     eax, [rcx]
0x140007041  mov     rsi, rcx
0x140007044  mov     [rdx], eax
0x140007046  and     eax, 6
0x140007049  cmp     al, 6
0x14000704b  jz      loc_140007181
0x140007051  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140007056  mov     ebp, eax
0x140007058  mov     [rsp+48h+var_28], 0
0x140007060  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140007067  mov     r15d, 40h ; '@'
0x14000706d  test    rax, rax
0x140007070  jnz     short loc_14000707E
0x140007072  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140007079  test    rax, rax
0x14000707c  jz      short loc_1400070CA
0x14000707e  lea     r8, [rsp+48h+var_28]
0x140007083  xor     edx, edx
0x140007085  mov     ecx, 36A5F60h
0x14000708a  call    _guard_dispatch_icall
0x14000708f  mov     r8d, eax
0x140007092  mov     edx, eax
0x140007094  and     r8d, 0FFFFFF3Fh
0x14000709b  and     eax, r15d
0x14000709e  and     edx, 80h
0x1400070a4  mov     ecx, r8d
0x1400070a7  and     ecx, 3
0x1400070aa  shl     ecx, 2
0x1400070ad  or      ecx, eax
0x1400070af  shl     ecx, 2
0x1400070b2  or      ecx, edx
0x1400070b4  shl     ecx, 3
0x1400070b7  test    r8d, r8d
0x1400070ba  jz      short loc_1400070CC
0x1400070bc  xor     eax, eax
0x1400070be  cmp     r8d, 2
0x1400070c2  cmovz   eax, r15d
0x1400070c6  or      eax, ecx
0x1400070c8  jmp     short loc_1400070CE
0x1400070ca  xor     ecx, ecx
0x1400070cc  mov     eax, ecx
0x1400070ce  mov     ebx, eax
0x1400070d0  shr     ebx, 6
0x1400070d3  and     ebx, 1
0x1400070d6  or      ebx, eax
0x1400070d8  test    ebp, ebp
0x1400070da  jnz     short loc_1400070E0
0x1400070dc  mov     [rsp+48h+var_28], ebp
0x1400070e0  mov     eax, [rdi]
0x1400070e2  cmp     [rsp+48h+var_28], 0
0x1400070e7  mov     edx, eax
0x1400070e9  mov     [rdi], eax
0x1400070eb  mov     ecx, eax
0x1400070ed  jz      short loc_140007122
0x1400070ef  test    dl, 2
0x1400070f2  jnz     short loc_140007122
0x1400070f4  mov     eax, ebx
0x1400070f6  xor     eax, ecx
0x1400070f8  and     eax, 180h
0x1400070fd  xor     eax, ecx
0x1400070ff  mov     ecx, eax
0x140007101  xor     ecx, ebx
0x140007103  and     ecx, r15d
0x140007106  xor     ecx, eax
0x140007108  mov     eax, ecx
0x14000710a  xor     eax, ebx
0x14000710c  and     eax, 1
0x14000710f  xor     eax, ecx
0x140007111  mov     ecx, eax
0x140007113  xor     ecx, ebx
0x140007115  and     ecx, 800h
0x14000711b  xor     ecx, eax
0x14000711d  or      ecx, 2
0x140007120  mov     [rdi], ecx
0x140007122  test    dl, 4
0x140007125  jnz     short loc_140007137
0x140007127  mov     eax, ebx
0x140007129  xor     eax, ecx
0x14000712b  and     eax, 400h
0x140007130  xor     ecx, eax
0x140007132  or      ecx, 4
0x140007135  mov     [rdi], ecx
0x140007137  mov     eax, edx
0x140007139  lock cmpxchg [rsi], ecx
0x14000713d  jnz     short loc_1400070E2
0x14000713f  test    dl, 4
0x140007142  jnz     short loc_140007151
0x140007144  mov     r8d, ebp
0x140007147  xor     edx, edx
0x140007149  mov     rcx, rsi
0x14000714c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140007151  test    byte ptr [rdi], 2
0x140007154  jnz     short loc_140007181
0x140007156  mov     eax, ebx
0x140007158  xor     eax, [rdi]
0x14000715a  and     eax, 180h
0x14000715f  xor     eax, [rdi]
0x140007161  mov     ecx, eax
0x140007163  xor     ecx, ebx
0x140007165  and     ecx, r15d
0x140007168  xor     ecx, eax
0x14000716a  mov     edx, ecx
0x14000716c  xor     edx, ebx
0x14000716e  and     edx, 1
0x140007171  xor     edx, ecx
0x140007173  mov     ecx, edx
0x140007175  xor     ecx, ebx
0x140007177  and     ecx, 800h
0x14000717d  xor     ecx, edx
0x14000717f  mov     [rdi], ecx
0x140007181  mov     rax, rdi
0x140007184  mov     rcx, [rsp+48h+var_20]
0x140007189  xor     rcx, rsp; StackCookie
0x14000718c  call    __security_check_cookie
0x140007191  mov     rbx, [rsp+48h+arg_10]
0x140007196  mov     rbp, [rsp+48h+arg_18]
0x14000719b  add     rsp, 30h
0x14000719f  pop     r15
0x1400071a1  pop     rdi
0x1400071a2  pop     rsi
0x1400071a3  retn
```
