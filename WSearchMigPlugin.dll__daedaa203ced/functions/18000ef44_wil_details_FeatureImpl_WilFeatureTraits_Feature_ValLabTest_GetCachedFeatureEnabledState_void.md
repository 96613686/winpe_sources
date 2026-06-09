# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ef44`
- end: `0x18000f0bb`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f704`

## callees

- `0x1800058e8`
- `0x180009270`
- `0x18000ef44`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(57048226, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValLabTest__descriptor, 3, v4);
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
0x18000ef44  mov     [rsp+arg_8], rbx
0x18000ef49  mov     [rsp+arg_10], rbp
0x18000ef4e  mov     [rsp+arg_0], rcx
0x18000ef53  push    rsi
0x18000ef54  push    rdi
0x18000ef55  push    r15
0x18000ef57  sub     rsp, 20h
0x18000ef5b  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18000ef62  mov     rbx, rdx
0x18000ef65  mov     qword ptr [rdx], 0
0x18000ef6c  mov     eax, [rsi]
0x18000ef6e  mov     [rdx], eax
0x18000ef70  and     eax, 6
0x18000ef73  cmp     al, 6
0x18000ef75  jz      loc_18000F0A5
0x18000ef7b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ef80  mov     ebp, eax
0x18000ef82  mov     dword ptr [rsp+38h+arg_0], 0
0x18000ef8a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ef91  test    rax, rax
0x18000ef94  jz      short loc_18000EFAE
0x18000ef96  lea     r8, [rsp+38h+arg_0]
0x18000ef9b  mov     edx, 3
0x18000efa0  mov     ecx, 3667CA2h
0x18000efa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efaa  mov     edx, eax
0x18000efac  jmp     short loc_18000EFBC
0x18000efae  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000efb5  test    rax, rax
0x18000efb8  jnz     short loc_18000EF96
0x18000efba  xor     edx, edx
0x18000efbc  mov     r8d, edx
0x18000efbf  mov     eax, edx
0x18000efc1  and     r8d, 0FFFFFF3Fh
0x18000efc8  and     edx, 80h
0x18000efce  mov     ecx, r8d
0x18000efd1  mov     r15d, 40h ; '@'
0x18000efd7  and     ecx, 3
0x18000efda  and     eax, r15d
0x18000efdd  shl     ecx, 2
0x18000efe0  or      ecx, eax
0x18000efe2  shl     ecx, 2
0x18000efe5  or      ecx, edx
0x18000efe7  lea     edi, ds:0[rcx*8]
0x18000efee  test    r8d, r8d
0x18000eff1  jnz     short loc_18000EFF8
0x18000eff3  mov     eax, r15d
0x18000eff6  jmp     short loc_18000F002
0x18000eff8  xor     eax, eax
0x18000effa  cmp     r8d, 2
0x18000effe  cmovz   eax, r15d
0x18000f002  or      edi, eax
0x18000f004  mov     eax, [rbx]
0x18000f006  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000f00b  mov     edx, eax
0x18000f00d  mov     [rbx], eax
0x18000f00f  jz      short loc_18000F03F
0x18000f011  test    dl, 2
0x18000f014  jnz     short loc_18000F03F
0x18000f016  mov     eax, edi
0x18000f018  xor     eax, edx
0x18000f01a  and     eax, 180h
0x18000f01f  xor     eax, edx
0x18000f021  mov     ecx, eax
0x18000f023  xor     ecx, edi
0x18000f025  and     ecx, r15d
0x18000f028  xor     ecx, eax
0x18000f02a  or      ecx, 1
0x18000f02d  mov     eax, ecx
0x18000f02f  xor     eax, edi
0x18000f031  and     eax, 800h
0x18000f036  xor     eax, ecx
0x18000f038  or      eax, 2
0x18000f03b  mov     [rbx], eax
0x18000f03d  jmp     short loc_18000F041
0x18000f03f  mov     eax, edx
0x18000f041  mov     r8d, edx
0x18000f044  and     r8d, 4
0x18000f048  jnz     short loc_18000F05D
0x18000f04a  mov     ecx, edi
0x18000f04c  xor     ecx, eax
0x18000f04e  and     ecx, 400h
0x18000f054  xor     ecx, eax
0x18000f056  or      ecx, 4
0x18000f059  mov     [rbx], ecx
0x18000f05b  jmp     short loc_18000F05F
0x18000f05d  mov     ecx, eax
0x18000f05f  mov     eax, edx
0x18000f061  lock cmpxchg [rsi], ecx
0x18000f065  jnz     short loc_18000F006
0x18000f067  test    r8d, r8d
0x18000f06a  jnz     short loc_18000F07C
0x18000f06c  mov     r8d, ebp
0x18000f06f  mov     edx, 3
0x18000f074  mov     rcx, rsi
0x18000f077  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f07c  test    byte ptr [rbx], 2
0x18000f07f  jnz     short loc_18000F0A5
0x18000f081  mov     eax, [rbx]
0x18000f083  xor     eax, edi
0x18000f085  and     eax, 180h
0x18000f08a  xor     eax, [rbx]
0x18000f08c  mov     ecx, eax
0x18000f08e  xor     ecx, edi
0x18000f090  and     ecx, r15d
0x18000f093  xor     ecx, eax
0x18000f095  or      ecx, 1
0x18000f098  mov     eax, ecx
0x18000f09a  xor     eax, edi
0x18000f09c  and     eax, 800h
0x18000f0a1  xor     eax, ecx
0x18000f0a3  mov     [rbx], eax
0x18000f0a5  mov     rbp, [rsp+38h+arg_10]
0x18000f0aa  mov     rax, rbx
0x18000f0ad  mov     rbx, [rsp+38h+arg_8]
0x18000f0b2  add     rsp, 20h
0x18000f0b6  pop     r15
0x18000f0b8  pop     rdi
0x18000f0b9  pop     rsi
0x18000f0ba  retn
```
