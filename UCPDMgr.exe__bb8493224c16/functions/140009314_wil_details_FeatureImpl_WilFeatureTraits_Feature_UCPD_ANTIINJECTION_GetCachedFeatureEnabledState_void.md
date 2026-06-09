# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_ANTIINJECTION>::GetCachedFeatureEnabledState(void)

- ea: `0x140009314`
- end: `0x1400094a5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_ANTIINJECTION@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `401`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005a00`
- `0x1400094ac`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140009314`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_ANTIINJECTION>::GetCachedFeatureEnabledState(
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
    v7 = v6(50054602, 0, &v18);
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
0x140009314  mov     [rsp+arg_10], rbx
0x140009319  mov     [rsp+arg_18], rbp
0x14000931e  push    rsi
0x14000931f  push    rdi
0x140009320  push    r15
0x140009322  sub     rsp, 30h
0x140009326  mov     rax, cs:__security_cookie
0x14000932d  xor     rax, rsp
0x140009330  mov     [rsp+48h+var_20], rax
0x140009335  mov     qword ptr [rdx], 0
0x14000933c  mov     rdi, rdx
0x14000933f  mov     eax, [rcx]
0x140009341  mov     rsi, rcx
0x140009344  mov     [rdx], eax
0x140009346  and     eax, 6
0x140009349  cmp     al, 6
0x14000934b  jz      loc_140009482
0x140009351  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140009356  mov     ebp, eax
0x140009358  mov     [rsp+48h+var_28], 0
0x140009360  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140009367  mov     r15d, 40h ; '@'
0x14000936d  test    rax, rax
0x140009370  jnz     short loc_14000937E
0x140009372  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140009379  test    rax, rax
0x14000937c  jz      short loc_1400093C8
0x14000937e  lea     r8, [rsp+48h+var_28]
0x140009383  xor     edx, edx
0x140009385  mov     ecx, 2FBC5CAh
0x14000938a  call    _guard_dispatch_icall
0x14000938f  mov     r8d, eax
0x140009392  mov     edx, eax
0x140009394  and     r8d, 0FFFFFF3Fh
0x14000939b  and     eax, r15d
0x14000939e  and     edx, 80h
0x1400093a4  mov     ecx, r8d
0x1400093a7  and     ecx, 3
0x1400093aa  shl     ecx, 2
0x1400093ad  or      ecx, eax
0x1400093af  shl     ecx, 2
0x1400093b2  or      ecx, edx
0x1400093b4  shl     ecx, 3
0x1400093b7  test    r8d, r8d
0x1400093ba  jz      short loc_1400093CA
0x1400093bc  xor     eax, eax
0x1400093be  cmp     r8d, 2
0x1400093c2  cmovz   eax, r15d
0x1400093c6  jmp     short loc_1400093CD
0x1400093c8  xor     ecx, ecx
0x1400093ca  mov     eax, r15d
0x1400093cd  or      ecx, eax
0x1400093cf  mov     ebx, ecx
0x1400093d1  shr     ebx, 6
0x1400093d4  and     ebx, 1
0x1400093d7  or      ebx, ecx
0x1400093d9  test    ebp, ebp
0x1400093db  jnz     short loc_1400093E1
0x1400093dd  mov     [rsp+48h+var_28], ebp
0x1400093e1  mov     eax, [rdi]
0x1400093e3  cmp     [rsp+48h+var_28], 0
0x1400093e8  mov     edx, eax
0x1400093ea  mov     [rdi], eax
0x1400093ec  mov     ecx, eax
0x1400093ee  jz      short loc_140009423
0x1400093f0  test    dl, 2
0x1400093f3  jnz     short loc_140009423
0x1400093f5  mov     eax, ebx
0x1400093f7  xor     eax, ecx
0x1400093f9  and     eax, 180h
0x1400093fe  xor     eax, ecx
0x140009400  mov     ecx, eax
0x140009402  xor     ecx, ebx
0x140009404  and     ecx, r15d
0x140009407  xor     ecx, eax
0x140009409  mov     eax, ecx
0x14000940b  xor     eax, ebx
0x14000940d  and     eax, 1
0x140009410  xor     eax, ecx
0x140009412  mov     ecx, eax
0x140009414  xor     ecx, ebx
0x140009416  and     ecx, 800h
0x14000941c  xor     ecx, eax
0x14000941e  or      ecx, 2
0x140009421  mov     [rdi], ecx
0x140009423  test    dl, 4
0x140009426  jnz     short loc_140009438
0x140009428  mov     eax, ebx
0x14000942a  xor     eax, ecx
0x14000942c  and     eax, 400h
0x140009431  xor     ecx, eax
0x140009433  or      ecx, 4
0x140009436  mov     [rdi], ecx
0x140009438  mov     eax, edx
0x14000943a  lock cmpxchg [rsi], ecx
0x14000943e  jnz     short loc_1400093E3
0x140009440  test    dl, 4
0x140009443  jnz     short loc_140009452
0x140009445  mov     r8d, ebp
0x140009448  xor     edx, edx
0x14000944a  mov     rcx, rsi
0x14000944d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140009452  test    byte ptr [rdi], 2
0x140009455  jnz     short loc_140009482
0x140009457  mov     eax, ebx
0x140009459  xor     eax, [rdi]
0x14000945b  and     eax, 180h
0x140009460  xor     eax, [rdi]
0x140009462  mov     ecx, eax
0x140009464  xor     ecx, ebx
0x140009466  and     ecx, r15d
0x140009469  xor     ecx, eax
0x14000946b  mov     edx, ecx
0x14000946d  xor     edx, ebx
0x14000946f  and     edx, 1
0x140009472  xor     edx, ecx
0x140009474  mov     ecx, edx
0x140009476  xor     ecx, ebx
0x140009478  and     ecx, 800h
0x14000947e  xor     ecx, edx
0x140009480  mov     [rdi], ecx
0x140009482  mov     rax, rdi
0x140009485  mov     rcx, [rsp+48h+var_20]
0x14000948a  xor     rcx, rsp; StackCookie
0x14000948d  call    __security_check_cookie
0x140009492  mov     rbx, [rsp+48h+arg_10]
0x140009497  mov     rbp, [rsp+48h+arg_18]
0x14000949c  add     rsp, 30h
0x1400094a0  pop     r15
0x1400094a2  pop     rdi
0x1400094a3  pop     rsi
0x1400094a4  retn
```
