# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow>::GetCachedFeatureEnabledState(void)

- ea: `0x180004b44`
- end: `0x180004cff`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `443`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800076b0`
- `0x1800091e4`

## callees

- `0x1800045f8`
- `0x180004b44`
- `0x1800084e4`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // al
  int v10; // eax
  int v11; // ebx
  signed __int32 v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  int v15; // r8d
  int v16; // r9d
  signed __int32 v17; // ecx
  wil::details *v19; // [rsp+40h] [rbp+8h] BYREF

  v19 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v19) = 0;
  v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  v6 = 0;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(60900037, 0, &v19);
  }
  if ( (v6 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (v6 & 0xFFFFFF3F) == 2 )
      v7 = 64;
  }
  else
  {
    v7 = 64;
  }
  v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
  }
  else
  {
    if ( (v8 & 0x40) != 0 )
    {
LABEL_16:
      v10 = 1;
      goto LABEL_17;
    }
    v9 = 0;
  }
  if ( (v8 & 0x40) != 0 && v9 )
    goto LABEL_16;
  v10 = 0;
LABEL_17:
  v11 = v10 | v8;
  if ( !v4 )
    LODWORD(v19) = 0;
  v12 = *(_DWORD *)a2;
  do
  {
    v13 = (_DWORD)v19 == 0;
    v14 = v12;
    *(_DWORD *)a2 = v12;
    if ( v13 || (v12 & 2) != 0 )
    {
      v15 = v12;
    }
    else
    {
      v15 = v12
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v11)
          & 0x180
          ^ (v11
           ^ v12
           ^ ((unsigned __int16)v12
            ^ (unsigned __int16)v11)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v11
           ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v11
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v11)
                              & 0x180
                              ^ (v11
                               ^ v12
                               ^ (v12
                                ^ v11)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v11
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    v16 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v17 = v15;
    }
    else
    {
      v17 = v15 ^ ((unsigned __int16)v15 ^ (unsigned __int16)v11) & 0x400 | 4;
      *(_DWORD *)a2 = v17;
    }
    v12 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow__descriptor,
            v17,
            v12);
  }
  while ( v14 != v12 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow__descriptor,
      0,
      v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v11
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v11
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v11
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v11
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v11
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v11
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v11
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v11
                       ^ (unsigned __int8)*(_DWORD *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x180004b44  mov     [rsp+arg_8], rbx
0x180004b49  mov     [rsp+arg_10], rbp
0x180004b4e  mov     [rsp+arg_0], rcx
0x180004b53  push    rsi
0x180004b54  push    rdi
0x180004b55  push    r15
0x180004b57  sub     rsp, 20h
0x180004b5b  mov     rsi, cs:Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow__descriptor
0x180004b62  mov     rdi, rdx
0x180004b65  mov     qword ptr [rdx], 0
0x180004b6c  mov     eax, [rsi]
0x180004b6e  mov     [rdx], eax
0x180004b70  and     eax, 6
0x180004b73  cmp     al, 6
0x180004b75  jz      loc_180004CE9
0x180004b7b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180004b80  mov     ebp, eax
0x180004b82  mov     dword ptr [rsp+38h+arg_0], 0
0x180004b8a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180004b91  xor     edx, edx
0x180004b93  test    rax, rax
0x180004b96  jnz     short loc_180004BA4
0x180004b98  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180004b9f  test    rax, rax
0x180004ba2  jz      short loc_180004BB5
0x180004ba4  lea     r8, [rsp+38h+arg_0]
0x180004ba9  mov     ecx, 3A142C5h
0x180004bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bb3  mov     edx, eax
0x180004bb5  mov     r8d, edx
0x180004bb8  mov     eax, edx
0x180004bba  and     r8d, 0FFFFFF3Fh
0x180004bc1  and     edx, 80h
0x180004bc7  mov     ecx, r8d
0x180004bca  mov     r15d, 40h ; '@'
0x180004bd0  and     ecx, 3
0x180004bd3  and     eax, r15d
0x180004bd6  shl     ecx, 2
0x180004bd9  or      ecx, eax
0x180004bdb  shl     ecx, 2
0x180004bde  or      ecx, edx
0x180004be0  lea     ebx, ds:0[rcx*8]
0x180004be7  test    r8d, r8d
0x180004bea  jnz     short loc_180004BF1
0x180004bec  mov     eax, r15d
0x180004bef  jmp     short loc_180004BFB
0x180004bf1  xor     eax, eax
0x180004bf3  cmp     r8d, 2
0x180004bf7  cmovz   eax, r15d
0x180004bfb  or      ebx, eax
0x180004bfd  mov     edx, 0C00h
0x180004c02  mov     ecx, ebx
0x180004c04  mov     eax, ebx
0x180004c06  and     ecx, r15d
0x180004c09  and     eax, edx
0x180004c0b  cmp     eax, edx
0x180004c0d  jnz     short loc_180004C13
0x180004c0f  mov     al, 1
0x180004c11  jmp     short loc_180004C19
0x180004c13  test    ecx, ecx
0x180004c15  jnz     short loc_180004C25
0x180004c17  xor     al, al
0x180004c19  test    ecx, ecx
0x180004c1b  jz      short loc_180004C21
0x180004c1d  test    al, al
0x180004c1f  jnz     short loc_180004C25
0x180004c21  xor     eax, eax
0x180004c23  jmp     short loc_180004C2A
0x180004c25  mov     eax, 1
0x180004c2a  or      ebx, eax
0x180004c2c  test    ebp, ebp
0x180004c2e  jnz     short loc_180004C34
0x180004c30  mov     dword ptr [rsp+38h+arg_0], ebp
0x180004c34  mov     eax, [rdi]
0x180004c36  cmp     dword ptr [rsp+38h+arg_0], 0
0x180004c3b  mov     edx, eax
0x180004c3d  mov     [rdi], eax
0x180004c3f  jz      short loc_180004C7C
0x180004c41  test    dl, 2
0x180004c44  jnz     short loc_180004C7C
0x180004c46  mov     eax, ebx
0x180004c48  xor     eax, edx
0x180004c4a  and     eax, 180h
0x180004c4f  xor     eax, edx
0x180004c51  mov     ecx, eax
0x180004c53  xor     ecx, ebx
0x180004c55  and     ecx, r15d
0x180004c58  xor     ecx, eax
0x180004c5a  mov     eax, ecx
0x180004c5c  xor     eax, ebx
0x180004c5e  and     eax, 1
0x180004c61  xor     eax, ecx
0x180004c63  mov     r8d, eax
0x180004c66  xor     r8d, ebx
0x180004c69  and     r8d, 800h
0x180004c70  xor     r8d, eax
0x180004c73  or      r8d, 2
0x180004c77  mov     [rdi], r8d
0x180004c7a  jmp     short loc_180004C7F
0x180004c7c  mov     r8d, edx
0x180004c7f  mov     r9d, edx
0x180004c82  and     r9d, 4
0x180004c86  jnz     short loc_180004C9D
0x180004c88  mov     ecx, ebx
0x180004c8a  xor     ecx, r8d
0x180004c8d  and     ecx, 400h
0x180004c93  xor     ecx, r8d
0x180004c96  or      ecx, 4
0x180004c99  mov     [rdi], ecx
0x180004c9b  jmp     short loc_180004CA0
0x180004c9d  mov     ecx, r8d
0x180004ca0  mov     eax, edx
0x180004ca2  lock cmpxchg [rsi], ecx
0x180004ca6  jnz     short loc_180004C36
0x180004ca8  test    r9d, r9d
0x180004cab  jnz     short loc_180004CBA
0x180004cad  mov     r8d, ebp
0x180004cb0  xor     edx, edx
0x180004cb2  mov     rcx, rsi
0x180004cb5  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180004cba  test    byte ptr [rdi], 2
0x180004cbd  jnz     short loc_180004CE9
0x180004cbf  mov     eax, [rdi]
0x180004cc1  xor     eax, ebx
0x180004cc3  and     eax, 180h
0x180004cc8  xor     eax, [rdi]
0x180004cca  mov     ecx, eax
0x180004ccc  xor     ecx, ebx
0x180004cce  and     ecx, r15d
0x180004cd1  xor     ecx, eax
0x180004cd3  mov     edx, ecx
0x180004cd5  xor     edx, ebx
0x180004cd7  and     edx, 1
0x180004cda  xor     edx, ecx
0x180004cdc  mov     eax, edx
0x180004cde  xor     eax, ebx
0x180004ce0  and     eax, 800h
0x180004ce5  xor     eax, edx
0x180004ce7  mov     [rdi], eax
0x180004ce9  mov     rbx, [rsp+38h+arg_8]
0x180004cee  mov     rax, rdi
0x180004cf1  mov     rbp, [rsp+38h+arg_10]
0x180004cf6  add     rsp, 20h
0x180004cfa  pop     r15
0x180004cfc  pop     rdi
0x180004cfd  pop     rsi
0x180004cfe  retn
```
