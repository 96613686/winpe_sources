# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_56888100>::GetCachedFeatureEnabledState(void)

- ea: `0x140007b04`
- end: `0x140007c94`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_56888100@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000576c`
- `0x140007c9c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140007b04`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_56888100>::GetCachedFeatureEnabledState(
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
    v7 = v6(56888100, 0, &v19);
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
0x140007b04  mov     [rsp+arg_10], rbx
0x140007b09  mov     [rsp+arg_18], rbp
0x140007b0e  push    rsi
0x140007b0f  push    rdi
0x140007b10  push    r15
0x140007b12  sub     rsp, 30h
0x140007b16  mov     rax, cs:__security_cookie
0x140007b1d  xor     rax, rsp
0x140007b20  mov     [rsp+48h+var_20], rax
0x140007b25  mov     qword ptr [rdx], 0
0x140007b2c  mov     rdi, rdx
0x140007b2f  mov     eax, [rcx]
0x140007b31  mov     rsi, rcx
0x140007b34  mov     [rdx], eax
0x140007b36  and     eax, 6
0x140007b39  cmp     al, 6
0x140007b3b  jz      loc_140007C71
0x140007b41  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140007b46  mov     ebp, eax
0x140007b48  mov     [rsp+48h+var_28], 0
0x140007b50  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140007b57  mov     r15d, 40h ; '@'
0x140007b5d  test    rax, rax
0x140007b60  jnz     short loc_140007B6E
0x140007b62  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140007b69  test    rax, rax
0x140007b6c  jz      short loc_140007BBA
0x140007b6e  lea     r8, [rsp+48h+var_28]
0x140007b73  xor     edx, edx
0x140007b75  mov     ecx, 3640B24h
0x140007b7a  call    _guard_dispatch_icall
0x140007b7f  mov     r8d, eax
0x140007b82  mov     edx, eax
0x140007b84  and     r8d, 0FFFFFF3Fh
0x140007b8b  and     eax, r15d
0x140007b8e  and     edx, 80h
0x140007b94  mov     ecx, r8d
0x140007b97  and     ecx, 3
0x140007b9a  shl     ecx, 2
0x140007b9d  or      ecx, eax
0x140007b9f  shl     ecx, 2
0x140007ba2  or      ecx, edx
0x140007ba4  shl     ecx, 3
0x140007ba7  test    r8d, r8d
0x140007baa  jz      short loc_140007BBC
0x140007bac  xor     eax, eax
0x140007bae  cmp     r8d, 2
0x140007bb2  cmovz   eax, r15d
0x140007bb6  or      eax, ecx
0x140007bb8  jmp     short loc_140007BBE
0x140007bba  xor     ecx, ecx
0x140007bbc  mov     eax, ecx
0x140007bbe  mov     ebx, eax
0x140007bc0  shr     ebx, 6
0x140007bc3  and     ebx, 1
0x140007bc6  or      ebx, eax
0x140007bc8  test    ebp, ebp
0x140007bca  jnz     short loc_140007BD0
0x140007bcc  mov     [rsp+48h+var_28], ebp
0x140007bd0  mov     eax, [rdi]
0x140007bd2  cmp     [rsp+48h+var_28], 0
0x140007bd7  mov     edx, eax
0x140007bd9  mov     [rdi], eax
0x140007bdb  mov     ecx, eax
0x140007bdd  jz      short loc_140007C12
0x140007bdf  test    dl, 2
0x140007be2  jnz     short loc_140007C12
0x140007be4  mov     eax, ebx
0x140007be6  xor     eax, ecx
0x140007be8  and     eax, 180h
0x140007bed  xor     eax, ecx
0x140007bef  mov     ecx, eax
0x140007bf1  xor     ecx, ebx
0x140007bf3  and     ecx, r15d
0x140007bf6  xor     ecx, eax
0x140007bf8  mov     eax, ecx
0x140007bfa  xor     eax, ebx
0x140007bfc  and     eax, 1
0x140007bff  xor     eax, ecx
0x140007c01  mov     ecx, eax
0x140007c03  xor     ecx, ebx
0x140007c05  and     ecx, 800h
0x140007c0b  xor     ecx, eax
0x140007c0d  or      ecx, 2
0x140007c10  mov     [rdi], ecx
0x140007c12  test    dl, 4
0x140007c15  jnz     short loc_140007C27
0x140007c17  mov     eax, ebx
0x140007c19  xor     eax, ecx
0x140007c1b  and     eax, 400h
0x140007c20  xor     ecx, eax
0x140007c22  or      ecx, 4
0x140007c25  mov     [rdi], ecx
0x140007c27  mov     eax, edx
0x140007c29  lock cmpxchg [rsi], ecx
0x140007c2d  jnz     short loc_140007BD2
0x140007c2f  test    dl, 4
0x140007c32  jnz     short loc_140007C41
0x140007c34  mov     r8d, ebp
0x140007c37  xor     edx, edx
0x140007c39  mov     rcx, rsi
0x140007c3c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140007c41  test    byte ptr [rdi], 2
0x140007c44  jnz     short loc_140007C71
0x140007c46  mov     eax, ebx
0x140007c48  xor     eax, [rdi]
0x140007c4a  and     eax, 180h
0x140007c4f  xor     eax, [rdi]
0x140007c51  mov     ecx, eax
0x140007c53  xor     ecx, ebx
0x140007c55  and     ecx, r15d
0x140007c58  xor     ecx, eax
0x140007c5a  mov     edx, ecx
0x140007c5c  xor     edx, ebx
0x140007c5e  and     edx, 1
0x140007c61  xor     edx, ecx
0x140007c63  mov     ecx, edx
0x140007c65  xor     ecx, ebx
0x140007c67  and     ecx, 800h
0x140007c6d  xor     ecx, edx
0x140007c6f  mov     [rdi], ecx
0x140007c71  mov     rax, rdi
0x140007c74  mov     rcx, [rsp+48h+var_20]
0x140007c79  xor     rcx, rsp; StackCookie
0x140007c7c  call    __security_check_cookie
0x140007c81  mov     rbx, [rsp+48h+arg_10]
0x140007c86  mov     rbp, [rsp+48h+arg_18]
0x140007c8b  add     rsp, 30h
0x140007c8f  pop     r15
0x140007c91  pop     rdi
0x140007c92  pop     rsi
0x140007c93  retn
```
