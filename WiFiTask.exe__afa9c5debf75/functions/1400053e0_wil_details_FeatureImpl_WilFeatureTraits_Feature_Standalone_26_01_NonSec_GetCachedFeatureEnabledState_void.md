# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1400053e0`
- end: `0x14000554d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005d00`

## callees

- `0x1400049e0`
- `0x1400053e0`
- `0x14000a88c`
- `0x140012010`

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
0x1400053e0  mov     [rsp+arg_8], rbx
0x1400053e5  mov     [rsp+arg_10], rbp
0x1400053ea  mov     [rsp+arg_0], rcx
0x1400053ef  push    rsi
0x1400053f0  push    rdi
0x1400053f1  push    r15
0x1400053f3  sub     rsp, 20h
0x1400053f7  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x1400053fe  mov     rbx, rdx
0x140005401  mov     qword ptr [rdx], 0
0x140005408  mov     eax, [rsi]
0x14000540a  mov     [rdx], eax
0x14000540c  and     eax, 6
0x14000540f  cmp     al, 6
0x140005411  jz      loc_140005537
0x140005417  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000541c  mov     ebp, eax
0x14000541e  mov     dword ptr [rsp+38h+arg_0], 0
0x140005426  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14000542d  test    rax, rax
0x140005430  jz      short loc_14000544A
0x140005432  lea     r8, [rsp+38h+arg_0]
0x140005437  mov     edx, 3
0x14000543c  mov     ecx, 37E286Ch
0x140005441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005446  mov     edx, eax
0x140005448  jmp     short loc_140005458
0x14000544a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140005451  test    rax, rax
0x140005454  jnz     short loc_140005432
0x140005456  xor     edx, edx
0x140005458  mov     r8d, edx
0x14000545b  mov     eax, edx
0x14000545d  and     r8d, 0FFFFFF3Fh
0x140005464  and     edx, 80h
0x14000546a  mov     ecx, r8d
0x14000546d  mov     r15d, 40h ; '@'
0x140005473  and     ecx, 3
0x140005476  and     eax, r15d
0x140005479  shl     ecx, 2
0x14000547c  or      ecx, eax
0x14000547e  shl     ecx, 2
0x140005481  or      ecx, edx
0x140005483  lea     edi, ds:0[rcx*8]
0x14000548a  test    r8d, r8d
0x14000548d  jnz     short loc_140005494
0x14000548f  mov     eax, r15d
0x140005492  jmp     short loc_14000549E
0x140005494  xor     eax, eax
0x140005496  cmp     r8d, 2
0x14000549a  cmovz   eax, r15d
0x14000549e  or      edi, eax
0x1400054a0  mov     eax, [rbx]
0x1400054a2  cmp     dword ptr [rsp+38h+arg_0], 0
0x1400054a7  mov     edx, eax
0x1400054a9  mov     [rbx], eax
0x1400054ab  jz      short loc_1400054D7
0x1400054ad  test    dl, 2
0x1400054b0  jnz     short loc_1400054D7
0x1400054b2  xor     eax, edi
0x1400054b4  and     eax, 180h
0x1400054b9  xor     eax, edx
0x1400054bb  mov     ecx, eax
0x1400054bd  xor     ecx, edi
0x1400054bf  and     ecx, r15d
0x1400054c2  xor     ecx, eax
0x1400054c4  or      ecx, 1
0x1400054c7  mov     eax, ecx
0x1400054c9  xor     eax, edi
0x1400054cb  and     eax, 800h
0x1400054d0  xor     eax, ecx
0x1400054d2  or      eax, 2
0x1400054d5  mov     [rbx], eax
0x1400054d7  mov     r8d, edx
0x1400054da  mov     ecx, eax
0x1400054dc  and     r8d, 4
0x1400054e0  jnz     short loc_1400054F1
0x1400054e2  xor     ecx, edi
0x1400054e4  and     ecx, 400h
0x1400054ea  xor     ecx, eax
0x1400054ec  or      ecx, 4
0x1400054ef  mov     [rbx], ecx
0x1400054f1  mov     eax, edx
0x1400054f3  lock cmpxchg [rsi], ecx
0x1400054f7  jnz     short loc_1400054A2
0x1400054f9  test    r8d, r8d
0x1400054fc  jnz     short loc_14000550E
0x1400054fe  mov     r8d, ebp
0x140005501  mov     edx, 3
0x140005506  mov     rcx, rsi
0x140005509  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000550e  test    byte ptr [rbx], 2
0x140005511  jnz     short loc_140005537
0x140005513  mov     eax, [rbx]
0x140005515  xor     eax, edi
0x140005517  and     eax, 180h
0x14000551c  xor     eax, [rbx]
0x14000551e  mov     ecx, eax
0x140005520  xor     ecx, edi
0x140005522  and     ecx, r15d
0x140005525  xor     ecx, eax
0x140005527  or      ecx, 1
0x14000552a  mov     eax, ecx
0x14000552c  xor     eax, edi
0x14000552e  and     eax, 800h
0x140005533  xor     eax, ecx
0x140005535  mov     [rbx], eax
0x140005537  mov     rbp, [rsp+38h+arg_10]
0x14000553c  mov     rax, rbx
0x14000553f  mov     rbx, [rsp+38h+arg_8]
0x140005544  add     rsp, 20h
0x140005548  pop     r15
0x14000554a  pop     rdi
0x14000554b  pop     rsi
0x14000554c  retn
```
