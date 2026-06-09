# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_PREF64_FromRA>::GetCachedFeatureEnabledState(void)

- ea: `0x180013a04`
- end: `0x180013bd1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_PREF64_FromRA@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800177b0`

## callees

- `0x180005498`
- `0x180008f34`
- `0x18000aff4`
- `0x180013a04`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_PREF64_FromRA>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CLAT_PREF64_FromRA__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_PREF64_FromRA__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(56662962, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CLAT_Core>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CLAT_PREF64_FromRA__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CLAT_PREF64_FromRA__descriptor, 3, v4);
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
0x180013a04  mov     [rsp+arg_0], rcx
0x180013a09  push    rbx
0x180013a0a  push    rbp
0x180013a0b  push    rsi
0x180013a0c  push    rdi
0x180013a0d  push    r12
0x180013a0f  push    r14
0x180013a11  sub     rsp, 28h
0x180013a15  mov     r14, cs:Feature_CLAT_PREF64_FromRA__descriptor
0x180013a1c  mov     rdi, rdx
0x180013a1f  mov     qword ptr [rdx], 0
0x180013a26  mov     eax, [r14]
0x180013a29  mov     [rdx], eax
0x180013a2b  and     eax, 6
0x180013a2e  cmp     al, 6
0x180013a30  jz      loc_180013BC1
0x180013a36  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013a3b  mov     ebp, eax
0x180013a3d  mov     dword ptr [rsp+58h+arg_0], 0
0x180013a45  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180013a4c  test    rax, rax
0x180013a4f  jz      short loc_180013A69
0x180013a51  lea     r8, [rsp+58h+arg_0]
0x180013a56  mov     edx, 3
0x180013a5b  mov     ecx, 3609BB2h
0x180013a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a65  mov     edx, eax
0x180013a67  jmp     short loc_180013A77
0x180013a69  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180013a70  test    rax, rax
0x180013a73  jnz     short loc_180013A51
0x180013a75  xor     edx, edx
0x180013a77  mov     r8d, edx
0x180013a7a  mov     eax, edx
0x180013a7c  and     r8d, 0FFFFFF3Fh
0x180013a83  and     edx, 80h
0x180013a89  mov     ecx, r8d
0x180013a8c  mov     r12d, 40h ; '@'
0x180013a92  and     ecx, 3
0x180013a95  and     eax, r12d
0x180013a98  shl     ecx, 2
0x180013a9b  or      ecx, eax
0x180013a9d  shl     ecx, 2
0x180013aa0  or      ecx, edx
0x180013aa2  lea     ebx, ds:0[rcx*8]
0x180013aa9  test    r8d, r8d
0x180013aac  jnz     short loc_180013AB3
0x180013aae  mov     eax, r12d
0x180013ab1  jmp     short loc_180013ABD
0x180013ab3  xor     eax, eax
0x180013ab5  cmp     r8d, 2
0x180013ab9  cmovz   eax, r12d
0x180013abd  or      ebx, eax
0x180013abf  mov     ecx, 0C00h
0x180013ac4  mov     eax, ebx
0x180013ac6  and     eax, ecx
0x180013ac8  cmp     eax, ecx
0x180013aca  jnz     short loc_180013AD1
0x180013acc  mov     sil, 1
0x180013acf  jmp     short loc_180013AD9
0x180013ad1  xor     sil, sil
0x180013ad4  test    r12b, bl
0x180013ad7  jz      short loc_180013AF4
0x180013ad9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Core@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Core@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Core>::GetImpl(void)'::`2'::impl
0x180013ae0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Core@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::__private_IsEnabled(wil::ReportingKind)
0x180013ae5  test    sil, sil
0x180013ae8  jz      short loc_180013AF6
0x180013aea  test    al, al
0x180013aec  jnz     short loc_180013AF6
0x180013aee  btr     ebx, 0Ah
0x180013af2  jmp     short loc_180013AF6
0x180013af4  xor     al, al
0x180013af6  test    r12b, bl
0x180013af9  jz      short loc_180013B06
0x180013afb  test    al, al
0x180013afd  jz      short loc_180013B06
0x180013aff  mov     esi, 1
0x180013b04  jmp     short loc_180013B08
0x180013b06  xor     esi, esi
0x180013b08  mov     eax, [rdi]
0x180013b0a  or      esi, ebx
0x180013b0c  mov     ebx, 180h
0x180013b11  cmp     dword ptr [rsp+58h+arg_0], 0
0x180013b16  mov     edx, eax
0x180013b18  mov     [rdi], eax
0x180013b1a  jz      short loc_180013B54
0x180013b1c  test    dl, 2
0x180013b1f  jnz     short loc_180013B54
0x180013b21  mov     eax, esi
0x180013b23  xor     eax, edx
0x180013b25  and     eax, ebx
0x180013b27  xor     eax, edx
0x180013b29  mov     ecx, eax
0x180013b2b  xor     ecx, esi
0x180013b2d  and     ecx, r12d
0x180013b30  xor     ecx, eax
0x180013b32  mov     eax, ecx
0x180013b34  xor     eax, esi
0x180013b36  and     eax, 1
0x180013b39  xor     eax, ecx
0x180013b3b  mov     r8d, eax
0x180013b3e  xor     r8d, esi
0x180013b41  and     r8d, 800h
0x180013b48  xor     r8d, eax
0x180013b4b  or      r8d, 2
0x180013b4f  mov     [rdi], r8d
0x180013b52  jmp     short loc_180013B57
0x180013b54  mov     r8d, edx
0x180013b57  mov     r9d, edx
0x180013b5a  and     r9d, 4
0x180013b5e  jnz     short loc_180013B75
0x180013b60  mov     ecx, esi
0x180013b62  xor     ecx, r8d
0x180013b65  and     ecx, 400h
0x180013b6b  xor     ecx, r8d
0x180013b6e  or      ecx, 4
0x180013b71  mov     [rdi], ecx
0x180013b73  jmp     short loc_180013B78
0x180013b75  mov     ecx, r8d
0x180013b78  mov     eax, edx
0x180013b7a  lock cmpxchg [r14], ecx
0x180013b7f  jnz     short loc_180013B11
0x180013b81  test    r9d, r9d
0x180013b84  jnz     short loc_180013B95
0x180013b86  mov     r8d, ebp
0x180013b89  lea     edx, [r9+3]
0x180013b8d  mov     rcx, r14
0x180013b90  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013b95  test    byte ptr [rdi], 2
0x180013b98  jnz     short loc_180013BC1
0x180013b9a  mov     eax, [rdi]
0x180013b9c  xor     eax, esi
0x180013b9e  and     eax, ebx
0x180013ba0  xor     eax, [rdi]
0x180013ba2  mov     ecx, eax
0x180013ba4  xor     ecx, esi
0x180013ba6  and     ecx, r12d
0x180013ba9  xor     ecx, eax
0x180013bab  mov     edx, ecx
0x180013bad  xor     edx, esi
0x180013baf  and     edx, 1
0x180013bb2  xor     edx, ecx
0x180013bb4  mov     eax, edx
0x180013bb6  xor     eax, esi
0x180013bb8  and     eax, 800h
0x180013bbd  xor     eax, edx
0x180013bbf  mov     [rdi], eax
0x180013bc1  mov     rax, rdi
0x180013bc4  add     rsp, 28h
0x180013bc8  pop     r14
0x180013bca  pop     r12
0x180013bcc  pop     rdi
0x180013bcd  pop     rsi
0x180013bce  pop     rbp
0x180013bcf  pop     rbx
0x180013bd0  retn
```
