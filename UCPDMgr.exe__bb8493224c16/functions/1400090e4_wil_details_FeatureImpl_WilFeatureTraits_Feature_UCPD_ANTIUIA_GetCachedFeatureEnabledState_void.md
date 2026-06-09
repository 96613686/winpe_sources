# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_ANTIUIA>::GetCachedFeatureEnabledState(void)

- ea: `0x1400090e4`
- end: `0x140009275`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_ANTIUIA@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `401`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400059c4`
- `0x14000927c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x1400090e4`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_ANTIUIA>::GetCachedFeatureEnabledState(
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
    v7 = v6(50054740, 0, &v18);
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
0x1400090e4  mov     [rsp+arg_10], rbx
0x1400090e9  mov     [rsp+arg_18], rbp
0x1400090ee  push    rsi
0x1400090ef  push    rdi
0x1400090f0  push    r15
0x1400090f2  sub     rsp, 30h
0x1400090f6  mov     rax, cs:__security_cookie
0x1400090fd  xor     rax, rsp
0x140009100  mov     [rsp+48h+var_20], rax
0x140009105  mov     qword ptr [rdx], 0
0x14000910c  mov     rdi, rdx
0x14000910f  mov     eax, [rcx]
0x140009111  mov     rsi, rcx
0x140009114  mov     [rdx], eax
0x140009116  and     eax, 6
0x140009119  cmp     al, 6
0x14000911b  jz      loc_140009252
0x140009121  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140009126  mov     ebp, eax
0x140009128  mov     [rsp+48h+var_28], 0
0x140009130  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140009137  mov     r15d, 40h ; '@'
0x14000913d  test    rax, rax
0x140009140  jnz     short loc_14000914E
0x140009142  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140009149  test    rax, rax
0x14000914c  jz      short loc_140009198
0x14000914e  lea     r8, [rsp+48h+var_28]
0x140009153  xor     edx, edx
0x140009155  mov     ecx, 2FBC654h
0x14000915a  call    _guard_dispatch_icall
0x14000915f  mov     r8d, eax
0x140009162  mov     edx, eax
0x140009164  and     r8d, 0FFFFFF3Fh
0x14000916b  and     eax, r15d
0x14000916e  and     edx, 80h
0x140009174  mov     ecx, r8d
0x140009177  and     ecx, 3
0x14000917a  shl     ecx, 2
0x14000917d  or      ecx, eax
0x14000917f  shl     ecx, 2
0x140009182  or      ecx, edx
0x140009184  shl     ecx, 3
0x140009187  test    r8d, r8d
0x14000918a  jz      short loc_14000919A
0x14000918c  xor     eax, eax
0x14000918e  cmp     r8d, 2
0x140009192  cmovz   eax, r15d
0x140009196  jmp     short loc_14000919D
0x140009198  xor     ecx, ecx
0x14000919a  mov     eax, r15d
0x14000919d  or      ecx, eax
0x14000919f  mov     ebx, ecx
0x1400091a1  shr     ebx, 6
0x1400091a4  and     ebx, 1
0x1400091a7  or      ebx, ecx
0x1400091a9  test    ebp, ebp
0x1400091ab  jnz     short loc_1400091B1
0x1400091ad  mov     [rsp+48h+var_28], ebp
0x1400091b1  mov     eax, [rdi]
0x1400091b3  cmp     [rsp+48h+var_28], 0
0x1400091b8  mov     edx, eax
0x1400091ba  mov     [rdi], eax
0x1400091bc  mov     ecx, eax
0x1400091be  jz      short loc_1400091F3
0x1400091c0  test    dl, 2
0x1400091c3  jnz     short loc_1400091F3
0x1400091c5  mov     eax, ebx
0x1400091c7  xor     eax, ecx
0x1400091c9  and     eax, 180h
0x1400091ce  xor     eax, ecx
0x1400091d0  mov     ecx, eax
0x1400091d2  xor     ecx, ebx
0x1400091d4  and     ecx, r15d
0x1400091d7  xor     ecx, eax
0x1400091d9  mov     eax, ecx
0x1400091db  xor     eax, ebx
0x1400091dd  and     eax, 1
0x1400091e0  xor     eax, ecx
0x1400091e2  mov     ecx, eax
0x1400091e4  xor     ecx, ebx
0x1400091e6  and     ecx, 800h
0x1400091ec  xor     ecx, eax
0x1400091ee  or      ecx, 2
0x1400091f1  mov     [rdi], ecx
0x1400091f3  test    dl, 4
0x1400091f6  jnz     short loc_140009208
0x1400091f8  mov     eax, ebx
0x1400091fa  xor     eax, ecx
0x1400091fc  and     eax, 400h
0x140009201  xor     ecx, eax
0x140009203  or      ecx, 4
0x140009206  mov     [rdi], ecx
0x140009208  mov     eax, edx
0x14000920a  lock cmpxchg [rsi], ecx
0x14000920e  jnz     short loc_1400091B3
0x140009210  test    dl, 4
0x140009213  jnz     short loc_140009222
0x140009215  mov     r8d, ebp
0x140009218  xor     edx, edx
0x14000921a  mov     rcx, rsi
0x14000921d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140009222  test    byte ptr [rdi], 2
0x140009225  jnz     short loc_140009252
0x140009227  mov     eax, ebx
0x140009229  xor     eax, [rdi]
0x14000922b  and     eax, 180h
0x140009230  xor     eax, [rdi]
0x140009232  mov     ecx, eax
0x140009234  xor     ecx, ebx
0x140009236  and     ecx, r15d
0x140009239  xor     ecx, eax
0x14000923b  mov     edx, ecx
0x14000923d  xor     edx, ebx
0x14000923f  and     edx, 1
0x140009242  xor     edx, ecx
0x140009244  mov     ecx, edx
0x140009246  xor     ecx, ebx
0x140009248  and     ecx, 800h
0x14000924e  xor     ecx, edx
0x140009250  mov     [rdi], ecx
0x140009252  mov     rax, rdi
0x140009255  mov     rcx, [rsp+48h+var_20]
0x14000925a  xor     rcx, rsp; StackCookie
0x14000925d  call    __security_check_cookie
0x140009262  mov     rbx, [rsp+48h+arg_10]
0x140009267  mov     rbp, [rsp+48h+arg_18]
0x14000926c  add     rsp, 30h
0x140009270  pop     r15
0x140009272  pop     rdi
0x140009273  pop     rsi
0x140009274  retn
```
