# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_WSB>::GetCachedFeatureEnabledState(void)

- ea: `0x140009544`
- end: `0x1400096d5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_WSB@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `401`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005a3c`
- `0x1400096dc`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140009544`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_WSB>::GetCachedFeatureEnabledState(
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
  unsigned int v11; // ebx
  signed __int32 v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  int v16; // ecx
  int v18; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v3 & 6) == 6 )
    return a2;
  v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v18 = 0;
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v7 = v6(48789334, 0, &v18);
    v8 = v7 & 0xFFFFFF3F;
    v9 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
    if ( (v7 & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
      goto LABEL_10;
    }
  }
  else
  {
    v9 = 0;
  }
  v10 = 64;
LABEL_10:
  v11 = v10 | v9 | ((v10 | (unsigned int)v9) >> 6) & 1;
  if ( !v5 )
    v18 = 0;
  v12 = *(_DWORD *)a2;
  do
  {
    v13 = v18 == 0;
    v14 = v12;
    *(_DWORD *)a2 = v12;
    v15 = v12;
    if ( !v13 && (v12 & 2) == 0 )
    {
      v16 = v12
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v11)
          & 0x180
          ^ (v11
           ^ v12
           ^ ((unsigned __int16)v12
            ^ (unsigned __int16)v11)
           & 0x180)
          & 0x40;
      v15 = v16
          ^ ((unsigned __int8)v11
           ^ (unsigned __int8)v16)
          & 1
          ^ ((unsigned __int16)v11
           ^ (unsigned __int16)(v16 ^ ((unsigned __int8)v11 ^ (unsigned __int8)v16) & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    if ( (v12 & 4) == 0 )
    {
      v15 = ((unsigned __int16)v15 ^ (unsigned __int16)v11) & 0x400 ^ v15 | 4;
      *(_DWORD *)a2 = v15;
    }
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v15, v12);
  }
  while ( v14 != v12 );
  if ( (v14 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(a1, 0, v5);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (*(_DWORD *)a2
                    ^ v11)
                   & 0x180
                   ^ (v11
                    ^ *(_DWORD *)a2
                    ^ (*(_DWORD *)a2
                     ^ v11)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v11
                    ^ *(_BYTE *)a2
                    ^ (*(_BYTE *)a2
                     ^ (unsigned __int8)v11)
                    & 0x80
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v11)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v11
                    ^ *(_WORD *)a2
                    ^ (*(_WORD *)a2
                     ^ (unsigned __int16)v11)
                    & 0x180
                    ^ ((unsigned __int16)v11
                     ^ *(_WORD *)a2
                     ^ (*(_WORD *)a2
                      ^ (unsigned __int16)v11)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v11)
                     & 0x80
                     ^ ((unsigned __int8)v11
                      ^ *(_BYTE *)a2
                      ^ (*(_BYTE *)a2
                       ^ (unsigned __int8)v11)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x140009544  mov     [rsp+arg_10], rbx
0x140009549  mov     [rsp+arg_18], rbp
0x14000954e  push    rsi
0x14000954f  push    rdi
0x140009550  push    r15
0x140009552  sub     rsp, 30h
0x140009556  mov     rax, cs:__security_cookie
0x14000955d  xor     rax, rsp
0x140009560  mov     [rsp+48h+var_20], rax
0x140009565  mov     qword ptr [rdx], 0
0x14000956c  mov     rdi, rdx
0x14000956f  mov     eax, [rcx]
0x140009571  mov     rsi, rcx
0x140009574  mov     [rdx], eax
0x140009576  and     eax, 6
0x140009579  cmp     al, 6
0x14000957b  jz      loc_1400096B2
0x140009581  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140009586  mov     ebp, eax
0x140009588  mov     [rsp+48h+var_28], 0
0x140009590  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140009597  mov     r15d, 40h ; '@'
0x14000959d  test    rax, rax
0x1400095a0  jnz     short loc_1400095AE
0x1400095a2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1400095a9  test    rax, rax
0x1400095ac  jz      short loc_1400095F8
0x1400095ae  lea     r8, [rsp+48h+var_28]
0x1400095b3  xor     edx, edx
0x1400095b5  mov     ecx, 2E87756h
0x1400095ba  call    _guard_dispatch_icall
0x1400095bf  mov     r8d, eax
0x1400095c2  mov     edx, eax
0x1400095c4  and     r8d, 0FFFFFF3Fh
0x1400095cb  and     eax, r15d
0x1400095ce  and     edx, 80h
0x1400095d4  mov     ecx, r8d
0x1400095d7  and     ecx, 3
0x1400095da  shl     ecx, 2
0x1400095dd  or      ecx, eax
0x1400095df  shl     ecx, 2
0x1400095e2  or      ecx, edx
0x1400095e4  shl     ecx, 3
0x1400095e7  test    r8d, r8d
0x1400095ea  jz      short loc_1400095FA
0x1400095ec  xor     eax, eax
0x1400095ee  cmp     r8d, 2
0x1400095f2  cmovz   eax, r15d
0x1400095f6  jmp     short loc_1400095FD
0x1400095f8  xor     ecx, ecx
0x1400095fa  mov     eax, r15d
0x1400095fd  or      ecx, eax
0x1400095ff  mov     ebx, ecx
0x140009601  shr     ebx, 6
0x140009604  and     ebx, 1
0x140009607  or      ebx, ecx
0x140009609  test    ebp, ebp
0x14000960b  jnz     short loc_140009611
0x14000960d  mov     [rsp+48h+var_28], ebp
0x140009611  mov     eax, [rdi]
0x140009613  cmp     [rsp+48h+var_28], 0
0x140009618  mov     edx, eax
0x14000961a  mov     [rdi], eax
0x14000961c  mov     ecx, eax
0x14000961e  jz      short loc_140009653
0x140009620  test    dl, 2
0x140009623  jnz     short loc_140009653
0x140009625  mov     eax, ebx
0x140009627  xor     eax, ecx
0x140009629  and     eax, 180h
0x14000962e  xor     eax, ecx
0x140009630  mov     ecx, eax
0x140009632  xor     ecx, ebx
0x140009634  and     ecx, r15d
0x140009637  xor     ecx, eax
0x140009639  mov     eax, ecx
0x14000963b  xor     eax, ebx
0x14000963d  and     eax, 1
0x140009640  xor     eax, ecx
0x140009642  mov     ecx, eax
0x140009644  xor     ecx, ebx
0x140009646  and     ecx, 800h
0x14000964c  xor     ecx, eax
0x14000964e  or      ecx, 2
0x140009651  mov     [rdi], ecx
0x140009653  test    dl, 4
0x140009656  jnz     short loc_140009668
0x140009658  mov     eax, ebx
0x14000965a  xor     eax, ecx
0x14000965c  and     eax, 400h
0x140009661  xor     ecx, eax
0x140009663  or      ecx, 4
0x140009666  mov     [rdi], ecx
0x140009668  mov     eax, edx
0x14000966a  lock cmpxchg [rsi], ecx
0x14000966e  jnz     short loc_140009613
0x140009670  test    dl, 4
0x140009673  jnz     short loc_140009682
0x140009675  mov     r8d, ebp
0x140009678  xor     edx, edx
0x14000967a  mov     rcx, rsi
0x14000967d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140009682  test    byte ptr [rdi], 2
0x140009685  jnz     short loc_1400096B2
0x140009687  mov     eax, ebx
0x140009689  xor     eax, [rdi]
0x14000968b  and     eax, 180h
0x140009690  xor     eax, [rdi]
0x140009692  mov     ecx, eax
0x140009694  xor     ecx, ebx
0x140009696  and     ecx, r15d
0x140009699  xor     ecx, eax
0x14000969b  mov     edx, ecx
0x14000969d  xor     edx, ebx
0x14000969f  and     edx, 1
0x1400096a2  xor     edx, ecx
0x1400096a4  mov     ecx, edx
0x1400096a6  xor     ecx, ebx
0x1400096a8  and     ecx, 800h
0x1400096ae  xor     ecx, edx
0x1400096b0  mov     [rdi], ecx
0x1400096b2  mov     rax, rdi
0x1400096b5  mov     rcx, [rsp+48h+var_20]
0x1400096ba  xor     rcx, rsp; StackCookie
0x1400096bd  call    __security_check_cookie
0x1400096c2  mov     rbx, [rsp+48h+arg_10]
0x1400096c7  mov     rbp, [rsp+48h+arg_18]
0x1400096cc  add     rsp, 30h
0x1400096d0  pop     r15
0x1400096d2  pop     rdi
0x1400096d3  pop     rsi
0x1400096d4  retn
```
