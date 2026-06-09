# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e3a0`
- end: `0x18000e50d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f704`

## callees

- `0x1800058e8`
- `0x180009270`
- `0x18000e3a0`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_10_NonSec__descriptor, 3, v4);
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
0x18000e3a0  mov     [rsp+arg_8], rbx
0x18000e3a5  mov     [rsp+arg_10], rbp
0x18000e3aa  mov     [rsp+arg_0], rcx
0x18000e3af  push    rsi
0x18000e3b0  push    rdi
0x18000e3b1  push    r15
0x18000e3b3  sub     rsp, 20h
0x18000e3b7  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18000e3be  mov     rbx, rdx
0x18000e3c1  mov     qword ptr [rdx], 0
0x18000e3c8  mov     eax, [rsi]
0x18000e3ca  mov     [rdx], eax
0x18000e3cc  and     eax, 6
0x18000e3cf  cmp     al, 6
0x18000e3d1  jz      loc_18000E4F7
0x18000e3d7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e3dc  mov     ebp, eax
0x18000e3de  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e3e6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e3ed  test    rax, rax
0x18000e3f0  jz      short loc_18000E40A
0x18000e3f2  lea     r8, [rsp+38h+arg_0]
0x18000e3f7  mov     edx, 3
0x18000e3fc  mov     ecx, 2AF34F8h
0x18000e401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e406  mov     edx, eax
0x18000e408  jmp     short loc_18000E418
0x18000e40a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e411  test    rax, rax
0x18000e414  jnz     short loc_18000E3F2
0x18000e416  xor     edx, edx
0x18000e418  mov     r8d, edx
0x18000e41b  mov     eax, edx
0x18000e41d  and     r8d, 0FFFFFF3Fh
0x18000e424  and     edx, 80h
0x18000e42a  mov     ecx, r8d
0x18000e42d  mov     r15d, 40h ; '@'
0x18000e433  and     ecx, 3
0x18000e436  and     eax, r15d
0x18000e439  shl     ecx, 2
0x18000e43c  or      ecx, eax
0x18000e43e  shl     ecx, 2
0x18000e441  or      ecx, edx
0x18000e443  lea     edi, ds:0[rcx*8]
0x18000e44a  test    r8d, r8d
0x18000e44d  jnz     short loc_18000E454
0x18000e44f  mov     eax, r15d
0x18000e452  jmp     short loc_18000E45E
0x18000e454  xor     eax, eax
0x18000e456  cmp     r8d, 2
0x18000e45a  cmovz   eax, r15d
0x18000e45e  or      edi, eax
0x18000e460  mov     eax, [rbx]
0x18000e462  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e467  mov     edx, eax
0x18000e469  mov     [rbx], eax
0x18000e46b  jz      short loc_18000E497
0x18000e46d  test    dl, 2
0x18000e470  jnz     short loc_18000E497
0x18000e472  xor     eax, edi
0x18000e474  and     eax, 180h
0x18000e479  xor     eax, edx
0x18000e47b  mov     ecx, eax
0x18000e47d  xor     ecx, edi
0x18000e47f  and     ecx, r15d
0x18000e482  xor     ecx, eax
0x18000e484  or      ecx, 1
0x18000e487  mov     eax, ecx
0x18000e489  xor     eax, edi
0x18000e48b  and     eax, 800h
0x18000e490  xor     eax, ecx
0x18000e492  or      eax, 2
0x18000e495  mov     [rbx], eax
0x18000e497  mov     r8d, edx
0x18000e49a  mov     ecx, eax
0x18000e49c  and     r8d, 4
0x18000e4a0  jnz     short loc_18000E4B1
0x18000e4a2  xor     ecx, edi
0x18000e4a4  and     ecx, 400h
0x18000e4aa  xor     ecx, eax
0x18000e4ac  or      ecx, 4
0x18000e4af  mov     [rbx], ecx
0x18000e4b1  mov     eax, edx
0x18000e4b3  lock cmpxchg [rsi], ecx
0x18000e4b7  jnz     short loc_18000E462
0x18000e4b9  test    r8d, r8d
0x18000e4bc  jnz     short loc_18000E4CE
0x18000e4be  mov     r8d, ebp
0x18000e4c1  mov     edx, 3
0x18000e4c6  mov     rcx, rsi
0x18000e4c9  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e4ce  test    byte ptr [rbx], 2
0x18000e4d1  jnz     short loc_18000E4F7
0x18000e4d3  mov     eax, [rbx]
0x18000e4d5  xor     eax, edi
0x18000e4d7  and     eax, 180h
0x18000e4dc  xor     eax, [rbx]
0x18000e4de  mov     ecx, eax
0x18000e4e0  xor     ecx, edi
0x18000e4e2  and     ecx, r15d
0x18000e4e5  xor     ecx, eax
0x18000e4e7  or      ecx, 1
0x18000e4ea  mov     eax, ecx
0x18000e4ec  xor     eax, edi
0x18000e4ee  and     eax, 800h
0x18000e4f3  xor     eax, ecx
0x18000e4f5  mov     [rbx], eax
0x18000e4f7  mov     rbp, [rsp+38h+arg_10]
0x18000e4fc  mov     rax, rbx
0x18000e4ff  mov     rbx, [rsp+38h+arg_8]
0x18000e504  add     rsp, 20h
0x18000e508  pop     r15
0x18000e50a  pop     rdi
0x18000e50b  pop     rsi
0x18000e50c  retn
```
