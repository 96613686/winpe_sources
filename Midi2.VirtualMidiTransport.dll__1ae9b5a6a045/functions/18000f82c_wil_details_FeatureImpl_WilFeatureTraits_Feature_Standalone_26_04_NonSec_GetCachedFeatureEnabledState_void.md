# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f82c`
- end: `0x18000f999`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_04_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800104b0`

## callees

- `0x18000ee50`
- `0x18000f82c`
- `0x180011648`
- `0x180021010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599559, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_04_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_04_NonSec__descriptor,
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
0x18000f82c  mov     [rsp+arg_8], rbx
0x18000f831  mov     [rsp+arg_10], rbp
0x18000f836  mov     [rsp+arg_0], rcx
0x18000f83b  push    rsi
0x18000f83c  push    rdi
0x18000f83d  push    r15
0x18000f83f  sub     rsp, 20h
0x18000f843  mov     rsi, cs:Feature_Standalone_26_04_NonSec__descriptor
0x18000f84a  mov     rbx, rdx
0x18000f84d  mov     qword ptr [rdx], 0
0x18000f854  mov     eax, [rsi]
0x18000f856  mov     [rdx], eax
0x18000f858  and     eax, 6
0x18000f85b  cmp     al, 6
0x18000f85d  jz      loc_18000F983
0x18000f863  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f868  mov     ebp, eax
0x18000f86a  mov     dword ptr [rsp+38h+arg_0], 0
0x18000f872  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f879  test    rax, rax
0x18000f87c  jz      short loc_18000F896
0x18000f87e  lea     r8, [rsp+38h+arg_0]
0x18000f883  mov     edx, 3
0x18000f888  mov     ecx, 37E2887h
0x18000f88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f892  mov     edx, eax
0x18000f894  jmp     short loc_18000F8A4
0x18000f896  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f89d  test    rax, rax
0x18000f8a0  jnz     short loc_18000F87E
0x18000f8a2  xor     edx, edx
0x18000f8a4  mov     r8d, edx
0x18000f8a7  mov     eax, edx
0x18000f8a9  and     r8d, 0FFFFFF3Fh
0x18000f8b0  and     edx, 80h
0x18000f8b6  mov     ecx, r8d
0x18000f8b9  mov     r15d, 40h ; '@'
0x18000f8bf  and     ecx, 3
0x18000f8c2  and     eax, r15d
0x18000f8c5  shl     ecx, 2
0x18000f8c8  or      ecx, eax
0x18000f8ca  shl     ecx, 2
0x18000f8cd  or      ecx, edx
0x18000f8cf  lea     edi, ds:0[rcx*8]
0x18000f8d6  test    r8d, r8d
0x18000f8d9  jnz     short loc_18000F8E0
0x18000f8db  mov     eax, r15d
0x18000f8de  jmp     short loc_18000F8EA
0x18000f8e0  xor     eax, eax
0x18000f8e2  cmp     r8d, 2
0x18000f8e6  cmovz   eax, r15d
0x18000f8ea  or      edi, eax
0x18000f8ec  mov     eax, [rbx]
0x18000f8ee  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000f8f3  mov     edx, eax
0x18000f8f5  mov     [rbx], eax
0x18000f8f7  jz      short loc_18000F923
0x18000f8f9  test    dl, 2
0x18000f8fc  jnz     short loc_18000F923
0x18000f8fe  xor     eax, edi
0x18000f900  and     eax, 180h
0x18000f905  xor     eax, edx
0x18000f907  mov     ecx, eax
0x18000f909  xor     ecx, edi
0x18000f90b  and     ecx, r15d
0x18000f90e  xor     ecx, eax
0x18000f910  or      ecx, 1
0x18000f913  mov     eax, ecx
0x18000f915  xor     eax, edi
0x18000f917  and     eax, 800h
0x18000f91c  xor     eax, ecx
0x18000f91e  or      eax, 2
0x18000f921  mov     [rbx], eax
0x18000f923  mov     r8d, edx
0x18000f926  mov     ecx, eax
0x18000f928  and     r8d, 4
0x18000f92c  jnz     short loc_18000F93D
0x18000f92e  xor     ecx, edi
0x18000f930  and     ecx, 400h
0x18000f936  xor     ecx, eax
0x18000f938  or      ecx, 4
0x18000f93b  mov     [rbx], ecx
0x18000f93d  mov     eax, edx
0x18000f93f  lock cmpxchg [rsi], ecx
0x18000f943  jnz     short loc_18000F8EE
0x18000f945  test    r8d, r8d
0x18000f948  jnz     short loc_18000F95A
0x18000f94a  mov     r8d, ebp
0x18000f94d  mov     edx, 3
0x18000f952  mov     rcx, rsi
0x18000f955  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f95a  test    byte ptr [rbx], 2
0x18000f95d  jnz     short loc_18000F983
0x18000f95f  mov     eax, [rbx]
0x18000f961  xor     eax, edi
0x18000f963  and     eax, 180h
0x18000f968  xor     eax, [rbx]
0x18000f96a  mov     ecx, eax
0x18000f96c  xor     ecx, edi
0x18000f96e  and     ecx, r15d
0x18000f971  xor     ecx, eax
0x18000f973  or      ecx, 1
0x18000f976  mov     eax, ecx
0x18000f978  xor     eax, edi
0x18000f97a  and     eax, 800h
0x18000f97f  xor     eax, ecx
0x18000f981  mov     [rbx], eax
0x18000f983  mov     rbp, [rsp+38h+arg_10]
0x18000f988  mov     rax, rbx
0x18000f98b  mov     rbx, [rsp+38h+arg_8]
0x18000f990  add     rsp, 20h
0x18000f994  pop     r15
0x18000f996  pop     rdi
0x18000f997  pop     rsi
0x18000f998  retn
```
