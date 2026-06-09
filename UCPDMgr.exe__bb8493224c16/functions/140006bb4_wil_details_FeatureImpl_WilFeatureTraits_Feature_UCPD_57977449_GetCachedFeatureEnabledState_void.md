# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_57977449>::GetCachedFeatureEnabledState(void)

- ea: `0x140006bb4`
- end: `0x140006d44`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_57977449@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400055c8`
- `0x140006d4c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140006bb4`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_57977449>::GetCachedFeatureEnabledState(
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
    v7 = v6(57977449, 0, &v19);
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
0x140006bb4  mov     [rsp+arg_10], rbx
0x140006bb9  mov     [rsp+arg_18], rbp
0x140006bbe  push    rsi
0x140006bbf  push    rdi
0x140006bc0  push    r15
0x140006bc2  sub     rsp, 30h
0x140006bc6  mov     rax, cs:__security_cookie
0x140006bcd  xor     rax, rsp
0x140006bd0  mov     [rsp+48h+var_20], rax
0x140006bd5  mov     qword ptr [rdx], 0
0x140006bdc  mov     rdi, rdx
0x140006bdf  mov     eax, [rcx]
0x140006be1  mov     rsi, rcx
0x140006be4  mov     [rdx], eax
0x140006be6  and     eax, 6
0x140006be9  cmp     al, 6
0x140006beb  jz      loc_140006D21
0x140006bf1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140006bf6  mov     ebp, eax
0x140006bf8  mov     [rsp+48h+var_28], 0
0x140006c00  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140006c07  mov     r15d, 40h ; '@'
0x140006c0d  test    rax, rax
0x140006c10  jnz     short loc_140006C1E
0x140006c12  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140006c19  test    rax, rax
0x140006c1c  jz      short loc_140006C6A
0x140006c1e  lea     r8, [rsp+48h+var_28]
0x140006c23  xor     edx, edx
0x140006c25  mov     ecx, 374AA69h
0x140006c2a  call    _guard_dispatch_icall
0x140006c2f  mov     r8d, eax
0x140006c32  mov     edx, eax
0x140006c34  and     r8d, 0FFFFFF3Fh
0x140006c3b  and     eax, r15d
0x140006c3e  and     edx, 80h
0x140006c44  mov     ecx, r8d
0x140006c47  and     ecx, 3
0x140006c4a  shl     ecx, 2
0x140006c4d  or      ecx, eax
0x140006c4f  shl     ecx, 2
0x140006c52  or      ecx, edx
0x140006c54  shl     ecx, 3
0x140006c57  test    r8d, r8d
0x140006c5a  jz      short loc_140006C6C
0x140006c5c  xor     eax, eax
0x140006c5e  cmp     r8d, 2
0x140006c62  cmovz   eax, r15d
0x140006c66  or      eax, ecx
0x140006c68  jmp     short loc_140006C6E
0x140006c6a  xor     ecx, ecx
0x140006c6c  mov     eax, ecx
0x140006c6e  mov     ebx, eax
0x140006c70  shr     ebx, 6
0x140006c73  and     ebx, 1
0x140006c76  or      ebx, eax
0x140006c78  test    ebp, ebp
0x140006c7a  jnz     short loc_140006C80
0x140006c7c  mov     [rsp+48h+var_28], ebp
0x140006c80  mov     eax, [rdi]
0x140006c82  cmp     [rsp+48h+var_28], 0
0x140006c87  mov     edx, eax
0x140006c89  mov     [rdi], eax
0x140006c8b  mov     ecx, eax
0x140006c8d  jz      short loc_140006CC2
0x140006c8f  test    dl, 2
0x140006c92  jnz     short loc_140006CC2
0x140006c94  mov     eax, ebx
0x140006c96  xor     eax, ecx
0x140006c98  and     eax, 180h
0x140006c9d  xor     eax, ecx
0x140006c9f  mov     ecx, eax
0x140006ca1  xor     ecx, ebx
0x140006ca3  and     ecx, r15d
0x140006ca6  xor     ecx, eax
0x140006ca8  mov     eax, ecx
0x140006caa  xor     eax, ebx
0x140006cac  and     eax, 1
0x140006caf  xor     eax, ecx
0x140006cb1  mov     ecx, eax
0x140006cb3  xor     ecx, ebx
0x140006cb5  and     ecx, 800h
0x140006cbb  xor     ecx, eax
0x140006cbd  or      ecx, 2
0x140006cc0  mov     [rdi], ecx
0x140006cc2  test    dl, 4
0x140006cc5  jnz     short loc_140006CD7
0x140006cc7  mov     eax, ebx
0x140006cc9  xor     eax, ecx
0x140006ccb  and     eax, 400h
0x140006cd0  xor     ecx, eax
0x140006cd2  or      ecx, 4
0x140006cd5  mov     [rdi], ecx
0x140006cd7  mov     eax, edx
0x140006cd9  lock cmpxchg [rsi], ecx
0x140006cdd  jnz     short loc_140006C82
0x140006cdf  test    dl, 4
0x140006ce2  jnz     short loc_140006CF1
0x140006ce4  mov     r8d, ebp
0x140006ce7  xor     edx, edx
0x140006ce9  mov     rcx, rsi
0x140006cec  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140006cf1  test    byte ptr [rdi], 2
0x140006cf4  jnz     short loc_140006D21
0x140006cf6  mov     eax, ebx
0x140006cf8  xor     eax, [rdi]
0x140006cfa  and     eax, 180h
0x140006cff  xor     eax, [rdi]
0x140006d01  mov     ecx, eax
0x140006d03  xor     ecx, ebx
0x140006d05  and     ecx, r15d
0x140006d08  xor     ecx, eax
0x140006d0a  mov     edx, ecx
0x140006d0c  xor     edx, ebx
0x140006d0e  and     edx, 1
0x140006d11  xor     edx, ecx
0x140006d13  mov     ecx, edx
0x140006d15  xor     ecx, ebx
0x140006d17  and     ecx, 800h
0x140006d1d  xor     ecx, edx
0x140006d1f  mov     [rdi], ecx
0x140006d21  mov     rax, rdi
0x140006d24  mov     rcx, [rsp+48h+var_20]
0x140006d29  xor     rcx, rsp; StackCookie
0x140006d2c  call    __security_check_cookie
0x140006d31  mov     rbx, [rsp+48h+arg_10]
0x140006d36  mov     rbp, [rsp+48h+arg_18]
0x140006d3b  add     rsp, 30h
0x140006d3f  pop     r15
0x140006d41  pop     rdi
0x140006d42  pop     rsi
0x140006d43  retn
```
