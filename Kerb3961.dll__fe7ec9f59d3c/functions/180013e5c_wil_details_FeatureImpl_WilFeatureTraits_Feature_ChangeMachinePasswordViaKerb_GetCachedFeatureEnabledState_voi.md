# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb>::GetCachedFeatureEnabledState(void)

- ea: `0x180013e5c`
- end: `0x180014017`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800180e4`

## callees

- `0x180013584`
- `0x180013e5c`
- `0x180017240`
- `0x18001e010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
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
  v3 = *(_DWORD *)Feature_ChangeMachinePasswordViaKerb__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ChangeMachinePasswordViaKerb__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v19) = 0;
  v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  v6 = 0;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(45832080, 0, &v19);
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
            (volatile signed __int32 *)Feature_ChangeMachinePasswordViaKerb__descriptor,
            v17,
            v12);
  }
  while ( v14 != v12 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_ChangeMachinePasswordViaKerb__descriptor,
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
0x180013e5c  mov     [rsp+arg_8], rbx
0x180013e61  mov     [rsp+arg_10], rbp
0x180013e66  mov     [rsp+arg_0], rcx
0x180013e6b  push    rsi
0x180013e6c  push    rdi
0x180013e6d  push    r15
0x180013e6f  sub     rsp, 20h
0x180013e73  mov     rsi, cs:Feature_ChangeMachinePasswordViaKerb__descriptor
0x180013e7a  mov     rdi, rdx
0x180013e7d  mov     qword ptr [rdx], 0
0x180013e84  mov     eax, [rsi]
0x180013e86  mov     [rdx], eax
0x180013e88  and     eax, 6
0x180013e8b  cmp     al, 6
0x180013e8d  jz      loc_180014001
0x180013e93  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013e98  mov     ebp, eax
0x180013e9a  mov     dword ptr [rsp+38h+arg_0], 0
0x180013ea2  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180013ea9  xor     edx, edx
0x180013eab  test    rax, rax
0x180013eae  jnz     short loc_180013EBC
0x180013eb0  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180013eb7  test    rax, rax
0x180013eba  jz      short loc_180013ECD
0x180013ebc  lea     r8, [rsp+38h+arg_0]
0x180013ec1  mov     ecx, 2BB5790h
0x180013ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ecb  mov     edx, eax
0x180013ecd  mov     r8d, edx
0x180013ed0  mov     eax, edx
0x180013ed2  and     r8d, 0FFFFFF3Fh
0x180013ed9  and     edx, 80h
0x180013edf  mov     ecx, r8d
0x180013ee2  mov     r15d, 40h ; '@'
0x180013ee8  and     ecx, 3
0x180013eeb  and     eax, r15d
0x180013eee  shl     ecx, 2
0x180013ef1  or      ecx, eax
0x180013ef3  shl     ecx, 2
0x180013ef6  or      ecx, edx
0x180013ef8  lea     ebx, ds:0[rcx*8]
0x180013eff  test    r8d, r8d
0x180013f02  jnz     short loc_180013F09
0x180013f04  mov     eax, r15d
0x180013f07  jmp     short loc_180013F13
0x180013f09  xor     eax, eax
0x180013f0b  cmp     r8d, 2
0x180013f0f  cmovz   eax, r15d
0x180013f13  or      ebx, eax
0x180013f15  mov     edx, 0C00h
0x180013f1a  mov     ecx, ebx
0x180013f1c  mov     eax, ebx
0x180013f1e  and     ecx, r15d
0x180013f21  and     eax, edx
0x180013f23  cmp     eax, edx
0x180013f25  jnz     short loc_180013F2B
0x180013f27  mov     al, 1
0x180013f29  jmp     short loc_180013F31
0x180013f2b  test    ecx, ecx
0x180013f2d  jnz     short loc_180013F3D
0x180013f2f  xor     al, al
0x180013f31  test    ecx, ecx
0x180013f33  jz      short loc_180013F39
0x180013f35  test    al, al
0x180013f37  jnz     short loc_180013F3D
0x180013f39  xor     eax, eax
0x180013f3b  jmp     short loc_180013F42
0x180013f3d  mov     eax, 1
0x180013f42  or      ebx, eax
0x180013f44  test    ebp, ebp
0x180013f46  jnz     short loc_180013F4C
0x180013f48  mov     dword ptr [rsp+38h+arg_0], ebp
0x180013f4c  mov     eax, [rdi]
0x180013f4e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180013f53  mov     edx, eax
0x180013f55  mov     [rdi], eax
0x180013f57  jz      short loc_180013F94
0x180013f59  test    dl, 2
0x180013f5c  jnz     short loc_180013F94
0x180013f5e  mov     eax, ebx
0x180013f60  xor     eax, edx
0x180013f62  and     eax, 180h
0x180013f67  xor     eax, edx
0x180013f69  mov     ecx, eax
0x180013f6b  xor     ecx, ebx
0x180013f6d  and     ecx, r15d
0x180013f70  xor     ecx, eax
0x180013f72  mov     eax, ecx
0x180013f74  xor     eax, ebx
0x180013f76  and     eax, 1
0x180013f79  xor     eax, ecx
0x180013f7b  mov     r8d, eax
0x180013f7e  xor     r8d, ebx
0x180013f81  and     r8d, 800h
0x180013f88  xor     r8d, eax
0x180013f8b  or      r8d, 2
0x180013f8f  mov     [rdi], r8d
0x180013f92  jmp     short loc_180013F97
0x180013f94  mov     r8d, edx
0x180013f97  mov     r9d, edx
0x180013f9a  and     r9d, 4
0x180013f9e  jnz     short loc_180013FB5
0x180013fa0  mov     ecx, ebx
0x180013fa2  xor     ecx, r8d
0x180013fa5  and     ecx, 400h
0x180013fab  xor     ecx, r8d
0x180013fae  or      ecx, 4
0x180013fb1  mov     [rdi], ecx
0x180013fb3  jmp     short loc_180013FB8
0x180013fb5  mov     ecx, r8d
0x180013fb8  mov     eax, edx
0x180013fba  lock cmpxchg [rsi], ecx
0x180013fbe  jnz     short loc_180013F4E
0x180013fc0  test    r9d, r9d
0x180013fc3  jnz     short loc_180013FD2
0x180013fc5  mov     r8d, ebp
0x180013fc8  xor     edx, edx
0x180013fca  mov     rcx, rsi
0x180013fcd  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013fd2  test    byte ptr [rdi], 2
0x180013fd5  jnz     short loc_180014001
0x180013fd7  mov     eax, [rdi]
0x180013fd9  xor     eax, ebx
0x180013fdb  and     eax, 180h
0x180013fe0  xor     eax, [rdi]
0x180013fe2  mov     ecx, eax
0x180013fe4  xor     ecx, ebx
0x180013fe6  and     ecx, r15d
0x180013fe9  xor     ecx, eax
0x180013feb  mov     edx, ecx
0x180013fed  xor     edx, ebx
0x180013fef  and     edx, 1
0x180013ff2  xor     edx, ecx
0x180013ff4  mov     eax, edx
0x180013ff6  xor     eax, ebx
0x180013ff8  and     eax, 800h
0x180013ffd  xor     eax, edx
0x180013fff  mov     [rdi], eax
0x180014001  mov     rbx, [rsp+38h+arg_8]
0x180014006  mov     rax, rdi
0x180014009  mov     rbp, [rsp+38h+arg_10]
0x18001400e  add     rsp, 20h
0x180014012  pop     r15
0x180014014  pop     rdi
0x180014015  pop     rsi
0x180014016  retn
```
