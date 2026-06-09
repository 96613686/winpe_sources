# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180008584`
- end: `0x1800086f1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008dd0`

## callees

- `0x18000787c`
- `0x180008584`
- `0x180010684`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_01_NonSec__descriptor, 3, v4);
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
0x180008584  mov     [rsp+arg_8], rbx
0x180008589  mov     [rsp+arg_10], rbp
0x18000858e  mov     [rsp+arg_0], rcx
0x180008593  push    rsi
0x180008594  push    rdi
0x180008595  push    r15
0x180008597  sub     rsp, 20h
0x18000859b  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x1800085a2  mov     rbx, rdx
0x1800085a5  mov     qword ptr [rdx], 0
0x1800085ac  mov     eax, [rsi]
0x1800085ae  mov     [rdx], eax
0x1800085b0  and     eax, 6
0x1800085b3  cmp     al, 6
0x1800085b5  jz      loc_1800086DB
0x1800085bb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800085c0  mov     ebp, eax
0x1800085c2  mov     dword ptr [rsp+38h+arg_0], 0
0x1800085ca  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800085d1  test    rax, rax
0x1800085d4  jz      short loc_1800085EE
0x1800085d6  lea     r8, [rsp+38h+arg_0]
0x1800085db  mov     edx, 3
0x1800085e0  mov     ecx, 37E286Ch
0x1800085e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085ea  mov     edx, eax
0x1800085ec  jmp     short loc_1800085FC
0x1800085ee  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800085f5  test    rax, rax
0x1800085f8  jnz     short loc_1800085D6
0x1800085fa  xor     edx, edx
0x1800085fc  mov     r8d, edx
0x1800085ff  mov     eax, edx
0x180008601  and     r8d, 0FFFFFF3Fh
0x180008608  and     edx, 80h
0x18000860e  mov     ecx, r8d
0x180008611  mov     r15d, 40h ; '@'
0x180008617  and     ecx, 3
0x18000861a  and     eax, r15d
0x18000861d  shl     ecx, 2
0x180008620  or      ecx, eax
0x180008622  shl     ecx, 2
0x180008625  or      ecx, edx
0x180008627  lea     edi, ds:0[rcx*8]
0x18000862e  test    r8d, r8d
0x180008631  jnz     short loc_180008638
0x180008633  mov     eax, r15d
0x180008636  jmp     short loc_180008642
0x180008638  xor     eax, eax
0x18000863a  cmp     r8d, 2
0x18000863e  cmovz   eax, r15d
0x180008642  or      edi, eax
0x180008644  mov     eax, [rbx]
0x180008646  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000864b  mov     edx, eax
0x18000864d  mov     [rbx], eax
0x18000864f  jz      short loc_18000867B
0x180008651  test    dl, 2
0x180008654  jnz     short loc_18000867B
0x180008656  xor     eax, edi
0x180008658  and     eax, 180h
0x18000865d  xor     eax, edx
0x18000865f  mov     ecx, eax
0x180008661  xor     ecx, edi
0x180008663  and     ecx, r15d
0x180008666  xor     ecx, eax
0x180008668  or      ecx, 1
0x18000866b  mov     eax, ecx
0x18000866d  xor     eax, edi
0x18000866f  and     eax, 800h
0x180008674  xor     eax, ecx
0x180008676  or      eax, 2
0x180008679  mov     [rbx], eax
0x18000867b  mov     r8d, edx
0x18000867e  mov     ecx, eax
0x180008680  and     r8d, 4
0x180008684  jnz     short loc_180008695
0x180008686  xor     ecx, edi
0x180008688  and     ecx, 400h
0x18000868e  xor     ecx, eax
0x180008690  or      ecx, 4
0x180008693  mov     [rbx], ecx
0x180008695  mov     eax, edx
0x180008697  lock cmpxchg [rsi], ecx
0x18000869b  jnz     short loc_180008646
0x18000869d  test    r8d, r8d
0x1800086a0  jnz     short loc_1800086B2
0x1800086a2  mov     r8d, ebp
0x1800086a5  mov     edx, 3
0x1800086aa  mov     rcx, rsi
0x1800086ad  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800086b2  test    byte ptr [rbx], 2
0x1800086b5  jnz     short loc_1800086DB
0x1800086b7  mov     eax, [rbx]
0x1800086b9  xor     eax, edi
0x1800086bb  and     eax, 180h
0x1800086c0  xor     eax, [rbx]
0x1800086c2  mov     ecx, eax
0x1800086c4  xor     ecx, edi
0x1800086c6  and     ecx, r15d
0x1800086c9  xor     ecx, eax
0x1800086cb  or      ecx, 1
0x1800086ce  mov     eax, ecx
0x1800086d0  xor     eax, edi
0x1800086d2  and     eax, 800h
0x1800086d7  xor     eax, ecx
0x1800086d9  mov     [rbx], eax
0x1800086db  mov     rbp, [rsp+38h+arg_10]
0x1800086e0  mov     rax, rbx
0x1800086e3  mov     rbx, [rsp+38h+arg_8]
0x1800086e8  add     rsp, 20h
0x1800086ec  pop     r15
0x1800086ee  pop     rdi
0x1800086ef  pop     rsi
0x1800086f0  retn
```
