# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000af84`
- end: `0x18000b0f1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bca4`

## callees

- `0x18000ab78`
- `0x18000af84`
- `0x18000d258`
- `0x18000f010`

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
0x18000af84  mov     [rsp+arg_8], rbx
0x18000af89  mov     [rsp+arg_10], rbp
0x18000af8e  mov     [rsp+arg_0], rcx
0x18000af93  push    rsi
0x18000af94  push    rdi
0x18000af95  push    r15
0x18000af97  sub     rsp, 20h
0x18000af9b  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000afa2  mov     rbx, rdx
0x18000afa5  mov     qword ptr [rdx], 0
0x18000afac  mov     eax, [rsi]
0x18000afae  mov     [rdx], eax
0x18000afb0  and     eax, 6
0x18000afb3  cmp     al, 6
0x18000afb5  jz      loc_18000B0DB
0x18000afbb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000afc0  mov     ebp, eax
0x18000afc2  mov     dword ptr [rsp+38h+arg_0], 0
0x18000afca  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000afd1  test    rax, rax
0x18000afd4  jz      short loc_18000AFEE
0x18000afd6  lea     r8, [rsp+38h+arg_0]
0x18000afdb  mov     edx, 3
0x18000afe0  mov     ecx, 2AF34FDh
0x18000afe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afea  mov     edx, eax
0x18000afec  jmp     short loc_18000AFFC
0x18000afee  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000aff5  test    rax, rax
0x18000aff8  jnz     short loc_18000AFD6
0x18000affa  xor     edx, edx
0x18000affc  mov     r8d, edx
0x18000afff  mov     eax, edx
0x18000b001  and     r8d, 0FFFFFF3Fh
0x18000b008  and     edx, 80h
0x18000b00e  mov     ecx, r8d
0x18000b011  mov     r15d, 40h ; '@'
0x18000b017  and     ecx, 3
0x18000b01a  and     eax, r15d
0x18000b01d  shl     ecx, 2
0x18000b020  or      ecx, eax
0x18000b022  shl     ecx, 2
0x18000b025  or      ecx, edx
0x18000b027  lea     edi, ds:0[rcx*8]
0x18000b02e  test    r8d, r8d
0x18000b031  jnz     short loc_18000B038
0x18000b033  mov     eax, r15d
0x18000b036  jmp     short loc_18000B042
0x18000b038  xor     eax, eax
0x18000b03a  cmp     r8d, 2
0x18000b03e  cmovz   eax, r15d
0x18000b042  or      edi, eax
0x18000b044  mov     eax, [rbx]
0x18000b046  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000b04b  mov     edx, eax
0x18000b04d  mov     [rbx], eax
0x18000b04f  jz      short loc_18000B07B
0x18000b051  test    dl, 2
0x18000b054  jnz     short loc_18000B07B
0x18000b056  xor     eax, edi
0x18000b058  and     eax, 180h
0x18000b05d  xor     eax, edx
0x18000b05f  mov     ecx, eax
0x18000b061  xor     ecx, edi
0x18000b063  and     ecx, r15d
0x18000b066  xor     ecx, eax
0x18000b068  or      ecx, 1
0x18000b06b  mov     eax, ecx
0x18000b06d  xor     eax, edi
0x18000b06f  and     eax, 800h
0x18000b074  xor     eax, ecx
0x18000b076  or      eax, 2
0x18000b079  mov     [rbx], eax
0x18000b07b  mov     r8d, edx
0x18000b07e  mov     ecx, eax
0x18000b080  and     r8d, 4
0x18000b084  jnz     short loc_18000B095
0x18000b086  xor     ecx, edi
0x18000b088  and     ecx, 400h
0x18000b08e  xor     ecx, eax
0x18000b090  or      ecx, 4
0x18000b093  mov     [rbx], ecx
0x18000b095  mov     eax, edx
0x18000b097  lock cmpxchg [rsi], ecx
0x18000b09b  jnz     short loc_18000B046
0x18000b09d  test    r8d, r8d
0x18000b0a0  jnz     short loc_18000B0B2
0x18000b0a2  mov     r8d, ebp
0x18000b0a5  mov     edx, 3
0x18000b0aa  mov     rcx, rsi
0x18000b0ad  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000b0b2  test    byte ptr [rbx], 2
0x18000b0b5  jnz     short loc_18000B0DB
0x18000b0b7  mov     eax, [rbx]
0x18000b0b9  xor     eax, edi
0x18000b0bb  and     eax, 180h
0x18000b0c0  xor     eax, [rbx]
0x18000b0c2  mov     ecx, eax
0x18000b0c4  xor     ecx, edi
0x18000b0c6  and     ecx, r15d
0x18000b0c9  xor     ecx, eax
0x18000b0cb  or      ecx, 1
0x18000b0ce  mov     eax, ecx
0x18000b0d0  xor     eax, edi
0x18000b0d2  and     eax, 800h
0x18000b0d7  xor     eax, ecx
0x18000b0d9  mov     [rbx], eax
0x18000b0db  mov     rbp, [rsp+38h+arg_10]
0x18000b0e0  mov     rax, rbx
0x18000b0e3  mov     rbx, [rsp+38h+arg_8]
0x18000b0e8  add     rsp, 20h
0x18000b0ec  pop     r15
0x18000b0ee  pop     rdi
0x18000b0ef  pop     rsi
0x18000b0f0  retn
```
