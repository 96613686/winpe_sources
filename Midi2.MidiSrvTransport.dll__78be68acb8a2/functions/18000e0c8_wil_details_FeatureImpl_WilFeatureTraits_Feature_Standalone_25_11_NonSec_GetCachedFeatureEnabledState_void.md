# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e0c8`
- end: `0x18000e235`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000eca4`

## callees

- `0x18000da08`
- `0x18000e0c8`
- `0x180010c28`
- `0x180015010`

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
0x18000e0c8  mov     [rsp+arg_8], rbx
0x18000e0cd  mov     [rsp+arg_10], rbp
0x18000e0d2  mov     [rsp+arg_0], rcx
0x18000e0d7  push    rsi
0x18000e0d8  push    rdi
0x18000e0d9  push    r15
0x18000e0db  sub     rsp, 20h
0x18000e0df  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000e0e6  mov     rbx, rdx
0x18000e0e9  mov     qword ptr [rdx], 0
0x18000e0f0  mov     eax, [rsi]
0x18000e0f2  mov     [rdx], eax
0x18000e0f4  and     eax, 6
0x18000e0f7  cmp     al, 6
0x18000e0f9  jz      loc_18000E21F
0x18000e0ff  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e104  mov     ebp, eax
0x18000e106  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e10e  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e115  test    rax, rax
0x18000e118  jz      short loc_18000E132
0x18000e11a  lea     r8, [rsp+38h+arg_0]
0x18000e11f  mov     edx, 3
0x18000e124  mov     ecx, 2AF34FDh
0x18000e129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e12e  mov     edx, eax
0x18000e130  jmp     short loc_18000E140
0x18000e132  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e139  test    rax, rax
0x18000e13c  jnz     short loc_18000E11A
0x18000e13e  xor     edx, edx
0x18000e140  mov     r8d, edx
0x18000e143  mov     eax, edx
0x18000e145  and     r8d, 0FFFFFF3Fh
0x18000e14c  and     edx, 80h
0x18000e152  mov     ecx, r8d
0x18000e155  mov     r15d, 40h ; '@'
0x18000e15b  and     ecx, 3
0x18000e15e  and     eax, r15d
0x18000e161  shl     ecx, 2
0x18000e164  or      ecx, eax
0x18000e166  shl     ecx, 2
0x18000e169  or      ecx, edx
0x18000e16b  lea     edi, ds:0[rcx*8]
0x18000e172  test    r8d, r8d
0x18000e175  jnz     short loc_18000E17C
0x18000e177  mov     eax, r15d
0x18000e17a  jmp     short loc_18000E186
0x18000e17c  xor     eax, eax
0x18000e17e  cmp     r8d, 2
0x18000e182  cmovz   eax, r15d
0x18000e186  or      edi, eax
0x18000e188  mov     eax, [rbx]
0x18000e18a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e18f  mov     edx, eax
0x18000e191  mov     [rbx], eax
0x18000e193  jz      short loc_18000E1BF
0x18000e195  test    dl, 2
0x18000e198  jnz     short loc_18000E1BF
0x18000e19a  xor     eax, edi
0x18000e19c  and     eax, 180h
0x18000e1a1  xor     eax, edx
0x18000e1a3  mov     ecx, eax
0x18000e1a5  xor     ecx, edi
0x18000e1a7  and     ecx, r15d
0x18000e1aa  xor     ecx, eax
0x18000e1ac  or      ecx, 1
0x18000e1af  mov     eax, ecx
0x18000e1b1  xor     eax, edi
0x18000e1b3  and     eax, 800h
0x18000e1b8  xor     eax, ecx
0x18000e1ba  or      eax, 2
0x18000e1bd  mov     [rbx], eax
0x18000e1bf  mov     r8d, edx
0x18000e1c2  mov     ecx, eax
0x18000e1c4  and     r8d, 4
0x18000e1c8  jnz     short loc_18000E1D9
0x18000e1ca  xor     ecx, edi
0x18000e1cc  and     ecx, 400h
0x18000e1d2  xor     ecx, eax
0x18000e1d4  or      ecx, 4
0x18000e1d7  mov     [rbx], ecx
0x18000e1d9  mov     eax, edx
0x18000e1db  lock cmpxchg [rsi], ecx
0x18000e1df  jnz     short loc_18000E18A
0x18000e1e1  test    r8d, r8d
0x18000e1e4  jnz     short loc_18000E1F6
0x18000e1e6  mov     r8d, ebp
0x18000e1e9  mov     edx, 3
0x18000e1ee  mov     rcx, rsi
0x18000e1f1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e1f6  test    byte ptr [rbx], 2
0x18000e1f9  jnz     short loc_18000E21F
0x18000e1fb  mov     eax, [rbx]
0x18000e1fd  xor     eax, edi
0x18000e1ff  and     eax, 180h
0x18000e204  xor     eax, [rbx]
0x18000e206  mov     ecx, eax
0x18000e208  xor     ecx, edi
0x18000e20a  and     ecx, r15d
0x18000e20d  xor     ecx, eax
0x18000e20f  or      ecx, 1
0x18000e212  mov     eax, ecx
0x18000e214  xor     eax, edi
0x18000e216  and     eax, 800h
0x18000e21b  xor     eax, ecx
0x18000e21d  mov     [rbx], eax
0x18000e21f  mov     rbp, [rsp+38h+arg_10]
0x18000e224  mov     rax, rbx
0x18000e227  mov     rbx, [rsp+38h+arg_8]
0x18000e22c  add     rsp, 20h
0x18000e230  pop     r15
0x18000e232  pop     rdi
0x18000e233  pop     rsi
0x18000e234  retn
```
