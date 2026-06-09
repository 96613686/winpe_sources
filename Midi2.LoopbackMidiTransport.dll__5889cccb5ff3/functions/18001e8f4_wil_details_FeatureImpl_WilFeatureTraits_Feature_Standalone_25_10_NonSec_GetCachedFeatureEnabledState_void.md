# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001e8f4`
- end: `0x18001ea61`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ff9c`

## callees

- `0x18001e65c`
- `0x18001e8f4`
- `0x180020fe4`
- `0x180032010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
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
0x18001e8f4  mov     [rsp+arg_8], rbx
0x18001e8f9  mov     [rsp+arg_10], rbp
0x18001e8fe  mov     [rsp+arg_0], rcx
0x18001e903  push    rsi
0x18001e904  push    rdi
0x18001e905  push    r15
0x18001e907  sub     rsp, 20h
0x18001e90b  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18001e912  mov     rbx, rdx
0x18001e915  mov     qword ptr [rdx], 0
0x18001e91c  mov     eax, [rsi]
0x18001e91e  mov     [rdx], eax
0x18001e920  and     eax, 6
0x18001e923  cmp     al, 6
0x18001e925  jz      loc_18001EA4B
0x18001e92b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001e930  mov     ebp, eax
0x18001e932  mov     dword ptr [rsp+38h+arg_0], 0
0x18001e93a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001e941  test    rax, rax
0x18001e944  jz      short loc_18001E95E
0x18001e946  lea     r8, [rsp+38h+arg_0]
0x18001e94b  mov     edx, 3
0x18001e950  mov     ecx, 2AF34F8h
0x18001e955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e95a  mov     edx, eax
0x18001e95c  jmp     short loc_18001E96C
0x18001e95e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001e965  test    rax, rax
0x18001e968  jnz     short loc_18001E946
0x18001e96a  xor     edx, edx
0x18001e96c  mov     r8d, edx
0x18001e96f  mov     eax, edx
0x18001e971  and     r8d, 0FFFFFF3Fh
0x18001e978  and     edx, 80h
0x18001e97e  mov     ecx, r8d
0x18001e981  mov     r15d, 40h ; '@'
0x18001e987  and     ecx, 3
0x18001e98a  and     eax, r15d
0x18001e98d  shl     ecx, 2
0x18001e990  or      ecx, eax
0x18001e992  shl     ecx, 2
0x18001e995  or      ecx, edx
0x18001e997  lea     edi, ds:0[rcx*8]
0x18001e99e  test    r8d, r8d
0x18001e9a1  jnz     short loc_18001E9A8
0x18001e9a3  mov     eax, r15d
0x18001e9a6  jmp     short loc_18001E9B2
0x18001e9a8  xor     eax, eax
0x18001e9aa  cmp     r8d, 2
0x18001e9ae  cmovz   eax, r15d
0x18001e9b2  or      edi, eax
0x18001e9b4  mov     eax, [rbx]
0x18001e9b6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001e9bb  mov     edx, eax
0x18001e9bd  mov     [rbx], eax
0x18001e9bf  jz      short loc_18001E9EB
0x18001e9c1  test    dl, 2
0x18001e9c4  jnz     short loc_18001E9EB
0x18001e9c6  xor     eax, edi
0x18001e9c8  and     eax, 180h
0x18001e9cd  xor     eax, edx
0x18001e9cf  mov     ecx, eax
0x18001e9d1  xor     ecx, edi
0x18001e9d3  and     ecx, r15d
0x18001e9d6  xor     ecx, eax
0x18001e9d8  or      ecx, 1
0x18001e9db  mov     eax, ecx
0x18001e9dd  xor     eax, edi
0x18001e9df  and     eax, 800h
0x18001e9e4  xor     eax, ecx
0x18001e9e6  or      eax, 2
0x18001e9e9  mov     [rbx], eax
0x18001e9eb  mov     r8d, edx
0x18001e9ee  mov     ecx, eax
0x18001e9f0  and     r8d, 4
0x18001e9f4  jnz     short loc_18001EA05
0x18001e9f6  xor     ecx, edi
0x18001e9f8  and     ecx, 400h
0x18001e9fe  xor     ecx, eax
0x18001ea00  or      ecx, 4
0x18001ea03  mov     [rbx], ecx
0x18001ea05  mov     eax, edx
0x18001ea07  lock cmpxchg [rsi], ecx
0x18001ea0b  jnz     short loc_18001E9B6
0x18001ea0d  test    r8d, r8d
0x18001ea10  jnz     short loc_18001EA22
0x18001ea12  mov     r8d, ebp
0x18001ea15  mov     edx, 3
0x18001ea1a  mov     rcx, rsi
0x18001ea1d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001ea22  test    byte ptr [rbx], 2
0x18001ea25  jnz     short loc_18001EA4B
0x18001ea27  mov     eax, [rbx]
0x18001ea29  xor     eax, edi
0x18001ea2b  and     eax, 180h
0x18001ea30  xor     eax, [rbx]
0x18001ea32  mov     ecx, eax
0x18001ea34  xor     ecx, edi
0x18001ea36  and     ecx, r15d
0x18001ea39  xor     ecx, eax
0x18001ea3b  or      ecx, 1
0x18001ea3e  mov     eax, ecx
0x18001ea40  xor     eax, edi
0x18001ea42  and     eax, 800h
0x18001ea47  xor     eax, ecx
0x18001ea49  mov     [rbx], eax
0x18001ea4b  mov     rbp, [rsp+38h+arg_10]
0x18001ea50  mov     rax, rbx
0x18001ea53  mov     rbx, [rsp+38h+arg_8]
0x18001ea58  add     rsp, 20h
0x18001ea5c  pop     r15
0x18001ea5e  pop     rdi
0x18001ea5f  pop     rsi
0x18001ea60  retn
```
