# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000df54`
- end: `0x18000e0c1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ef84`

## callees

- `0x18000da08`
- `0x18000df54`
- `0x180010c28`
- `0x180015010`

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
0x18000df54  mov     [rsp+arg_8], rbx
0x18000df59  mov     [rsp+arg_10], rbp
0x18000df5e  mov     [rsp+arg_0], rcx
0x18000df63  push    rsi
0x18000df64  push    rdi
0x18000df65  push    r15
0x18000df67  sub     rsp, 20h
0x18000df6b  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18000df72  mov     rbx, rdx
0x18000df75  mov     qword ptr [rdx], 0
0x18000df7c  mov     eax, [rsi]
0x18000df7e  mov     [rdx], eax
0x18000df80  and     eax, 6
0x18000df83  cmp     al, 6
0x18000df85  jz      loc_18000E0AB
0x18000df8b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000df90  mov     ebp, eax
0x18000df92  mov     dword ptr [rsp+38h+arg_0], 0
0x18000df9a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000dfa1  test    rax, rax
0x18000dfa4  jz      short loc_18000DFBE
0x18000dfa6  lea     r8, [rsp+38h+arg_0]
0x18000dfab  mov     edx, 3
0x18000dfb0  mov     ecx, 2AF34F8h
0x18000dfb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfba  mov     edx, eax
0x18000dfbc  jmp     short loc_18000DFCC
0x18000dfbe  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000dfc5  test    rax, rax
0x18000dfc8  jnz     short loc_18000DFA6
0x18000dfca  xor     edx, edx
0x18000dfcc  mov     r8d, edx
0x18000dfcf  mov     eax, edx
0x18000dfd1  and     r8d, 0FFFFFF3Fh
0x18000dfd8  and     edx, 80h
0x18000dfde  mov     ecx, r8d
0x18000dfe1  mov     r15d, 40h ; '@'
0x18000dfe7  and     ecx, 3
0x18000dfea  and     eax, r15d
0x18000dfed  shl     ecx, 2
0x18000dff0  or      ecx, eax
0x18000dff2  shl     ecx, 2
0x18000dff5  or      ecx, edx
0x18000dff7  lea     edi, ds:0[rcx*8]
0x18000dffe  test    r8d, r8d
0x18000e001  jnz     short loc_18000E008
0x18000e003  mov     eax, r15d
0x18000e006  jmp     short loc_18000E012
0x18000e008  xor     eax, eax
0x18000e00a  cmp     r8d, 2
0x18000e00e  cmovz   eax, r15d
0x18000e012  or      edi, eax
0x18000e014  mov     eax, [rbx]
0x18000e016  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e01b  mov     edx, eax
0x18000e01d  mov     [rbx], eax
0x18000e01f  jz      short loc_18000E04B
0x18000e021  test    dl, 2
0x18000e024  jnz     short loc_18000E04B
0x18000e026  xor     eax, edi
0x18000e028  and     eax, 180h
0x18000e02d  xor     eax, edx
0x18000e02f  mov     ecx, eax
0x18000e031  xor     ecx, edi
0x18000e033  and     ecx, r15d
0x18000e036  xor     ecx, eax
0x18000e038  or      ecx, 1
0x18000e03b  mov     eax, ecx
0x18000e03d  xor     eax, edi
0x18000e03f  and     eax, 800h
0x18000e044  xor     eax, ecx
0x18000e046  or      eax, 2
0x18000e049  mov     [rbx], eax
0x18000e04b  mov     r8d, edx
0x18000e04e  mov     ecx, eax
0x18000e050  and     r8d, 4
0x18000e054  jnz     short loc_18000E065
0x18000e056  xor     ecx, edi
0x18000e058  and     ecx, 400h
0x18000e05e  xor     ecx, eax
0x18000e060  or      ecx, 4
0x18000e063  mov     [rbx], ecx
0x18000e065  mov     eax, edx
0x18000e067  lock cmpxchg [rsi], ecx
0x18000e06b  jnz     short loc_18000E016
0x18000e06d  test    r8d, r8d
0x18000e070  jnz     short loc_18000E082
0x18000e072  mov     r8d, ebp
0x18000e075  mov     edx, 3
0x18000e07a  mov     rcx, rsi
0x18000e07d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e082  test    byte ptr [rbx], 2
0x18000e085  jnz     short loc_18000E0AB
0x18000e087  mov     eax, [rbx]
0x18000e089  xor     eax, edi
0x18000e08b  and     eax, 180h
0x18000e090  xor     eax, [rbx]
0x18000e092  mov     ecx, eax
0x18000e094  xor     ecx, edi
0x18000e096  and     ecx, r15d
0x18000e099  xor     ecx, eax
0x18000e09b  or      ecx, 1
0x18000e09e  mov     eax, ecx
0x18000e0a0  xor     eax, edi
0x18000e0a2  and     eax, 800h
0x18000e0a7  xor     eax, ecx
0x18000e0a9  mov     [rbx], eax
0x18000e0ab  mov     rbp, [rsp+38h+arg_10]
0x18000e0b0  mov     rax, rbx
0x18000e0b3  mov     rbx, [rsp+38h+arg_8]
0x18000e0b8  add     rsp, 20h
0x18000e0bc  pop     r15
0x18000e0be  pop     rdi
0x18000e0bf  pop     rsi
0x18000e0c0  retn
```
