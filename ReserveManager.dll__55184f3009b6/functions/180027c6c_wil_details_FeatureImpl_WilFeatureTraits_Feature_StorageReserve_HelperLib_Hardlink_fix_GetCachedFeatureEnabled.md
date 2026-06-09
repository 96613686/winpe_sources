# wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::GetCachedFeatureEnabledState(void)

- ea: `0x180027c6c`
- end: `0x180027e52`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `486`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18002a0b0`
- `0x18002ce34`

## callees

- `0x180003870`
- `0x180006e18`
- `0x18000acc8`
- `0x180027c6c`
- `0x18002ce70`
- `0x180033010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, int *); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // si
  char IsEnabled; // al
  BOOL v11; // esi
  signed __int32 v12; // eax
  int v13; // esi
  bool v14; // zf
  signed __int32 v15; // edx
  int v16; // r8d
  int v17; // r9d
  signed __int32 v18; // ecx
  int v20; // [rsp+20h] [rbp-48h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_StorageReserve_HelperLib_Hardlink_fix__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_StorageReserve_HelperLib_Hardlink_fix__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v20 = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(56033854, 3, &v20);
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
LABEL_13:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
    if ( v9 && !IsEnabled )
      v8 &= ~0x400u;
    goto LABEL_17;
  }
  v9 = 0;
  if ( (v8 & 0x40) != 0 )
    goto LABEL_13;
  IsEnabled = 0;
