# wil::details::FeatureImpl<__WilFeatureTraits_Feature_AesSha2>::GetCachedFeatureEnabledState(void)

- ea: `0x180013c8c`
- end: `0x180013e53`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AesSha2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018044`

## callees

- `0x180013584`
- `0x180013c8c`
- `0x180017240`
- `0x1800180e4`
- `0x18001e010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_AesSha2>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // si
  char IsEnabled; // al
  BOOL v11; // esi
  int v12; // esi
  signed __int32 v13; // eax
  bool v14; // zf
  signed __int32 v15; // edx
  int v16; // r8d
  int v17; // r9d
  signed __int32 v18; // ecx
  wil::details *v20; // [rsp+60h] [rbp+8h] BYREF

  v20 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_AesSha2__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_AesSha2__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  v6 = 0;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(48772363, 0, &v20);
  }
  v7 = 0;
  if ( (v6 & 0xFFFFFF3F) == 2 )
    v7 = 64;
  v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
LABEL_10:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb>::GetImpl'::`2'::impl);
    if ( v9 && !IsEnabled )
      v8 &= ~0x400u;
    goto LABEL_14;
  }
  v9 = 0;
  if ( (v8 & 0x40) != 0 )
    goto LABEL_10;
  IsEnabled = 0;
LABEL_14:
  v11 = (v8 & 0x40) != 0 && IsEnabled;
  v12 = v8 | v11;
  if ( !v4 )
    LODWORD(v20) = 0;
  v13 = *(_DWORD *)a2;
  do
  {
    v14 = (_DWORD)v20 == 0;
    v15 = v13;
    *(_DWORD *)a2 = v13;
    if ( v14 || (v13 & 2) != 0 )
    {
      v16 = v13;
    }
    else
    {
      v16 = v13
          ^ (v13
           ^ v12)
          & 0x180
          ^ (v12
           ^ v13
           ^ (v13
            ^ v12)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v12
           ^ (unsigned __int8)(v13 ^ (v13 ^ v12) & 0x80 ^ (v12 ^ v13 ^ (v13 ^ v12) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)(v13
                              ^ (v13
                               ^ v12)
                              & 0x180
                              ^ (v12
                               ^ v13
                               ^ (v13
                                ^ v12)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v12
                               ^ (unsigned __int8)(v13 ^ (v13 ^ v12) & 0x80 ^ (v12 ^ v13 ^ (v13 ^ v12) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v16;
    }
    v17 = v13 & 4;
    if ( (v13 & 4) != 0 )
    {
      v18 = v16;
    }
    else
    {
      v18 = v16 ^ ((unsigned __int16)v16 ^ (unsigned __int16)v12) & 0x400 | 4;
      *(_DWORD *)a2 = v18;
    }
    v13 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_AesSha2__descriptor, v18, v13);
  }
  while ( v15 != v13 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_AesSha2__descriptor, 0, v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (v12
                    ^ *(_DWORD *)a2)
                   & 0x180
                   ^ (v12
                    ^ *(_DWORD *)a2
                    ^ (v12
                     ^ *(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v12
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v12
                      ^ *(_BYTE *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v12
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v12
                     ^ *(_WORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v12
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v12
                      ^ *(_WORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v12
                      ^ *(_BYTE *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v12
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v12
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
0x180013c8c  mov     [rsp+arg_0], rcx
0x180013c91  push    rbx
0x180013c92  push    rbp
0x180013c93  push    rsi
0x180013c94  push    rdi
0x180013c95  push    r12
0x180013c97  push    r14
0x180013c99  sub     rsp, 28h
0x180013c9d  mov     r14, cs:Feature_AesSha2__descriptor
0x180013ca4  mov     rdi, rdx
0x180013ca7  mov     qword ptr [rdx], 0
0x180013cae  mov     eax, [r14]
0x180013cb1  mov     [rdx], eax
0x180013cb3  and     eax, 6
0x180013cb6  cmp     al, 6
0x180013cb8  jz      loc_180013E43
0x180013cbe  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013cc3  mov     ebp, eax
0x180013cc5  mov     dword ptr [rsp+58h+arg_0], 0
0x180013ccd  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180013cd4  xor     edx, edx
0x180013cd6  test    rax, rax
0x180013cd9  jnz     short loc_180013CE7
0x180013cdb  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180013ce2  test    rax, rax
0x180013ce5  jz      short loc_180013CF8
0x180013ce7  lea     r8, [rsp+58h+arg_0]
0x180013cec  mov     ecx, 2E8350Bh
0x180013cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cf6  mov     edx, eax
0x180013cf8  mov     r8d, edx
0x180013cfb  mov     eax, edx
0x180013cfd  and     r8d, 0FFFFFF3Fh
0x180013d04  and     edx, 80h
0x180013d0a  mov     ecx, r8d
0x180013d0d  mov     r12d, 40h ; '@'
0x180013d13  and     ecx, 3
0x180013d16  and     eax, r12d
0x180013d19  shl     ecx, 2
0x180013d1c  or      ecx, eax
0x180013d1e  xor     eax, eax
0x180013d20  shl     ecx, 2
0x180013d23  or      ecx, edx
0x180013d25  lea     ebx, ds:0[rcx*8]
0x180013d2c  test    r8d, r8d
0x180013d2f  jz      short loc_180013D39
0x180013d31  cmp     r8d, 2
0x180013d35  cmovz   eax, r12d
0x180013d39  or      ebx, eax
0x180013d3b  mov     ecx, 0C00h
0x180013d40  mov     eax, ebx
0x180013d42  and     eax, ecx
0x180013d44  cmp     eax, ecx
0x180013d46  jnz     short loc_180013D4D
0x180013d48  mov     sil, 1
0x180013d4b  jmp     short loc_180013D55
0x180013d4d  xor     sil, sil
0x180013d50  test    r12b, bl
0x180013d53  jz      short loc_180013D70
0x180013d55  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb> `wil::Feature<__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb>::GetImpl(void)'::`2'::impl
0x180013d5c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb>::__private_IsEnabled(wil::ReportingKind)
0x180013d61  test    sil, sil
0x180013d64  jz      short loc_180013D72
0x180013d66  test    al, al
0x180013d68  jnz     short loc_180013D72
0x180013d6a  btr     ebx, 0Ah
0x180013d6e  jmp     short loc_180013D72
0x180013d70  xor     al, al
0x180013d72  test    r12b, bl
0x180013d75  jz      short loc_180013D82
0x180013d77  test    al, al
0x180013d79  jz      short loc_180013D82
0x180013d7b  mov     esi, 1
0x180013d80  jmp     short loc_180013D84
0x180013d82  xor     esi, esi
0x180013d84  or      esi, ebx
0x180013d86  test    ebp, ebp
0x180013d88  jnz     short loc_180013D8E
0x180013d8a  mov     dword ptr [rsp+58h+arg_0], ebp
0x180013d8e  mov     eax, [rdi]
0x180013d90  mov     ebx, 180h
0x180013d95  cmp     dword ptr [rsp+58h+arg_0], 0
0x180013d9a  mov     edx, eax
0x180013d9c  mov     [rdi], eax
0x180013d9e  jz      short loc_180013DD8
0x180013da0  test    dl, 2
0x180013da3  jnz     short loc_180013DD8
0x180013da5  mov     eax, esi
0x180013da7  xor     eax, edx
0x180013da9  and     eax, ebx
0x180013dab  xor     eax, edx
0x180013dad  mov     ecx, eax
0x180013daf  xor     ecx, esi
0x180013db1  and     ecx, r12d
0x180013db4  xor     ecx, eax
0x180013db6  mov     eax, ecx
0x180013db8  xor     eax, esi
0x180013dba  and     eax, 1
0x180013dbd  xor     eax, ecx
0x180013dbf  mov     r8d, eax
0x180013dc2  xor     r8d, esi
0x180013dc5  and     r8d, 800h
0x180013dcc  xor     r8d, eax
0x180013dcf  or      r8d, 2
0x180013dd3  mov     [rdi], r8d
0x180013dd6  jmp     short loc_180013DDB
0x180013dd8  mov     r8d, edx
0x180013ddb  mov     r9d, edx
0x180013dde  and     r9d, 4
0x180013de2  jnz     short loc_180013DF9
0x180013de4  mov     ecx, esi
0x180013de6  xor     ecx, r8d
0x180013de9  and     ecx, 400h
0x180013def  xor     ecx, r8d
0x180013df2  or      ecx, 4
0x180013df5  mov     [rdi], ecx
0x180013df7  jmp     short loc_180013DFC
0x180013df9  mov     ecx, r8d
0x180013dfc  mov     eax, edx
0x180013dfe  lock cmpxchg [r14], ecx
0x180013e03  jnz     short loc_180013D95
0x180013e05  test    r9d, r9d
0x180013e08  jnz     short loc_180013E17
0x180013e0a  mov     r8d, ebp
0x180013e0d  xor     edx, edx
0x180013e0f  mov     rcx, r14
0x180013e12  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013e17  test    byte ptr [rdi], 2
0x180013e1a  jnz     short loc_180013E43
0x180013e1c  mov     eax, [rdi]
0x180013e1e  xor     eax, esi
0x180013e20  and     eax, ebx
0x180013e22  xor     eax, [rdi]
0x180013e24  mov     ecx, eax
0x180013e26  xor     ecx, esi
0x180013e28  and     ecx, r12d
0x180013e2b  xor     ecx, eax
0x180013e2d  mov     edx, ecx
0x180013e2f  xor     edx, esi
0x180013e31  and     edx, 1
0x180013e34  xor     edx, ecx
0x180013e36  mov     eax, edx
0x180013e38  xor     eax, esi
0x180013e3a  and     eax, 800h
0x180013e3f  xor     eax, edx
0x180013e41  mov     [rdi], eax
0x180013e43  mov     rax, rdi
0x180013e46  add     rsp, 28h
0x180013e4a  pop     r14
0x180013e4c  pop     r12
0x180013e4e  pop     rdi
0x180013e4f  pop     rsi
0x180013e50  pop     rbp
0x180013e51  pop     rbx
0x180013e52  retn
```
