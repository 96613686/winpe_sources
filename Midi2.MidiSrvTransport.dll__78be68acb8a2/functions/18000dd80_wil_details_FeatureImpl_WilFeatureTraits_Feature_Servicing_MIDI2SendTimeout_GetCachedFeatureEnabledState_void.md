# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::GetCachedFeatureEnabledState(void)

- ea: `0x18000dd80`
- end: `0x18000df4d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001131c`

## callees

- `0x18000da08`
- `0x18000dd80`
- `0x180010c28`
- `0x180011280`
- `0x180015010`

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
0x18000dd80  mov     [rsp+arg_0], rcx
0x18000dd85  push    rbx
0x18000dd86  push    rbp
0x18000dd87  push    rsi
0x18000dd88  push    rdi
0x18000dd89  push    r12
0x18000dd8b  push    r14
0x18000dd8d  sub     rsp, 28h
0x18000dd91  mov     r14, cs:Feature_Servicing_MIDI2SendTimeout__descriptor
0x18000dd98  mov     rdi, rdx
0x18000dd9b  mov     qword ptr [rdx], 0
0x18000dda2  mov     eax, [r14]
0x18000dda5  mov     [rdx], eax
0x18000dda7  and     eax, 6
0x18000ddaa  cmp     al, 6
0x18000ddac  jz      loc_18000DF3D
0x18000ddb2  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ddb7  mov     ebp, eax
0x18000ddb9  mov     dword ptr [rsp+58h+arg_0], 0
0x18000ddc1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ddc8  test    rax, rax
0x18000ddcb  jz      short loc_18000DDE5
0x18000ddcd  lea     r8, [rsp+58h+arg_0]
0x18000ddd2  mov     edx, 3
0x18000ddd7  mov     ecx, 39B6FDBh
0x18000dddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dde1  mov     edx, eax
0x18000dde3  jmp     short loc_18000DDF3
0x18000dde5  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ddec  test    rax, rax
0x18000ddef  jnz     short loc_18000DDCD
0x18000ddf1  xor     edx, edx
0x18000ddf3  mov     r8d, edx
0x18000ddf6  mov     eax, edx
0x18000ddf8  and     r8d, 0FFFFFF3Fh
0x18000ddff  and     edx, 80h
0x18000de05  mov     ecx, r8d
0x18000de08  mov     r12d, 40h ; '@'
0x18000de0e  and     ecx, 3
0x18000de11  and     eax, r12d
0x18000de14  shl     ecx, 2
0x18000de17  or      ecx, eax
0x18000de19  shl     ecx, 2
0x18000de1c  or      ecx, edx
0x18000de1e  lea     ebx, ds:0[rcx*8]
0x18000de25  test    r8d, r8d
0x18000de28  jnz     short loc_18000DE2F
0x18000de2a  mov     eax, r12d
0x18000de2d  jmp     short loc_18000DE39
0x18000de2f  xor     eax, eax
0x18000de31  cmp     r8d, 2
0x18000de35  cmovz   eax, r12d
0x18000de39  or      ebx, eax
0x18000de3b  mov     ecx, 0C00h
0x18000de40  mov     eax, ebx
0x18000de42  and     eax, ecx
0x18000de44  cmp     eax, ecx
0x18000de46  jnz     short loc_18000DE4D
0x18000de48  mov     sil, 1
0x18000de4b  jmp     short loc_18000DE55
0x18000de4d  xor     sil, sil
0x18000de50  test    r12b, bl
0x18000de53  jz      short loc_18000DE70
0x18000de55  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MediaQI2602@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602> `wil::Feature<__WilFeatureTraits_Feature_MediaQI2602>::GetImpl(void)'::`2'::impl
0x18000de5c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::__private_IsEnabled(wil::ReportingKind)
0x18000de61  test    sil, sil
0x18000de64  jz      short loc_18000DE72
0x18000de66  test    al, al
0x18000de68  jnz     short loc_18000DE72
0x18000de6a  btr     ebx, 0Ah
0x18000de6e  jmp     short loc_18000DE72
0x18000de70  xor     al, al
0x18000de72  test    r12b, bl
0x18000de75  jz      short loc_18000DE82
0x18000de77  test    al, al
0x18000de79  jz      short loc_18000DE82
0x18000de7b  mov     esi, 1
0x18000de80  jmp     short loc_18000DE84
0x18000de82  xor     esi, esi
0x18000de84  mov     eax, [rdi]
0x18000de86  or      esi, ebx
0x18000de88  mov     ebx, 180h
0x18000de8d  cmp     dword ptr [rsp+58h+arg_0], 0
0x18000de92  mov     edx, eax
0x18000de94  mov     [rdi], eax
0x18000de96  jz      short loc_18000DED0
0x18000de98  test    dl, 2
0x18000de9b  jnz     short loc_18000DED0
0x18000de9d  mov     eax, esi
0x18000de9f  xor     eax, edx
0x18000dea1  and     eax, ebx
0x18000dea3  xor     eax, edx
0x18000dea5  mov     ecx, eax
0x18000dea7  xor     ecx, esi
0x18000dea9  and     ecx, r12d
0x18000deac  xor     ecx, eax
0x18000deae  mov     eax, ecx
0x18000deb0  xor     eax, esi
0x18000deb2  and     eax, 1
0x18000deb5  xor     eax, ecx
0x18000deb7  mov     r8d, eax
0x18000deba  xor     r8d, esi
0x18000debd  and     r8d, 800h
0x18000dec4  xor     r8d, eax
0x18000dec7  or      r8d, 2
0x18000decb  mov     [rdi], r8d
0x18000dece  jmp     short loc_18000DED3
0x18000ded0  mov     r8d, edx
0x18000ded3  mov     r9d, edx
0x18000ded6  and     r9d, 4
0x18000deda  jnz     short loc_18000DEF1
0x18000dedc  mov     ecx, esi
0x18000dede  xor     ecx, r8d
0x18000dee1  and     ecx, 400h
0x18000dee7  xor     ecx, r8d
0x18000deea  or      ecx, 4
0x18000deed  mov     [rdi], ecx
0x18000deef  jmp     short loc_18000DEF4
0x18000def1  mov     ecx, r8d
0x18000def4  mov     eax, edx
0x18000def6  lock cmpxchg [r14], ecx
0x18000defb  jnz     short loc_18000DE8D
0x18000defd  test    r9d, r9d
0x18000df00  jnz     short loc_18000DF11
0x18000df02  mov     r8d, ebp
0x18000df05  lea     edx, [r9+3]
0x18000df09  mov     rcx, r14
0x18000df0c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000df11  test    byte ptr [rdi], 2
0x18000df14  jnz     short loc_18000DF3D
0x18000df16  mov     eax, [rdi]
0x18000df18  xor     eax, esi
0x18000df1a  and     eax, ebx
0x18000df1c  xor     eax, [rdi]
0x18000df1e  mov     ecx, eax
0x18000df20  xor     ecx, esi
0x18000df22  and     ecx, r12d
0x18000df25  xor     ecx, eax
0x18000df27  mov     edx, ecx
0x18000df29  xor     edx, esi
0x18000df2b  and     edx, 1
0x18000df2e  xor     edx, ecx
0x18000df30  mov     eax, edx
0x18000df32  xor     eax, esi
0x18000df34  and     eax, 800h
0x18000df39  xor     eax, edx
0x18000df3b  mov     [rdi], eax
0x18000df3d  mov     rax, rdi
0x18000df40  add     rsp, 28h
0x18000df44  pop     r14
0x18000df46  pop     r12
0x18000df48  pop     rdi
0x18000df49  pop     rsi
0x18000df4a  pop     rbp
0x18000df4b  pop     rbx
0x18000df4c  retn
```
