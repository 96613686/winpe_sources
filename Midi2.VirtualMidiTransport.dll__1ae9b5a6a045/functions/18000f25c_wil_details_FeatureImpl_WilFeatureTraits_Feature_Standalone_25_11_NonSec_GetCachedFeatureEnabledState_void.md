# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f25c`
- end: `0x18000f3c9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800101d0`

## callees

- `0x18000ee50`
- `0x18000f25c`
- `0x180011648`
- `0x180021010`

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
0x18000f25c  mov     [rsp+arg_8], rbx
0x18000f261  mov     [rsp+arg_10], rbp
0x18000f266  mov     [rsp+arg_0], rcx
0x18000f26b  push    rsi
0x18000f26c  push    rdi
0x18000f26d  push    r15
0x18000f26f  sub     rsp, 20h
0x18000f273  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000f27a  mov     rbx, rdx
0x18000f27d  mov     qword ptr [rdx], 0
0x18000f284  mov     eax, [rsi]
0x18000f286  mov     [rdx], eax
0x18000f288  and     eax, 6
0x18000f28b  cmp     al, 6
0x18000f28d  jz      loc_18000F3B3
0x18000f293  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f298  mov     ebp, eax
0x18000f29a  mov     dword ptr [rsp+38h+arg_0], 0
0x18000f2a2  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f2a9  test    rax, rax
0x18000f2ac  jz      short loc_18000F2C6
0x18000f2ae  lea     r8, [rsp+38h+arg_0]
0x18000f2b3  mov     edx, 3
0x18000f2b8  mov     ecx, 2AF34FDh
0x18000f2bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2c2  mov     edx, eax
0x18000f2c4  jmp     short loc_18000F2D4
0x18000f2c6  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f2cd  test    rax, rax
0x18000f2d0  jnz     short loc_18000F2AE
0x18000f2d2  xor     edx, edx
0x18000f2d4  mov     r8d, edx
0x18000f2d7  mov     eax, edx
0x18000f2d9  and     r8d, 0FFFFFF3Fh
0x18000f2e0  and     edx, 80h
0x18000f2e6  mov     ecx, r8d
0x18000f2e9  mov     r15d, 40h ; '@'
0x18000f2ef  and     ecx, 3
0x18000f2f2  and     eax, r15d
0x18000f2f5  shl     ecx, 2
0x18000f2f8  or      ecx, eax
0x18000f2fa  shl     ecx, 2
0x18000f2fd  or      ecx, edx
0x18000f2ff  lea     edi, ds:0[rcx*8]
0x18000f306  test    r8d, r8d
0x18000f309  jnz     short loc_18000F310
0x18000f30b  mov     eax, r15d
0x18000f30e  jmp     short loc_18000F31A
0x18000f310  xor     eax, eax
0x18000f312  cmp     r8d, 2
0x18000f316  cmovz   eax, r15d
0x18000f31a  or      edi, eax
0x18000f31c  mov     eax, [rbx]
0x18000f31e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000f323  mov     edx, eax
0x18000f325  mov     [rbx], eax
0x18000f327  jz      short loc_18000F353
0x18000f329  test    dl, 2
0x18000f32c  jnz     short loc_18000F353
0x18000f32e  xor     eax, edi
0x18000f330  and     eax, 180h
0x18000f335  xor     eax, edx
0x18000f337  mov     ecx, eax
0x18000f339  xor     ecx, edi
0x18000f33b  and     ecx, r15d
0x18000f33e  xor     ecx, eax
0x18000f340  or      ecx, 1
0x18000f343  mov     eax, ecx
0x18000f345  xor     eax, edi
0x18000f347  and     eax, 800h
0x18000f34c  xor     eax, ecx
0x18000f34e  or      eax, 2
0x18000f351  mov     [rbx], eax
0x18000f353  mov     r8d, edx
0x18000f356  mov     ecx, eax
0x18000f358  and     r8d, 4
0x18000f35c  jnz     short loc_18000F36D
0x18000f35e  xor     ecx, edi
0x18000f360  and     ecx, 400h
0x18000f366  xor     ecx, eax
0x18000f368  or      ecx, 4
0x18000f36b  mov     [rbx], ecx
0x18000f36d  mov     eax, edx
0x18000f36f  lock cmpxchg [rsi], ecx
0x18000f373  jnz     short loc_18000F31E
0x18000f375  test    r8d, r8d
0x18000f378  jnz     short loc_18000F38A
0x18000f37a  mov     r8d, ebp
0x18000f37d  mov     edx, 3
0x18000f382  mov     rcx, rsi
0x18000f385  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f38a  test    byte ptr [rbx], 2
0x18000f38d  jnz     short loc_18000F3B3
0x18000f38f  mov     eax, [rbx]
0x18000f391  xor     eax, edi
0x18000f393  and     eax, 180h
0x18000f398  xor     eax, [rbx]
0x18000f39a  mov     ecx, eax
0x18000f39c  xor     ecx, edi
0x18000f39e  and     ecx, r15d
0x18000f3a1  xor     ecx, eax
0x18000f3a3  or      ecx, 1
0x18000f3a6  mov     eax, ecx
0x18000f3a8  xor     eax, edi
0x18000f3aa  and     eax, 800h
0x18000f3af  xor     eax, ecx
0x18000f3b1  mov     [rbx], eax
0x18000f3b3  mov     rbp, [rsp+38h+arg_10]
0x18000f3b8  mov     rax, rbx
0x18000f3bb  mov     rbx, [rsp+38h+arg_8]
0x18000f3c0  add     rsp, 20h
0x18000f3c4  pop     r15
0x18000f3c6  pop     rdi
0x18000f3c7  pop     rsi
0x18000f3c8  retn
```
