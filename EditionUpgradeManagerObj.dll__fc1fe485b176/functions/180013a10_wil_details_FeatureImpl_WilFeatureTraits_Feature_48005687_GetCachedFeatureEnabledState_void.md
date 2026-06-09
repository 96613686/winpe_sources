# wil::details::FeatureImpl<__WilFeatureTraits_Feature_48005687>::GetCachedFeatureEnabledState(void)

- ea: `0x180013a10`
- end: `0x180013b85`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_48005687@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `373`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013b8c`

## callees

- `0x180004728`
- `0x180007a78`
- `0x180013a10`
- `0x180023010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_48005687>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
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
  v3 = *(_DWORD *)Feature_48005687__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_48005687__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    v6 = 0;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(48005687, 0, &v14);
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
    if ( !v4 )
      LODWORD(v14) = 0;
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_48005687__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_48005687__descriptor, 0, v4);
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
0x180013a10  mov     [rsp+arg_8], rbx
0x180013a15  mov     [rsp+arg_10], rbp
0x180013a1a  mov     [rsp+arg_0], rcx
0x180013a1f  push    rsi
0x180013a20  push    rdi
0x180013a21  push    r15
0x180013a23  sub     rsp, 20h
0x180013a27  mov     rsi, cs:Feature_48005687__descriptor
0x180013a2e  mov     rbx, rdx
0x180013a31  mov     qword ptr [rdx], 0
0x180013a38  mov     eax, [rsi]
0x180013a3a  mov     [rdx], eax
0x180013a3c  and     eax, 6
0x180013a3f  cmp     al, 6
0x180013a41  jz      loc_180013B6F
0x180013a47  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013a4c  mov     ebp, eax
0x180013a4e  mov     dword ptr [rsp+38h+arg_0], 0
0x180013a56  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180013a5d  xor     edx, edx
0x180013a5f  test    rax, rax
0x180013a62  jnz     short loc_180013A70
0x180013a64  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180013a6b  test    rax, rax
0x180013a6e  jz      short loc_180013A81
0x180013a70  lea     r8, [rsp+38h+arg_0]
0x180013a75  mov     ecx, 2DC8237h
0x180013a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a7f  mov     edx, eax
0x180013a81  mov     r8d, edx
0x180013a84  mov     eax, edx
0x180013a86  and     r8d, 0FFFFFF3Fh
0x180013a8d  and     edx, 80h
0x180013a93  mov     ecx, r8d
0x180013a96  mov     r15d, 40h ; '@'
0x180013a9c  and     ecx, 3
0x180013a9f  and     eax, r15d
0x180013aa2  shl     ecx, 2
0x180013aa5  or      ecx, eax
0x180013aa7  shl     ecx, 2
0x180013aaa  or      ecx, edx
0x180013aac  lea     edi, ds:0[rcx*8]
0x180013ab3  test    r8d, r8d
0x180013ab6  jnz     short loc_180013ABD
0x180013ab8  mov     eax, r15d
0x180013abb  jmp     short loc_180013AC7
0x180013abd  xor     eax, eax
0x180013abf  cmp     r8d, 2
0x180013ac3  cmovz   eax, r15d
0x180013ac7  or      edi, eax
0x180013ac9  test    ebp, ebp
0x180013acb  jnz     short loc_180013AD1
0x180013acd  mov     dword ptr [rsp+38h+arg_0], ebp
0x180013ad1  mov     eax, [rbx]
0x180013ad3  cmp     dword ptr [rsp+38h+arg_0], 0
0x180013ad8  mov     edx, eax
0x180013ada  mov     [rbx], eax
0x180013adc  jz      short loc_180013B0C
0x180013ade  test    dl, 2
0x180013ae1  jnz     short loc_180013B0C
0x180013ae3  mov     eax, edi
0x180013ae5  xor     eax, edx
0x180013ae7  and     eax, 180h
0x180013aec  xor     eax, edx
0x180013aee  mov     ecx, eax
0x180013af0  xor     ecx, edi
0x180013af2  and     ecx, r15d
0x180013af5  xor     ecx, eax
0x180013af7  or      ecx, 1
0x180013afa  mov     eax, ecx
0x180013afc  xor     eax, edi
0x180013afe  and     eax, 800h
0x180013b03  xor     eax, ecx
0x180013b05  or      eax, 2
0x180013b08  mov     [rbx], eax
0x180013b0a  jmp     short loc_180013B0E
0x180013b0c  mov     eax, edx
0x180013b0e  mov     r8d, edx
0x180013b11  and     r8d, 4
0x180013b15  jnz     short loc_180013B2A
0x180013b17  mov     ecx, edi
0x180013b19  xor     ecx, eax
0x180013b1b  and     ecx, 400h
0x180013b21  xor     ecx, eax
0x180013b23  or      ecx, 4
0x180013b26  mov     [rbx], ecx
0x180013b28  jmp     short loc_180013B2C
0x180013b2a  mov     ecx, eax
0x180013b2c  mov     eax, edx
0x180013b2e  lock cmpxchg [rsi], ecx
0x180013b32  jnz     short loc_180013AD3
0x180013b34  test    r8d, r8d
0x180013b37  jnz     short loc_180013B46
0x180013b39  mov     r8d, ebp
0x180013b3c  xor     edx, edx
0x180013b3e  mov     rcx, rsi
0x180013b41  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013b46  test    byte ptr [rbx], 2
0x180013b49  jnz     short loc_180013B6F
0x180013b4b  mov     eax, [rbx]
0x180013b4d  xor     eax, edi
0x180013b4f  and     eax, 180h
0x180013b54  xor     eax, [rbx]
0x180013b56  mov     ecx, eax
0x180013b58  xor     ecx, edi
0x180013b5a  and     ecx, r15d
0x180013b5d  xor     ecx, eax
0x180013b5f  or      ecx, 1
0x180013b62  mov     eax, ecx
0x180013b64  xor     eax, edi
0x180013b66  and     eax, 800h
0x180013b6b  xor     eax, ecx
0x180013b6d  mov     [rbx], eax
0x180013b6f  mov     rbp, [rsp+38h+arg_10]
0x180013b74  mov     rax, rbx
0x180013b77  mov     rbx, [rsp+38h+arg_8]
0x180013b7c  add     rsp, 20h
0x180013b80  pop     r15
0x180013b82  pop     rdi
0x180013b83  pop     rsi
0x180013b84  retn
```
