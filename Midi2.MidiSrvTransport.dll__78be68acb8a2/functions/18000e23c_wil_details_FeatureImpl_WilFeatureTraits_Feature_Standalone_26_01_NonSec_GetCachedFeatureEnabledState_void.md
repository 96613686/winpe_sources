# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e23c`
- end: `0x18000e3a9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ee14`

## callees

- `0x18000da08`
- `0x18000e23c`
- `0x180010c28`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
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
0x18000e23c  mov     [rsp+arg_8], rbx
0x18000e241  mov     [rsp+arg_10], rbp
0x18000e246  mov     [rsp+arg_0], rcx
0x18000e24b  push    rsi
0x18000e24c  push    rdi
0x18000e24d  push    r15
0x18000e24f  sub     rsp, 20h
0x18000e253  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18000e25a  mov     rbx, rdx
0x18000e25d  mov     qword ptr [rdx], 0
0x18000e264  mov     eax, [rsi]
0x18000e266  mov     [rdx], eax
0x18000e268  and     eax, 6
0x18000e26b  cmp     al, 6
0x18000e26d  jz      loc_18000E393
0x18000e273  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e278  mov     ebp, eax
0x18000e27a  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e282  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e289  test    rax, rax
0x18000e28c  jz      short loc_18000E2A6
0x18000e28e  lea     r8, [rsp+38h+arg_0]
0x18000e293  mov     edx, 3
0x18000e298  mov     ecx, 37E286Ch
0x18000e29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2a2  mov     edx, eax
0x18000e2a4  jmp     short loc_18000E2B4
0x18000e2a6  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e2ad  test    rax, rax
0x18000e2b0  jnz     short loc_18000E28E
0x18000e2b2  xor     edx, edx
0x18000e2b4  mov     r8d, edx
0x18000e2b7  mov     eax, edx
0x18000e2b9  and     r8d, 0FFFFFF3Fh
0x18000e2c0  and     edx, 80h
0x18000e2c6  mov     ecx, r8d
0x18000e2c9  mov     r15d, 40h ; '@'
0x18000e2cf  and     ecx, 3
0x18000e2d2  and     eax, r15d
0x18000e2d5  shl     ecx, 2
0x18000e2d8  or      ecx, eax
0x18000e2da  shl     ecx, 2
0x18000e2dd  or      ecx, edx
0x18000e2df  lea     edi, ds:0[rcx*8]
0x18000e2e6  test    r8d, r8d
0x18000e2e9  jnz     short loc_18000E2F0
0x18000e2eb  mov     eax, r15d
0x18000e2ee  jmp     short loc_18000E2FA
0x18000e2f0  xor     eax, eax
0x18000e2f2  cmp     r8d, 2
0x18000e2f6  cmovz   eax, r15d
0x18000e2fa  or      edi, eax
0x18000e2fc  mov     eax, [rbx]
0x18000e2fe  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e303  mov     edx, eax
0x18000e305  mov     [rbx], eax
0x18000e307  jz      short loc_18000E333
0x18000e309  test    dl, 2
0x18000e30c  jnz     short loc_18000E333
0x18000e30e  xor     eax, edi
0x18000e310  and     eax, 180h
0x18000e315  xor     eax, edx
0x18000e317  mov     ecx, eax
0x18000e319  xor     ecx, edi
0x18000e31b  and     ecx, r15d
0x18000e31e  xor     ecx, eax
0x18000e320  or      ecx, 1
0x18000e323  mov     eax, ecx
0x18000e325  xor     eax, edi
0x18000e327  and     eax, 800h
0x18000e32c  xor     eax, ecx
0x18000e32e  or      eax, 2
0x18000e331  mov     [rbx], eax
0x18000e333  mov     r8d, edx
0x18000e336  mov     ecx, eax
0x18000e338  and     r8d, 4
0x18000e33c  jnz     short loc_18000E34D
0x18000e33e  xor     ecx, edi
0x18000e340  and     ecx, 400h
0x18000e346  xor     ecx, eax
0x18000e348  or      ecx, 4
0x18000e34b  mov     [rbx], ecx
0x18000e34d  mov     eax, edx
0x18000e34f  lock cmpxchg [rsi], ecx
0x18000e353  jnz     short loc_18000E2FE
0x18000e355  test    r8d, r8d
0x18000e358  jnz     short loc_18000E36A
0x18000e35a  mov     r8d, ebp
0x18000e35d  mov     edx, 3
0x18000e362  mov     rcx, rsi
0x18000e365  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e36a  test    byte ptr [rbx], 2
0x18000e36d  jnz     short loc_18000E393
0x18000e36f  mov     eax, [rbx]
0x18000e371  xor     eax, edi
0x18000e373  and     eax, 180h
0x18000e378  xor     eax, [rbx]
0x18000e37a  mov     ecx, eax
0x18000e37c  xor     ecx, edi
0x18000e37e  and     ecx, r15d
0x18000e381  xor     ecx, eax
0x18000e383  or      ecx, 1
0x18000e386  mov     eax, ecx
0x18000e388  xor     eax, edi
0x18000e38a  and     eax, 800h
0x18000e38f  xor     eax, ecx
0x18000e391  mov     [rbx], eax
0x18000e393  mov     rbp, [rsp+38h+arg_10]
0x18000e398  mov     rax, rbx
0x18000e39b  mov     rbx, [rsp+38h+arg_8]
0x18000e3a0  add     rsp, 20h
0x18000e3a4  pop     r15
0x18000e3a6  pop     rdi
0x18000e3a7  pop     rsi
0x18000e3a8  retn
```
