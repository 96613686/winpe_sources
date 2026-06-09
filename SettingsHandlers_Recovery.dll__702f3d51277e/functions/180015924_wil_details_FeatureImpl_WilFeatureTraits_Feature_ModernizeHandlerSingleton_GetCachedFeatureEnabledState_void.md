# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetCachedFeatureEnabledState(void)

- ea: `0x180015924`
- end: `0x180015a9b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e840`

## callees

- `0x180005b50`
- `0x1800097b0`
- `0x180015924`
- `0x18002b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ModernizeHandlerSingleton__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ModernizeHandlerSingleton__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(37716471, 1, &v14);
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
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)v8)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)v8)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v9 ^ v8) & 0x180 ^ (v8 ^ v9 ^ (v9 ^ v8) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_ModernizeHandlerSingleton__descriptor,
             v12,
             v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ModernizeHandlerSingleton__descriptor,
        1u,
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
0x180015924  mov     [rsp+arg_8], rbx
0x180015929  mov     [rsp+arg_10], rbp
0x18001592e  mov     [rsp+arg_0], rcx
0x180015933  push    rsi
0x180015934  push    rdi
0x180015935  push    r12
0x180015937  sub     rsp, 20h
0x18001593b  mov     rsi, cs:Feature_ModernizeHandlerSingleton__descriptor
0x180015942  mov     rbx, rdx
0x180015945  mov     qword ptr [rdx], 0
0x18001594c  mov     eax, [rsi]
0x18001594e  mov     [rdx], eax
0x180015950  and     eax, 6
0x180015953  cmp     al, 6
0x180015955  jz      loc_180015A85
0x18001595b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015960  mov     ebp, eax
0x180015962  mov     dword ptr [rsp+38h+arg_0], 0
0x18001596a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180015971  test    rax, rax
0x180015974  jz      short loc_18001598E
0x180015976  lea     r8, [rsp+38h+arg_0]
0x18001597b  mov     edx, 1
0x180015980  mov     ecx, 23F81F7h
0x180015985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001598a  mov     edx, eax
0x18001598c  jmp     short loc_18001599C
0x18001598e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180015995  test    rax, rax
0x180015998  jnz     short loc_180015976
0x18001599a  xor     edx, edx
0x18001599c  mov     r8d, edx
0x18001599f  mov     eax, edx
0x1800159a1  and     r8d, 0FFFFFF3Fh
0x1800159a8  and     edx, 80h
0x1800159ae  mov     ecx, r8d
0x1800159b1  mov     r12d, 40h ; '@'
0x1800159b7  and     ecx, 3
0x1800159ba  and     eax, r12d
0x1800159bd  shl     ecx, 2
0x1800159c0  or      ecx, eax
0x1800159c2  shl     ecx, 2
0x1800159c5  or      ecx, edx
0x1800159c7  lea     edi, ds:0[rcx*8]
0x1800159ce  test    r8d, r8d
0x1800159d1  jnz     short loc_1800159D8
0x1800159d3  mov     eax, r12d
0x1800159d6  jmp     short loc_1800159E2
0x1800159d8  xor     eax, eax
0x1800159da  cmp     r8d, 2
0x1800159de  cmovz   eax, r12d
0x1800159e2  or      edi, eax
0x1800159e4  mov     eax, [rbx]
0x1800159e6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800159eb  mov     edx, eax
0x1800159ed  mov     [rbx], eax
0x1800159ef  jz      short loc_180015A1F
0x1800159f1  test    dl, 2
0x1800159f4  jnz     short loc_180015A1F
0x1800159f6  mov     eax, edi
0x1800159f8  xor     eax, edx
0x1800159fa  and     eax, 180h
0x1800159ff  xor     eax, edx
0x180015a01  mov     ecx, eax
0x180015a03  xor     ecx, edi
0x180015a05  and     ecx, r12d
0x180015a08  xor     ecx, eax
0x180015a0a  or      ecx, 1
0x180015a0d  mov     eax, ecx
0x180015a0f  xor     eax, edi
0x180015a11  and     eax, 800h
0x180015a16  xor     eax, ecx
0x180015a18  or      eax, 2
0x180015a1b  mov     [rbx], eax
0x180015a1d  jmp     short loc_180015A21
0x180015a1f  mov     eax, edx
0x180015a21  mov     r8d, edx
0x180015a24  and     r8d, 4
0x180015a28  jnz     short loc_180015A3D
0x180015a2a  mov     ecx, edi
0x180015a2c  xor     ecx, eax
0x180015a2e  and     ecx, 400h
0x180015a34  xor     ecx, eax
0x180015a36  or      ecx, 4
0x180015a39  mov     [rbx], ecx
0x180015a3b  jmp     short loc_180015A3F
0x180015a3d  mov     ecx, eax
0x180015a3f  mov     eax, edx
0x180015a41  lock cmpxchg [rsi], ecx
0x180015a45  jnz     short loc_1800159E6
0x180015a47  test    r8d, r8d
0x180015a4a  jnz     short loc_180015A5C
0x180015a4c  mov     r8d, ebp
0x180015a4f  mov     edx, 1
0x180015a54  mov     rcx, rsi
0x180015a57  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180015a5c  test    byte ptr [rbx], 2
0x180015a5f  jnz     short loc_180015A85
0x180015a61  mov     eax, [rbx]
0x180015a63  xor     eax, edi
0x180015a65  and     eax, 180h
0x180015a6a  xor     eax, [rbx]
0x180015a6c  mov     ecx, eax
0x180015a6e  xor     ecx, edi
0x180015a70  and     ecx, r12d
0x180015a73  xor     ecx, eax
0x180015a75  or      ecx, 1
0x180015a78  mov     eax, ecx
0x180015a7a  xor     eax, edi
0x180015a7c  and     eax, 800h
0x180015a81  xor     eax, ecx
0x180015a83  mov     [rbx], eax
0x180015a85  mov     rbp, [rsp+38h+arg_10]
0x180015a8a  mov     rax, rbx
0x180015a8d  mov     rbx, [rsp+38h+arg_8]
0x180015a92  add     rsp, 20h
0x180015a96  pop     r12
0x180015a98  pop     rdi
0x180015a99  pop     rsi
0x180015a9a  retn
```
