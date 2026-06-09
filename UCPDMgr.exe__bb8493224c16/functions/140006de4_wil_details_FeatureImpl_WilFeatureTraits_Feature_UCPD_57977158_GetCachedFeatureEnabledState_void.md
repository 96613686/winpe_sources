# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_57977158>::GetCachedFeatureEnabledState(void)

- ea: `0x140006de4`
- end: `0x140006f74`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_57977158@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005604`
- `0x140006f7c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140006de4`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_57977158>::GetCachedFeatureEnabledState(
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
    v7 = v6(57977158, 0, &v19);
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
0x140006de4  mov     [rsp+arg_10], rbx
0x140006de9  mov     [rsp+arg_18], rbp
0x140006dee  push    rsi
0x140006def  push    rdi
0x140006df0  push    r15
0x140006df2  sub     rsp, 30h
0x140006df6  mov     rax, cs:__security_cookie
0x140006dfd  xor     rax, rsp
0x140006e00  mov     [rsp+48h+var_20], rax
0x140006e05  mov     qword ptr [rdx], 0
0x140006e0c  mov     rdi, rdx
0x140006e0f  mov     eax, [rcx]
0x140006e11  mov     rsi, rcx
0x140006e14  mov     [rdx], eax
0x140006e16  and     eax, 6
0x140006e19  cmp     al, 6
0x140006e1b  jz      loc_140006F51
0x140006e21  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140006e26  mov     ebp, eax
0x140006e28  mov     [rsp+48h+var_28], 0
0x140006e30  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140006e37  mov     r15d, 40h ; '@'
0x140006e3d  test    rax, rax
0x140006e40  jnz     short loc_140006E4E
0x140006e42  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140006e49  test    rax, rax
0x140006e4c  jz      short loc_140006E9A
0x140006e4e  lea     r8, [rsp+48h+var_28]
0x140006e53  xor     edx, edx
0x140006e55  mov     ecx, 374A946h
0x140006e5a  call    _guard_dispatch_icall
0x140006e5f  mov     r8d, eax
0x140006e62  mov     edx, eax
0x140006e64  and     r8d, 0FFFFFF3Fh
0x140006e6b  and     eax, r15d
0x140006e6e  and     edx, 80h
0x140006e74  mov     ecx, r8d
0x140006e77  and     ecx, 3
0x140006e7a  shl     ecx, 2
0x140006e7d  or      ecx, eax
0x140006e7f  shl     ecx, 2
0x140006e82  or      ecx, edx
0x140006e84  shl     ecx, 3
0x140006e87  test    r8d, r8d
0x140006e8a  jz      short loc_140006E9C
0x140006e8c  xor     eax, eax
0x140006e8e  cmp     r8d, 2
0x140006e92  cmovz   eax, r15d
0x140006e96  or      eax, ecx
0x140006e98  jmp     short loc_140006E9E
0x140006e9a  xor     ecx, ecx
0x140006e9c  mov     eax, ecx
0x140006e9e  mov     ebx, eax
0x140006ea0  shr     ebx, 6
0x140006ea3  and     ebx, 1
0x140006ea6  or      ebx, eax
0x140006ea8  test    ebp, ebp
0x140006eaa  jnz     short loc_140006EB0
0x140006eac  mov     [rsp+48h+var_28], ebp
0x140006eb0  mov     eax, [rdi]
0x140006eb2  cmp     [rsp+48h+var_28], 0
0x140006eb7  mov     edx, eax
0x140006eb9  mov     [rdi], eax
0x140006ebb  mov     ecx, eax
0x140006ebd  jz      short loc_140006EF2
0x140006ebf  test    dl, 2
0x140006ec2  jnz     short loc_140006EF2
0x140006ec4  mov     eax, ebx
0x140006ec6  xor     eax, ecx
0x140006ec8  and     eax, 180h
0x140006ecd  xor     eax, ecx
0x140006ecf  mov     ecx, eax
0x140006ed1  xor     ecx, ebx
0x140006ed3  and     ecx, r15d
0x140006ed6  xor     ecx, eax
0x140006ed8  mov     eax, ecx
0x140006eda  xor     eax, ebx
0x140006edc  and     eax, 1
0x140006edf  xor     eax, ecx
0x140006ee1  mov     ecx, eax
0x140006ee3  xor     ecx, ebx
0x140006ee5  and     ecx, 800h
0x140006eeb  xor     ecx, eax
0x140006eed  or      ecx, 2
0x140006ef0  mov     [rdi], ecx
0x140006ef2  test    dl, 4
0x140006ef5  jnz     short loc_140006F07
0x140006ef7  mov     eax, ebx
0x140006ef9  xor     eax, ecx
0x140006efb  and     eax, 400h
0x140006f00  xor     ecx, eax
0x140006f02  or      ecx, 4
0x140006f05  mov     [rdi], ecx
0x140006f07  mov     eax, edx
0x140006f09  lock cmpxchg [rsi], ecx
0x140006f0d  jnz     short loc_140006EB2
0x140006f0f  test    dl, 4
0x140006f12  jnz     short loc_140006F21
0x140006f14  mov     r8d, ebp
0x140006f17  xor     edx, edx
0x140006f19  mov     rcx, rsi
0x140006f1c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140006f21  test    byte ptr [rdi], 2
0x140006f24  jnz     short loc_140006F51
0x140006f26  mov     eax, ebx
0x140006f28  xor     eax, [rdi]
0x140006f2a  and     eax, 180h
0x140006f2f  xor     eax, [rdi]
0x140006f31  mov     ecx, eax
0x140006f33  xor     ecx, ebx
0x140006f35  and     ecx, r15d
0x140006f38  xor     ecx, eax
0x140006f3a  mov     edx, ecx
0x140006f3c  xor     edx, ebx
0x140006f3e  and     edx, 1
0x140006f41  xor     edx, ecx
0x140006f43  mov     ecx, edx
0x140006f45  xor     ecx, ebx
0x140006f47  and     ecx, 800h
0x140006f4d  xor     ecx, edx
0x140006f4f  mov     [rdi], ecx
0x140006f51  mov     rax, rdi
0x140006f54  mov     rcx, [rsp+48h+var_20]
0x140006f59  xor     rcx, rsp; StackCookie
0x140006f5c  call    __security_check_cookie
0x140006f61  mov     rbx, [rsp+48h+arg_10]
0x140006f66  mov     rbp, [rsp+48h+arg_18]
0x140006f6b  add     rsp, 30h
0x140006f6f  pop     r15
0x140006f71  pop     rdi
0x140006f72  pop     rsi
0x140006f73  retn
```
