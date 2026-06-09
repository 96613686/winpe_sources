# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e0bc`
- end: `0x18000e229`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_04_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ed40`

## callees

- `0x18000d6e0`
- `0x18000e0bc`
- `0x18000ff38`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599559, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_04_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_04_NonSec__descriptor,
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
0x18000e0bc  mov     [rsp+arg_8], rbx
0x18000e0c1  mov     [rsp+arg_10], rbp
0x18000e0c6  mov     [rsp+arg_0], rcx
0x18000e0cb  push    rsi
0x18000e0cc  push    rdi
0x18000e0cd  push    r15
0x18000e0cf  sub     rsp, 20h
0x18000e0d3  mov     rsi, cs:Feature_Standalone_26_04_NonSec__descriptor
0x18000e0da  mov     rbx, rdx
0x18000e0dd  mov     qword ptr [rdx], 0
0x18000e0e4  mov     eax, [rsi]
0x18000e0e6  mov     [rdx], eax
0x18000e0e8  and     eax, 6
0x18000e0eb  cmp     al, 6
0x18000e0ed  jz      loc_18000E213
0x18000e0f3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e0f8  mov     ebp, eax
0x18000e0fa  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e102  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e109  test    rax, rax
0x18000e10c  jz      short loc_18000E126
0x18000e10e  lea     r8, [rsp+38h+arg_0]
0x18000e113  mov     edx, 3
0x18000e118  mov     ecx, 37E2887h
0x18000e11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e122  mov     edx, eax
0x18000e124  jmp     short loc_18000E134
0x18000e126  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e12d  test    rax, rax
0x18000e130  jnz     short loc_18000E10E
0x18000e132  xor     edx, edx
0x18000e134  mov     r8d, edx
0x18000e137  mov     eax, edx
0x18000e139  and     r8d, 0FFFFFF3Fh
0x18000e140  and     edx, 80h
0x18000e146  mov     ecx, r8d
0x18000e149  mov     r15d, 40h ; '@'
0x18000e14f  and     ecx, 3
0x18000e152  and     eax, r15d
0x18000e155  shl     ecx, 2
0x18000e158  or      ecx, eax
0x18000e15a  shl     ecx, 2
0x18000e15d  or      ecx, edx
0x18000e15f  lea     edi, ds:0[rcx*8]
0x18000e166  test    r8d, r8d
0x18000e169  jnz     short loc_18000E170
0x18000e16b  mov     eax, r15d
0x18000e16e  jmp     short loc_18000E17A
0x18000e170  xor     eax, eax
0x18000e172  cmp     r8d, 2
0x18000e176  cmovz   eax, r15d
0x18000e17a  or      edi, eax
0x18000e17c  mov     eax, [rbx]
0x18000e17e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e183  mov     edx, eax
0x18000e185  mov     [rbx], eax
0x18000e187  jz      short loc_18000E1B3
0x18000e189  test    dl, 2
0x18000e18c  jnz     short loc_18000E1B3
0x18000e18e  xor     eax, edi
0x18000e190  and     eax, 180h
0x18000e195  xor     eax, edx
0x18000e197  mov     ecx, eax
0x18000e199  xor     ecx, edi
0x18000e19b  and     ecx, r15d
0x18000e19e  xor     ecx, eax
0x18000e1a0  or      ecx, 1
0x18000e1a3  mov     eax, ecx
0x18000e1a5  xor     eax, edi
0x18000e1a7  and     eax, 800h
0x18000e1ac  xor     eax, ecx
0x18000e1ae  or      eax, 2
0x18000e1b1  mov     [rbx], eax
0x18000e1b3  mov     r8d, edx
0x18000e1b6  mov     ecx, eax
0x18000e1b8  and     r8d, 4
0x18000e1bc  jnz     short loc_18000E1CD
0x18000e1be  xor     ecx, edi
0x18000e1c0  and     ecx, 400h
0x18000e1c6  xor     ecx, eax
0x18000e1c8  or      ecx, 4
0x18000e1cb  mov     [rbx], ecx
0x18000e1cd  mov     eax, edx
0x18000e1cf  lock cmpxchg [rsi], ecx
0x18000e1d3  jnz     short loc_18000E17E
0x18000e1d5  test    r8d, r8d
0x18000e1d8  jnz     short loc_18000E1EA
0x18000e1da  mov     r8d, ebp
0x18000e1dd  mov     edx, 3
0x18000e1e2  mov     rcx, rsi
0x18000e1e5  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e1ea  test    byte ptr [rbx], 2
0x18000e1ed  jnz     short loc_18000E213
0x18000e1ef  mov     eax, [rbx]
0x18000e1f1  xor     eax, edi
0x18000e1f3  and     eax, 180h
0x18000e1f8  xor     eax, [rbx]
0x18000e1fa  mov     ecx, eax
0x18000e1fc  xor     ecx, edi
0x18000e1fe  and     ecx, r15d
0x18000e201  xor     ecx, eax
0x18000e203  or      ecx, 1
0x18000e206  mov     eax, ecx
0x18000e208  xor     eax, edi
0x18000e20a  and     eax, 800h
0x18000e20f  xor     eax, ecx
0x18000e211  mov     [rbx], eax
0x18000e213  mov     rbp, [rsp+38h+arg_10]
0x18000e218  mov     rax, rbx
0x18000e21b  mov     rbx, [rsp+38h+arg_8]
0x18000e220  add     rsp, 20h
0x18000e224  pop     r15
0x18000e226  pop     rdi
0x18000e227  pop     rsi
0x18000e228  retn
```
