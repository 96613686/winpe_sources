# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180013ac4`
- end: `0x180013c31`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_04_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014d9c`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180013ac4`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_04_NonSec__descriptor, 3, v4);
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
0x180013ac4  mov     [rsp+arg_8], rbx
0x180013ac9  mov     [rsp+arg_10], rbp
0x180013ace  mov     [rsp+arg_0], rcx
0x180013ad3  push    rsi
0x180013ad4  push    rdi
0x180013ad5  push    r15
0x180013ad7  sub     rsp, 20h
0x180013adb  mov     rsi, cs:Feature_Standalone_26_04_NonSec__descriptor
0x180013ae2  mov     rbx, rdx
0x180013ae5  mov     qword ptr [rdx], 0
0x180013aec  mov     eax, [rsi]
0x180013aee  mov     [rdx], eax
0x180013af0  and     eax, 6
0x180013af3  cmp     al, 6
0x180013af5  jz      loc_180013C1B
0x180013afb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013b00  mov     ebp, eax
0x180013b02  mov     dword ptr [rsp+38h+arg_0], 0
0x180013b0a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180013b11  test    rax, rax
0x180013b14  jz      short loc_180013B2E
0x180013b16  lea     r8, [rsp+38h+arg_0]
0x180013b1b  mov     edx, 3
0x180013b20  mov     ecx, 37E2887h
0x180013b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b2a  mov     edx, eax
0x180013b2c  jmp     short loc_180013B3C
0x180013b2e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180013b35  test    rax, rax
0x180013b38  jnz     short loc_180013B16
0x180013b3a  xor     edx, edx
0x180013b3c  mov     r8d, edx
0x180013b3f  mov     eax, edx
0x180013b41  and     r8d, 0FFFFFF3Fh
0x180013b48  and     edx, 80h
0x180013b4e  mov     ecx, r8d
0x180013b51  mov     r15d, 40h ; '@'
0x180013b57  and     ecx, 3
0x180013b5a  and     eax, r15d
0x180013b5d  shl     ecx, 2
0x180013b60  or      ecx, eax
0x180013b62  shl     ecx, 2
0x180013b65  or      ecx, edx
0x180013b67  lea     edi, ds:0[rcx*8]
0x180013b6e  test    r8d, r8d
0x180013b71  jnz     short loc_180013B78
0x180013b73  mov     eax, r15d
0x180013b76  jmp     short loc_180013B82
0x180013b78  xor     eax, eax
0x180013b7a  cmp     r8d, 2
0x180013b7e  cmovz   eax, r15d
0x180013b82  or      edi, eax
0x180013b84  mov     eax, [rbx]
0x180013b86  cmp     dword ptr [rsp+38h+arg_0], 0
0x180013b8b  mov     edx, eax
0x180013b8d  mov     [rbx], eax
0x180013b8f  jz      short loc_180013BBB
0x180013b91  test    dl, 2
0x180013b94  jnz     short loc_180013BBB
0x180013b96  xor     eax, edi
0x180013b98  and     eax, 180h
0x180013b9d  xor     eax, edx
0x180013b9f  mov     ecx, eax
0x180013ba1  xor     ecx, edi
0x180013ba3  and     ecx, r15d
0x180013ba6  xor     ecx, eax
0x180013ba8  or      ecx, 1
0x180013bab  mov     eax, ecx
0x180013bad  xor     eax, edi
0x180013baf  and     eax, 800h
0x180013bb4  xor     eax, ecx
0x180013bb6  or      eax, 2
0x180013bb9  mov     [rbx], eax
0x180013bbb  mov     r8d, edx
0x180013bbe  mov     ecx, eax
0x180013bc0  and     r8d, 4
0x180013bc4  jnz     short loc_180013BD5
0x180013bc6  xor     ecx, edi
0x180013bc8  and     ecx, 400h
0x180013bce  xor     ecx, eax
0x180013bd0  or      ecx, 4
0x180013bd3  mov     [rbx], ecx
0x180013bd5  mov     eax, edx
0x180013bd7  lock cmpxchg [rsi], ecx
0x180013bdb  jnz     short loc_180013B86
0x180013bdd  test    r8d, r8d
0x180013be0  jnz     short loc_180013BF2
0x180013be2  mov     r8d, ebp
0x180013be5  mov     edx, 3
0x180013bea  mov     rcx, rsi
0x180013bed  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013bf2  test    byte ptr [rbx], 2
0x180013bf5  jnz     short loc_180013C1B
0x180013bf7  mov     eax, [rbx]
0x180013bf9  xor     eax, edi
0x180013bfb  and     eax, 180h
0x180013c00  xor     eax, [rbx]
0x180013c02  mov     ecx, eax
0x180013c04  xor     ecx, edi
0x180013c06  and     ecx, r15d
0x180013c09  xor     ecx, eax
0x180013c0b  or      ecx, 1
0x180013c0e  mov     eax, ecx
0x180013c10  xor     eax, edi
0x180013c12  and     eax, 800h
0x180013c17  xor     eax, ecx
0x180013c19  mov     [rbx], eax
0x180013c1b  mov     rbp, [rsp+38h+arg_10]
0x180013c20  mov     rax, rbx
0x180013c23  mov     rbx, [rsp+38h+arg_8]
0x180013c28  add     rsp, 20h
0x180013c2c  pop     r15
0x180013c2e  pop     rdi
0x180013c2f  pop     rsi
0x180013c30  retn
```
