# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::GetCachedFeatureEnabledState(void)

- ea: `0x18003c8e8`
- end: `0x18003cab5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003e2d0`

## callees

- `0x180007d0c`
- `0x18000b2e0`
- `0x18002700c`
- `0x18003c8e8`
- `0x180041010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_MIDI2SendTimeout__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_MIDI2SendTimeout__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(60518363, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MediaQI2602>::GetImpl'::`2'::impl);
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
            (volatile signed __int32 *)Feature_Servicing_MIDI2SendTimeout__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_Servicing_MIDI2SendTimeout__descriptor,
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
0x18003c8e8  mov     [rsp+arg_0], rcx
0x18003c8ed  push    rbx
0x18003c8ee  push    rbp
0x18003c8ef  push    rsi
0x18003c8f0  push    rdi
0x18003c8f1  push    r12
0x18003c8f3  push    r14
0x18003c8f5  sub     rsp, 28h
0x18003c8f9  mov     r14, cs:Feature_Servicing_MIDI2SendTimeout__descriptor
0x18003c900  mov     rdi, rdx
0x18003c903  mov     qword ptr [rdx], 0
0x18003c90a  mov     eax, [r14]
0x18003c90d  mov     [rdx], eax
0x18003c90f  and     eax, 6
0x18003c912  cmp     al, 6
0x18003c914  jz      loc_18003CAA5
0x18003c91a  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18003c91f  mov     ebp, eax
0x18003c921  mov     dword ptr [rsp+58h+arg_0], 0
0x18003c929  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18003c930  test    rax, rax
0x18003c933  jz      short loc_18003C94D
0x18003c935  lea     r8, [rsp+58h+arg_0]
0x18003c93a  mov     edx, 3
0x18003c93f  mov     ecx, 39B6FDBh
0x18003c944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c949  mov     edx, eax
0x18003c94b  jmp     short loc_18003C95B
0x18003c94d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18003c954  test    rax, rax
0x18003c957  jnz     short loc_18003C935
0x18003c959  xor     edx, edx
0x18003c95b  mov     r8d, edx
0x18003c95e  mov     eax, edx
0x18003c960  and     r8d, 0FFFFFF3Fh
0x18003c967  and     edx, 80h
0x18003c96d  mov     ecx, r8d
0x18003c970  mov     r12d, 40h ; '@'
0x18003c976  and     ecx, 3
0x18003c979  and     eax, r12d
0x18003c97c  shl     ecx, 2
0x18003c97f  or      ecx, eax
0x18003c981  shl     ecx, 2
0x18003c984  or      ecx, edx
0x18003c986  lea     ebx, ds:0[rcx*8]
0x18003c98d  test    r8d, r8d
0x18003c990  jnz     short loc_18003C997
0x18003c992  mov     eax, r12d
0x18003c995  jmp     short loc_18003C9A1
0x18003c997  xor     eax, eax
0x18003c999  cmp     r8d, 2
0x18003c99d  cmovz   eax, r12d
0x18003c9a1  or      ebx, eax
0x18003c9a3  mov     ecx, 0C00h
0x18003c9a8  mov     eax, ebx
0x18003c9aa  and     eax, ecx
0x18003c9ac  cmp     eax, ecx
0x18003c9ae  jnz     short loc_18003C9B5
0x18003c9b0  mov     sil, 1
0x18003c9b3  jmp     short loc_18003C9BD
0x18003c9b5  xor     sil, sil
0x18003c9b8  test    r12b, bl
0x18003c9bb  jz      short loc_18003C9D8
0x18003c9bd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MediaQI2602@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602> `wil::Feature<__WilFeatureTraits_Feature_MediaQI2602>::GetImpl(void)'::`2'::impl
0x18003c9c4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::__private_IsEnabled(wil::ReportingKind)
0x18003c9c9  test    sil, sil
0x18003c9cc  jz      short loc_18003C9DA
0x18003c9ce  test    al, al
0x18003c9d0  jnz     short loc_18003C9DA
0x18003c9d2  btr     ebx, 0Ah
0x18003c9d6  jmp     short loc_18003C9DA
0x18003c9d8  xor     al, al
0x18003c9da  test    r12b, bl
0x18003c9dd  jz      short loc_18003C9EA
0x18003c9df  test    al, al
0x18003c9e1  jz      short loc_18003C9EA
0x18003c9e3  mov     esi, 1
0x18003c9e8  jmp     short loc_18003C9EC
0x18003c9ea  xor     esi, esi
0x18003c9ec  mov     eax, [rdi]
0x18003c9ee  or      esi, ebx
0x18003c9f0  mov     ebx, 180h
0x18003c9f5  cmp     dword ptr [rsp+58h+arg_0], 0
0x18003c9fa  mov     edx, eax
0x18003c9fc  mov     [rdi], eax
0x18003c9fe  jz      short loc_18003CA38
0x18003ca00  test    dl, 2
0x18003ca03  jnz     short loc_18003CA38
0x18003ca05  mov     eax, esi
0x18003ca07  xor     eax, edx
0x18003ca09  and     eax, ebx
0x18003ca0b  xor     eax, edx
0x18003ca0d  mov     ecx, eax
0x18003ca0f  xor     ecx, esi
0x18003ca11  and     ecx, r12d
0x18003ca14  xor     ecx, eax
0x18003ca16  mov     eax, ecx
0x18003ca18  xor     eax, esi
0x18003ca1a  and     eax, 1
0x18003ca1d  xor     eax, ecx
0x18003ca1f  mov     r8d, eax
0x18003ca22  xor     r8d, esi
0x18003ca25  and     r8d, 800h
0x18003ca2c  xor     r8d, eax
0x18003ca2f  or      r8d, 2
0x18003ca33  mov     [rdi], r8d
0x18003ca36  jmp     short loc_18003CA3B
0x18003ca38  mov     r8d, edx
0x18003ca3b  mov     r9d, edx
0x18003ca3e  and     r9d, 4
0x18003ca42  jnz     short loc_18003CA59
0x18003ca44  mov     ecx, esi
0x18003ca46  xor     ecx, r8d
0x18003ca49  and     ecx, 400h
0x18003ca4f  xor     ecx, r8d
0x18003ca52  or      ecx, 4
0x18003ca55  mov     [rdi], ecx
0x18003ca57  jmp     short loc_18003CA5C
0x18003ca59  mov     ecx, r8d
0x18003ca5c  mov     eax, edx
0x18003ca5e  lock cmpxchg [r14], ecx
0x18003ca63  jnz     short loc_18003C9F5
0x18003ca65  test    r9d, r9d
0x18003ca68  jnz     short loc_18003CA79
0x18003ca6a  mov     r8d, ebp
0x18003ca6d  lea     edx, [r9+3]
0x18003ca71  mov     rcx, r14
0x18003ca74  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18003ca79  test    byte ptr [rdi], 2
0x18003ca7c  jnz     short loc_18003CAA5
0x18003ca7e  mov     eax, [rdi]
0x18003ca80  xor     eax, esi
0x18003ca82  and     eax, ebx
0x18003ca84  xor     eax, [rdi]
0x18003ca86  mov     ecx, eax
0x18003ca88  xor     ecx, esi
0x18003ca8a  and     ecx, r12d
0x18003ca8d  xor     ecx, eax
0x18003ca8f  mov     edx, ecx
0x18003ca91  xor     edx, esi
0x18003ca93  and     edx, 1
0x18003ca96  xor     edx, ecx
0x18003ca98  mov     eax, edx
0x18003ca9a  xor     eax, esi
0x18003ca9c  and     eax, 800h
0x18003caa1  xor     eax, edx
0x18003caa3  mov     [rdi], eax
0x18003caa5  mov     rax, rdi
0x18003caa8  add     rsp, 28h
0x18003caac  pop     r14
0x18003caae  pop     r12
0x18003cab0  pop     rdi
0x18003cab1  pop     rsi
0x18003cab2  pop     rbp
0x18003cab3  pop     rbx
0x18003cab4  retn
```
