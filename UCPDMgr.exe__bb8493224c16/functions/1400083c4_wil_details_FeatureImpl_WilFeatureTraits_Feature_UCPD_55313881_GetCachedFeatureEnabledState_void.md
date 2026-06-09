# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_55313881>::GetCachedFeatureEnabledState(void)

- ea: `0x1400083c4`
- end: `0x140008554`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_55313881@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000585c`
- `0x14000855c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x1400083c4`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_55313881>::GetCachedFeatureEnabledState(
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
    v7 = v6(55313881, 0, &v19);
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
0x1400083c4  mov     [rsp+arg_10], rbx
0x1400083c9  mov     [rsp+arg_18], rbp
0x1400083ce  push    rsi
0x1400083cf  push    rdi
0x1400083d0  push    r15
0x1400083d2  sub     rsp, 30h
0x1400083d6  mov     rax, cs:__security_cookie
0x1400083dd  xor     rax, rsp
0x1400083e0  mov     [rsp+48h+var_20], rax
0x1400083e5  mov     qword ptr [rdx], 0
0x1400083ec  mov     rdi, rdx
0x1400083ef  mov     eax, [rcx]
0x1400083f1  mov     rsi, rcx
0x1400083f4  mov     [rdx], eax
0x1400083f6  and     eax, 6
0x1400083f9  cmp     al, 6
0x1400083fb  jz      loc_140008531
0x140008401  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140008406  mov     ebp, eax
0x140008408  mov     [rsp+48h+var_28], 0
0x140008410  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140008417  mov     r15d, 40h ; '@'
0x14000841d  test    rax, rax
0x140008420  jnz     short loc_14000842E
0x140008422  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140008429  test    rax, rax
0x14000842c  jz      short loc_14000847A
0x14000842e  lea     r8, [rsp+48h+var_28]
0x140008433  xor     edx, edx
0x140008435  mov     ecx, 34C05D9h
0x14000843a  call    _guard_dispatch_icall
0x14000843f  mov     r8d, eax
0x140008442  mov     edx, eax
0x140008444  and     r8d, 0FFFFFF3Fh
0x14000844b  and     eax, r15d
0x14000844e  and     edx, 80h
0x140008454  mov     ecx, r8d
0x140008457  and     ecx, 3
0x14000845a  shl     ecx, 2
0x14000845d  or      ecx, eax
0x14000845f  shl     ecx, 2
0x140008462  or      ecx, edx
0x140008464  shl     ecx, 3
0x140008467  test    r8d, r8d
0x14000846a  jz      short loc_14000847C
0x14000846c  xor     eax, eax
0x14000846e  cmp     r8d, 2
0x140008472  cmovz   eax, r15d
0x140008476  or      eax, ecx
0x140008478  jmp     short loc_14000847E
0x14000847a  xor     ecx, ecx
0x14000847c  mov     eax, ecx
0x14000847e  mov     ebx, eax
0x140008480  shr     ebx, 6
0x140008483  and     ebx, 1
0x140008486  or      ebx, eax
0x140008488  test    ebp, ebp
0x14000848a  jnz     short loc_140008490
0x14000848c  mov     [rsp+48h+var_28], ebp
0x140008490  mov     eax, [rdi]
0x140008492  cmp     [rsp+48h+var_28], 0
0x140008497  mov     edx, eax
0x140008499  mov     [rdi], eax
0x14000849b  mov     ecx, eax
0x14000849d  jz      short loc_1400084D2
0x14000849f  test    dl, 2
0x1400084a2  jnz     short loc_1400084D2
0x1400084a4  mov     eax, ebx
0x1400084a6  xor     eax, ecx
0x1400084a8  and     eax, 180h
0x1400084ad  xor     eax, ecx
0x1400084af  mov     ecx, eax
0x1400084b1  xor     ecx, ebx
0x1400084b3  and     ecx, r15d
0x1400084b6  xor     ecx, eax
0x1400084b8  mov     eax, ecx
0x1400084ba  xor     eax, ebx
0x1400084bc  and     eax, 1
0x1400084bf  xor     eax, ecx
0x1400084c1  mov     ecx, eax
0x1400084c3  xor     ecx, ebx
0x1400084c5  and     ecx, 800h
0x1400084cb  xor     ecx, eax
0x1400084cd  or      ecx, 2
0x1400084d0  mov     [rdi], ecx
0x1400084d2  test    dl, 4
0x1400084d5  jnz     short loc_1400084E7
0x1400084d7  mov     eax, ebx
0x1400084d9  xor     eax, ecx
0x1400084db  and     eax, 400h
0x1400084e0  xor     ecx, eax
0x1400084e2  or      ecx, 4
0x1400084e5  mov     [rdi], ecx
0x1400084e7  mov     eax, edx
0x1400084e9  lock cmpxchg [rsi], ecx
0x1400084ed  jnz     short loc_140008492
0x1400084ef  test    dl, 4
0x1400084f2  jnz     short loc_140008501
0x1400084f4  mov     r8d, ebp
0x1400084f7  xor     edx, edx
0x1400084f9  mov     rcx, rsi
0x1400084fc  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140008501  test    byte ptr [rdi], 2
0x140008504  jnz     short loc_140008531
0x140008506  mov     eax, ebx
0x140008508  xor     eax, [rdi]
0x14000850a  and     eax, 180h
0x14000850f  xor     eax, [rdi]
0x140008511  mov     ecx, eax
0x140008513  xor     ecx, ebx
0x140008515  and     ecx, r15d
0x140008518  xor     ecx, eax
0x14000851a  mov     edx, ecx
0x14000851c  xor     edx, ebx
0x14000851e  and     edx, 1
0x140008521  xor     edx, ecx
0x140008523  mov     ecx, edx
0x140008525  xor     ecx, ebx
0x140008527  and     ecx, 800h
0x14000852d  xor     ecx, edx
0x14000852f  mov     [rdi], ecx
0x140008531  mov     rax, rdi
0x140008534  mov     rcx, [rsp+48h+var_20]
0x140008539  xor     rcx, rsp; StackCookie
0x14000853c  call    __security_check_cookie
0x140008541  mov     rbx, [rsp+48h+arg_10]
0x140008546  mov     rbp, [rsp+48h+arg_18]
0x14000854b  add     rsp, 30h
0x14000854f  pop     r15
0x140008551  pop     rdi
0x140008552  pop     rsi
0x140008553  retn
```
