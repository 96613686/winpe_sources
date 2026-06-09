# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch>::GetCachedFeatureEnabledState(void)

- ea: `0x18002caf8`
- end: `0x18002ccc5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002d640`

## callees

- `0x180007d0c`
- `0x18000b2e0`
- `0x18002010c`
- `0x18002caf8`
- `0x180041010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_MIDI2USBDeviceMatch__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_MIDI2USBDeviceMatch__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(61264490, 3, &v20);
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
            (volatile signed __int32 *)Feature_Servicing_MIDI2USBDeviceMatch__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_Servicing_MIDI2USBDeviceMatch__descriptor,
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
0x18002caf8  mov     [rsp+arg_0], rcx
0x18002cafd  push    rbx
0x18002cafe  push    rbp
0x18002caff  push    rsi
0x18002cb00  push    rdi
0x18002cb01  push    r12
0x18002cb03  push    r14
0x18002cb05  sub     rsp, 28h
0x18002cb09  mov     r14, cs:Feature_Servicing_MIDI2USBDeviceMatch__descriptor
0x18002cb10  mov     rdi, rdx
0x18002cb13  mov     qword ptr [rdx], 0
0x18002cb1a  mov     eax, [r14]
0x18002cb1d  mov     [rdx], eax
0x18002cb1f  and     eax, 6
0x18002cb22  cmp     al, 6
0x18002cb24  jz      loc_18002CCB5
0x18002cb2a  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002cb2f  mov     ebp, eax
0x18002cb31  mov     dword ptr [rsp+58h+arg_0], 0
0x18002cb39  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18002cb40  test    rax, rax
0x18002cb43  jz      short loc_18002CB5D
0x18002cb45  lea     r8, [rsp+58h+arg_0]
0x18002cb4a  mov     edx, 3
0x18002cb4f  mov     ecx, 3A6D26Ah
0x18002cb54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb59  mov     edx, eax
0x18002cb5b  jmp     short loc_18002CB6B
0x18002cb5d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18002cb64  test    rax, rax
0x18002cb67  jnz     short loc_18002CB45
0x18002cb69  xor     edx, edx
0x18002cb6b  mov     r8d, edx
0x18002cb6e  mov     eax, edx
0x18002cb70  and     r8d, 0FFFFFF3Fh
0x18002cb77  and     edx, 80h
0x18002cb7d  mov     ecx, r8d
0x18002cb80  mov     r12d, 40h ; '@'
0x18002cb86  and     ecx, 3
0x18002cb89  and     eax, r12d
0x18002cb8c  shl     ecx, 2
0x18002cb8f  or      ecx, eax
0x18002cb91  shl     ecx, 2
0x18002cb94  or      ecx, edx
0x18002cb96  lea     ebx, ds:0[rcx*8]
0x18002cb9d  test    r8d, r8d
0x18002cba0  jnz     short loc_18002CBA7
0x18002cba2  mov     eax, r12d
0x18002cba5  jmp     short loc_18002CBB1
0x18002cba7  xor     eax, eax
0x18002cba9  cmp     r8d, 2
0x18002cbad  cmovz   eax, r12d
0x18002cbb1  or      ebx, eax
0x18002cbb3  mov     ecx, 0C00h
0x18002cbb8  mov     eax, ebx
0x18002cbba  and     eax, ecx
0x18002cbbc  cmp     eax, ecx
0x18002cbbe  jnz     short loc_18002CBC5
0x18002cbc0  mov     sil, 1
0x18002cbc3  jmp     short loc_18002CBCD
0x18002cbc5  xor     sil, sil
0x18002cbc8  test    r12b, bl
0x18002cbcb  jz      short loc_18002CBE8
0x18002cbcd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestUex12@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12> `wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl(void)'::`2'::impl
0x18002cbd4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(wil::ReportingKind)
0x18002cbd9  test    sil, sil
0x18002cbdc  jz      short loc_18002CBEA
0x18002cbde  test    al, al
0x18002cbe0  jnz     short loc_18002CBEA
0x18002cbe2  btr     ebx, 0Ah
0x18002cbe6  jmp     short loc_18002CBEA
0x18002cbe8  xor     al, al
0x18002cbea  test    r12b, bl
0x18002cbed  jz      short loc_18002CBFA
0x18002cbef  test    al, al
0x18002cbf1  jz      short loc_18002CBFA
0x18002cbf3  mov     esi, 1
0x18002cbf8  jmp     short loc_18002CBFC
0x18002cbfa  xor     esi, esi
0x18002cbfc  mov     eax, [rdi]
0x18002cbfe  or      esi, ebx
0x18002cc00  mov     ebx, 180h
0x18002cc05  cmp     dword ptr [rsp+58h+arg_0], 0
0x18002cc0a  mov     edx, eax
0x18002cc0c  mov     [rdi], eax
0x18002cc0e  jz      short loc_18002CC48
0x18002cc10  test    dl, 2
0x18002cc13  jnz     short loc_18002CC48
0x18002cc15  mov     eax, esi
0x18002cc17  xor     eax, edx
0x18002cc19  and     eax, ebx
0x18002cc1b  xor     eax, edx
0x18002cc1d  mov     ecx, eax
0x18002cc1f  xor     ecx, esi
0x18002cc21  and     ecx, r12d
0x18002cc24  xor     ecx, eax
0x18002cc26  mov     eax, ecx
0x18002cc28  xor     eax, esi
0x18002cc2a  and     eax, 1
0x18002cc2d  xor     eax, ecx
0x18002cc2f  mov     r8d, eax
0x18002cc32  xor     r8d, esi
0x18002cc35  and     r8d, 800h
0x18002cc3c  xor     r8d, eax
0x18002cc3f  or      r8d, 2
0x18002cc43  mov     [rdi], r8d
0x18002cc46  jmp     short loc_18002CC4B
0x18002cc48  mov     r8d, edx
0x18002cc4b  mov     r9d, edx
0x18002cc4e  and     r9d, 4
0x18002cc52  jnz     short loc_18002CC69
0x18002cc54  mov     ecx, esi
0x18002cc56  xor     ecx, r8d
0x18002cc59  and     ecx, 400h
0x18002cc5f  xor     ecx, r8d
0x18002cc62  or      ecx, 4
0x18002cc65  mov     [rdi], ecx
0x18002cc67  jmp     short loc_18002CC6C
0x18002cc69  mov     ecx, r8d
0x18002cc6c  mov     eax, edx
0x18002cc6e  lock cmpxchg [r14], ecx
0x18002cc73  jnz     short loc_18002CC05
0x18002cc75  test    r9d, r9d
0x18002cc78  jnz     short loc_18002CC89
0x18002cc7a  mov     r8d, ebp
0x18002cc7d  lea     edx, [r9+3]
0x18002cc81  mov     rcx, r14
0x18002cc84  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002cc89  test    byte ptr [rdi], 2
0x18002cc8c  jnz     short loc_18002CCB5
0x18002cc8e  mov     eax, [rdi]
0x18002cc90  xor     eax, esi
0x18002cc92  and     eax, ebx
0x18002cc94  xor     eax, [rdi]
0x18002cc96  mov     ecx, eax
0x18002cc98  xor     ecx, esi
0x18002cc9a  and     ecx, r12d
0x18002cc9d  xor     ecx, eax
0x18002cc9f  mov     edx, ecx
0x18002cca1  xor     edx, esi
0x18002cca3  and     edx, 1
0x18002cca6  xor     edx, ecx
0x18002cca8  mov     eax, edx
0x18002ccaa  xor     eax, esi
0x18002ccac  and     eax, 800h
0x18002ccb1  xor     eax, edx
0x18002ccb3  mov     [rdi], eax
0x18002ccb5  mov     rax, rdi
0x18002ccb8  add     rsp, 28h
0x18002ccbc  pop     r14
0x18002ccbe  pop     r12
0x18002ccc0  pop     rdi
0x18002ccc1  pop     rsi
0x18002ccc2  pop     rbp
0x18002ccc3  pop     rbx
0x18002ccc4  retn
```