LABEL_17:
  v11 = (v8 & 0x40) != 0 && IsEnabled;
  v12 = *(_DWORD *)a2;
  v13 = v8 | v11;
  do
  {
    v14 = v20 == 0;
    v15 = v12;
    *(_DWORD *)a2 = v12;
    if ( v14 || (v12 & 2) != 0 )
    {
      v16 = v12;
    }
    else
    {
      v16 = v12
          ^ (v12
           ^ v13)
          & 0x180
          ^ (v13
           ^ v12
           ^ (v12
            ^ v13)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v13
           ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v13
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v13)
                              & 0x180
                              ^ (v13
                               ^ v12
                               ^ (v12
                                ^ v13)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v13
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v16;
    }
    v17 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v18 = v16;
    }
    else
    {
      v18 = v16 ^ ((unsigned __int16)v16 ^ (unsigned __int16)v13) & 0x400 | 4;
      *(_DWORD *)a2 = v18;
    }
    v12 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_StorageReserve_HelperLib_Hardlink_fix__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      Feature_StorageReserve_HelperLib_Hardlink_fix__descriptor,
      3,
      v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (v13
                    ^ *(_DWORD *)a2)
                   & 0x180
                   ^ (v13
                    ^ *(_DWORD *)a2
                    ^ (v13
                     ^ *(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v13
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v13
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v13
                     ^ *(_WORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v13
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v13
                      ^ *(_WORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v13
                       ^ *(_BYTE *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x180027c6c  push    rbx
0x180027c6e  push    rbp
0x180027c6f  push    rsi
0x180027c70  push    rdi
0x180027c71  push    r12
0x180027c73  push    r14
0x180027c75  sub     rsp, 38h
0x180027c79  mov     rax, cs:__security_cookie
0x180027c80  xor     rax, rsp
0x180027c83  mov     [rsp+68h+var_40], rax
0x180027c88  mov     r14, cs:Feature_StorageReserve_HelperLib_Hardlink_fix__descriptor
0x180027c8f  mov     rdi, rdx
0x180027c92  mov     qword ptr [rdx], 0
0x180027c99  mov     eax, [r14]
0x180027c9c  mov     [rdx], eax
0x180027c9e  and     eax, 6
0x180027ca1  cmp     al, 6
0x180027ca3  jz      loc_180027E35
0x180027ca9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180027cae  mov     ebp, eax
0x180027cb0  mov     [rsp+68h+var_48], 0
0x180027cb8  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180027cbf  test    rax, rax
0x180027cc2  jz      short loc_180027CDC
0x180027cc4  lea     r8, [rsp+68h+var_48]
0x180027cc9  mov     edx, 3
0x180027cce  mov     ecx, 357023Eh
0x180027cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cd8  mov     edx, eax
0x180027cda  jmp     short loc_180027CEA
0x180027cdc  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180027ce3  test    rax, rax
0x180027ce6  jnz     short loc_180027CC4
0x180027ce8  xor     edx, edx
0x180027cea  mov     r8d, edx
0x180027ced  mov     eax, edx
0x180027cef  and     r8d, 0FFFFFF3Fh
0x180027cf6  and     edx, 80h
0x180027cfc  mov     ecx, r8d
0x180027cff  mov     r12d, 40h ; '@'
0x180027d05  and     ecx, 3
0x180027d08  and     eax, r12d
0x180027d0b  shl     ecx, 2
0x180027d0e  or      ecx, eax
0x180027d10  shl     ecx, 2
0x180027d13  or      ecx, edx
0x180027d15  lea     ebx, ds:0[rcx*8]
0x180027d1c  test    r8d, r8d
0x180027d1f  jnz     short loc_180027D26
0x180027d21  mov     eax, r12d
0x180027d24  jmp     short loc_180027D30
0x180027d26  xor     eax, eax
0x180027d28  cmp     r8d, 2
0x180027d2c  cmovz   eax, r12d
0x180027d30  or      ebx, eax
0x180027d32  mov     ecx, 0C00h
0x180027d37  mov     eax, ebx
0x180027d39  and     eax, ecx
0x180027d3b  cmp     eax, ecx
0x180027d3d  jnz     short loc_180027D44
0x180027d3f  mov     sil, 1
0x180027d42  jmp     short loc_180027D4C
0x180027d44  xor     sil, sil
0x180027d47  test    r12b, bl
0x180027d4a  jz      short loc_180027D67
0x180027d4c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x180027d53  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x180027d58  test    sil, sil
0x180027d5b  jz      short loc_180027D69
0x180027d5d  test    al, al
0x180027d5f  jnz     short loc_180027D69
0x180027d61  btr     ebx, 0Ah
0x180027d65  jmp     short loc_180027D69
0x180027d67  xor     al, al
0x180027d69  test    r12b, bl
0x180027d6c  jz      short loc_180027D79
0x180027d6e  test    al, al
0x180027d70  jz      short loc_180027D79
0x180027d72  mov     esi, 1
0x180027d77  jmp     short loc_180027D7B
0x180027d79  xor     esi, esi
0x180027d7b  mov     eax, [rdi]
0x180027d7d  or      esi, ebx
0x180027d7f  mov     ebx, 180h
0x180027d84  cmp     [rsp+68h+var_48], 0
0x180027d89  mov     edx, eax
0x180027d8b  mov     [rdi], eax
0x180027d8d  jz      short loc_180027DC7
0x180027d8f  test    dl, 2
0x180027d92  jnz     short loc_180027DC7
0x180027d94  mov     eax, esi
0x180027d96  xor     eax, edx
0x180027d98  and     eax, ebx
0x180027d9a  xor     eax, edx
0x180027d9c  mov     ecx, eax
0x180027d9e  xor     ecx, esi
0x180027da0  and     ecx, r12d
0x180027da3  xor     ecx, eax
0x180027da5  mov     eax, ecx
0x180027da7  xor     eax, esi
0x180027da9  and     eax, 1
0x180027dac  xor     eax, ecx
0x180027dae  mov     r8d, eax
0x180027db1  xor     r8d, esi
0x180027db4  and     r8d, 800h
0x180027dbb  xor     r8d, eax
0x180027dbe  or      r8d, 2
0x180027dc2  mov     [rdi], r8d
0x180027dc5  jmp     short loc_180027DCA
0x180027dc7  mov     r8d, edx
0x180027dca  mov     r9d, edx
0x180027dcd  and     r9d, 4
0x180027dd1  jnz     short loc_180027DE8
0x180027dd3  mov     ecx, esi
0x180027dd5  xor     ecx, r8d
0x180027dd8  and     ecx, 400h
0x180027dde  xor     ecx, r8d
0x180027de1  or      ecx, 4
0x180027de4  mov     [rdi], ecx
0x180027de6  jmp     short loc_180027DEB
0x180027de8  mov     ecx, r8d
0x180027deb  mov     eax, edx
0x180027ded  lock cmpxchg [r14], ecx
0x180027df2  jnz     short loc_180027D84
0x180027df4  test    r9d, r9d
0x180027df7  jnz     short loc_180027E08
0x180027df9  mov     r8d, ebp
0x180027dfc  lea     edx, [r9+3]
0x180027e00  mov     rcx, r14
0x180027e03  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180027e08  test    byte ptr [rdi], 2
0x180027e0b  jnz     short loc_180027E35
0x180027e0d  mov     eax, [rdi]
0x180027e0f  xor     eax, esi
0x180027e11  and     eax, ebx
0x180027e13  xor     eax, [rdi]
0x180027e15  mov     ecx, eax
0x180027e17  xor     ecx, esi
0x180027e19  and     ecx, r12d
0x180027e1c  xor     ecx, eax
0x180027e1e  mov     edx, ecx
0x180027e20  xor     edx, esi
0x180027e22  and     edx, 1
0x180027e25  xor     edx, ecx
0x180027e27  mov     ecx, edx
0x180027e29  xor     ecx, esi
0x180027e2b  and     ecx, 800h
0x180027e31  xor     ecx, edx
0x180027e33  mov     [rdi], ecx
0x180027e35  mov     rax, rdi
0x180027e38  mov     rcx, [rsp+68h+var_40]
0x180027e3d  xor     rcx, rsp; StackCookie
0x180027e40  call    __security_check_cookie
0x180027e45  add     rsp, 38h
0x180027e49  pop     r14
0x180027e4b  pop     r12
0x180027e4d  pop     rdi
0x180027e4e  pop     rsi
0x180027e4f  pop     rbp
0x180027e50  pop     rbx
0x180027e51  retn
```
