# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b594`
- end: `0x18000b750`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000ca94`
- `0x18000d248`

## callees

- `0x18000ae28`
- `0x18000b594`
- `0x18000cd04`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // al
  int v10; // eax
  int v11; // ebx
  signed __int32 v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  int v15; // r8d
  int v16; // r9d
  signed __int32 v17; // ecx
  wil::details *v19; // [rsp+40h] [rbp+8h] BYREF

  v19 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Servicing_KdsSvc_DynamicCacheRefresh__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_KdsSvc_DynamicCacheRefresh__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v19) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(22235952, 3, &v19);
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
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
  }
  else
  {
    if ( (v8 & 0x40) != 0 )
      goto LABEL_17;
    v9 = 0;
  }
  if ( (v8 & 0x40) == 0 || !v9 )
  {
    v10 = 0;
    goto LABEL_18;
  }
LABEL_17:
  v10 = 1;
LABEL_18:
  v11 = v10 | v8;
  v12 = *(_DWORD *)a2;
  do
  {
    v13 = (_DWORD)v19 == 0;
    v14 = v12;
    *(_DWORD *)a2 = v12;
    if ( v13 || (v12 & 2) != 0 )
    {
      v15 = v12;
    }
    else
    {
      v15 = v12
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v11)
          & 0x180
          ^ (v11
           ^ v12
           ^ ((unsigned __int16)v12
            ^ (unsigned __int16)v11)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v11
           ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v11
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v11)
                              & 0x180
                              ^ (v11
                               ^ v12
                               ^ (v12
                                ^ v11)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v11
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    v16 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v17 = v15;
    }
    else
    {
      v17 = v15 ^ ((unsigned __int16)v15 ^ (unsigned __int16)v11) & 0x400 | 4;
      *(_DWORD *)a2 = v17;
    }
    v12 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_Servicing_KdsSvc_DynamicCacheRefresh__descriptor,
            v17,
            v12);
  }
  while ( v14 != v12 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      Feature_Servicing_KdsSvc_DynamicCacheRefresh__descriptor,
      3,
      v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v11
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v11
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v11
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v11
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v11
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v11
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v11
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v11
                       ^ (unsigned __int8)*(_DWORD *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x18000b594  mov     [rsp+arg_8], rbx
0x18000b599  mov     [rsp+arg_10], rbp
0x18000b59e  mov     [rsp+arg_0], rcx
0x18000b5a3  push    rsi
0x18000b5a4  push    rdi
0x18000b5a5  push    r15
0x18000b5a7  sub     rsp, 20h
0x18000b5ab  mov     rsi, cs:Feature_Servicing_KdsSvc_DynamicCacheRefresh__descriptor
0x18000b5b2  mov     rdi, rdx
0x18000b5b5  mov     qword ptr [rdx], 0
0x18000b5bc  mov     eax, [rsi]
0x18000b5be  mov     [rdx], eax
0x18000b5c0  and     eax, 6
0x18000b5c3  cmp     al, 6
0x18000b5c5  jz      loc_18000B73A
0x18000b5cb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b5d0  mov     ebp, eax
0x18000b5d2  mov     dword ptr [rsp+38h+arg_0], 0
0x18000b5da  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000b5e1  test    rax, rax
0x18000b5e4  jz      short loc_18000B5FE
0x18000b5e6  lea     r8, [rsp+38h+arg_0]
0x18000b5eb  mov     edx, 3
0x18000b5f0  mov     ecx, 1534B30h
0x18000b5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5fa  mov     edx, eax
0x18000b5fc  jmp     short loc_18000B60C
0x18000b5fe  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000b605  test    rax, rax
0x18000b608  jnz     short loc_18000B5E6
0x18000b60a  xor     edx, edx
0x18000b60c  mov     r8d, edx
0x18000b60f  mov     eax, edx
0x18000b611  and     r8d, 0FFFFFF3Fh
0x18000b618  and     edx, 80h
0x18000b61e  mov     ecx, r8d
0x18000b621  mov     r15d, 40h ; '@'
0x18000b627  and     ecx, 3
0x18000b62a  and     eax, r15d
0x18000b62d  shl     ecx, 2
0x18000b630  or      ecx, eax
0x18000b632  shl     ecx, 2
0x18000b635  or      ecx, edx
0x18000b637  lea     ebx, ds:0[rcx*8]
0x18000b63e  test    r8d, r8d
0x18000b641  jnz     short loc_18000B648
0x18000b643  mov     eax, r15d
0x18000b646  jmp     short loc_18000B652
0x18000b648  xor     eax, eax
0x18000b64a  cmp     r8d, 2
0x18000b64e  cmovz   eax, r15d
0x18000b652  or      ebx, eax
0x18000b654  mov     edx, 0C00h
0x18000b659  mov     ecx, ebx
0x18000b65b  mov     eax, ebx
0x18000b65d  and     ecx, r15d
0x18000b660  and     eax, edx
0x18000b662  cmp     eax, edx
0x18000b664  jnz     short loc_18000B66A
0x18000b666  mov     al, 1
0x18000b668  jmp     short loc_18000B670
0x18000b66a  test    ecx, ecx
0x18000b66c  jnz     short loc_18000B67C
0x18000b66e  xor     al, al
0x18000b670  test    ecx, ecx
0x18000b672  jz      short loc_18000B678
0x18000b674  test    al, al
0x18000b676  jnz     short loc_18000B67C
0x18000b678  xor     eax, eax
0x18000b67a  jmp     short loc_18000B681
0x18000b67c  mov     eax, 1
0x18000b681  or      ebx, eax
0x18000b683  mov     eax, [rdi]
0x18000b685  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000b68a  mov     edx, eax
0x18000b68c  mov     [rdi], eax
0x18000b68e  jz      short loc_18000B6CB
0x18000b690  test    dl, 2
0x18000b693  jnz     short loc_18000B6CB
0x18000b695  mov     eax, ebx
0x18000b697  xor     eax, edx
0x18000b699  and     eax, 180h
0x18000b69e  xor     eax, edx
0x18000b6a0  mov     ecx, eax
0x18000b6a2  xor     ecx, ebx
0x18000b6a4  and     ecx, r15d
0x18000b6a7  xor     ecx, eax
0x18000b6a9  mov     eax, ecx
0x18000b6ab  xor     eax, ebx
0x18000b6ad  and     eax, 1
0x18000b6b0  xor     eax, ecx
0x18000b6b2  mov     r8d, eax
0x18000b6b5  xor     r8d, ebx
0x18000b6b8  and     r8d, 800h
0x18000b6bf  xor     r8d, eax
0x18000b6c2  or      r8d, 2
0x18000b6c6  mov     [rdi], r8d
0x18000b6c9  jmp     short loc_18000B6CE
0x18000b6cb  mov     r8d, edx
0x18000b6ce  mov     r9d, edx
0x18000b6d1  and     r9d, 4
0x18000b6d5  jnz     short loc_18000B6EC
0x18000b6d7  mov     ecx, ebx
0x18000b6d9  xor     ecx, r8d
0x18000b6dc  and     ecx, 400h
0x18000b6e2  xor     ecx, r8d
0x18000b6e5  or      ecx, 4
0x18000b6e8  mov     [rdi], ecx
0x18000b6ea  jmp     short loc_18000B6EF
0x18000b6ec  mov     ecx, r8d
0x18000b6ef  mov     eax, edx
0x18000b6f1  lock cmpxchg [rsi], ecx
0x18000b6f5  jnz     short loc_18000B685
0x18000b6f7  test    r9d, r9d
0x18000b6fa  jnz     short loc_18000B70B
0x18000b6fc  mov     r8d, ebp
0x18000b6ff  lea     edx, [r9+3]
0x18000b703  mov     rcx, rsi
0x18000b706  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000b70b  test    byte ptr [rdi], 2
0x18000b70e  jnz     short loc_18000B73A
0x18000b710  mov     eax, [rdi]
0x18000b712  xor     eax, ebx
0x18000b714  and     eax, 180h
0x18000b719  xor     eax, [rdi]
0x18000b71b  mov     ecx, eax
0x18000b71d  xor     ecx, ebx
0x18000b71f  and     ecx, r15d
0x18000b722  xor     ecx, eax
0x18000b724  mov     edx, ecx
0x18000b726  xor     edx, ebx
0x18000b728  and     edx, 1
0x18000b72b  xor     edx, ecx
0x18000b72d  mov     eax, edx
0x18000b72f  xor     eax, ebx
0x18000b731  and     eax, 800h
0x18000b736  xor     eax, edx
0x18000b738  mov     [rdi], eax
0x18000b73a  mov     rbx, [rsp+38h+arg_8]
0x18000b73f  mov     rax, rdi
0x18000b742  mov     rbp, [rsp+38h+arg_10]
0x18000b747  add     rsp, 20h
0x18000b74b  pop     r15
0x18000b74d  pop     rdi
0x18000b74e  pop     rsi
0x18000b74f  retn
```
