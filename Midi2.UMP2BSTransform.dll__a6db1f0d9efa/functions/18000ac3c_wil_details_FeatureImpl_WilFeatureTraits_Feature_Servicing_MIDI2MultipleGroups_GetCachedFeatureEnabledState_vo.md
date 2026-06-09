# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2MultipleGroups>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ac3c`
- end: `0x18000ae09`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2MultipleGroups@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000dd78`

## callees

- `0x18000ab78`
- `0x18000ac3c`
- `0x18000d258`
- `0x18000dfec`
- `0x18000f010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2MultipleGroups>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_MIDI2MultipleGroups__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_MIDI2MultipleGroups__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(60893609, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl'::`2'::impl);
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
            (volatile signed __int32 *)Feature_Servicing_MIDI2MultipleGroups__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_Servicing_MIDI2MultipleGroups__descriptor,
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
0x18000ac3c  mov     [rsp+arg_0], rcx
0x18000ac41  push    rbx
0x18000ac42  push    rbp
0x18000ac43  push    rsi
0x18000ac44  push    rdi
0x18000ac45  push    r12
0x18000ac47  push    r14
0x18000ac49  sub     rsp, 28h
0x18000ac4d  mov     r14, cs:Feature_Servicing_MIDI2MultipleGroups__descriptor
0x18000ac54  mov     rdi, rdx
0x18000ac57  mov     qword ptr [rdx], 0
0x18000ac5e  mov     eax, [r14]
0x18000ac61  mov     [rdx], eax
0x18000ac63  and     eax, 6
0x18000ac66  cmp     al, 6
0x18000ac68  jz      loc_18000ADF9
0x18000ac6e  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ac73  mov     ebp, eax
0x18000ac75  mov     dword ptr [rsp+58h+arg_0], 0
0x18000ac7d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ac84  test    rax, rax
0x18000ac87  jz      short loc_18000ACA1
0x18000ac89  lea     r8, [rsp+58h+arg_0]
0x18000ac8e  mov     edx, 3
0x18000ac93  mov     ecx, 3A129A9h
0x18000ac98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac9d  mov     edx, eax
0x18000ac9f  jmp     short loc_18000ACAF
0x18000aca1  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000aca8  test    rax, rax
0x18000acab  jnz     short loc_18000AC89
0x18000acad  xor     edx, edx
0x18000acaf  mov     r8d, edx
0x18000acb2  mov     eax, edx
0x18000acb4  and     r8d, 0FFFFFF3Fh
0x18000acbb  and     edx, 80h
0x18000acc1  mov     ecx, r8d
0x18000acc4  mov     r12d, 40h ; '@'
0x18000acca  and     ecx, 3
0x18000accd  and     eax, r12d
0x18000acd0  shl     ecx, 2
0x18000acd3  or      ecx, eax
0x18000acd5  shl     ecx, 2
0x18000acd8  or      ecx, edx
0x18000acda  lea     ebx, ds:0[rcx*8]
0x18000ace1  test    r8d, r8d
0x18000ace4  jnz     short loc_18000ACEB
0x18000ace6  mov     eax, r12d
0x18000ace9  jmp     short loc_18000ACF5
0x18000aceb  xor     eax, eax
0x18000aced  cmp     r8d, 2
0x18000acf1  cmovz   eax, r12d
0x18000acf5  or      ebx, eax
0x18000acf7  mov     ecx, 0C00h
0x18000acfc  mov     eax, ebx
0x18000acfe  and     eax, ecx
0x18000ad00  cmp     eax, ecx
0x18000ad02  jnz     short loc_18000AD09
0x18000ad04  mov     sil, 1
0x18000ad07  jmp     short loc_18000AD11
0x18000ad09  xor     sil, sil
0x18000ad0c  test    r12b, bl
0x18000ad0f  jz      short loc_18000AD2C
0x18000ad11  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x18000ad18  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x18000ad1d  test    sil, sil
0x18000ad20  jz      short loc_18000AD2E
0x18000ad22  test    al, al
0x18000ad24  jnz     short loc_18000AD2E
0x18000ad26  btr     ebx, 0Ah
0x18000ad2a  jmp     short loc_18000AD2E
0x18000ad2c  xor     al, al
0x18000ad2e  test    r12b, bl
0x18000ad31  jz      short loc_18000AD3E
0x18000ad33  test    al, al
0x18000ad35  jz      short loc_18000AD3E
0x18000ad37  mov     esi, 1
0x18000ad3c  jmp     short loc_18000AD40
0x18000ad3e  xor     esi, esi
0x18000ad40  mov     eax, [rdi]
0x18000ad42  or      esi, ebx
0x18000ad44  mov     ebx, 180h
0x18000ad49  cmp     dword ptr [rsp+58h+arg_0], 0
0x18000ad4e  mov     edx, eax
0x18000ad50  mov     [rdi], eax
0x18000ad52  jz      short loc_18000AD8C
0x18000ad54  test    dl, 2
0x18000ad57  jnz     short loc_18000AD8C
0x18000ad59  mov     eax, esi
0x18000ad5b  xor     eax, edx
0x18000ad5d  and     eax, ebx
0x18000ad5f  xor     eax, edx
0x18000ad61  mov     ecx, eax
0x18000ad63  xor     ecx, esi
0x18000ad65  and     ecx, r12d
0x18000ad68  xor     ecx, eax
0x18000ad6a  mov     eax, ecx
0x18000ad6c  xor     eax, esi
0x18000ad6e  and     eax, 1
0x18000ad71  xor     eax, ecx
0x18000ad73  mov     r8d, eax
0x18000ad76  xor     r8d, esi
0x18000ad79  and     r8d, 800h
0x18000ad80  xor     r8d, eax
0x18000ad83  or      r8d, 2
0x18000ad87  mov     [rdi], r8d
0x18000ad8a  jmp     short loc_18000AD8F
0x18000ad8c  mov     r8d, edx
0x18000ad8f  mov     r9d, edx
0x18000ad92  and     r9d, 4
0x18000ad96  jnz     short loc_18000ADAD
0x18000ad98  mov     ecx, esi
0x18000ad9a  xor     ecx, r8d
0x18000ad9d  and     ecx, 400h
0x18000ada3  xor     ecx, r8d
0x18000ada6  or      ecx, 4
0x18000ada9  mov     [rdi], ecx
0x18000adab  jmp     short loc_18000ADB0
0x18000adad  mov     ecx, r8d
0x18000adb0  mov     eax, edx
0x18000adb2  lock cmpxchg [r14], ecx
0x18000adb7  jnz     short loc_18000AD49
0x18000adb9  test    r9d, r9d
0x18000adbc  jnz     short loc_18000ADCD
0x18000adbe  mov     r8d, ebp
0x18000adc1  lea     edx, [r9+3]
0x18000adc5  mov     rcx, r14
0x18000adc8  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000adcd  test    byte ptr [rdi], 2
0x18000add0  jnz     short loc_18000ADF9
0x18000add2  mov     eax, [rdi]
0x18000add4  xor     eax, esi
0x18000add6  and     eax, ebx
0x18000add8  xor     eax, [rdi]
0x18000adda  mov     ecx, eax
0x18000addc  xor     ecx, esi
0x18000adde  and     ecx, r12d
0x18000ade1  xor     ecx, eax
0x18000ade3  mov     edx, ecx
0x18000ade5  xor     edx, esi
0x18000ade7  and     edx, 1
0x18000adea  xor     edx, ecx
0x18000adec  mov     eax, edx
0x18000adee  xor     eax, esi
0x18000adf0  and     eax, 800h
0x18000adf5  xor     eax, edx
0x18000adf7  mov     [rdi], eax
0x18000adf9  mov     rax, rdi
0x18000adfc  add     rsp, 28h
0x18000ae00  pop     r14
0x18000ae02  pop     r12
0x18000ae04  pop     rdi
0x18000ae05  pop     rsi
0x18000ae06  pop     rbp
0x18000ae07  pop     rbx
0x18000ae08  retn
```
