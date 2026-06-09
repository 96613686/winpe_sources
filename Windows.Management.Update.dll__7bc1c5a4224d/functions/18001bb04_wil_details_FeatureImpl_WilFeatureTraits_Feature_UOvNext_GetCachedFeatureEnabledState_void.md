# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::GetCachedFeatureEnabledState(void)

- ea: `0x18001bb04`
- end: `0x18001bcd1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c8a0`

## callees

- `0x18000ace8`
- `0x18000eed4`
- `0x18001bb04`
- `0x18001c940`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
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
  wil::details *v20; // [rsp+60h] [rbp+8h] BYREF

  v20 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_UOvNext__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UOvNext__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(59927085, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UOvNext__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_UOvNext__descriptor,
      3u,
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
0x18001bb04  mov     [rsp+arg_0], rcx
0x18001bb09  push    rbx
0x18001bb0a  push    rbp
0x18001bb0b  push    rsi
0x18001bb0c  push    rdi
0x18001bb0d  push    r12
0x18001bb0f  push    r14
0x18001bb11  sub     rsp, 28h
0x18001bb15  mov     r14, cs:Feature_UOvNext__descriptor
0x18001bb1c  mov     rdi, rdx
0x18001bb1f  mov     qword ptr [rdx], 0
0x18001bb26  mov     eax, [r14]
0x18001bb29  mov     [rdx], eax
0x18001bb2b  and     eax, 6
0x18001bb2e  cmp     al, 6
0x18001bb30  jz      loc_18001BCC1
0x18001bb36  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001bb3b  mov     ebp, eax
0x18001bb3d  mov     dword ptr [rsp+58h+arg_0], 0
0x18001bb45  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001bb4c  test    rax, rax
0x18001bb4f  jz      short loc_18001BB69
0x18001bb51  lea     r8, [rsp+58h+arg_0]
0x18001bb56  mov     edx, 3
0x18001bb5b  mov     ecx, 3926A2Dh
0x18001bb60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb65  mov     edx, eax
0x18001bb67  jmp     short loc_18001BB77
0x18001bb69  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001bb70  test    rax, rax
0x18001bb73  jnz     short loc_18001BB51
0x18001bb75  xor     edx, edx
0x18001bb77  mov     r8d, edx
0x18001bb7a  mov     eax, edx
0x18001bb7c  and     r8d, 0FFFFFF3Fh
0x18001bb83  and     edx, 80h
0x18001bb89  mov     ecx, r8d
0x18001bb8c  mov     r12d, 40h ; '@'
0x18001bb92  and     ecx, 3
0x18001bb95  and     eax, r12d
0x18001bb98  shl     ecx, 2
0x18001bb9b  or      ecx, eax
0x18001bb9d  shl     ecx, 2
0x18001bba0  or      ecx, edx
0x18001bba2  lea     ebx, ds:0[rcx*8]
0x18001bba9  test    r8d, r8d
0x18001bbac  jnz     short loc_18001BBB3
0x18001bbae  mov     eax, r12d
0x18001bbb1  jmp     short loc_18001BBBD
0x18001bbb3  xor     eax, eax
0x18001bbb5  cmp     r8d, 2
0x18001bbb9  cmovz   eax, r12d
0x18001bbbd  or      ebx, eax
0x18001bbbf  mov     ecx, 0C00h
0x18001bbc4  mov     eax, ebx
0x18001bbc6  and     eax, ecx
0x18001bbc8  cmp     eax, ecx
0x18001bbca  jnz     short loc_18001BBD1
0x18001bbcc  mov     sil, 1
0x18001bbcf  jmp     short loc_18001BBD9
0x18001bbd1  xor     sil, sil
0x18001bbd4  test    r12b, bl
0x18001bbd7  jz      short loc_18001BBF4
0x18001bbd9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18001bbe0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18001bbe5  test    sil, sil
0x18001bbe8  jz      short loc_18001BBF6
0x18001bbea  test    al, al
0x18001bbec  jnz     short loc_18001BBF6
0x18001bbee  btr     ebx, 0Ah
0x18001bbf2  jmp     short loc_18001BBF6
0x18001bbf4  xor     al, al
0x18001bbf6  test    r12b, bl
0x18001bbf9  jz      short loc_18001BC06
0x18001bbfb  test    al, al
0x18001bbfd  jz      short loc_18001BC06
0x18001bbff  mov     esi, 1
0x18001bc04  jmp     short loc_18001BC08
0x18001bc06  xor     esi, esi
0x18001bc08  mov     eax, [rdi]
0x18001bc0a  or      esi, ebx
0x18001bc0c  mov     ebx, 180h
0x18001bc11  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001bc16  mov     edx, eax
0x18001bc18  mov     [rdi], eax
0x18001bc1a  jz      short loc_18001BC54
0x18001bc1c  test    dl, 2
0x18001bc1f  jnz     short loc_18001BC54
0x18001bc21  mov     eax, esi
0x18001bc23  xor     eax, edx
0x18001bc25  and     eax, ebx
0x18001bc27  xor     eax, edx
0x18001bc29  mov     ecx, eax
0x18001bc2b  xor     ecx, esi
0x18001bc2d  and     ecx, r12d
0x18001bc30  xor     ecx, eax
0x18001bc32  mov     eax, ecx
0x18001bc34  xor     eax, esi
0x18001bc36  and     eax, 1
0x18001bc39  xor     eax, ecx
0x18001bc3b  mov     r8d, eax
0x18001bc3e  xor     r8d, esi
0x18001bc41  and     r8d, 800h
0x18001bc48  xor     r8d, eax
0x18001bc4b  or      r8d, 2
0x18001bc4f  mov     [rdi], r8d
0x18001bc52  jmp     short loc_18001BC57
0x18001bc54  mov     r8d, edx
0x18001bc57  mov     r9d, edx
0x18001bc5a  and     r9d, 4
0x18001bc5e  jnz     short loc_18001BC75
0x18001bc60  mov     ecx, esi
0x18001bc62  xor     ecx, r8d
0x18001bc65  and     ecx, 400h
0x18001bc6b  xor     ecx, r8d
0x18001bc6e  or      ecx, 4
0x18001bc71  mov     [rdi], ecx
0x18001bc73  jmp     short loc_18001BC78
0x18001bc75  mov     ecx, r8d
0x18001bc78  mov     eax, edx
0x18001bc7a  lock cmpxchg [r14], ecx
0x18001bc7f  jnz     short loc_18001BC11
0x18001bc81  test    r9d, r9d
0x18001bc84  jnz     short loc_18001BC95
0x18001bc86  mov     r8d, ebp
0x18001bc89  lea     edx, [r9+3]
0x18001bc8d  mov     rcx, r14
0x18001bc90  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001bc95  test    byte ptr [rdi], 2
0x18001bc98  jnz     short loc_18001BCC1
0x18001bc9a  mov     eax, [rdi]
0x18001bc9c  xor     eax, esi
0x18001bc9e  and     eax, ebx
0x18001bca0  xor     eax, [rdi]
0x18001bca2  mov     ecx, eax
0x18001bca4  xor     ecx, esi
0x18001bca6  and     ecx, r12d
0x18001bca9  xor     ecx, eax
0x18001bcab  mov     edx, ecx
0x18001bcad  xor     edx, esi
0x18001bcaf  and     edx, 1
0x18001bcb2  xor     edx, ecx
0x18001bcb4  mov     eax, edx
0x18001bcb6  xor     eax, esi
0x18001bcb8  and     eax, 800h
0x18001bcbd  xor     eax, edx
0x18001bcbf  mov     [rdi], eax
0x18001bcc1  mov     rax, rdi
0x18001bcc4  add     rsp, 28h
0x18001bcc8  pop     r14
0x18001bcca  pop     r12
0x18001bccc  pop     rdi
0x18001bccd  pop     rsi
0x18001bcce  pop     rbp
0x18001bccf  pop     rbx
0x18001bcd0  retn
```
