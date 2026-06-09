# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_56888076>::GetCachedFeatureEnabledState(void)

- ea: `0x140007d34`
- end: `0x140007ec4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_56888076@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400057a8`
- `0x140007ecc`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140007d34`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_56888076>::GetCachedFeatureEnabledState(
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
    v7 = v6(56888076, 0, &v19);
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
0x140007d34  mov     [rsp+arg_10], rbx
0x140007d39  mov     [rsp+arg_18], rbp
0x140007d3e  push    rsi
0x140007d3f  push    rdi
0x140007d40  push    r15
0x140007d42  sub     rsp, 30h
0x140007d46  mov     rax, cs:__security_cookie
0x140007d4d  xor     rax, rsp
0x140007d50  mov     [rsp+48h+var_20], rax
0x140007d55  mov     qword ptr [rdx], 0
0x140007d5c  mov     rdi, rdx
0x140007d5f  mov     eax, [rcx]
0x140007d61  mov     rsi, rcx
0x140007d64  mov     [rdx], eax
0x140007d66  and     eax, 6
0x140007d69  cmp     al, 6
0x140007d6b  jz      loc_140007EA1
0x140007d71  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140007d76  mov     ebp, eax
0x140007d78  mov     [rsp+48h+var_28], 0
0x140007d80  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140007d87  mov     r15d, 40h ; '@'
0x140007d8d  test    rax, rax
0x140007d90  jnz     short loc_140007D9E
0x140007d92  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140007d99  test    rax, rax
0x140007d9c  jz      short loc_140007DEA
0x140007d9e  lea     r8, [rsp+48h+var_28]
0x140007da3  xor     edx, edx
0x140007da5  mov     ecx, 3640B0Ch
0x140007daa  call    _guard_dispatch_icall
0x140007daf  mov     r8d, eax
0x140007db2  mov     edx, eax
0x140007db4  and     r8d, 0FFFFFF3Fh
0x140007dbb  and     eax, r15d
0x140007dbe  and     edx, 80h
0x140007dc4  mov     ecx, r8d
0x140007dc7  and     ecx, 3
0x140007dca  shl     ecx, 2
0x140007dcd  or      ecx, eax
0x140007dcf  shl     ecx, 2
0x140007dd2  or      ecx, edx
0x140007dd4  shl     ecx, 3
0x140007dd7  test    r8d, r8d
0x140007dda  jz      short loc_140007DEC
0x140007ddc  xor     eax, eax
0x140007dde  cmp     r8d, 2
0x140007de2  cmovz   eax, r15d
0x140007de6  or      eax, ecx
0x140007de8  jmp     short loc_140007DEE
0x140007dea  xor     ecx, ecx
0x140007dec  mov     eax, ecx
0x140007dee  mov     ebx, eax
0x140007df0  shr     ebx, 6
0x140007df3  and     ebx, 1
0x140007df6  or      ebx, eax
0x140007df8  test    ebp, ebp
0x140007dfa  jnz     short loc_140007E00
0x140007dfc  mov     [rsp+48h+var_28], ebp
0x140007e00  mov     eax, [rdi]
0x140007e02  cmp     [rsp+48h+var_28], 0
0x140007e07  mov     edx, eax
0x140007e09  mov     [rdi], eax
0x140007e0b  mov     ecx, eax
0x140007e0d  jz      short loc_140007E42
0x140007e0f  test    dl, 2
0x140007e12  jnz     short loc_140007E42
0x140007e14  mov     eax, ebx
0x140007e16  xor     eax, ecx
0x140007e18  and     eax, 180h
0x140007e1d  xor     eax, ecx
0x140007e1f  mov     ecx, eax
0x140007e21  xor     ecx, ebx
0x140007e23  and     ecx, r15d
0x140007e26  xor     ecx, eax
0x140007e28  mov     eax, ecx
0x140007e2a  xor     eax, ebx
0x140007e2c  and     eax, 1
0x140007e2f  xor     eax, ecx
0x140007e31  mov     ecx, eax
0x140007e33  xor     ecx, ebx
0x140007e35  and     ecx, 800h
0x140007e3b  xor     ecx, eax
0x140007e3d  or      ecx, 2
0x140007e40  mov     [rdi], ecx
0x140007e42  test    dl, 4
0x140007e45  jnz     short loc_140007E57
0x140007e47  mov     eax, ebx
0x140007e49  xor     eax, ecx
0x140007e4b  and     eax, 400h
0x140007e50  xor     ecx, eax
0x140007e52  or      ecx, 4
0x140007e55  mov     [rdi], ecx
0x140007e57  mov     eax, edx
0x140007e59  lock cmpxchg [rsi], ecx
0x140007e5d  jnz     short loc_140007E02
0x140007e5f  test    dl, 4
0x140007e62  jnz     short loc_140007E71
0x140007e64  mov     r8d, ebp
0x140007e67  xor     edx, edx
0x140007e69  mov     rcx, rsi
0x140007e6c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140007e71  test    byte ptr [rdi], 2
0x140007e74  jnz     short loc_140007EA1
0x140007e76  mov     eax, ebx
0x140007e78  xor     eax, [rdi]
0x140007e7a  and     eax, 180h
0x140007e7f  xor     eax, [rdi]
0x140007e81  mov     ecx, eax
0x140007e83  xor     ecx, ebx
0x140007e85  and     ecx, r15d
0x140007e88  xor     ecx, eax
0x140007e8a  mov     edx, ecx
0x140007e8c  xor     edx, ebx
0x140007e8e  and     edx, 1
0x140007e91  xor     edx, ecx
0x140007e93  mov     ecx, edx
0x140007e95  xor     ecx, ebx
0x140007e97  and     ecx, 800h
0x140007e9d  xor     ecx, edx
0x140007e9f  mov     [rdi], ecx
0x140007ea1  mov     rax, rdi
0x140007ea4  mov     rcx, [rsp+48h+var_20]
0x140007ea9  xor     rcx, rsp; StackCookie
0x140007eac  call    __security_check_cookie
0x140007eb1  mov     rbx, [rsp+48h+arg_10]
0x140007eb6  mov     rbp, [rsp+48h+arg_18]
0x140007ebb  add     rsp, 30h
0x140007ebf  pop     r15
0x140007ec1  pop     rdi
0x140007ec2  pop     rsi
0x140007ec3  retn
```
