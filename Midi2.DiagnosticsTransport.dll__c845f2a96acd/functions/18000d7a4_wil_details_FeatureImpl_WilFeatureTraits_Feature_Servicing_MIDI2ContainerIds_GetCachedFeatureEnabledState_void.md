# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetCachedFeatureEnabledState(void)

- ea: `0x18000d7a4`
- end: `0x18000d971`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010078`

## callees

- `0x18000d6e0`
- `0x18000d7a4`
- `0x18000ff38`
- `0x1800102ec`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_MIDI2ContainerIds__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_MIDI2ContainerIds__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(61091483, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl'::`2'::impl);
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
            (volatile signed __int32 *)Feature_Servicing_MIDI2ContainerIds__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_Servicing_MIDI2ContainerIds__descriptor,
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
0x18000d7a4  mov     [rsp+arg_0], rcx
0x18000d7a9  push    rbx
0x18000d7aa  push    rbp
0x18000d7ab  push    rsi
0x18000d7ac  push    rdi
0x18000d7ad  push    r12
0x18000d7af  push    r14
0x18000d7b1  sub     rsp, 28h
0x18000d7b5  mov     r14, cs:Feature_Servicing_MIDI2ContainerIds__descriptor
0x18000d7bc  mov     rdi, rdx
0x18000d7bf  mov     qword ptr [rdx], 0
0x18000d7c6  mov     eax, [r14]
0x18000d7c9  mov     [rdx], eax
0x18000d7cb  and     eax, 6
0x18000d7ce  cmp     al, 6
0x18000d7d0  jz      loc_18000D961
0x18000d7d6  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000d7db  mov     ebp, eax
0x18000d7dd  mov     dword ptr [rsp+58h+arg_0], 0
0x18000d7e5  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000d7ec  test    rax, rax
0x18000d7ef  jz      short loc_18000D809
0x18000d7f1  lea     r8, [rsp+58h+arg_0]
0x18000d7f6  mov     edx, 3
0x18000d7fb  mov     ecx, 3A42E9Bh
0x18000d800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d805  mov     edx, eax
0x18000d807  jmp     short loc_18000D817
0x18000d809  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000d810  test    rax, rax
0x18000d813  jnz     short loc_18000D7F1
0x18000d815  xor     edx, edx
0x18000d817  mov     r8d, edx
0x18000d81a  mov     eax, edx
0x18000d81c  and     r8d, 0FFFFFF3Fh
0x18000d823  and     edx, 80h
0x18000d829  mov     ecx, r8d
0x18000d82c  mov     r12d, 40h ; '@'
0x18000d832  and     ecx, 3
0x18000d835  and     eax, r12d
0x18000d838  shl     ecx, 2
0x18000d83b  or      ecx, eax
0x18000d83d  shl     ecx, 2
0x18000d840  or      ecx, edx
0x18000d842  lea     ebx, ds:0[rcx*8]
0x18000d849  test    r8d, r8d
0x18000d84c  jnz     short loc_18000D853
0x18000d84e  mov     eax, r12d
0x18000d851  jmp     short loc_18000D85D
0x18000d853  xor     eax, eax
0x18000d855  cmp     r8d, 2
0x18000d859  cmovz   eax, r12d
0x18000d85d  or      ebx, eax
0x18000d85f  mov     ecx, 0C00h
0x18000d864  mov     eax, ebx
0x18000d866  and     eax, ecx
0x18000d868  cmp     eax, ecx
0x18000d86a  jnz     short loc_18000D871
0x18000d86c  mov     sil, 1
0x18000d86f  jmp     short loc_18000D879
0x18000d871  xor     sil, sil
0x18000d874  test    r12b, bl
0x18000d877  jz      short loc_18000D894
0x18000d879  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestUex12@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12> `wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl(void)'::`2'::impl
0x18000d880  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(wil::ReportingKind)
0x18000d885  test    sil, sil
0x18000d888  jz      short loc_18000D896
0x18000d88a  test    al, al
0x18000d88c  jnz     short loc_18000D896
0x18000d88e  btr     ebx, 0Ah
0x18000d892  jmp     short loc_18000D896
0x18000d894  xor     al, al
0x18000d896  test    r12b, bl
0x18000d899  jz      short loc_18000D8A6
0x18000d89b  test    al, al
0x18000d89d  jz      short loc_18000D8A6
0x18000d89f  mov     esi, 1
0x18000d8a4  jmp     short loc_18000D8A8
0x18000d8a6  xor     esi, esi
0x18000d8a8  mov     eax, [rdi]
0x18000d8aa  or      esi, ebx
0x18000d8ac  mov     ebx, 180h
0x18000d8b1  cmp     dword ptr [rsp+58h+arg_0], 0
0x18000d8b6  mov     edx, eax
0x18000d8b8  mov     [rdi], eax
0x18000d8ba  jz      short loc_18000D8F4
0x18000d8bc  test    dl, 2
0x18000d8bf  jnz     short loc_18000D8F4
0x18000d8c1  mov     eax, esi
0x18000d8c3  xor     eax, edx
0x18000d8c5  and     eax, ebx
0x18000d8c7  xor     eax, edx
0x18000d8c9  mov     ecx, eax
0x18000d8cb  xor     ecx, esi
0x18000d8cd  and     ecx, r12d
0x18000d8d0  xor     ecx, eax
0x18000d8d2  mov     eax, ecx
0x18000d8d4  xor     eax, esi
0x18000d8d6  and     eax, 1
0x18000d8d9  xor     eax, ecx
0x18000d8db  mov     r8d, eax
0x18000d8de  xor     r8d, esi
0x18000d8e1  and     r8d, 800h
0x18000d8e8  xor     r8d, eax
0x18000d8eb  or      r8d, 2
0x18000d8ef  mov     [rdi], r8d
0x18000d8f2  jmp     short loc_18000D8F7
0x18000d8f4  mov     r8d, edx
0x18000d8f7  mov     r9d, edx
0x18000d8fa  and     r9d, 4
0x18000d8fe  jnz     short loc_18000D915
0x18000d900  mov     ecx, esi
0x18000d902  xor     ecx, r8d
0x18000d905  and     ecx, 400h
0x18000d90b  xor     ecx, r8d
0x18000d90e  or      ecx, 4
0x18000d911  mov     [rdi], ecx
0x18000d913  jmp     short loc_18000D918
0x18000d915  mov     ecx, r8d
0x18000d918  mov     eax, edx
0x18000d91a  lock cmpxchg [r14], ecx
0x18000d91f  jnz     short loc_18000D8B1
0x18000d921  test    r9d, r9d
0x18000d924  jnz     short loc_18000D935
0x18000d926  mov     r8d, ebp
0x18000d929  lea     edx, [r9+3]
0x18000d92d  mov     rcx, r14
0x18000d930  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000d935  test    byte ptr [rdi], 2
0x18000d938  jnz     short loc_18000D961
0x18000d93a  mov     eax, [rdi]
0x18000d93c  xor     eax, esi
0x18000d93e  and     eax, ebx
0x18000d940  xor     eax, [rdi]
0x18000d942  mov     ecx, eax
0x18000d944  xor     ecx, esi
0x18000d946  and     ecx, r12d
0x18000d949  xor     ecx, eax
0x18000d94b  mov     edx, ecx
0x18000d94d  xor     edx, esi
0x18000d94f  and     edx, 1
0x18000d952  xor     edx, ecx
0x18000d954  mov     eax, edx
0x18000d956  xor     eax, esi
0x18000d958  and     eax, 800h
0x18000d95d  xor     eax, edx
0x18000d95f  mov     [rdi], eax
0x18000d961  mov     rax, rdi
0x18000d964  add     rsp, 28h
0x18000d968  pop     r14
0x18000d96a  pop     r12
0x18000d96c  pop     rdi
0x18000d96d  pop     rsi
0x18000d96e  pop     rbp
0x18000d96f  pop     rbx
0x18000d970  retn
```
