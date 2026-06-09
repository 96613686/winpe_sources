# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x14000526c`
- end: `0x1400053d9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005b90`

## callees

- `0x1400049e0`
- `0x14000526c`
- `0x14000a88c`
- `0x140012010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_11_NonSec__descriptor, 3, v4);
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
0x14000526c  mov     [rsp+arg_8], rbx
0x140005271  mov     [rsp+arg_10], rbp
0x140005276  mov     [rsp+arg_0], rcx
0x14000527b  push    rsi
0x14000527c  push    rdi
0x14000527d  push    r15
0x14000527f  sub     rsp, 20h
0x140005283  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x14000528a  mov     rbx, rdx
0x14000528d  mov     qword ptr [rdx], 0
0x140005294  mov     eax, [rsi]
0x140005296  mov     [rdx], eax
0x140005298  and     eax, 6
0x14000529b  cmp     al, 6
0x14000529d  jz      loc_1400053C3
0x1400052a3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400052a8  mov     ebp, eax
0x1400052aa  mov     dword ptr [rsp+38h+arg_0], 0
0x1400052b2  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1400052b9  test    rax, rax
0x1400052bc  jz      short loc_1400052D6
0x1400052be  lea     r8, [rsp+38h+arg_0]
0x1400052c3  mov     edx, 3
0x1400052c8  mov     ecx, 2AF34FDh
0x1400052cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052d2  mov     edx, eax
0x1400052d4  jmp     short loc_1400052E4
0x1400052d6  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1400052dd  test    rax, rax
0x1400052e0  jnz     short loc_1400052BE
0x1400052e2  xor     edx, edx
0x1400052e4  mov     r8d, edx
0x1400052e7  mov     eax, edx
0x1400052e9  and     r8d, 0FFFFFF3Fh
0x1400052f0  and     edx, 80h
0x1400052f6  mov     ecx, r8d
0x1400052f9  mov     r15d, 40h ; '@'
0x1400052ff  and     ecx, 3
0x140005302  and     eax, r15d
0x140005305  shl     ecx, 2
0x140005308  or      ecx, eax
0x14000530a  shl     ecx, 2
0x14000530d  or      ecx, edx
0x14000530f  lea     edi, ds:0[rcx*8]
0x140005316  test    r8d, r8d
0x140005319  jnz     short loc_140005320
0x14000531b  mov     eax, r15d
0x14000531e  jmp     short loc_14000532A
0x140005320  xor     eax, eax
0x140005322  cmp     r8d, 2
0x140005326  cmovz   eax, r15d
0x14000532a  or      edi, eax
0x14000532c  mov     eax, [rbx]
0x14000532e  cmp     dword ptr [rsp+38h+arg_0], 0
0x140005333  mov     edx, eax
0x140005335  mov     [rbx], eax
0x140005337  jz      short loc_140005363
0x140005339  test    dl, 2
0x14000533c  jnz     short loc_140005363
0x14000533e  xor     eax, edi
0x140005340  and     eax, 180h
0x140005345  xor     eax, edx
0x140005347  mov     ecx, eax
0x140005349  xor     ecx, edi
0x14000534b  and     ecx, r15d
0x14000534e  xor     ecx, eax
0x140005350  or      ecx, 1
0x140005353  mov     eax, ecx
0x140005355  xor     eax, edi
0x140005357  and     eax, 800h
0x14000535c  xor     eax, ecx
0x14000535e  or      eax, 2
0x140005361  mov     [rbx], eax
0x140005363  mov     r8d, edx
0x140005366  mov     ecx, eax
0x140005368  and     r8d, 4
0x14000536c  jnz     short loc_14000537D
0x14000536e  xor     ecx, edi
0x140005370  and     ecx, 400h
0x140005376  xor     ecx, eax
0x140005378  or      ecx, 4
0x14000537b  mov     [rbx], ecx
0x14000537d  mov     eax, edx
0x14000537f  lock cmpxchg [rsi], ecx
0x140005383  jnz     short loc_14000532E
0x140005385  test    r8d, r8d
0x140005388  jnz     short loc_14000539A
0x14000538a  mov     r8d, ebp
0x14000538d  mov     edx, 3
0x140005392  mov     rcx, rsi
0x140005395  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000539a  test    byte ptr [rbx], 2
0x14000539d  jnz     short loc_1400053C3
0x14000539f  mov     eax, [rbx]
0x1400053a1  xor     eax, edi
0x1400053a3  and     eax, 180h
0x1400053a8  xor     eax, [rbx]
0x1400053aa  mov     ecx, eax
0x1400053ac  xor     ecx, edi
0x1400053ae  and     ecx, r15d
0x1400053b1  xor     ecx, eax
0x1400053b3  or      ecx, 1
0x1400053b6  mov     eax, ecx
0x1400053b8  xor     eax, edi
0x1400053ba  and     eax, 800h
0x1400053bf  xor     eax, ecx
0x1400053c1  mov     [rbx], eax
0x1400053c3  mov     rbp, [rsp+38h+arg_10]
0x1400053c8  mov     rax, rbx
0x1400053cb  mov     rbx, [rsp+38h+arg_8]
0x1400053d0  add     rsp, 20h
0x1400053d4  pop     r15
0x1400053d6  pop     rdi
0x1400053d7  pop     rsi
0x1400053d8  retn
```
