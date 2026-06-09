# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b648`
- end: `0x18000b815`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b81c`
- `0x18000c1cc`
- `0x180017850`

## callees

- `0x180005498`
- `0x180008f34`
- `0x18000b090`
- `0x18000b648`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // si
  unsigned __int8 IsEnabled; // al
  BOOL v11; // esi
  signed __int32 v12; // eax
  int v13; // esi
  bool v14; // zf
  signed __int32 v15; // edx
  int v16; // r8d
  int v17; // r9d
  signed __int32 v18; // ecx
  wil::details *v20; // [rsp+60h] [rbp+8h] BYREF

  v20 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_CLAT_Preview2_IpxlatSvcRpc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_Preview2_IpxlatSvcRpc__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(59797225, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2>::GetImpl'::`2'::impl);
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
    v14 = (_DWORD)v20 == 0;
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
            (volatile signed __int32 *)Feature_CLAT_Preview2_IpxlatSvcRpc__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      Feature_CLAT_Preview2_IpxlatSvcRpc__descriptor,
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
0x18000b648  mov     [rsp+arg_0], rcx
0x18000b64d  push    rbx
0x18000b64e  push    rbp
0x18000b64f  push    rsi
0x18000b650  push    rdi
0x18000b651  push    r12
0x18000b653  push    r14
0x18000b655  sub     rsp, 28h
0x18000b659  mov     r14, cs:Feature_CLAT_Preview2_IpxlatSvcRpc__descriptor
0x18000b660  mov     rdi, rdx
0x18000b663  mov     qword ptr [rdx], 0
0x18000b66a  mov     eax, [r14]
0x18000b66d  mov     [rdx], eax
0x18000b66f  and     eax, 6
0x18000b672  cmp     al, 6
0x18000b674  jz      loc_18000B805
0x18000b67a  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b67f  mov     ebp, eax
0x18000b681  mov     dword ptr [rsp+58h+arg_0], 0
0x18000b689  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000b690  test    rax, rax
0x18000b693  jz      short loc_18000B6AD
0x18000b695  lea     r8, [rsp+58h+arg_0]
0x18000b69a  mov     edx, 3
0x18000b69f  mov     ecx, 3906EE9h
0x18000b6a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6a9  mov     edx, eax
0x18000b6ab  jmp     short loc_18000B6BB
0x18000b6ad  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000b6b4  test    rax, rax
0x18000b6b7  jnz     short loc_18000B695
0x18000b6b9  xor     edx, edx
0x18000b6bb  mov     r8d, edx
0x18000b6be  mov     eax, edx
0x18000b6c0  and     r8d, 0FFFFFF3Fh
0x18000b6c7  and     edx, 80h
0x18000b6cd  mov     ecx, r8d
0x18000b6d0  mov     r12d, 40h ; '@'
0x18000b6d6  and     ecx, 3
0x18000b6d9  and     eax, r12d
0x18000b6dc  shl     ecx, 2
0x18000b6df  or      ecx, eax
0x18000b6e1  shl     ecx, 2
0x18000b6e4  or      ecx, edx
0x18000b6e6  lea     ebx, ds:0[rcx*8]
0x18000b6ed  test    r8d, r8d
0x18000b6f0  jnz     short loc_18000B6F7
0x18000b6f2  mov     eax, r12d
0x18000b6f5  jmp     short loc_18000B701
0x18000b6f7  xor     eax, eax
0x18000b6f9  cmp     r8d, 2
0x18000b6fd  cmovz   eax, r12d
0x18000b701  or      ebx, eax
0x18000b703  mov     ecx, 0C00h
0x18000b708  mov     eax, ebx
0x18000b70a  and     eax, ecx
0x18000b70c  cmp     eax, ecx
0x18000b70e  jnz     short loc_18000B715
0x18000b710  mov     sil, 1
0x18000b713  jmp     short loc_18000B71D
0x18000b715  xor     sil, sil
0x18000b718  test    r12b, bl
0x18000b71b  jz      short loc_18000B738
0x18000b71d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2>::GetImpl(void)'::`2'::impl
0x18000b724  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::__private_IsEnabled(wil::ReportingKind)
0x18000b729  test    sil, sil
0x18000b72c  jz      short loc_18000B73A
0x18000b72e  test    al, al
0x18000b730  jnz     short loc_18000B73A
0x18000b732  btr     ebx, 0Ah
0x18000b736  jmp     short loc_18000B73A
0x18000b738  xor     al, al
0x18000b73a  test    r12b, bl
0x18000b73d  jz      short loc_18000B74A
0x18000b73f  test    al, al
0x18000b741  jz      short loc_18000B74A
0x18000b743  mov     esi, 1
0x18000b748  jmp     short loc_18000B74C
0x18000b74a  xor     esi, esi
0x18000b74c  mov     eax, [rdi]
0x18000b74e  or      esi, ebx
0x18000b750  mov     ebx, 180h
0x18000b755  cmp     dword ptr [rsp+58h+arg_0], 0
0x18000b75a  mov     edx, eax
0x18000b75c  mov     [rdi], eax
0x18000b75e  jz      short loc_18000B798
0x18000b760  test    dl, 2
0x18000b763  jnz     short loc_18000B798
0x18000b765  mov     eax, esi
0x18000b767  xor     eax, edx
0x18000b769  and     eax, ebx
0x18000b76b  xor     eax, edx
0x18000b76d  mov     ecx, eax
0x18000b76f  xor     ecx, esi
0x18000b771  and     ecx, r12d
0x18000b774  xor     ecx, eax
0x18000b776  mov     eax, ecx
0x18000b778  xor     eax, esi
0x18000b77a  and     eax, 1
0x18000b77d  xor     eax, ecx
0x18000b77f  mov     r8d, eax
0x18000b782  xor     r8d, esi
0x18000b785  and     r8d, 800h
0x18000b78c  xor     r8d, eax
0x18000b78f  or      r8d, 2
0x18000b793  mov     [rdi], r8d
0x18000b796  jmp     short loc_18000B79B
0x18000b798  mov     r8d, edx
0x18000b79b  mov     r9d, edx
0x18000b79e  and     r9d, 4
0x18000b7a2  jnz     short loc_18000B7B9
0x18000b7a4  mov     ecx, esi
0x18000b7a6  xor     ecx, r8d
0x18000b7a9  and     ecx, 400h
0x18000b7af  xor     ecx, r8d
0x18000b7b2  or      ecx, 4
0x18000b7b5  mov     [rdi], ecx
0x18000b7b7  jmp     short loc_18000B7BC
0x18000b7b9  mov     ecx, r8d
0x18000b7bc  mov     eax, edx
0x18000b7be  lock cmpxchg [r14], ecx
0x18000b7c3  jnz     short loc_18000B755
0x18000b7c5  test    r9d, r9d
0x18000b7c8  jnz     short loc_18000B7D9
0x18000b7ca  mov     r8d, ebp
0x18000b7cd  lea     edx, [r9+3]
0x18000b7d1  mov     rcx, r14
0x18000b7d4  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000b7d9  test    byte ptr [rdi], 2
0x18000b7dc  jnz     short loc_18000B805
0x18000b7de  mov     eax, [rdi]
0x18000b7e0  xor     eax, esi
0x18000b7e2  and     eax, ebx
0x18000b7e4  xor     eax, [rdi]
0x18000b7e6  mov     ecx, eax
0x18000b7e8  xor     ecx, esi
0x18000b7ea  and     ecx, r12d
0x18000b7ed  xor     ecx, eax
0x18000b7ef  mov     edx, ecx
0x18000b7f1  xor     edx, esi
0x18000b7f3  and     edx, 1
0x18000b7f6  xor     edx, ecx
0x18000b7f8  mov     eax, edx
0x18000b7fa  xor     eax, esi
0x18000b7fc  and     eax, 800h
0x18000b801  xor     eax, edx
0x18000b803  mov     [rdi], eax
0x18000b805  mov     rax, rdi
0x18000b808  add     rsp, 28h
0x18000b80c  pop     r14
0x18000b80e  pop     r12
0x18000b810  pop     rdi
0x18000b811  pop     rsi
0x18000b812  pop     rbp
0x18000b813  pop     rbx
0x18000b814  retn
```
