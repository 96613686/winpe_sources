# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001eec4`
- end: `0x18001f031`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fe2c`

## callees

- `0x18001e65c`
- `0x18001eec4`
- `0x180020fe4`
- `0x180032010`

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
0x18001eec4  mov     [rsp+arg_8], rbx
0x18001eec9  mov     [rsp+arg_10], rbp
0x18001eece  mov     [rsp+arg_0], rcx
0x18001eed3  push    rsi
0x18001eed4  push    rdi
0x18001eed5  push    r15
0x18001eed7  sub     rsp, 20h
0x18001eedb  mov     rsi, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18001eee2  mov     rbx, rdx
0x18001eee5  mov     qword ptr [rdx], 0
0x18001eeec  mov     eax, [rsi]
0x18001eeee  mov     [rdx], eax
0x18001eef0  and     eax, 6
0x18001eef3  cmp     al, 6
0x18001eef5  jz      loc_18001F01B
0x18001eefb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001ef00  mov     ebp, eax
0x18001ef02  mov     dword ptr [rsp+38h+arg_0], 0
0x18001ef0a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001ef11  test    rax, rax
0x18001ef14  jz      short loc_18001EF2E
0x18001ef16  lea     r8, [rsp+38h+arg_0]
0x18001ef1b  mov     edx, 3
0x18001ef20  mov     ecx, 37E2881h
0x18001ef25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef2a  mov     edx, eax
0x18001ef2c  jmp     short loc_18001EF3C
0x18001ef2e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001ef35  test    rax, rax
0x18001ef38  jnz     short loc_18001EF16
0x18001ef3a  xor     edx, edx
0x18001ef3c  mov     r8d, edx
0x18001ef3f  mov     eax, edx
0x18001ef41  and     r8d, 0FFFFFF3Fh
0x18001ef48  and     edx, 80h
0x18001ef4e  mov     ecx, r8d
0x18001ef51  mov     r15d, 40h ; '@'
0x18001ef57  and     ecx, 3
0x18001ef5a  and     eax, r15d
0x18001ef5d  shl     ecx, 2
0x18001ef60  or      ecx, eax
0x18001ef62  shl     ecx, 2
0x18001ef65  or      ecx, edx
0x18001ef67  lea     edi, ds:0[rcx*8]
0x18001ef6e  test    r8d, r8d
0x18001ef71  jnz     short loc_18001EF78
0x18001ef73  mov     eax, r15d
0x18001ef76  jmp     short loc_18001EF82
0x18001ef78  xor     eax, eax
0x18001ef7a  cmp     r8d, 2
0x18001ef7e  cmovz   eax, r15d
0x18001ef82  or      edi, eax
0x18001ef84  mov     eax, [rbx]
0x18001ef86  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001ef8b  mov     edx, eax
0x18001ef8d  mov     [rbx], eax
0x18001ef8f  jz      short loc_18001EFBB
0x18001ef91  test    dl, 2
0x18001ef94  jnz     short loc_18001EFBB
0x18001ef96  xor     eax, edi
0x18001ef98  and     eax, 180h
0x18001ef9d  xor     eax, edx
0x18001ef9f  mov     ecx, eax
0x18001efa1  xor     ecx, edi
0x18001efa3  and     ecx, r15d
0x18001efa6  xor     ecx, eax
0x18001efa8  or      ecx, 1
0x18001efab  mov     eax, ecx
0x18001efad  xor     eax, edi
0x18001efaf  and     eax, 800h
0x18001efb4  xor     eax, ecx
0x18001efb6  or      eax, 2
0x18001efb9  mov     [rbx], eax
0x18001efbb  mov     r8d, edx
0x18001efbe  mov     ecx, eax
0x18001efc0  and     r8d, 4
0x18001efc4  jnz     short loc_18001EFD5
0x18001efc6  xor     ecx, edi
0x18001efc8  and     ecx, 400h
0x18001efce  xor     ecx, eax
0x18001efd0  or      ecx, 4
0x18001efd3  mov     [rbx], ecx
0x18001efd5  mov     eax, edx
0x18001efd7  lock cmpxchg [rsi], ecx
0x18001efdb  jnz     short loc_18001EF86
0x18001efdd  test    r8d, r8d
0x18001efe0  jnz     short loc_18001EFF2
0x18001efe2  mov     r8d, ebp
0x18001efe5  mov     edx, 3
0x18001efea  mov     rcx, rsi
0x18001efed  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001eff2  test    byte ptr [rbx], 2
0x18001eff5  jnz     short loc_18001F01B
0x18001eff7  mov     eax, [rbx]
0x18001eff9  xor     eax, edi
0x18001effb  and     eax, 180h
0x18001f000  xor     eax, [rbx]
0x18001f002  mov     ecx, eax
0x18001f004  xor     ecx, edi
0x18001f006  and     ecx, r15d
0x18001f009  xor     ecx, eax
0x18001f00b  or      ecx, 1
0x18001f00e  mov     eax, ecx
0x18001f010  xor     eax, edi
0x18001f012  and     eax, 800h
0x18001f017  xor     eax, ecx
0x18001f019  mov     [rbx], eax
0x18001f01b  mov     rbp, [rsp+38h+arg_10]
0x18001f020  mov     rax, rbx
0x18001f023  mov     rbx, [rsp+38h+arg_8]
0x18001f028  add     rsp, 20h
0x18001f02c  pop     r15
0x18001f02e  pop     rdi
0x18001f02f  pop     rsi
0x18001f030  retn
```
