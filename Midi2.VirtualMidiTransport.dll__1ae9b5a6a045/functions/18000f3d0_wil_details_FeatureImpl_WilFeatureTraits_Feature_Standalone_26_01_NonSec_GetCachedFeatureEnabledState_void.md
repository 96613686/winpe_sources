# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f3d0`
- end: `0x18000f53d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010340`

## callees

- `0x18000ee50`
- `0x18000f3d0`
- `0x180011648`
- `0x180021010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599532, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
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
0x18000f3d0  mov     [rsp+arg_8], rbx
0x18000f3d5  mov     [rsp+arg_10], rbp
0x18000f3da  mov     [rsp+arg_0], rcx
0x18000f3df  push    rsi
0x18000f3e0  push    rdi
0x18000f3e1  push    r15
0x18000f3e3  sub     rsp, 20h
0x18000f3e7  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18000f3ee  mov     rbx, rdx
0x18000f3f1  mov     qword ptr [rdx], 0
0x18000f3f8  mov     eax, [rsi]
0x18000f3fa  mov     [rdx], eax
0x18000f3fc  and     eax, 6
0x18000f3ff  cmp     al, 6
0x18000f401  jz      loc_18000F527
0x18000f407  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f40c  mov     ebp, eax
0x18000f40e  mov     dword ptr [rsp+38h+arg_0], 0
0x18000f416  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f41d  test    rax, rax
0x18000f420  jz      short loc_18000F43A
0x18000f422  lea     r8, [rsp+38h+arg_0]
0x18000f427  mov     edx, 3
0x18000f42c  mov     ecx, 37E286Ch
0x18000f431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f436  mov     edx, eax
0x18000f438  jmp     short loc_18000F448
0x18000f43a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f441  test    rax, rax
0x18000f444  jnz     short loc_18000F422
0x18000f446  xor     edx, edx
0x18000f448  mov     r8d, edx
0x18000f44b  mov     eax, edx
0x18000f44d  and     r8d, 0FFFFFF3Fh
0x18000f454  and     edx, 80h
0x18000f45a  mov     ecx, r8d
0x18000f45d  mov     r15d, 40h ; '@'
0x18000f463  and     ecx, 3
0x18000f466  and     eax, r15d
0x18000f469  shl     ecx, 2
0x18000f46c  or      ecx, eax
0x18000f46e  shl     ecx, 2
0x18000f471  or      ecx, edx
0x18000f473  lea     edi, ds:0[rcx*8]
0x18000f47a  test    r8d, r8d
0x18000f47d  jnz     short loc_18000F484
0x18000f47f  mov     eax, r15d
0x18000f482  jmp     short loc_18000F48E
0x18000f484  xor     eax, eax
0x18000f486  cmp     r8d, 2
0x18000f48a  cmovz   eax, r15d
0x18000f48e  or      edi, eax
0x18000f490  mov     eax, [rbx]
0x18000f492  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000f497  mov     edx, eax
0x18000f499  mov     [rbx], eax
0x18000f49b  jz      short loc_18000F4C7
0x18000f49d  test    dl, 2
0x18000f4a0  jnz     short loc_18000F4C7
0x18000f4a2  xor     eax, edi
0x18000f4a4  and     eax, 180h
0x18000f4a9  xor     eax, edx
0x18000f4ab  mov     ecx, eax
0x18000f4ad  xor     ecx, edi
0x18000f4af  and     ecx, r15d
0x18000f4b2  xor     ecx, eax
0x18000f4b4  or      ecx, 1
0x18000f4b7  mov     eax, ecx
0x18000f4b9  xor     eax, edi
0x18000f4bb  and     eax, 800h
0x18000f4c0  xor     eax, ecx
0x18000f4c2  or      eax, 2
0x18000f4c5  mov     [rbx], eax
0x18000f4c7  mov     r8d, edx
0x18000f4ca  mov     ecx, eax
0x18000f4cc  and     r8d, 4
0x18000f4d0  jnz     short loc_18000F4E1
0x18000f4d2  xor     ecx, edi
0x18000f4d4  and     ecx, 400h
0x18000f4da  xor     ecx, eax
0x18000f4dc  or      ecx, 4
0x18000f4df  mov     [rbx], ecx
0x18000f4e1  mov     eax, edx
0x18000f4e3  lock cmpxchg [rsi], ecx
0x18000f4e7  jnz     short loc_18000F492
0x18000f4e9  test    r8d, r8d
0x18000f4ec  jnz     short loc_18000F4FE
0x18000f4ee  mov     r8d, ebp
0x18000f4f1  mov     edx, 3
0x18000f4f6  mov     rcx, rsi
0x18000f4f9  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f4fe  test    byte ptr [rbx], 2
0x18000f501  jnz     short loc_18000F527
0x18000f503  mov     eax, [rbx]
0x18000f505  xor     eax, edi
0x18000f507  and     eax, 180h
0x18000f50c  xor     eax, [rbx]
0x18000f50e  mov     ecx, eax
0x18000f510  xor     ecx, edi
0x18000f512  and     ecx, r15d
0x18000f515  xor     ecx, eax
0x18000f517  or      ecx, 1
0x18000f51a  mov     eax, ecx
0x18000f51c  xor     eax, edi
0x18000f51e  and     eax, 800h
0x18000f523  xor     eax, ecx
0x18000f525  mov     [rbx], eax
0x18000f527  mov     rbp, [rsp+38h+arg_10]
0x18000f52c  mov     rax, rbx
0x18000f52f  mov     rbx, [rsp+38h+arg_8]
0x18000f534  add     rsp, 20h
0x18000f538  pop     r15
0x18000f53a  pop     rdi
0x18000f53b  pop     rsi
0x18000f53c  retn
```
