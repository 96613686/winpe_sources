# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GatePerf>::GetCachedFeatureEnabledState(void)

- ea: `0x180012b40`
- end: `0x180012cb7`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GatePerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012cc0`

## callees

- `0x1800119a8`
- `0x180012b40`
- `0x1800159a4`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GatePerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_GatePerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_GatePerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(54238000, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_GatePerf__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_GatePerf__descriptor, 3, v4);
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
0x180012b40  mov     [rsp+arg_8], rbx
0x180012b45  mov     [rsp+arg_10], rbp
0x180012b4a  mov     [rsp+arg_0], rcx
0x180012b4f  push    rsi
0x180012b50  push    rdi
0x180012b51  push    r15
0x180012b53  sub     rsp, 20h
0x180012b57  mov     rsi, cs:Feature_GatePerf__descriptor
0x180012b5e  mov     rbx, rdx
0x180012b61  mov     qword ptr [rdx], 0
0x180012b68  mov     eax, [rsi]
0x180012b6a  mov     [rdx], eax
0x180012b6c  and     eax, 6
0x180012b6f  cmp     al, 6
0x180012b71  jz      loc_180012CA1
0x180012b77  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012b7c  mov     ebp, eax
0x180012b7e  mov     dword ptr [rsp+38h+arg_0], 0
0x180012b86  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012b8d  test    rax, rax
0x180012b90  jz      short loc_180012BAA
0x180012b92  lea     r8, [rsp+38h+arg_0]
0x180012b97  mov     edx, 3
0x180012b9c  mov     ecx, 33B9B30h
0x180012ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ba6  mov     edx, eax
0x180012ba8  jmp     short loc_180012BB8
0x180012baa  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012bb1  test    rax, rax
0x180012bb4  jnz     short loc_180012B92
0x180012bb6  xor     edx, edx
0x180012bb8  mov     r8d, edx
0x180012bbb  mov     eax, edx
0x180012bbd  and     r8d, 0FFFFFF3Fh
0x180012bc4  and     edx, 80h
0x180012bca  mov     ecx, r8d
0x180012bcd  mov     r15d, 40h ; '@'
0x180012bd3  and     ecx, 3
0x180012bd6  and     eax, r15d
0x180012bd9  shl     ecx, 2
0x180012bdc  or      ecx, eax
0x180012bde  shl     ecx, 2
0x180012be1  or      ecx, edx
0x180012be3  lea     edi, ds:0[rcx*8]
0x180012bea  test    r8d, r8d
0x180012bed  jnz     short loc_180012BF4
0x180012bef  mov     eax, r15d
0x180012bf2  jmp     short loc_180012BFE
0x180012bf4  xor     eax, eax
0x180012bf6  cmp     r8d, 2
0x180012bfa  cmovz   eax, r15d
0x180012bfe  or      edi, eax
0x180012c00  mov     eax, [rbx]
0x180012c02  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012c07  mov     edx, eax
0x180012c09  mov     [rbx], eax
0x180012c0b  jz      short loc_180012C3B
0x180012c0d  test    dl, 2
0x180012c10  jnz     short loc_180012C3B
0x180012c12  mov     eax, edi
0x180012c14  xor     eax, edx
0x180012c16  and     eax, 180h
0x180012c1b  xor     eax, edx
0x180012c1d  mov     ecx, eax
0x180012c1f  xor     ecx, edi
0x180012c21  and     ecx, r15d
0x180012c24  xor     ecx, eax
0x180012c26  or      ecx, 1
0x180012c29  mov     eax, ecx
0x180012c2b  xor     eax, edi
0x180012c2d  and     eax, 800h
0x180012c32  xor     eax, ecx
0x180012c34  or      eax, 2
0x180012c37  mov     [rbx], eax
0x180012c39  jmp     short loc_180012C3D
0x180012c3b  mov     eax, edx
0x180012c3d  mov     r8d, edx
0x180012c40  and     r8d, 4
0x180012c44  jnz     short loc_180012C59
0x180012c46  mov     ecx, edi
0x180012c48  xor     ecx, eax
0x180012c4a  and     ecx, 400h
0x180012c50  xor     ecx, eax
0x180012c52  or      ecx, 4
0x180012c55  mov     [rbx], ecx
0x180012c57  jmp     short loc_180012C5B
0x180012c59  mov     ecx, eax
0x180012c5b  mov     eax, edx
0x180012c5d  lock cmpxchg [rsi], ecx
0x180012c61  jnz     short loc_180012C02
0x180012c63  test    r8d, r8d
0x180012c66  jnz     short loc_180012C78
0x180012c68  mov     r8d, ebp
0x180012c6b  mov     edx, 3
0x180012c70  mov     rcx, rsi
0x180012c73  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012c78  test    byte ptr [rbx], 2
0x180012c7b  jnz     short loc_180012CA1
0x180012c7d  mov     eax, [rbx]
0x180012c7f  xor     eax, edi
0x180012c81  and     eax, 180h
0x180012c86  xor     eax, [rbx]
0x180012c88  mov     ecx, eax
0x180012c8a  xor     ecx, edi
0x180012c8c  and     ecx, r15d
0x180012c8f  xor     ecx, eax
0x180012c91  or      ecx, 1
0x180012c94  mov     eax, ecx
0x180012c96  xor     eax, edi
0x180012c98  and     eax, 800h
0x180012c9d  xor     eax, ecx
0x180012c9f  mov     [rbx], eax
0x180012ca1  mov     rbp, [rsp+38h+arg_10]
0x180012ca6  mov     rax, rbx
0x180012ca9  mov     rbx, [rsp+38h+arg_8]
0x180012cae  add     rsp, 20h
0x180012cb2  pop     r15
0x180012cb4  pop     rdi
0x180012cb5  pop     rsi
0x180012cb6  retn
```
