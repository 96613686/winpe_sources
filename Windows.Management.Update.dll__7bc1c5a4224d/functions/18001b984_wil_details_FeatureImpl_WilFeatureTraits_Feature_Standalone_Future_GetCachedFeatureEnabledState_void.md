# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b984`
- end: `0x18001bafb`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bdb8`

## callees

- `0x18000ace8`
- `0x18000eed4`
- `0x18001b984`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(49453572, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_Future__descriptor,
        3u,
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
0x18001b984  mov     [rsp+arg_8], rbx
0x18001b989  mov     [rsp+arg_10], rbp
0x18001b98e  mov     [rsp+arg_0], rcx
0x18001b993  push    rsi
0x18001b994  push    rdi
0x18001b995  push    r15
0x18001b997  sub     rsp, 20h
0x18001b99b  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18001b9a2  mov     rbx, rdx
0x18001b9a5  mov     qword ptr [rdx], 0
0x18001b9ac  mov     eax, [rsi]
0x18001b9ae  mov     [rdx], eax
0x18001b9b0  and     eax, 6
0x18001b9b3  cmp     al, 6
0x18001b9b5  jz      loc_18001BAE5
0x18001b9bb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b9c0  mov     ebp, eax
0x18001b9c2  mov     dword ptr [rsp+38h+arg_0], 0
0x18001b9ca  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001b9d1  test    rax, rax
0x18001b9d4  jz      short loc_18001B9EE
0x18001b9d6  lea     r8, [rsp+38h+arg_0]
0x18001b9db  mov     edx, 3
0x18001b9e0  mov     ecx, 2F29A04h
0x18001b9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9ea  mov     edx, eax
0x18001b9ec  jmp     short loc_18001B9FC
0x18001b9ee  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001b9f5  test    rax, rax
0x18001b9f8  jnz     short loc_18001B9D6
0x18001b9fa  xor     edx, edx
0x18001b9fc  mov     r8d, edx
0x18001b9ff  mov     eax, edx
0x18001ba01  and     r8d, 0FFFFFF3Fh
0x18001ba08  and     edx, 80h
0x18001ba0e  mov     ecx, r8d
0x18001ba11  mov     r15d, 40h ; '@'
0x18001ba17  and     ecx, 3
0x18001ba1a  and     eax, r15d
0x18001ba1d  shl     ecx, 2
0x18001ba20  or      ecx, eax
0x18001ba22  shl     ecx, 2
0x18001ba25  or      ecx, edx
0x18001ba27  lea     edi, ds:0[rcx*8]
0x18001ba2e  test    r8d, r8d
0x18001ba31  jnz     short loc_18001BA38
0x18001ba33  mov     eax, r15d
0x18001ba36  jmp     short loc_18001BA42
0x18001ba38  xor     eax, eax
0x18001ba3a  cmp     r8d, 2
0x18001ba3e  cmovz   eax, r15d
0x18001ba42  or      edi, eax
0x18001ba44  mov     eax, [rbx]
0x18001ba46  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001ba4b  mov     edx, eax
0x18001ba4d  mov     [rbx], eax
0x18001ba4f  jz      short loc_18001BA7F
0x18001ba51  test    dl, 2
0x18001ba54  jnz     short loc_18001BA7F
0x18001ba56  mov     eax, edi
0x18001ba58  xor     eax, edx
0x18001ba5a  and     eax, 180h
0x18001ba5f  xor     eax, edx
0x18001ba61  mov     ecx, eax
0x18001ba63  xor     ecx, edi
0x18001ba65  and     ecx, r15d
0x18001ba68  xor     ecx, eax
0x18001ba6a  or      ecx, 1
0x18001ba6d  mov     eax, ecx
0x18001ba6f  xor     eax, edi
0x18001ba71  and     eax, 800h
0x18001ba76  xor     eax, ecx
0x18001ba78  or      eax, 2
0x18001ba7b  mov     [rbx], eax
0x18001ba7d  jmp     short loc_18001BA81
0x18001ba7f  mov     eax, edx
0x18001ba81  mov     r8d, edx
0x18001ba84  and     r8d, 4
0x18001ba88  jnz     short loc_18001BA9D
0x18001ba8a  mov     ecx, edi
0x18001ba8c  xor     ecx, eax
0x18001ba8e  and     ecx, 400h
0x18001ba94  xor     ecx, eax
0x18001ba96  or      ecx, 4
0x18001ba99  mov     [rbx], ecx
0x18001ba9b  jmp     short loc_18001BA9F
0x18001ba9d  mov     ecx, eax
0x18001ba9f  mov     eax, edx
0x18001baa1  lock cmpxchg [rsi], ecx
0x18001baa5  jnz     short loc_18001BA46
0x18001baa7  test    r8d, r8d
0x18001baaa  jnz     short loc_18001BABC
0x18001baac  mov     r8d, ebp
0x18001baaf  mov     edx, 3
0x18001bab4  mov     rcx, rsi
0x18001bab7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001babc  test    byte ptr [rbx], 2
0x18001babf  jnz     short loc_18001BAE5
0x18001bac1  mov     eax, [rbx]
0x18001bac3  xor     eax, edi
0x18001bac5  and     eax, 180h
0x18001baca  xor     eax, [rbx]
0x18001bacc  mov     ecx, eax
0x18001bace  xor     ecx, edi
0x18001bad0  and     ecx, r15d
0x18001bad3  xor     ecx, eax
0x18001bad5  or      ecx, 1
0x18001bad8  mov     eax, ecx
0x18001bada  xor     eax, edi
0x18001badc  and     eax, 800h
0x18001bae1  xor     eax, ecx
0x18001bae3  mov     [rbx], eax
0x18001bae5  mov     rbp, [rsp+38h+arg_10]
0x18001baea  mov     rax, rbx
0x18001baed  mov     rbx, [rsp+38h+arg_8]
0x18001baf2  add     rsp, 20h
0x18001baf6  pop     r15
0x18001baf8  pop     rdi
0x18001baf9  pop     rsi
0x18001bafa  retn
```
