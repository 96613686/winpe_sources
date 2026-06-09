# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e688`
- end: `0x18000e7f5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f424`

## callees

- `0x1800058e8`
- `0x180009270`
- `0x18000e688`
- `0x180018010`

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
0x18000e688  mov     [rsp+arg_8], rbx
0x18000e68d  mov     [rsp+arg_10], rbp
0x18000e692  mov     [rsp+arg_0], rcx
0x18000e697  push    rsi
0x18000e698  push    rdi
0x18000e699  push    r15
0x18000e69b  sub     rsp, 20h
0x18000e69f  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18000e6a6  mov     rbx, rdx
0x18000e6a9  mov     qword ptr [rdx], 0
0x18000e6b0  mov     eax, [rsi]
0x18000e6b2  mov     [rdx], eax
0x18000e6b4  and     eax, 6
0x18000e6b7  cmp     al, 6
0x18000e6b9  jz      loc_18000E7DF
0x18000e6bf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e6c4  mov     ebp, eax
0x18000e6c6  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e6ce  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e6d5  test    rax, rax
0x18000e6d8  jz      short loc_18000E6F2
0x18000e6da  lea     r8, [rsp+38h+arg_0]
0x18000e6df  mov     edx, 3
0x18000e6e4  mov     ecx, 37E286Ch
0x18000e6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ee  mov     edx, eax
0x18000e6f0  jmp     short loc_18000E700
0x18000e6f2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e6f9  test    rax, rax
0x18000e6fc  jnz     short loc_18000E6DA
0x18000e6fe  xor     edx, edx
0x18000e700  mov     r8d, edx
0x18000e703  mov     eax, edx
0x18000e705  and     r8d, 0FFFFFF3Fh
0x18000e70c  and     edx, 80h
0x18000e712  mov     ecx, r8d
0x18000e715  mov     r15d, 40h ; '@'
0x18000e71b  and     ecx, 3
0x18000e71e  and     eax, r15d
0x18000e721  shl     ecx, 2
0x18000e724  or      ecx, eax
0x18000e726  shl     ecx, 2
0x18000e729  or      ecx, edx
0x18000e72b  lea     edi, ds:0[rcx*8]
0x18000e732  test    r8d, r8d
0x18000e735  jnz     short loc_18000E73C
0x18000e737  mov     eax, r15d
0x18000e73a  jmp     short loc_18000E746
0x18000e73c  xor     eax, eax
0x18000e73e  cmp     r8d, 2
0x18000e742  cmovz   eax, r15d
0x18000e746  or      edi, eax
0x18000e748  mov     eax, [rbx]
0x18000e74a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e74f  mov     edx, eax
0x18000e751  mov     [rbx], eax
0x18000e753  jz      short loc_18000E77F
0x18000e755  test    dl, 2
0x18000e758  jnz     short loc_18000E77F
0x18000e75a  xor     eax, edi
0x18000e75c  and     eax, 180h
0x18000e761  xor     eax, edx
0x18000e763  mov     ecx, eax
0x18000e765  xor     ecx, edi
0x18000e767  and     ecx, r15d
0x18000e76a  xor     ecx, eax
0x18000e76c  or      ecx, 1
0x18000e76f  mov     eax, ecx
0x18000e771  xor     eax, edi
0x18000e773  and     eax, 800h
0x18000e778  xor     eax, ecx
0x18000e77a  or      eax, 2
0x18000e77d  mov     [rbx], eax
0x18000e77f  mov     r8d, edx
0x18000e782  mov     ecx, eax
0x18000e784  and     r8d, 4
0x18000e788  jnz     short loc_18000E799
0x18000e78a  xor     ecx, edi
0x18000e78c  and     ecx, 400h
0x18000e792  xor     ecx, eax
0x18000e794  or      ecx, 4
0x18000e797  mov     [rbx], ecx
0x18000e799  mov     eax, edx
0x18000e79b  lock cmpxchg [rsi], ecx
0x18000e79f  jnz     short loc_18000E74A
0x18000e7a1  test    r8d, r8d
0x18000e7a4  jnz     short loc_18000E7B6
0x18000e7a6  mov     r8d, ebp
0x18000e7a9  mov     edx, 3
0x18000e7ae  mov     rcx, rsi
0x18000e7b1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e7b6  test    byte ptr [rbx], 2
0x18000e7b9  jnz     short loc_18000E7DF
0x18000e7bb  mov     eax, [rbx]
0x18000e7bd  xor     eax, edi
0x18000e7bf  and     eax, 180h
0x18000e7c4  xor     eax, [rbx]
0x18000e7c6  mov     ecx, eax
0x18000e7c8  xor     ecx, edi
0x18000e7ca  and     ecx, r15d
0x18000e7cd  xor     ecx, eax
0x18000e7cf  or      ecx, 1
0x18000e7d2  mov     eax, ecx
0x18000e7d4  xor     eax, edi
0x18000e7d6  and     eax, 800h
0x18000e7db  xor     eax, ecx
0x18000e7dd  mov     [rbx], eax
0x18000e7df  mov     rbp, [rsp+38h+arg_10]
0x18000e7e4  mov     rax, rbx
0x18000e7e7  mov     rbx, [rsp+38h+arg_8]
0x18000e7ec  add     rsp, 20h
0x18000e7f0  pop     r15
0x18000e7f2  pop     rdi
0x18000e7f3  pop     rsi
0x18000e7f4  retn
```
