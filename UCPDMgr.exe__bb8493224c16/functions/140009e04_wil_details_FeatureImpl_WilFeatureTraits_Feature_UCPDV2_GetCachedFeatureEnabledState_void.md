# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPDV2>::GetCachedFeatureEnabledState(void)

- ea: `0x140009e04`
- end: `0x140009f95`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPDV2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `401`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005b2c`
- `0x140009f9c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140009e04`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPDV2>::GetCachedFeatureEnabledState(
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
    v7 = v6(46591190, 0, &v18);
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
0x140009e04  mov     [rsp+arg_10], rbx
0x140009e09  mov     [rsp+arg_18], rbp
0x140009e0e  push    rsi
0x140009e0f  push    rdi
0x140009e10  push    r15
0x140009e12  sub     rsp, 30h
0x140009e16  mov     rax, cs:__security_cookie
0x140009e1d  xor     rax, rsp
0x140009e20  mov     [rsp+48h+var_20], rax
0x140009e25  mov     qword ptr [rdx], 0
0x140009e2c  mov     rdi, rdx
0x140009e2f  mov     eax, [rcx]
0x140009e31  mov     rsi, rcx
0x140009e34  mov     [rdx], eax
0x140009e36  and     eax, 6
0x140009e39  cmp     al, 6
0x140009e3b  jz      loc_140009F72
0x140009e41  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140009e46  mov     ebp, eax
0x140009e48  mov     [rsp+48h+var_28], 0
0x140009e50  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140009e57  mov     r15d, 40h ; '@'
0x140009e5d  test    rax, rax
0x140009e60  jnz     short loc_140009E6E
0x140009e62  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140009e69  test    rax, rax
0x140009e6c  jz      short loc_140009EB8
0x140009e6e  lea     r8, [rsp+48h+var_28]
0x140009e73  xor     edx, edx
0x140009e75  mov     ecx, 2C6ECD6h
0x140009e7a  call    _guard_dispatch_icall
0x140009e7f  mov     r8d, eax
0x140009e82  mov     edx, eax
0x140009e84  and     r8d, 0FFFFFF3Fh
0x140009e8b  and     eax, r15d
0x140009e8e  and     edx, 80h
0x140009e94  mov     ecx, r8d
0x140009e97  and     ecx, 3
0x140009e9a  shl     ecx, 2
0x140009e9d  or      ecx, eax
0x140009e9f  shl     ecx, 2
0x140009ea2  or      ecx, edx
0x140009ea4  shl     ecx, 3
0x140009ea7  test    r8d, r8d
0x140009eaa  jz      short loc_140009EBA
0x140009eac  xor     eax, eax
0x140009eae  cmp     r8d, 2
0x140009eb2  cmovz   eax, r15d
0x140009eb6  jmp     short loc_140009EBD
0x140009eb8  xor     ecx, ecx
0x140009eba  mov     eax, r15d
0x140009ebd  or      ecx, eax
0x140009ebf  mov     ebx, ecx
0x140009ec1  shr     ebx, 6
0x140009ec4  and     ebx, 1
0x140009ec7  or      ebx, ecx
0x140009ec9  test    ebp, ebp
0x140009ecb  jnz     short loc_140009ED1
0x140009ecd  mov     [rsp+48h+var_28], ebp
0x140009ed1  mov     eax, [rdi]
0x140009ed3  cmp     [rsp+48h+var_28], 0
0x140009ed8  mov     edx, eax
0x140009eda  mov     [rdi], eax
0x140009edc  mov     ecx, eax
0x140009ede  jz      short loc_140009F13
0x140009ee0  test    dl, 2
0x140009ee3  jnz     short loc_140009F13
0x140009ee5  mov     eax, ebx
0x140009ee7  xor     eax, ecx
0x140009ee9  and     eax, 180h
0x140009eee  xor     eax, ecx
0x140009ef0  mov     ecx, eax
0x140009ef2  xor     ecx, ebx
0x140009ef4  and     ecx, r15d
0x140009ef7  xor     ecx, eax
0x140009ef9  mov     eax, ecx
0x140009efb  xor     eax, ebx
0x140009efd  and     eax, 1
0x140009f00  xor     eax, ecx
0x140009f02  mov     ecx, eax
0x140009f04  xor     ecx, ebx
0x140009f06  and     ecx, 800h
0x140009f0c  xor     ecx, eax
0x140009f0e  or      ecx, 2
0x140009f11  mov     [rdi], ecx
0x140009f13  test    dl, 4
0x140009f16  jnz     short loc_140009F28
0x140009f18  mov     eax, ebx
0x140009f1a  xor     eax, ecx
0x140009f1c  and     eax, 400h
0x140009f21  xor     ecx, eax
0x140009f23  or      ecx, 4
0x140009f26  mov     [rdi], ecx
0x140009f28  mov     eax, edx
0x140009f2a  lock cmpxchg [rsi], ecx
0x140009f2e  jnz     short loc_140009ED3
0x140009f30  test    dl, 4
0x140009f33  jnz     short loc_140009F42
0x140009f35  mov     r8d, ebp
0x140009f38  xor     edx, edx
0x140009f3a  mov     rcx, rsi
0x140009f3d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140009f42  test    byte ptr [rdi], 2
0x140009f45  jnz     short loc_140009F72
0x140009f47  mov     eax, ebx
0x140009f49  xor     eax, [rdi]
0x140009f4b  and     eax, 180h
0x140009f50  xor     eax, [rdi]
0x140009f52  mov     ecx, eax
0x140009f54  xor     ecx, ebx
0x140009f56  and     ecx, r15d
0x140009f59  xor     ecx, eax
0x140009f5b  mov     edx, ecx
0x140009f5d  xor     edx, ebx
0x140009f5f  and     edx, 1
0x140009f62  xor     edx, ecx
0x140009f64  mov     ecx, edx
0x140009f66  xor     ecx, ebx
0x140009f68  and     ecx, 800h
0x140009f6e  xor     ecx, edx
0x140009f70  mov     [rdi], ecx
0x140009f72  mov     rax, rdi
0x140009f75  mov     rcx, [rsp+48h+var_20]
0x140009f7a  xor     rcx, rsp; StackCookie
0x140009f7d  call    __security_check_cookie
0x140009f82  mov     rbx, [rsp+48h+arg_10]
0x140009f87  mov     rbp, [rsp+48h+arg_18]
0x140009f8c  add     rsp, 30h
0x140009f90  pop     r15
0x140009f92  pop     rdi
0x140009f93  pop     rsi
0x140009f94  retn
```
