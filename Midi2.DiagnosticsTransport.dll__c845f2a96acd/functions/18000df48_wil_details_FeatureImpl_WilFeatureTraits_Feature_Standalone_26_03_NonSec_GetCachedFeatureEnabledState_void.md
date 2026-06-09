# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000df48`
- end: `0x18000e0b5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000eeb0`

## callees

- `0x18000d6e0`
- `0x18000df48`
- `0x18000ff38`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599553, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor,
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
0x18000df48  mov     [rsp+arg_8], rbx
0x18000df4d  mov     [rsp+arg_10], rbp
0x18000df52  mov     [rsp+arg_0], rcx
0x18000df57  push    rsi
0x18000df58  push    rdi
0x18000df59  push    r15
0x18000df5b  sub     rsp, 20h
0x18000df5f  mov     rsi, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18000df66  mov     rbx, rdx
0x18000df69  mov     qword ptr [rdx], 0
0x18000df70  mov     eax, [rsi]
0x18000df72  mov     [rdx], eax
0x18000df74  and     eax, 6
0x18000df77  cmp     al, 6
0x18000df79  jz      loc_18000E09F
0x18000df7f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000df84  mov     ebp, eax
0x18000df86  mov     dword ptr [rsp+38h+arg_0], 0
0x18000df8e  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000df95  test    rax, rax
0x18000df98  jz      short loc_18000DFB2
0x18000df9a  lea     r8, [rsp+38h+arg_0]
0x18000df9f  mov     edx, 3
0x18000dfa4  mov     ecx, 37E2881h
0x18000dfa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfae  mov     edx, eax
0x18000dfb0  jmp     short loc_18000DFC0
0x18000dfb2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000dfb9  test    rax, rax
0x18000dfbc  jnz     short loc_18000DF9A
0x18000dfbe  xor     edx, edx
0x18000dfc0  mov     r8d, edx
0x18000dfc3  mov     eax, edx
0x18000dfc5  and     r8d, 0FFFFFF3Fh
0x18000dfcc  and     edx, 80h
0x18000dfd2  mov     ecx, r8d
0x18000dfd5  mov     r15d, 40h ; '@'
0x18000dfdb  and     ecx, 3
0x18000dfde  and     eax, r15d
0x18000dfe1  shl     ecx, 2
0x18000dfe4  or      ecx, eax
0x18000dfe6  shl     ecx, 2
0x18000dfe9  or      ecx, edx
0x18000dfeb  lea     edi, ds:0[rcx*8]
0x18000dff2  test    r8d, r8d
0x18000dff5  jnz     short loc_18000DFFC
0x18000dff7  mov     eax, r15d
0x18000dffa  jmp     short loc_18000E006
0x18000dffc  xor     eax, eax
0x18000dffe  cmp     r8d, 2
0x18000e002  cmovz   eax, r15d
0x18000e006  or      edi, eax
0x18000e008  mov     eax, [rbx]
0x18000e00a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e00f  mov     edx, eax
0x18000e011  mov     [rbx], eax
0x18000e013  jz      short loc_18000E03F
0x18000e015  test    dl, 2
0x18000e018  jnz     short loc_18000E03F
0x18000e01a  xor     eax, edi
0x18000e01c  and     eax, 180h
0x18000e021  xor     eax, edx
0x18000e023  mov     ecx, eax
0x18000e025  xor     ecx, edi
0x18000e027  and     ecx, r15d
0x18000e02a  xor     ecx, eax
0x18000e02c  or      ecx, 1
0x18000e02f  mov     eax, ecx
0x18000e031  xor     eax, edi
0x18000e033  and     eax, 800h
0x18000e038  xor     eax, ecx
0x18000e03a  or      eax, 2
0x18000e03d  mov     [rbx], eax
0x18000e03f  mov     r8d, edx
0x18000e042  mov     ecx, eax
0x18000e044  and     r8d, 4
0x18000e048  jnz     short loc_18000E059
0x18000e04a  xor     ecx, edi
0x18000e04c  and     ecx, 400h
0x18000e052  xor     ecx, eax
0x18000e054  or      ecx, 4
0x18000e057  mov     [rbx], ecx
0x18000e059  mov     eax, edx
0x18000e05b  lock cmpxchg [rsi], ecx
0x18000e05f  jnz     short loc_18000E00A
0x18000e061  test    r8d, r8d
0x18000e064  jnz     short loc_18000E076
0x18000e066  mov     r8d, ebp
0x18000e069  mov     edx, 3
0x18000e06e  mov     rcx, rsi
0x18000e071  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e076  test    byte ptr [rbx], 2
0x18000e079  jnz     short loc_18000E09F
0x18000e07b  mov     eax, [rbx]
0x18000e07d  xor     eax, edi
0x18000e07f  and     eax, 180h
0x18000e084  xor     eax, [rbx]
0x18000e086  mov     ecx, eax
0x18000e088  xor     ecx, edi
0x18000e08a  and     ecx, r15d
0x18000e08d  xor     ecx, eax
0x18000e08f  or      ecx, 1
0x18000e092  mov     eax, ecx
0x18000e094  xor     eax, edi
0x18000e096  and     eax, 800h
0x18000e09b  xor     eax, ecx
0x18000e09d  mov     [rbx], eax
0x18000e09f  mov     rbp, [rsp+38h+arg_10]
0x18000e0a4  mov     rax, rbx
0x18000e0a7  mov     rbx, [rsp+38h+arg_8]
0x18000e0ac  add     rsp, 20h
0x18000e0b0  pop     r15
0x18000e0b2  pop     rdi
0x18000e0b3  pop     rsi
0x18000e0b4  retn
```
