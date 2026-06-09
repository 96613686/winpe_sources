# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_PRONG2>::GetCachedFeatureEnabledState(void)

- ea: `0x1400099a4`
- end: `0x140009b35`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_PRONG2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `401`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005ab4`
- `0x140009b3c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x1400099a4`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_PRONG2>::GetCachedFeatureEnabledState(
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
    v7 = v6(47508383, 0, &v18);
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
0x1400099a4  mov     [rsp+arg_10], rbx
0x1400099a9  mov     [rsp+arg_18], rbp
0x1400099ae  push    rsi
0x1400099af  push    rdi
0x1400099b0  push    r15
0x1400099b2  sub     rsp, 30h
0x1400099b6  mov     rax, cs:__security_cookie
0x1400099bd  xor     rax, rsp
0x1400099c0  mov     [rsp+48h+var_20], rax
0x1400099c5  mov     qword ptr [rdx], 0
0x1400099cc  mov     rdi, rdx
0x1400099cf  mov     eax, [rcx]
0x1400099d1  mov     rsi, rcx
0x1400099d4  mov     [rdx], eax
0x1400099d6  and     eax, 6
0x1400099d9  cmp     al, 6
0x1400099db  jz      loc_140009B12
0x1400099e1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400099e6  mov     ebp, eax
0x1400099e8  mov     [rsp+48h+var_28], 0
0x1400099f0  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1400099f7  mov     r15d, 40h ; '@'
0x1400099fd  test    rax, rax
0x140009a00  jnz     short loc_140009A0E
0x140009a02  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140009a09  test    rax, rax
0x140009a0c  jz      short loc_140009A58
0x140009a0e  lea     r8, [rsp+48h+var_28]
0x140009a13  xor     edx, edx
0x140009a15  mov     ecx, 2D4EB9Fh
0x140009a1a  call    _guard_dispatch_icall
0x140009a1f  mov     r8d, eax
0x140009a22  mov     edx, eax
0x140009a24  and     r8d, 0FFFFFF3Fh
0x140009a2b  and     eax, r15d
0x140009a2e  and     edx, 80h
0x140009a34  mov     ecx, r8d
0x140009a37  and     ecx, 3
0x140009a3a  shl     ecx, 2
0x140009a3d  or      ecx, eax
0x140009a3f  shl     ecx, 2
0x140009a42  or      ecx, edx
0x140009a44  shl     ecx, 3
0x140009a47  test    r8d, r8d
0x140009a4a  jz      short loc_140009A5A
0x140009a4c  xor     eax, eax
0x140009a4e  cmp     r8d, 2
0x140009a52  cmovz   eax, r15d
0x140009a56  jmp     short loc_140009A5D
0x140009a58  xor     ecx, ecx
0x140009a5a  mov     eax, r15d
0x140009a5d  or      ecx, eax
0x140009a5f  mov     ebx, ecx
0x140009a61  shr     ebx, 6
0x140009a64  and     ebx, 1
0x140009a67  or      ebx, ecx
0x140009a69  test    ebp, ebp
0x140009a6b  jnz     short loc_140009A71
0x140009a6d  mov     [rsp+48h+var_28], ebp
0x140009a71  mov     eax, [rdi]
0x140009a73  cmp     [rsp+48h+var_28], 0
0x140009a78  mov     edx, eax
0x140009a7a  mov     [rdi], eax
0x140009a7c  mov     ecx, eax
0x140009a7e  jz      short loc_140009AB3
0x140009a80  test    dl, 2
0x140009a83  jnz     short loc_140009AB3
0x140009a85  mov     eax, ebx
0x140009a87  xor     eax, ecx
0x140009a89  and     eax, 180h
0x140009a8e  xor     eax, ecx
0x140009a90  mov     ecx, eax
0x140009a92  xor     ecx, ebx
0x140009a94  and     ecx, r15d
0x140009a97  xor     ecx, eax
0x140009a99  mov     eax, ecx
0x140009a9b  xor     eax, ebx
0x140009a9d  and     eax, 1
0x140009aa0  xor     eax, ecx
0x140009aa2  mov     ecx, eax
0x140009aa4  xor     ecx, ebx
0x140009aa6  and     ecx, 800h
0x140009aac  xor     ecx, eax
0x140009aae  or      ecx, 2
0x140009ab1  mov     [rdi], ecx
0x140009ab3  test    dl, 4
0x140009ab6  jnz     short loc_140009AC8
0x140009ab8  mov     eax, ebx
0x140009aba  xor     eax, ecx
0x140009abc  and     eax, 400h
0x140009ac1  xor     ecx, eax
0x140009ac3  or      ecx, 4
0x140009ac6  mov     [rdi], ecx
0x140009ac8  mov     eax, edx
0x140009aca  lock cmpxchg [rsi], ecx
0x140009ace  jnz     short loc_140009A73
0x140009ad0  test    dl, 4
0x140009ad3  jnz     short loc_140009AE2
0x140009ad5  mov     r8d, ebp
0x140009ad8  xor     edx, edx
0x140009ada  mov     rcx, rsi
0x140009add  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140009ae2  test    byte ptr [rdi], 2
0x140009ae5  jnz     short loc_140009B12
0x140009ae7  mov     eax, ebx
0x140009ae9  xor     eax, [rdi]
0x140009aeb  and     eax, 180h
0x140009af0  xor     eax, [rdi]
0x140009af2  mov     ecx, eax
0x140009af4  xor     ecx, ebx
0x140009af6  and     ecx, r15d
0x140009af9  xor     ecx, eax
0x140009afb  mov     edx, ecx
0x140009afd  xor     edx, ebx
0x140009aff  and     edx, 1
0x140009b02  xor     edx, ecx
0x140009b04  mov     ecx, edx
0x140009b06  xor     ecx, ebx
0x140009b08  and     ecx, 800h
0x140009b0e  xor     ecx, edx
0x140009b10  mov     [rdi], ecx
0x140009b12  mov     rax, rdi
0x140009b15  mov     rcx, [rsp+48h+var_20]
0x140009b1a  xor     rcx, rsp; StackCookie
0x140009b1d  call    __security_check_cookie
0x140009b22  mov     rbx, [rsp+48h+arg_10]
0x140009b27  mov     rbp, [rsp+48h+arg_18]
0x140009b2c  add     rsp, 30h
0x140009b30  pop     r15
0x140009b32  pop     rdi
0x140009b33  pop     rsi
0x140009b34  retn
```
