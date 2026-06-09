# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e8a4`
- end: `0x18000ea1b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ef84`

## callees

- `0x18000da08`
- `0x18000e8a4`
- `0x180010c28`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValLabTest__descriptor,
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
0x18000e8a4  mov     [rsp+arg_8], rbx
0x18000e8a9  mov     [rsp+arg_10], rbp
0x18000e8ae  mov     [rsp+arg_0], rcx
0x18000e8b3  push    rsi
0x18000e8b4  push    rdi
0x18000e8b5  push    r15
0x18000e8b7  sub     rsp, 20h
0x18000e8bb  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18000e8c2  mov     rbx, rdx
0x18000e8c5  mov     qword ptr [rdx], 0
0x18000e8cc  mov     eax, [rsi]
0x18000e8ce  mov     [rdx], eax
0x18000e8d0  and     eax, 6
0x18000e8d3  cmp     al, 6
0x18000e8d5  jz      loc_18000EA05
0x18000e8db  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e8e0  mov     ebp, eax
0x18000e8e2  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e8ea  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e8f1  test    rax, rax
0x18000e8f4  jz      short loc_18000E90E
0x18000e8f6  lea     r8, [rsp+38h+arg_0]
0x18000e8fb  mov     edx, 3
0x18000e900  mov     ecx, 3667CA2h
0x18000e905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e90a  mov     edx, eax
0x18000e90c  jmp     short loc_18000E91C
0x18000e90e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e915  test    rax, rax
0x18000e918  jnz     short loc_18000E8F6
0x18000e91a  xor     edx, edx
0x18000e91c  mov     r8d, edx
0x18000e91f  mov     eax, edx
0x18000e921  and     r8d, 0FFFFFF3Fh
0x18000e928  and     edx, 80h
0x18000e92e  mov     ecx, r8d
0x18000e931  mov     r15d, 40h ; '@'
0x18000e937  and     ecx, 3
0x18000e93a  and     eax, r15d
0x18000e93d  shl     ecx, 2
0x18000e940  or      ecx, eax
0x18000e942  shl     ecx, 2
0x18000e945  or      ecx, edx
0x18000e947  lea     edi, ds:0[rcx*8]
0x18000e94e  test    r8d, r8d
0x18000e951  jnz     short loc_18000E958
0x18000e953  mov     eax, r15d
0x18000e956  jmp     short loc_18000E962
0x18000e958  xor     eax, eax
0x18000e95a  cmp     r8d, 2
0x18000e95e  cmovz   eax, r15d
0x18000e962  or      edi, eax
0x18000e964  mov     eax, [rbx]
0x18000e966  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e96b  mov     edx, eax
0x18000e96d  mov     [rbx], eax
0x18000e96f  jz      short loc_18000E99F
0x18000e971  test    dl, 2
0x18000e974  jnz     short loc_18000E99F
0x18000e976  mov     eax, edi
0x18000e978  xor     eax, edx
0x18000e97a  and     eax, 180h
0x18000e97f  xor     eax, edx
0x18000e981  mov     ecx, eax
0x18000e983  xor     ecx, edi
0x18000e985  and     ecx, r15d
0x18000e988  xor     ecx, eax
0x18000e98a  or      ecx, 1
0x18000e98d  mov     eax, ecx
0x18000e98f  xor     eax, edi
0x18000e991  and     eax, 800h
0x18000e996  xor     eax, ecx
0x18000e998  or      eax, 2
0x18000e99b  mov     [rbx], eax
0x18000e99d  jmp     short loc_18000E9A1
0x18000e99f  mov     eax, edx
0x18000e9a1  mov     r8d, edx
0x18000e9a4  and     r8d, 4
0x18000e9a8  jnz     short loc_18000E9BD
0x18000e9aa  mov     ecx, edi
0x18000e9ac  xor     ecx, eax
0x18000e9ae  and     ecx, 400h
0x18000e9b4  xor     ecx, eax
0x18000e9b6  or      ecx, 4
0x18000e9b9  mov     [rbx], ecx
0x18000e9bb  jmp     short loc_18000E9BF
0x18000e9bd  mov     ecx, eax
0x18000e9bf  mov     eax, edx
0x18000e9c1  lock cmpxchg [rsi], ecx
0x18000e9c5  jnz     short loc_18000E966
0x18000e9c7  test    r8d, r8d
0x18000e9ca  jnz     short loc_18000E9DC
0x18000e9cc  mov     r8d, ebp
0x18000e9cf  mov     edx, 3
0x18000e9d4  mov     rcx, rsi
0x18000e9d7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e9dc  test    byte ptr [rbx], 2
0x18000e9df  jnz     short loc_18000EA05
0x18000e9e1  mov     eax, [rbx]
0x18000e9e3  xor     eax, edi
0x18000e9e5  and     eax, 180h
0x18000e9ea  xor     eax, [rbx]
0x18000e9ec  mov     ecx, eax
0x18000e9ee  xor     ecx, edi
0x18000e9f0  and     ecx, r15d
0x18000e9f3  xor     ecx, eax
0x18000e9f5  or      ecx, 1
0x18000e9f8  mov     eax, ecx
0x18000e9fa  xor     eax, edi
0x18000e9fc  and     eax, 800h
0x18000ea01  xor     eax, ecx
0x18000ea03  mov     [rbx], eax
0x18000ea05  mov     rbp, [rsp+38h+arg_10]
0x18000ea0a  mov     rax, rbx
0x18000ea0d  mov     rbx, [rsp+38h+arg_8]
0x18000ea12  add     rsp, 20h
0x18000ea16  pop     r15
0x18000ea18  pop     rdi
0x18000ea19  pop     rsi
0x18000ea1a  retn
```
