# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f6b8`
- end: `0x18000f825`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010620`

## callees

- `0x18000ee50`
- `0x18000f6b8`
- `0x180011648`
- `0x180021010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599553, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor,
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
0x18000f6b8  mov     [rsp+arg_8], rbx
0x18000f6bd  mov     [rsp+arg_10], rbp
0x18000f6c2  mov     [rsp+arg_0], rcx
0x18000f6c7  push    rsi
0x18000f6c8  push    rdi
0x18000f6c9  push    r15
0x18000f6cb  sub     rsp, 20h
0x18000f6cf  mov     rsi, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18000f6d6  mov     rbx, rdx
0x18000f6d9  mov     qword ptr [rdx], 0
0x18000f6e0  mov     eax, [rsi]
0x18000f6e2  mov     [rdx], eax
0x18000f6e4  and     eax, 6
0x18000f6e7  cmp     al, 6
0x18000f6e9  jz      loc_18000F80F
0x18000f6ef  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f6f4  mov     ebp, eax
0x18000f6f6  mov     dword ptr [rsp+38h+arg_0], 0
0x18000f6fe  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f705  test    rax, rax
0x18000f708  jz      short loc_18000F722
0x18000f70a  lea     r8, [rsp+38h+arg_0]
0x18000f70f  mov     edx, 3
0x18000f714  mov     ecx, 37E2881h
0x18000f719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f71e  mov     edx, eax
0x18000f720  jmp     short loc_18000F730
0x18000f722  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f729  test    rax, rax
0x18000f72c  jnz     short loc_18000F70A
0x18000f72e  xor     edx, edx
0x18000f730  mov     r8d, edx
0x18000f733  mov     eax, edx
0x18000f735  and     r8d, 0FFFFFF3Fh
0x18000f73c  and     edx, 80h
0x18000f742  mov     ecx, r8d
0x18000f745  mov     r15d, 40h ; '@'
0x18000f74b  and     ecx, 3
0x18000f74e  and     eax, r15d
0x18000f751  shl     ecx, 2
0x18000f754  or      ecx, eax
0x18000f756  shl     ecx, 2
0x18000f759  or      ecx, edx
0x18000f75b  lea     edi, ds:0[rcx*8]
0x18000f762  test    r8d, r8d
0x18000f765  jnz     short loc_18000F76C
0x18000f767  mov     eax, r15d
0x18000f76a  jmp     short loc_18000F776
0x18000f76c  xor     eax, eax
0x18000f76e  cmp     r8d, 2
0x18000f772  cmovz   eax, r15d
0x18000f776  or      edi, eax
0x18000f778  mov     eax, [rbx]
0x18000f77a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000f77f  mov     edx, eax
0x18000f781  mov     [rbx], eax
0x18000f783  jz      short loc_18000F7AF
0x18000f785  test    dl, 2
0x18000f788  jnz     short loc_18000F7AF
0x18000f78a  xor     eax, edi
0x18000f78c  and     eax, 180h
0x18000f791  xor     eax, edx
0x18000f793  mov     ecx, eax
0x18000f795  xor     ecx, edi
0x18000f797  and     ecx, r15d
0x18000f79a  xor     ecx, eax
0x18000f79c  or      ecx, 1
0x18000f79f  mov     eax, ecx
0x18000f7a1  xor     eax, edi
0x18000f7a3  and     eax, 800h
0x18000f7a8  xor     eax, ecx
0x18000f7aa  or      eax, 2
0x18000f7ad  mov     [rbx], eax
0x18000f7af  mov     r8d, edx
0x18000f7b2  mov     ecx, eax
0x18000f7b4  and     r8d, 4
0x18000f7b8  jnz     short loc_18000F7C9
0x18000f7ba  xor     ecx, edi
0x18000f7bc  and     ecx, 400h
0x18000f7c2  xor     ecx, eax
0x18000f7c4  or      ecx, 4
0x18000f7c7  mov     [rbx], ecx
0x18000f7c9  mov     eax, edx
0x18000f7cb  lock cmpxchg [rsi], ecx
0x18000f7cf  jnz     short loc_18000F77A
0x18000f7d1  test    r8d, r8d
0x18000f7d4  jnz     short loc_18000F7E6
0x18000f7d6  mov     r8d, ebp
0x18000f7d9  mov     edx, 3
0x18000f7de  mov     rcx, rsi
0x18000f7e1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f7e6  test    byte ptr [rbx], 2
0x18000f7e9  jnz     short loc_18000F80F
0x18000f7eb  mov     eax, [rbx]
0x18000f7ed  xor     eax, edi
0x18000f7ef  and     eax, 180h
0x18000f7f4  xor     eax, [rbx]
0x18000f7f6  mov     ecx, eax
0x18000f7f8  xor     ecx, edi
0x18000f7fa  and     ecx, r15d
0x18000f7fd  xor     ecx, eax
0x18000f7ff  or      ecx, 1
0x18000f802  mov     eax, ecx
0x18000f804  xor     eax, edi
0x18000f806  and     eax, 800h
0x18000f80b  xor     eax, ecx
0x18000f80d  mov     [rbx], eax
0x18000f80f  mov     rbp, [rsp+38h+arg_10]
0x18000f814  mov     rax, rbx
0x18000f817  mov     rbx, [rsp+38h+arg_8]
0x18000f81c  add     rsp, 20h
0x18000f820  pop     r15
0x18000f822  pop     rdi
0x18000f823  pop     rsi
0x18000f824  retn
```
