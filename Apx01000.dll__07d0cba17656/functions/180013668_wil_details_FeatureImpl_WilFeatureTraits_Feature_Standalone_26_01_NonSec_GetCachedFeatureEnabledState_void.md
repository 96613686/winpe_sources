# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180013668`
- end: `0x1800137d5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014c2c`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180013668`
- `0x18002a010`

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
0x180013668  mov     [rsp+arg_8], rbx
0x18001366d  mov     [rsp+arg_10], rbp
0x180013672  mov     [rsp+arg_0], rcx
0x180013677  push    rsi
0x180013678  push    rdi
0x180013679  push    r15
0x18001367b  sub     rsp, 20h
0x18001367f  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180013686  mov     rbx, rdx
0x180013689  mov     qword ptr [rdx], 0
0x180013690  mov     eax, [rsi]
0x180013692  mov     [rdx], eax
0x180013694  and     eax, 6
0x180013697  cmp     al, 6
0x180013699  jz      loc_1800137BF
0x18001369f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800136a4  mov     ebp, eax
0x1800136a6  mov     dword ptr [rsp+38h+arg_0], 0
0x1800136ae  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800136b5  test    rax, rax
0x1800136b8  jz      short loc_1800136D2
0x1800136ba  lea     r8, [rsp+38h+arg_0]
0x1800136bf  mov     edx, 3
0x1800136c4  mov     ecx, 37E286Ch
0x1800136c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136ce  mov     edx, eax
0x1800136d0  jmp     short loc_1800136E0
0x1800136d2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800136d9  test    rax, rax
0x1800136dc  jnz     short loc_1800136BA
0x1800136de  xor     edx, edx
0x1800136e0  mov     r8d, edx
0x1800136e3  mov     eax, edx
0x1800136e5  and     r8d, 0FFFFFF3Fh
0x1800136ec  and     edx, 80h
0x1800136f2  mov     ecx, r8d
0x1800136f5  mov     r15d, 40h ; '@'
0x1800136fb  and     ecx, 3
0x1800136fe  and     eax, r15d
0x180013701  shl     ecx, 2
0x180013704  or      ecx, eax
0x180013706  shl     ecx, 2
0x180013709  or      ecx, edx
0x18001370b  lea     edi, ds:0[rcx*8]
0x180013712  test    r8d, r8d
0x180013715  jnz     short loc_18001371C
0x180013717  mov     eax, r15d
0x18001371a  jmp     short loc_180013726
0x18001371c  xor     eax, eax
0x18001371e  cmp     r8d, 2
0x180013722  cmovz   eax, r15d
0x180013726  or      edi, eax
0x180013728  mov     eax, [rbx]
0x18001372a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001372f  mov     edx, eax
0x180013731  mov     [rbx], eax
0x180013733  jz      short loc_18001375F
0x180013735  test    dl, 2
0x180013738  jnz     short loc_18001375F
0x18001373a  xor     eax, edi
0x18001373c  and     eax, 180h
0x180013741  xor     eax, edx
0x180013743  mov     ecx, eax
0x180013745  xor     ecx, edi
0x180013747  and     ecx, r15d
0x18001374a  xor     ecx, eax
0x18001374c  or      ecx, 1
0x18001374f  mov     eax, ecx
0x180013751  xor     eax, edi
0x180013753  and     eax, 800h
0x180013758  xor     eax, ecx
0x18001375a  or      eax, 2
0x18001375d  mov     [rbx], eax
0x18001375f  mov     r8d, edx
0x180013762  mov     ecx, eax
0x180013764  and     r8d, 4
0x180013768  jnz     short loc_180013779
0x18001376a  xor     ecx, edi
0x18001376c  and     ecx, 400h
0x180013772  xor     ecx, eax
0x180013774  or      ecx, 4
0x180013777  mov     [rbx], ecx
0x180013779  mov     eax, edx
0x18001377b  lock cmpxchg [rsi], ecx
0x18001377f  jnz     short loc_18001372A
0x180013781  test    r8d, r8d
0x180013784  jnz     short loc_180013796
0x180013786  mov     r8d, ebp
0x180013789  mov     edx, 3
0x18001378e  mov     rcx, rsi
0x180013791  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013796  test    byte ptr [rbx], 2
0x180013799  jnz     short loc_1800137BF
0x18001379b  mov     eax, [rbx]
0x18001379d  xor     eax, edi
0x18001379f  and     eax, 180h
0x1800137a4  xor     eax, [rbx]
0x1800137a6  mov     ecx, eax
0x1800137a8  xor     ecx, edi
0x1800137aa  and     ecx, r15d
0x1800137ad  xor     ecx, eax
0x1800137af  or      ecx, 1
0x1800137b2  mov     eax, ecx
0x1800137b4  xor     eax, edi
0x1800137b6  and     eax, 800h
0x1800137bb  xor     eax, ecx
0x1800137bd  mov     [rbx], eax
0x1800137bf  mov     rbp, [rsp+38h+arg_10]
0x1800137c4  mov     rax, rbx
0x1800137c7  mov     rbx, [rsp+38h+arg_8]
0x1800137cc  add     rsp, 20h
0x1800137d0  pop     r15
0x1800137d2  pop     rdi
0x1800137d3  pop     rsi
0x1800137d4  retn
```
