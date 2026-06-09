# WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::WriteNonCommonProperties(std::vector<_DEVPROPERTY,std::allocator<_DEVPROPERTY>> &)

- ea: `0x18002c1e0`
- end: `0x18002c469`
- name: `?WriteNonCommonProperties@MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@QEAA_NAEAV?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@@Z`
- size: `649`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b7a0`
- `0x18002c0a8`

## callees

- `0x180016de0`
- `0x18002bc00`
- `0x18002c1e0`

## pseudocode

```c
char __fastcall WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::WriteNonCommonProperties(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rcx
  __int128 **v5; // rbx
  _QWORD *v6; // r14
  _OWORD *v7; // rdx
  int v8; // eax
  __int128 v9; // xmm1
  __int128 v10; // xmm2
  __int128 *v11; // rdx
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int64 v14; // r15
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 *v17; // rdx
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 *v20; // rdx
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 *v23; // rdx
  __int128 v24; // xmm1
  __int128 v26; // [rsp+20h] [rbp-38h] BYREF
  __int128 v27; // [rsp+30h] [rbp-28h]
  __int128 v28; // [rsp+40h] [rbp-18h]

  WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::Normalize((WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties *)a1);
  v4 = *(_QWORD *)(a1 + 16);
  v5 = (__int128 **)(a2 + 8);
  v6 = (_QWORD *)(a2 + 16);
  v7 = *(_OWORD **)(a2 + 8);
  v27 = 0x1F6u;
  v26 = PKEY_MIDI_CustomImagePath;
  if ( v4 )
  {
    v8 = *(_DWORD *)(v4 + 4);
    LODWORD(v28) = 18;
    DWORD1(v28) = 2 * v8 + 2;
    *((_QWORD *)&v28 + 1) = *(_QWORD *)(v4 + 16);
  }
  else
  {
    v28 = 0u;
  }
  if ( v7 == (_OWORD *)*v6 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(a2, v7, &v26);
  }
  else
  {
    v9 = v28;
    *v7 = PKEY_MIDI_CustomImagePath;
    v7[1] = v27;
    v7[2] = v9;
    *v5 += 3;
  }
  v10 = PKEY_MIDI_RequiresNoteOffTranslation;
  v11 = *v5;
  v26 = PKEY_MIDI_RequiresNoteOffTranslation;
  *(_QWORD *)&v28 = 0x100000011LL;
  v27 = 0x262u;
  if ( *(_BYTE *)(a1 + 24) )
  {
    *((_QWORD *)&v28 + 1) = a1 + 64;
    if ( v11 == (__int128 *)*v6 )
    {
      std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(a2, v11, &v26);
      v10 = PKEY_MIDI_RequiresNoteOffTranslation;
    }
    else
    {
      v12 = v27;
      v13 = v28;
      *v11 = PKEY_MIDI_RequiresNoteOffTranslation;
      v11[1] = v12;
      v11[2] = v13;
      *v5 += 3;
    }
    v14 = a1 + 65;
  }
  else
  {
    v14 = a1 + 65;
    *((_QWORD *)&v28 + 1) = a1 + 65;
    if ( v11 == (__int128 *)*v6 )
    {
      std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(a2, v11, &v26);
      v10 = PKEY_MIDI_RequiresNoteOffTranslation;
    }
    else
    {
      v15 = v27;
      v16 = v28;
      *v11 = PKEY_MIDI_RequiresNoteOffTranslation;
      v11[1] = v15;
      v11[2] = v16;
      *v5 += 3;
    }
  }
  v17 = *v5;
  v26 = v10;
  v27 = 0x262u;
  *(_QWORD *)&v28 = 0x100000011LL;
  if ( *(_BYTE *)(a1 + 25) )
    *((_QWORD *)&v28 + 1) = a1 + 64;
  else
    *((_QWORD *)&v28 + 1) = v14;
  if ( v17 == (__int128 *)*v6 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(a2, v17, &v26);
    v10 = PKEY_MIDI_RequiresNoteOffTranslation;
  }
  else
  {
    v18 = v27;
    v19 = v28;
    *v17 = v10;
    v17[1] = v18;
    v17[2] = v19;
    *v5 += 3;
  }
  v20 = *v5;
  v26 = v10;
  v27 = 0x262u;
  *(_QWORD *)&v28 = 0x200000005LL;
  *((_QWORD *)&v28 + 1) = a1 + 26;
  if ( v20 == (__int128 *)*v6 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(a2, v20, &v26);
  }
  else
  {
    v21 = v27;
    v22 = v28;
    *v20 = v10;
    v20[1] = v21;
    v20[2] = v22;
    *v5 += 3;
  }
  v23 = *v5;
  v27 = 0x3BBu;
  v26 = PKEY_MIDI_Midi1PortNamingSelection;
  *((_QWORD *)&v28 + 1) = a1 + 28;
  *(_QWORD *)&v28 = 0x400000007LL;
  if ( v23 == (__int128 *)*v6 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(a2, v23, &v26);
  }
  else
  {
    v24 = v28;
    *v23 = PKEY_MIDI_Midi1PortNamingSelection;
    v23[1] = v27;
    v23[2] = v24;
    *v5 += 3;
  }
  return 1;
}

