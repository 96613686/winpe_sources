# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e3b0`
- end: `0x18000e51d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000eb34`

## callees

- `0x18000da08`
- `0x18000e3b0`
- `0x180010c28`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599550, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor,
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
0x18000e3b0  mov     [rsp+arg_8], rbx
0x18000e3b5  mov     [rsp+arg_10], rbp
0x18000e3ba  mov     [rsp+arg_0], rcx
0x18000e3bf  push    rsi
0x18000e3c0  push    rdi
0x18000e3c1  push    r15
0x18000e3c3  sub     rsp, 20h
0x18000e3c7  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18000e3ce  mov     rbx, rdx
0x18000e3d1  mov     qword ptr [rdx], 0
0x18000e3d8  mov     eax, [rsi]
0x18000e3da  mov     [rdx], eax
0x18000e3dc  and     eax, 6
0x18000e3df  cmp     al, 6
0x18000e3e1  jz      loc_18000E507
0x18000e3e7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e3ec  mov     ebp, eax
0x18000e3ee  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e3f6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e3fd  test    rax, rax
0x18000e400  jz      short loc_18000E41A
0x18000e402  lea     r8, [rsp+38h+arg_0]
0x18000e407  mov     edx, 3
0x18000e40c  mov     ecx, 37E287Eh
0x18000e411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e416  mov     edx, eax
0x18000e418  jmp     short loc_18000E428
0x18000e41a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e421  test    rax, rax
0x18000e424  jnz     short loc_18000E402
0x18000e426  xor     edx, edx
0x18000e428  mov     r8d, edx
0x18000e42b  mov     eax, edx
0x18000e42d  and     r8d, 0FFFFFF3Fh
0x18000e434  and     edx, 80h
0x18000e43a  mov     ecx, r8d
0x18000e43d  mov     r15d, 40h ; '@'
0x18000e443  and     ecx, 3
0x18000e446  and     eax, r15d
0x18000e449  shl     ecx, 2
0x18000e44c  or      ecx, eax
0x18000e44e  shl     ecx, 2
0x18000e451  or      ecx, edx
0x18000e453  lea     edi, ds:0[rcx*8]
0x18000e45a  test    r8d, r8d
0x18000e45d  jnz     short loc_18000E464
0x18000e45f  mov     eax, r15d
0x18000e462  jmp     short loc_18000E46E
0x18000e464  xor     eax, eax
0x18000e466  cmp     r8d, 2
0x18000e46a  cmovz   eax, r15d
0x18000e46e  or      edi, eax
0x18000e470  mov     eax, [rbx]
0x18000e472  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e477  mov     edx, eax
0x18000e479  mov     [rbx], eax
0x18000e47b  jz      short loc_18000E4A7
0x18000e47d  test    dl, 2
0x18000e480  jnz     short loc_18000E4A7
0x18000e482  xor     eax, edi
0x18000e484  and     eax, 180h
0x18000e489  xor     eax, edx
0x18000e48b  mov     ecx, eax
0x18000e48d  xor     ecx, edi
0x18000e48f  and     ecx, r15d
0x18000e492  xor     ecx, eax
0x18000e494  or      ecx, 1
0x18000e497  mov     eax, ecx
0x18000e499  xor     eax, edi
0x18000e49b  and     eax, 800h
0x18000e4a0  xor     eax, ecx
0x18000e4a2  or      eax, 2
0x18000e4a5  mov     [rbx], eax
0x18000e4a7  mov     r8d, edx
0x18000e4aa  mov     ecx, eax
0x18000e4ac  and     r8d, 4
0x18000e4b0  jnz     short loc_18000E4C1
0x18000e4b2  xor     ecx, edi
0x18000e4b4  and     ecx, 400h
0x18000e4ba  xor     ecx, eax
0x18000e4bc  or      ecx, 4
0x18000e4bf  mov     [rbx], ecx
0x18000e4c1  mov     eax, edx
0x18000e4c3  lock cmpxchg [rsi], ecx
0x18000e4c7  jnz     short loc_18000E472
0x18000e4c9  test    r8d, r8d
0x18000e4cc  jnz     short loc_18000E4DE
0x18000e4ce  mov     r8d, ebp
0x18000e4d1  mov     edx, 3
0x18000e4d6  mov     rcx, rsi
0x18000e4d9  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e4de  test    byte ptr [rbx], 2
0x18000e4e1  jnz     short loc_18000E507
0x18000e4e3  mov     eax, [rbx]
0x18000e4e5  xor     eax, edi
0x18000e4e7  and     eax, 180h
0x18000e4ec  xor     eax, [rbx]
0x18000e4ee  mov     ecx, eax
0x18000e4f0  xor     ecx, edi
0x18000e4f2  and     ecx, r15d
0x18000e4f5  xor     ecx, eax
0x18000e4f7  or      ecx, 1
0x18000e4fa  mov     eax, ecx
0x18000e4fc  xor     eax, edi
0x18000e4fe  and     eax, 800h
0x18000e503  xor     eax, ecx
0x18000e505  mov     [rbx], eax
0x18000e507  mov     rbp, [rsp+38h+arg_10]
0x18000e50c  mov     rax, rbx
0x18000e50f  mov     rbx, [rsp+38h+arg_8]
0x18000e514  add     rsp, 20h
0x18000e518  pop     r15
0x18000e51a  pop     rdi
0x18000e51b  pop     rsi
0x18000e51c  retn
```
