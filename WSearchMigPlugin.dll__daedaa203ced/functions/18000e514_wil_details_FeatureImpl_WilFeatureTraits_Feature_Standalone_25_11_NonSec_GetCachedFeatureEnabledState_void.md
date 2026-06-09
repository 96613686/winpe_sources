# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e514`
- end: `0x18000e681`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f2b4`

## callees

- `0x1800058e8`
- `0x180009270`
- `0x18000e514`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036797, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_11_NonSec__descriptor, 3, v4);
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
0x18000e514  mov     [rsp+arg_8], rbx
0x18000e519  mov     [rsp+arg_10], rbp
0x18000e51e  mov     [rsp+arg_0], rcx
0x18000e523  push    rsi
0x18000e524  push    rdi
0x18000e525  push    r15
0x18000e527  sub     rsp, 20h
0x18000e52b  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000e532  mov     rbx, rdx
0x18000e535  mov     qword ptr [rdx], 0
0x18000e53c  mov     eax, [rsi]
0x18000e53e  mov     [rdx], eax
0x18000e540  and     eax, 6
0x18000e543  cmp     al, 6
0x18000e545  jz      loc_18000E66B
0x18000e54b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e550  mov     ebp, eax
0x18000e552  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e55a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e561  test    rax, rax
0x18000e564  jz      short loc_18000E57E
0x18000e566  lea     r8, [rsp+38h+arg_0]
0x18000e56b  mov     edx, 3
0x18000e570  mov     ecx, 2AF34FDh
0x18000e575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e57a  mov     edx, eax
0x18000e57c  jmp     short loc_18000E58C
0x18000e57e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e585  test    rax, rax
0x18000e588  jnz     short loc_18000E566
0x18000e58a  xor     edx, edx
0x18000e58c  mov     r8d, edx
0x18000e58f  mov     eax, edx
0x18000e591  and     r8d, 0FFFFFF3Fh
0x18000e598  and     edx, 80h
0x18000e59e  mov     ecx, r8d
0x18000e5a1  mov     r15d, 40h ; '@'
0x18000e5a7  and     ecx, 3
0x18000e5aa  and     eax, r15d
0x18000e5ad  shl     ecx, 2
0x18000e5b0  or      ecx, eax
0x18000e5b2  shl     ecx, 2
0x18000e5b5  or      ecx, edx
0x18000e5b7  lea     edi, ds:0[rcx*8]
0x18000e5be  test    r8d, r8d
0x18000e5c1  jnz     short loc_18000E5C8
0x18000e5c3  mov     eax, r15d
0x18000e5c6  jmp     short loc_18000E5D2
0x18000e5c8  xor     eax, eax
0x18000e5ca  cmp     r8d, 2
0x18000e5ce  cmovz   eax, r15d
0x18000e5d2  or      edi, eax
0x18000e5d4  mov     eax, [rbx]
0x18000e5d6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e5db  mov     edx, eax
0x18000e5dd  mov     [rbx], eax
0x18000e5df  jz      short loc_18000E60B
0x18000e5e1  test    dl, 2
0x18000e5e4  jnz     short loc_18000E60B
0x18000e5e6  xor     eax, edi
0x18000e5e8  and     eax, 180h
0x18000e5ed  xor     eax, edx
0x18000e5ef  mov     ecx, eax
0x18000e5f1  xor     ecx, edi
0x18000e5f3  and     ecx, r15d
0x18000e5f6  xor     ecx, eax
0x18000e5f8  or      ecx, 1
0x18000e5fb  mov     eax, ecx
0x18000e5fd  xor     eax, edi
0x18000e5ff  and     eax, 800h
0x18000e604  xor     eax, ecx
0x18000e606  or      eax, 2
0x18000e609  mov     [rbx], eax
0x18000e60b  mov     r8d, edx
0x18000e60e  mov     ecx, eax
0x18000e610  and     r8d, 4
0x18000e614  jnz     short loc_18000E625
0x18000e616  xor     ecx, edi
0x18000e618  and     ecx, 400h
0x18000e61e  xor     ecx, eax
0x18000e620  or      ecx, 4
0x18000e623  mov     [rbx], ecx
0x18000e625  mov     eax, edx
0x18000e627  lock cmpxchg [rsi], ecx
0x18000e62b  jnz     short loc_18000E5D6
0x18000e62d  test    r8d, r8d
0x18000e630  jnz     short loc_18000E642
0x18000e632  mov     r8d, ebp
0x18000e635  mov     edx, 3
0x18000e63a  mov     rcx, rsi
0x18000e63d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e642  test    byte ptr [rbx], 2
0x18000e645  jnz     short loc_18000E66B
0x18000e647  mov     eax, [rbx]
0x18000e649  xor     eax, edi
0x18000e64b  and     eax, 180h
0x18000e650  xor     eax, [rbx]
0x18000e652  mov     ecx, eax
0x18000e654  xor     ecx, edi
0x18000e656  and     ecx, r15d
0x18000e659  xor     ecx, eax
0x18000e65b  or      ecx, 1
0x18000e65e  mov     eax, ecx
0x18000e660  xor     eax, edi
0x18000e662  and     eax, 800h
0x18000e667  xor     eax, ecx
0x18000e669  mov     [rbx], eax
0x18000e66b  mov     rbp, [rsp+38h+arg_10]
0x18000e670  mov     rax, rbx
0x18000e673  mov     rbx, [rsp+38h+arg_8]
0x18000e678  add     rsp, 20h
0x18000e67c  pop     r15
0x18000e67e  pop     rdi
0x18000e67f  pop     rsi
0x18000e680  retn
```
