# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_PRONG1>::GetCachedFeatureEnabledState(void)

- ea: `0x140009bd4`
- end: `0x140009d65`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_PRONG1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `401`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005af0`
- `0x140009d6c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140009bd4`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_PRONG1>::GetCachedFeatureEnabledState(
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
    v7 = v6(47080059, 0, &v18);
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
0x140009bd4  mov     [rsp+arg_10], rbx
0x140009bd9  mov     [rsp+arg_18], rbp
0x140009bde  push    rsi
0x140009bdf  push    rdi
0x140009be0  push    r15
0x140009be2  sub     rsp, 30h
0x140009be6  mov     rax, cs:__security_cookie
0x140009bed  xor     rax, rsp
0x140009bf0  mov     [rsp+48h+var_20], rax
0x140009bf5  mov     qword ptr [rdx], 0
0x140009bfc  mov     rdi, rdx
0x140009bff  mov     eax, [rcx]
0x140009c01  mov     rsi, rcx
0x140009c04  mov     [rdx], eax
0x140009c06  and     eax, 6
0x140009c09  cmp     al, 6
0x140009c0b  jz      loc_140009D42
0x140009c11  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140009c16  mov     ebp, eax
0x140009c18  mov     [rsp+48h+var_28], 0
0x140009c20  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140009c27  mov     r15d, 40h ; '@'
0x140009c2d  test    rax, rax
0x140009c30  jnz     short loc_140009C3E
0x140009c32  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140009c39  test    rax, rax
0x140009c3c  jz      short loc_140009C88
0x140009c3e  lea     r8, [rsp+48h+var_28]
0x140009c43  xor     edx, edx
0x140009c45  mov     ecx, 2CE627Bh
0x140009c4a  call    _guard_dispatch_icall
0x140009c4f  mov     r8d, eax
0x140009c52  mov     edx, eax
0x140009c54  and     r8d, 0FFFFFF3Fh
0x140009c5b  and     eax, r15d
0x140009c5e  and     edx, 80h
0x140009c64  mov     ecx, r8d
0x140009c67  and     ecx, 3
0x140009c6a  shl     ecx, 2
0x140009c6d  or      ecx, eax
0x140009c6f  shl     ecx, 2
0x140009c72  or      ecx, edx
0x140009c74  shl     ecx, 3
0x140009c77  test    r8d, r8d
0x140009c7a  jz      short loc_140009C8A
0x140009c7c  xor     eax, eax
0x140009c7e  cmp     r8d, 2
0x140009c82  cmovz   eax, r15d
0x140009c86  jmp     short loc_140009C8D
0x140009c88  xor     ecx, ecx
0x140009c8a  mov     eax, r15d
0x140009c8d  or      ecx, eax
0x140009c8f  mov     ebx, ecx
0x140009c91  shr     ebx, 6
0x140009c94  and     ebx, 1
0x140009c97  or      ebx, ecx
0x140009c99  test    ebp, ebp
0x140009c9b  jnz     short loc_140009CA1
0x140009c9d  mov     [rsp+48h+var_28], ebp
0x140009ca1  mov     eax, [rdi]
0x140009ca3  cmp     [rsp+48h+var_28], 0
0x140009ca8  mov     edx, eax
0x140009caa  mov     [rdi], eax
0x140009cac  mov     ecx, eax
0x140009cae  jz      short loc_140009CE3
0x140009cb0  test    dl, 2
0x140009cb3  jnz     short loc_140009CE3
0x140009cb5  mov     eax, ebx
0x140009cb7  xor     eax, ecx
0x140009cb9  and     eax, 180h
0x140009cbe  xor     eax, ecx
0x140009cc0  mov     ecx, eax
0x140009cc2  xor     ecx, ebx
0x140009cc4  and     ecx, r15d
0x140009cc7  xor     ecx, eax
0x140009cc9  mov     eax, ecx
0x140009ccb  xor     eax, ebx
0x140009ccd  and     eax, 1
0x140009cd0  xor     eax, ecx
0x140009cd2  mov     ecx, eax
0x140009cd4  xor     ecx, ebx
0x140009cd6  and     ecx, 800h
0x140009cdc  xor     ecx, eax
0x140009cde  or      ecx, 2
0x140009ce1  mov     [rdi], ecx
0x140009ce3  test    dl, 4
0x140009ce6  jnz     short loc_140009CF8
0x140009ce8  mov     eax, ebx
0x140009cea  xor     eax, ecx
0x140009cec  and     eax, 400h
0x140009cf1  xor     ecx, eax
0x140009cf3  or      ecx, 4
0x140009cf6  mov     [rdi], ecx
0x140009cf8  mov     eax, edx
0x140009cfa  lock cmpxchg [rsi], ecx
0x140009cfe  jnz     short loc_140009CA3
0x140009d00  test    dl, 4
0x140009d03  jnz     short loc_140009D12
0x140009d05  mov     r8d, ebp
0x140009d08  xor     edx, edx
0x140009d0a  mov     rcx, rsi
0x140009d0d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140009d12  test    byte ptr [rdi], 2
0x140009d15  jnz     short loc_140009D42
0x140009d17  mov     eax, ebx
0x140009d19  xor     eax, [rdi]
0x140009d1b  and     eax, 180h
0x140009d20  xor     eax, [rdi]
0x140009d22  mov     ecx, eax
0x140009d24  xor     ecx, ebx
0x140009d26  and     ecx, r15d
0x140009d29  xor     ecx, eax
0x140009d2b  mov     edx, ecx
0x140009d2d  xor     edx, ebx
0x140009d2f  and     edx, 1
0x140009d32  xor     edx, ecx
0x140009d34  mov     ecx, edx
0x140009d36  xor     ecx, ebx
0x140009d38  and     ecx, 800h
0x140009d3e  xor     ecx, edx
0x140009d40  mov     [rdi], ecx
0x140009d42  mov     rax, rdi
0x140009d45  mov     rcx, [rsp+48h+var_20]
0x140009d4a  xor     rcx, rsp; StackCookie
0x140009d4d  call    __security_check_cookie
0x140009d52  mov     rbx, [rsp+48h+arg_10]
0x140009d57  mov     rbp, [rsp+48h+arg_18]
0x140009d5c  add     rsp, 30h
0x140009d60  pop     r15
0x140009d62  pop     rdi
0x140009d63  pop     rsi
0x140009d64  retn
```
