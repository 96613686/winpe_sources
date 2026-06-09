# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001ea68`
- end: `0x18001ebd5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f9dc`

## callees

- `0x18001e65c`
- `0x18001ea68`
- `0x180020fe4`
- `0x180032010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor,
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
0x18001ea68  mov     [rsp+arg_8], rbx
0x18001ea6d  mov     [rsp+arg_10], rbp
0x18001ea72  mov     [rsp+arg_0], rcx
0x18001ea77  push    rsi
0x18001ea78  push    rdi
0x18001ea79  push    r15
0x18001ea7b  sub     rsp, 20h
0x18001ea7f  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18001ea86  mov     rbx, rdx
0x18001ea89  mov     qword ptr [rdx], 0
0x18001ea90  mov     eax, [rsi]
0x18001ea92  mov     [rdx], eax
0x18001ea94  and     eax, 6
0x18001ea97  cmp     al, 6
0x18001ea99  jz      loc_18001EBBF
0x18001ea9f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001eaa4  mov     ebp, eax
0x18001eaa6  mov     dword ptr [rsp+38h+arg_0], 0
0x18001eaae  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001eab5  test    rax, rax
0x18001eab8  jz      short loc_18001EAD2
0x18001eaba  lea     r8, [rsp+38h+arg_0]
0x18001eabf  mov     edx, 3
0x18001eac4  mov     ecx, 2AF34FDh
0x18001eac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eace  mov     edx, eax
0x18001ead0  jmp     short loc_18001EAE0
0x18001ead2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001ead9  test    rax, rax
0x18001eadc  jnz     short loc_18001EABA
0x18001eade  xor     edx, edx
0x18001eae0  mov     r8d, edx
0x18001eae3  mov     eax, edx
0x18001eae5  and     r8d, 0FFFFFF3Fh
0x18001eaec  and     edx, 80h
0x18001eaf2  mov     ecx, r8d
0x18001eaf5  mov     r15d, 40h ; '@'
0x18001eafb  and     ecx, 3
0x18001eafe  and     eax, r15d
0x18001eb01  shl     ecx, 2
0x18001eb04  or      ecx, eax
0x18001eb06  shl     ecx, 2
0x18001eb09  or      ecx, edx
0x18001eb0b  lea     edi, ds:0[rcx*8]
0x18001eb12  test    r8d, r8d
0x18001eb15  jnz     short loc_18001EB1C
0x18001eb17  mov     eax, r15d
0x18001eb1a  jmp     short loc_18001EB26
0x18001eb1c  xor     eax, eax
0x18001eb1e  cmp     r8d, 2
0x18001eb22  cmovz   eax, r15d
0x18001eb26  or      edi, eax
0x18001eb28  mov     eax, [rbx]
0x18001eb2a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001eb2f  mov     edx, eax
0x18001eb31  mov     [rbx], eax
0x18001eb33  jz      short loc_18001EB5F
0x18001eb35  test    dl, 2
0x18001eb38  jnz     short loc_18001EB5F
0x18001eb3a  xor     eax, edi
0x18001eb3c  and     eax, 180h
0x18001eb41  xor     eax, edx
0x18001eb43  mov     ecx, eax
0x18001eb45  xor     ecx, edi
0x18001eb47  and     ecx, r15d
0x18001eb4a  xor     ecx, eax
0x18001eb4c  or      ecx, 1
0x18001eb4f  mov     eax, ecx
0x18001eb51  xor     eax, edi
0x18001eb53  and     eax, 800h
0x18001eb58  xor     eax, ecx
0x18001eb5a  or      eax, 2
0x18001eb5d  mov     [rbx], eax
0x18001eb5f  mov     r8d, edx
0x18001eb62  mov     ecx, eax
0x18001eb64  and     r8d, 4
0x18001eb68  jnz     short loc_18001EB79
0x18001eb6a  xor     ecx, edi
0x18001eb6c  and     ecx, 400h
0x18001eb72  xor     ecx, eax
0x18001eb74  or      ecx, 4
0x18001eb77  mov     [rbx], ecx
0x18001eb79  mov     eax, edx
0x18001eb7b  lock cmpxchg [rsi], ecx
0x18001eb7f  jnz     short loc_18001EB2A
0x18001eb81  test    r8d, r8d
0x18001eb84  jnz     short loc_18001EB96
0x18001eb86  mov     r8d, ebp
0x18001eb89  mov     edx, 3
0x18001eb8e  mov     rcx, rsi
0x18001eb91  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001eb96  test    byte ptr [rbx], 2
0x18001eb99  jnz     short loc_18001EBBF
0x18001eb9b  mov     eax, [rbx]
0x18001eb9d  xor     eax, edi
0x18001eb9f  and     eax, 180h
0x18001eba4  xor     eax, [rbx]
0x18001eba6  mov     ecx, eax
0x18001eba8  xor     ecx, edi
0x18001ebaa  and     ecx, r15d
0x18001ebad  xor     ecx, eax
0x18001ebaf  or      ecx, 1
0x18001ebb2  mov     eax, ecx
0x18001ebb4  xor     eax, edi
0x18001ebb6  and     eax, 800h
0x18001ebbb  xor     eax, ecx
0x18001ebbd  mov     [rbx], eax
0x18001ebbf  mov     rbp, [rsp+38h+arg_10]
0x18001ebc4  mov     rax, rbx
0x18001ebc7  mov     rbx, [rsp+38h+arg_8]
0x18001ebcc  add     rsp, 20h
0x18001ebd0  pop     r15
0x18001ebd2  pop     rdi
0x18001ebd3  pop     rsi
0x18001ebd4  retn
```
