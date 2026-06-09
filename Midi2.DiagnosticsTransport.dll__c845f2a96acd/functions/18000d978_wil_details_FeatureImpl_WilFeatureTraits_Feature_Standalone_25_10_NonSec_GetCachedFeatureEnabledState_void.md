# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000d978`
- end: `0x18000dae5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f020`

## callees

- `0x18000d6e0`
- `0x18000d978`
- `0x18000ff38`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036792, 3, &v14);
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
            ^ ((unsigned __int16)v8
             ^ (unsigned __int16)v9)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v8
              ^ (unsigned __int16)v9)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v8 ^ v9) & 0x180 ^ (v8 ^ v9 ^ (v8 ^ v9) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      v12 = v9;
      if ( (v11 & 4) == 0 )
      {
        v12 = v9 ^ ((unsigned __int16)v8 ^ (unsigned __int16)v9) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
        3,
        v4);
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
0x18000d978  mov     [rsp+arg_8], rbx
0x18000d97d  mov     [rsp+arg_10], rbp
0x18000d982  mov     [rsp+arg_0], rcx
0x18000d987  push    rsi
0x18000d988  push    rdi
0x18000d989  push    r15
0x18000d98b  sub     rsp, 20h
0x18000d98f  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18000d996  mov     rbx, rdx
0x18000d999  mov     qword ptr [rdx], 0
0x18000d9a0  mov     eax, [rsi]
0x18000d9a2  mov     [rdx], eax
0x18000d9a4  and     eax, 6
0x18000d9a7  cmp     al, 6
0x18000d9a9  jz      loc_18000DACF
0x18000d9af  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000d9b4  mov     ebp, eax
0x18000d9b6  mov     dword ptr [rsp+38h+arg_0], 0
0x18000d9be  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000d9c5  test    rax, rax
0x18000d9c8  jz      short loc_18000D9E2
0x18000d9ca  lea     r8, [rsp+38h+arg_0]
0x18000d9cf  mov     edx, 3
0x18000d9d4  mov     ecx, 2AF34F8h
0x18000d9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9de  mov     edx, eax
0x18000d9e0  jmp     short loc_18000D9F0
0x18000d9e2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000d9e9  test    rax, rax
0x18000d9ec  jnz     short loc_18000D9CA
0x18000d9ee  xor     edx, edx
0x18000d9f0  mov     r8d, edx
0x18000d9f3  mov     eax, edx
0x18000d9f5  and     r8d, 0FFFFFF3Fh
0x18000d9fc  and     edx, 80h
0x18000da02  mov     ecx, r8d
0x18000da05  mov     r15d, 40h ; '@'
0x18000da0b  and     ecx, 3
0x18000da0e  and     eax, r15d
0x18000da11  shl     ecx, 2
0x18000da14  or      ecx, eax
0x18000da16  shl     ecx, 2
0x18000da19  or      ecx, edx
0x18000da1b  lea     edi, ds:0[rcx*8]
0x18000da22  test    r8d, r8d
0x18000da25  jnz     short loc_18000DA2C
0x18000da27  mov     eax, r15d
0x18000da2a  jmp     short loc_18000DA36
0x18000da2c  xor     eax, eax
0x18000da2e  cmp     r8d, 2
0x18000da32  cmovz   eax, r15d
0x18000da36  or      edi, eax
0x18000da38  mov     eax, [rbx]
0x18000da3a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000da3f  mov     edx, eax
0x18000da41  mov     [rbx], eax
0x18000da43  jz      short loc_18000DA6F
0x18000da45  test    dl, 2
0x18000da48  jnz     short loc_18000DA6F
0x18000da4a  xor     eax, edi
0x18000da4c  and     eax, 180h
0x18000da51  xor     eax, edx
0x18000da53  mov     ecx, eax
0x18000da55  xor     ecx, edi
0x18000da57  and     ecx, r15d
0x18000da5a  xor     ecx, eax
0x18000da5c  or      ecx, 1
0x18000da5f  mov     eax, ecx
0x18000da61  xor     eax, edi
0x18000da63  and     eax, 800h
0x18000da68  xor     eax, ecx
0x18000da6a  or      eax, 2
0x18000da6d  mov     [rbx], eax
0x18000da6f  mov     r8d, edx
0x18000da72  mov     ecx, eax
0x18000da74  and     r8d, 4
0x18000da78  jnz     short loc_18000DA89
0x18000da7a  xor     ecx, edi
0x18000da7c  and     ecx, 400h
0x18000da82  xor     ecx, eax
0x18000da84  or      ecx, 4
0x18000da87  mov     [rbx], ecx
0x18000da89  mov     eax, edx
0x18000da8b  lock cmpxchg [rsi], ecx
0x18000da8f  jnz     short loc_18000DA3A
0x18000da91  test    r8d, r8d
0x18000da94  jnz     short loc_18000DAA6
0x18000da96  mov     r8d, ebp
0x18000da99  mov     edx, 3
0x18000da9e  mov     rcx, rsi
0x18000daa1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000daa6  test    byte ptr [rbx], 2
0x18000daa9  jnz     short loc_18000DACF
0x18000daab  mov     eax, [rbx]
0x18000daad  xor     eax, edi
0x18000daaf  and     eax, 180h
0x18000dab4  xor     eax, [rbx]
0x18000dab6  mov     ecx, eax
0x18000dab8  xor     ecx, edi
0x18000daba  and     ecx, r15d
0x18000dabd  xor     ecx, eax
0x18000dabf  or      ecx, 1
0x18000dac2  mov     eax, ecx
0x18000dac4  xor     eax, edi
0x18000dac6  and     eax, 800h
0x18000dacb  xor     eax, ecx
0x18000dacd  mov     [rbx], eax
0x18000dacf  mov     rbp, [rsp+38h+arg_10]
0x18000dad4  mov     rax, rbx
0x18000dad7  mov     rbx, [rsp+38h+arg_8]
0x18000dadc  add     rsp, 20h
0x18000dae0  pop     r15
0x18000dae2  pop     rdi
0x18000dae3  pop     rsi
0x18000dae4  retn
```
