# wil::details::FeatureImpl<__WilFeatureTraits_Feature_LCTest>::GetCachedFeatureEnabledState(void)

- ea: `0x14000c50c`
- end: `0x14000c683`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_LCTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c68c`

## callees

- `0x140004d18`
- `0x140009b34`
- `0x14000c50c`
- `0x140017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_LCTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  bool v10; // zf
  signed __int32 v11; // edx
  signed __int32 v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_LCTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_LCTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(31072829, 3, &v14);
    }
    else
    {
      v6 = 0;
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
    v9 = *(_DWORD *)a2;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v9;
      *(_DWORD *)a2 = v9;
      if ( !v10 && (v9 & 2) == 0 )
      {
        v9 = (v9
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)v8)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)v8)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v9 ^ v8) & 0x180 ^ (v8 ^ v9 ^ (v9 ^ v8) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_LCTest__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_LCTest__descriptor, 3, v4);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v8
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v8
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v8
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v8
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v8
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x14000c50c  mov     [rsp+arg_8], rbx
0x14000c511  mov     [rsp+arg_10], rbp
0x14000c516  mov     [rsp+arg_0], rcx
0x14000c51b  push    rsi
0x14000c51c  push    rdi
0x14000c51d  push    r15
0x14000c51f  sub     rsp, 20h
0x14000c523  mov     rsi, cs:Feature_LCTest__descriptor
0x14000c52a  mov     rbx, rdx
0x14000c52d  mov     qword ptr [rdx], 0
0x14000c534  mov     eax, [rsi]
0x14000c536  mov     [rdx], eax
0x14000c538  and     eax, 6
0x14000c53b  cmp     al, 6
0x14000c53d  jz      loc_14000C66D
0x14000c543  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000c548  mov     ebp, eax
0x14000c54a  mov     dword ptr [rsp+38h+arg_0], 0
0x14000c552  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14000c559  test    rax, rax
0x14000c55c  jz      short loc_14000C576
0x14000c55e  lea     r8, [rsp+38h+arg_0]
0x14000c563  mov     edx, 3
0x14000c568  mov     ecx, 1DA223Dh
0x14000c56d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c572  mov     edx, eax
0x14000c574  jmp     short loc_14000C584
0x14000c576  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000c57d  test    rax, rax
0x14000c580  jnz     short loc_14000C55E
0x14000c582  xor     edx, edx
0x14000c584  mov     r8d, edx
0x14000c587  mov     eax, edx
0x14000c589  and     r8d, 0FFFFFF3Fh
0x14000c590  and     edx, 80h
0x14000c596  mov     ecx, r8d
0x14000c599  mov     r15d, 40h ; '@'
0x14000c59f  and     ecx, 3
0x14000c5a2  and     eax, r15d
0x14000c5a5  shl     ecx, 2
0x14000c5a8  or      ecx, eax
0x14000c5aa  shl     ecx, 2
0x14000c5ad  or      ecx, edx
0x14000c5af  lea     edi, ds:0[rcx*8]
0x14000c5b6  test    r8d, r8d
0x14000c5b9  jnz     short loc_14000C5C0
0x14000c5bb  mov     eax, r15d
0x14000c5be  jmp     short loc_14000C5CA
0x14000c5c0  xor     eax, eax
0x14000c5c2  cmp     r8d, 2
0x14000c5c6  cmovz   eax, r15d
0x14000c5ca  or      edi, eax
0x14000c5cc  mov     eax, [rbx]
0x14000c5ce  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000c5d3  mov     edx, eax
0x14000c5d5  mov     [rbx], eax
0x14000c5d7  jz      short loc_14000C607
0x14000c5d9  test    dl, 2
0x14000c5dc  jnz     short loc_14000C607
0x14000c5de  mov     eax, edi
0x14000c5e0  xor     eax, edx
0x14000c5e2  and     eax, 180h
0x14000c5e7  xor     eax, edx
0x14000c5e9  mov     ecx, eax
0x14000c5eb  xor     ecx, edi
0x14000c5ed  and     ecx, r15d
0x14000c5f0  xor     ecx, eax
0x14000c5f2  or      ecx, 1
0x14000c5f5  mov     eax, ecx
0x14000c5f7  xor     eax, edi
0x14000c5f9  and     eax, 800h
0x14000c5fe  xor     eax, ecx
0x14000c600  or      eax, 2
0x14000c603  mov     [rbx], eax
0x14000c605  jmp     short loc_14000C609
0x14000c607  mov     eax, edx
0x14000c609  mov     r8d, edx
0x14000c60c  and     r8d, 4
0x14000c610  jnz     short loc_14000C625
0x14000c612  mov     ecx, edi
0x14000c614  xor     ecx, eax
0x14000c616  and     ecx, 400h
0x14000c61c  xor     ecx, eax
0x14000c61e  or      ecx, 4
0x14000c621  mov     [rbx], ecx
0x14000c623  jmp     short loc_14000C627
0x14000c625  mov     ecx, eax
0x14000c627  mov     eax, edx
0x14000c629  lock cmpxchg [rsi], ecx
0x14000c62d  jnz     short loc_14000C5CE
0x14000c62f  test    r8d, r8d
0x14000c632  jnz     short loc_14000C644
0x14000c634  mov     r8d, ebp
0x14000c637  mov     edx, 3
0x14000c63c  mov     rcx, rsi
0x14000c63f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000c644  test    byte ptr [rbx], 2
0x14000c647  jnz     short loc_14000C66D
0x14000c649  mov     eax, [rbx]
0x14000c64b  xor     eax, edi
0x14000c64d  and     eax, 180h
0x14000c652  xor     eax, [rbx]
0x14000c654  mov     ecx, eax
0x14000c656  xor     ecx, edi
0x14000c658  and     ecx, r15d
0x14000c65b  xor     ecx, eax
0x14000c65d  or      ecx, 1
0x14000c660  mov     eax, ecx
0x14000c662  xor     eax, edi
0x14000c664  and     eax, 800h
0x14000c669  xor     eax, ecx
0x14000c66b  mov     [rbx], eax
0x14000c66d  mov     rbp, [rsp+38h+arg_10]
0x14000c672  mov     rax, rbx
0x14000c675  mov     rbx, [rsp+38h+arg_8]
0x14000c67a  add     rsp, 20h
0x14000c67e  pop     r15
0x14000c680  pop     rdi
0x14000c681  pop     rsi
0x14000c682  retn
```