```

## disassembly

```asm
0x18002c1e0  push    rbp
0x18002c1e2  push    rbx
0x18002c1e3  push    rsi
0x18002c1e4  push    rdi
0x18002c1e5  push    r14
0x18002c1e7  push    r15
0x18002c1e9  mov     rbp, rsp
0x18002c1ec  sub     rsp, 58h
0x18002c1f0  mov     rdi, rdx
0x18002c1f3  mov     rsi, rcx
0x18002c1f6  call    ?Normalize@MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@AEAAXXZ; WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::Normalize(void)
0x18002c1fb  movups  xmm0, cs:PKEY_MIDI_CustomImagePath
0x18002c202  mov     rcx, [rsi+10h]
0x18002c206  lea     rbx, [rdi+8]
0x18002c20a  mov     eax, cs:dword_180061540
0x18002c210  lea     r14, [rdi+10h]
0x18002c214  mov     rdx, [rbx]
0x18002c217  xor     r15d, r15d
0x18002c21a  mov     dword ptr [rbp+var_28+4], r15d
0x18002c21e  mov     qword ptr [rbp+var_28+8], r15
0x18002c222  mov     dword ptr [rbp+var_28], eax
0x18002c225  movups  [rbp+var_38], xmm0
0x18002c229  test    rcx, rcx
0x18002c22c  jz      short loc_18002C24C
0x18002c22e  mov     eax, [rcx+4]
0x18002c231  mov     dword ptr [rbp+var_18], 12h
0x18002c238  lea     eax, ds:2[rax*2]
0x18002c23f  mov     dword ptr [rbp+var_18+4], eax
0x18002c242  mov     rax, [rcx+10h]
0x18002c246  mov     qword ptr [rbp+var_18+8], rax
0x18002c24a  jmp     short loc_18002C254
0x18002c24c  mov     qword ptr [rbp+var_18], r15
0x18002c250  mov     qword ptr [rbp+var_18+8], r15
0x18002c254  cmp     rdx, [r14]
0x18002c257  jz      short loc_18002C272
0x18002c259  movups  xmm1, [rbp+var_18]
0x18002c25d  movups  xmmword ptr [rdx], xmm0
0x18002c260  movups  xmm0, [rbp+var_28]
0x18002c264  movups  xmmword ptr [rdx+10h], xmm0
0x18002c268  movups  xmmword ptr [rdx+20h], xmm1
0x18002c26c  add     qword ptr [rbx], 30h ; '0'
0x18002c270  jmp     short loc_18002C27E
0x18002c272  lea     r8, [rbp+var_38]
0x18002c276  mov     rcx, rdi
0x18002c279  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x18002c27e  movups  xmm2, cs:PKEY_MIDI_RequiresNoteOffTranslation
0x18002c285  mov     ecx, cs:dword_180061570
0x18002c28b  mov     rdx, [rbx]
0x18002c28e  movups  [rbp+var_38], xmm2
0x18002c292  mov     dword ptr [rbp+var_28+4], r15d
0x18002c296  mov     qword ptr [rbp+var_28+8], r15
0x18002c29a  mov     dword ptr [rbp+var_18], 11h
0x18002c2a1  mov     dword ptr [rbp+var_18+4], 1
0x18002c2a8  mov     dword ptr [rbp+var_28], ecx
0x18002c2ab  cmp     [rsi+18h], r15b
0x18002c2af  jz      short loc_18002C2F6
0x18002c2b1  lea     rax, [rsi+40h]
0x18002c2b5  mov     qword ptr [rbp+var_18+8], rax
0x18002c2b9  cmp     rdx, [r14]
0x18002c2bc  jz      short loc_18002C2D7
0x18002c2be  movups  xmm0, [rbp+var_28]
0x18002c2c2  movups  xmm1, [rbp+var_18]
0x18002c2c6  movups  xmmword ptr [rdx], xmm2
0x18002c2c9  movups  xmmword ptr [rdx+10h], xmm0
0x18002c2cd  movups  xmmword ptr [rdx+20h], xmm1
0x18002c2d1  add     qword ptr [rbx], 30h ; '0'
0x18002c2d5  jmp     short loc_18002C2F0
0x18002c2d7  lea     r8, [rbp+var_38]
0x18002c2db  mov     rcx, rdi
0x18002c2de  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x18002c2e3  mov     ecx, cs:dword_180061570
0x18002c2e9  movups  xmm2, cs:PKEY_MIDI_RequiresNoteOffTranslation
0x18002c2f0  lea     r15, [rsi+41h]
0x18002c2f4  jmp     short loc_18002C335
0x18002c2f6  lea     r15, [rsi+41h]
0x18002c2fa  mov     qword ptr [rbp+var_18+8], r15
0x18002c2fe  cmp     rdx, [r14]
0x18002c301  jz      short loc_18002C31C
0x18002c303  movups  xmm0, [rbp+var_28]
0x18002c307  movups  xmm1, [rbp+var_18]
0x18002c30b  movups  xmmword ptr [rdx], xmm2
0x18002c30e  movups  xmmword ptr [rdx+10h], xmm0
0x18002c312  movups  xmmword ptr [rdx+20h], xmm1
0x18002c316  add     qword ptr [rbx], 30h ; '0'
0x18002c31a  jmp     short loc_18002C335
0x18002c31c  lea     r8, [rbp+var_38]
0x18002c320  mov     rcx, rdi
0x18002c323  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x18002c328  mov     ecx, cs:dword_180061570
0x18002c32e  movups  xmm2, cs:PKEY_MIDI_RequiresNoteOffTranslation
0x18002c335  mov     rdx, [rbx]
0x18002c338  xor     r8d, r8d
0x18002c33b  movups  [rbp+var_38], xmm2
0x18002c33f  mov     dword ptr [rbp+var_28], ecx
0x18002c342  mov     dword ptr [rbp+var_28+4], r8d
0x18002c346  mov     qword ptr [rbp+var_28+8], r8
0x18002c34a  mov     dword ptr [rbp+var_18], 11h
0x18002c351  mov     dword ptr [rbp+var_18+4], 1
0x18002c358  cmp     [rsi+19h], r8b
0x18002c35c  jz      short loc_18002C368
0x18002c35e  lea     rax, [rsi+40h]
0x18002c362  mov     qword ptr [rbp+var_18+8], rax
0x18002c366  jmp     short loc_18002C36C
0x18002c368  mov     qword ptr [rbp+var_18+8], r15
0x18002c36c  cmp     rdx, [r14]
0x18002c36f  jz      short loc_18002C38A
0x18002c371  movups  xmm0, [rbp+var_28]
0x18002c375  movups  xmm1, [rbp+var_18]
0x18002c379  movups  xmmword ptr [rdx], xmm2
0x18002c37c  movups  xmmword ptr [rdx+10h], xmm0
0x18002c380  movups  xmmword ptr [rdx+20h], xmm1
0x18002c384  add     qword ptr [rbx], 30h ; '0'
0x18002c388  jmp     short loc_18002C3A6
0x18002c38a  lea     r8, [rbp+var_38]
0x18002c38e  mov     rcx, rdi
0x18002c391  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x18002c396  movups  xmm2, cs:PKEY_MIDI_RequiresNoteOffTranslation
0x18002c39d  mov     ecx, cs:dword_180061570
0x18002c3a3  xor     r8d, r8d
0x18002c3a6  mov     rdx, [rbx]
0x18002c3a9  lea     rax, [rsi+1Ah]
0x18002c3ad  movups  [rbp+var_38], xmm2
0x18002c3b1  mov     dword ptr [rbp+var_28], ecx
0x18002c3b4  mov     dword ptr [rbp+var_28+4], r8d
0x18002c3b8  mov     qword ptr [rbp+var_28+8], r8
0x18002c3bc  mov     dword ptr [rbp+var_18], 5
0x18002c3c3  mov     dword ptr [rbp+var_18+4], 2
0x18002c3ca  mov     qword ptr [rbp+var_18+8], rax
0x18002c3ce  cmp     rdx, [r14]
0x18002c3d1  jz      short loc_18002C3EC
0x18002c3d3  movups  xmm0, [rbp+var_28]
0x18002c3d7  movups  xmm1, [rbp+var_18]
0x18002c3db  movups  xmmword ptr [rdx], xmm2
0x18002c3de  movups  xmmword ptr [rdx+10h], xmm0
0x18002c3e2  movups  xmmword ptr [rdx+20h], xmm1
0x18002c3e6  add     qword ptr [rbx], 30h ; '0'
0x18002c3ea  jmp     short loc_18002C3FB
0x18002c3ec  lea     r8, [rbp+var_38]
0x18002c3f0  mov     rcx, rdi
0x18002c3f3  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x18002c3f8  xor     r8d, r8d
0x18002c3fb  mov     eax, cs:dword_180060E28
0x18002c401  movups  xmm0, cs:PKEY_MIDI_Midi1PortNamingSelection
0x18002c408  mov     rdx, [rbx]
0x18002c40b  mov     dword ptr [rbp+var_28], eax
0x18002c40e  lea     rax, [rsi+1Ch]
0x18002c412  movups  [rbp+var_38], xmm0
0x18002c416  mov     qword ptr [rbp+var_18+8], rax
0x18002c41a  mov     dword ptr [rbp+var_28+4], r8d
0x18002c41e  mov     qword ptr [rbp+var_28+8], r8
0x18002c422  mov     dword ptr [rbp+var_18], 7
0x18002c429  mov     dword ptr [rbp+var_18+4], 4
0x18002c430  cmp     rdx, [r14]
0x18002c433  jz      short loc_18002C44E
0x18002c435  movups  xmm1, [rbp+var_18]
0x18002c439  movups  xmmword ptr [rdx], xmm0
0x18002c43c  movups  xmm0, [rbp+var_28]
0x18002c440  movups  xmmword ptr [rdx+10h], xmm0
0x18002c444  movups  xmmword ptr [rdx+20h], xmm1
0x18002c448  add     qword ptr [rbx], 30h ; '0'
0x18002c44c  jmp     short loc_18002C45A
0x18002c44e  lea     r8, [rbp+var_38]
0x18002c452  mov     rcx, rdi
0x18002c455  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x18002c45a  mov     al, 1
0x18002c45c  add     rsp, 58h
0x18002c460  pop     r15
0x18002c462  pop     r14
0x18002c464  pop     rdi
0x18002c465  pop     rsi
0x18002c466  pop     rbx
0x18002c467  pop     rbp
0x18002c468  retn
```
