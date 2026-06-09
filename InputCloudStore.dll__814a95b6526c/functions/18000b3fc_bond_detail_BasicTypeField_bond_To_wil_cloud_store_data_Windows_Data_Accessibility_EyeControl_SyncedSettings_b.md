# bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)

- ea: `0x18000b3fc`
- end: `0x18000b794`
- name: `??$BasicTypeField@V?$To@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z`
- size: `920`
- prototype: `char __fastcall(__int16, __int64, int, __int64, bond::InputBuffer *)`
- caller_count: `11`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011070`
- `0x180011250`
- `0x1800113d4`
- `0x18001150c`
- `0x1800115fc`
- `0x1800116ec`
- `0x18001178c`
- `0x18001182c`
- `0x1800118cc`
- `0x18001196c`
- `0x180011ae8`

## callees

- `0x18000aa94`
- `0x18000b3fc`
- `0x18000f934`
- `0x18000f9c0`
- `0x18001b468`
- `0x18001b488`
- `0x18001b4a8`
- `0x18001b4c8`
- `0x18001b4e8`
- `0x18001b508`
- `0x18001b528`
- `0x18001f55c`
- `0x180020960`

## pseudocode

```c
char __fastcall bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(
        __int16 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        bond::InputBuffer *a5)
{
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  bond::InputBuffer *v11; // r9
  __int64 v12; // rbx
  __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 v15; // rbx
  bond::InputBuffer *v16; // r8
  char v17; // di
  int v19; // r8d
  int v20; // r8d
  int v21; // r8d
  int v22; // r8d
  int v23; // r8d
  bond::InputBuffer *v24; // [rsp+20h] [rbp-10h] BYREF
  char v25; // [rsp+28h] [rbp-8h]
  unsigned __int16 v26; // [rsp+50h] [rbp+20h] BYREF

  if ( a3 > 8 )
  {
    v19 = a3 - 9;
    if ( !v19 )
    {
      v24 = a5;
      v25 = 1;
      bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(&v24);
      return 0;
    }
    v20 = v19 - 5;
    if ( !v20 )
    {
      v24 = a5;
      v25 = 1;
      bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v24);
      return 0;
    }
    v21 = v20 - 1;
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( v23 )
        {
          if ( v23 == 1 )
          {
            v24 = a5;
            v25 = 1;
            bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(&v24);
          }
          return 0;
        }
      }
    }
    goto LABEL_45;
  }
  if ( a3 == 8 )
  {
    v24 = a5;
    v25 = 1;
    bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(&v24);
    return 0;
  }
  v6 = a3 - 2;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( !v7 )
    {
      v24 = a5;
      v25 = 1;
      if ( a1 == 5 )
      {
        v14 = *(_QWORD *)(a4 + 8);
        LOBYTE(v26) = 0;
        v25 = 0;
        bond::InputBuffer::Read(a5, (unsigned __int8 *)&v26);
        *(_DWORD *)(v14 + 8) = (unsigned __int8)v26;
      }
      else if ( a1 == 4 )
      {
        v15 = *(_QWORD *)(a4 + 8);
        LOBYTE(v26) = 0;
        v25 = 0;
        bond::InputBuffer::Read(a5, (unsigned __int8 *)&v26);
        *(_DWORD *)(v15 + 4) = (unsigned __int8)v26;
      }
      bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v24);
      return 0;
    }
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          if ( v10 != 1 )
            return 0;
          v11 = a5;
          v24 = a5;
          v25 = 1;
          if ( a1 == 7 )
          {
            v25 = 0;
            if ( (unsigned int)(*((_DWORD *)a5 + 6) - *((_DWORD *)a5 + 8)) >= 4 )
            {
              *(_DWORD *)(*(_QWORD *)(a4 + 8) + 16LL) = *(_DWORD *)(*((unsigned int *)a5 + 8) + *((_QWORD *)a5 + 2));
LABEL_15:
              *((_DWORD *)v11 + 8) += 4;
              goto LABEL_16;
            }
          }
          else
          {
            if ( a1 != 6 )
            {
LABEL_16:
              bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(&v24);
              return 0;
            }
            v25 = 0;
            if ( (unsigned int)(*((_DWORD *)a5 + 6) - *((_DWORD *)a5 + 8)) >= 4 )
            {
              *(_DWORD *)(*(_QWORD *)(a4 + 8) + 12LL) = *(_DWORD *)(*((unsigned int *)a5 + 8) + *((_QWORD *)a5 + 2));
              goto LABEL_15;
            }
          }
          bond::InputBuffer::EofException(a5, 4u);
        }
LABEL_45:
        v24 = a5;
        v25 = 1;
        bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v24);
        return 0;
      }
      v24 = a5;
      v25 = 1;
      if ( a1 == 5 || a1 == 4 )
      {
        v25 = 0;
        bond::InputBuffer::ReadVariableUnsigned<unsigned int>(a5);
      }
    }
    else
    {
      v24 = a5;
      v25 = 1;
      if ( a1 == 5 )
      {
        v12 = *(_QWORD *)(a4 + 8);
        v26 = 0;
        v25 = 0;
        bond::InputBuffer::ReadVariableUnsigned<unsigned short>(a5, &v26);
        *(_DWORD *)(v12 + 8) = v26;
      }
      else if ( a1 == 4 )
      {
        v13 = *(_QWORD *)(a4 + 8);
        v26 = 0;
        v25 = 0;
        bond::InputBuffer::ReadVariableUnsigned<unsigned short>(a5, &v26);
        *(_DWORD *)(v13 + 4) = v26;
      }
    }
    bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v24);
    return 0;
  }
  v16 = a5;
  v24 = a5;
  v25 = 1;
  if ( a1 == 10 )
  {
    v17 = 0;
    v25 = 0;
    if ( *((_DWORD *)a5 + 6) == *((_DWORD *)a5 + 8) )
      bond::InputBuffer::EofException(a5, 1u);
    *(_BYTE *)(*(_QWORD *)(a4 + 8) + 22LL) = *(_BYTE *)(*((unsigned int *)a5 + 8) + *((_QWORD *)a5 + 2));
    ++*((_DWORD *)v16 + 8);
  }
  else
  {
    v17 = bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>::AssignToField<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<6>,bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,21,&private: static bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_dockedBottom_metadata>,boost::mpl::l_item<boost::mpl::long_<5>,bond::reflection::FieldTemplate<8,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,20,&private: static bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_isDwellModeEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<4>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,3,&private: static bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_useAdvancedMouseFeatures_metadata>,boost::mpl::l_item<boost::mpl::long_<3>,bond::reflection::FieldTemplate<2,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,2,&private: static bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_useShapeWriting_metadata>,boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,1,&private: static bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_showGazeCursor_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,0,&private: static bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_eyeControlEnabled_metadata>,boost::mpl::l_end>>>>>>>,bond::value<bool,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(
            a4,
            a2,
            a1,
            (__int64)&v24);
  }
  bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v24);
  return v17;
}

```

## disassembly

```asm
0x18000b3fc  mov     [rsp-8+arg_0], rbx
0x18000b401  mov     [rsp-8+arg_8], rdi
0x18000b406  push    rbp
0x18000b407  mov     rbp, rsp
0x18000b40a  sub     rsp, 30h
0x18000b40e  mov     r10, r9
0x18000b411  cmp     r8d, 8
0x18000b415  jg      loc_18000B6B4
0x18000b41b  jz      loc_18000B69A
0x18000b421  sub     r8d, 2
0x18000b425  jz      loc_18000B635
0x18000b42b  sub     r8d, 1
0x18000b42f  jz      loc_18000B5C1
0x18000b435  sub     r8d, 1
0x18000b439  jz      loc_18000B54D
0x18000b43f  sub     r8d, 1
0x18000b443  jz      loc_18000B4FD
0x18000b449  sub     r8d, 1
0x18000b44d  jz      loc_18000B4E3
0x18000b453  cmp     r8d, 1
0x18000b457  jnz     loc_18000B768
0x18000b45d  mov     r9, [rbp+arg_20]
0x18000b461  mov     [rbp+var_10], r9
0x18000b465  mov     [rbp+var_8], r8b
0x18000b469  cmp     cx, 7
0x18000b46d  jnz     short loc_18000B49E
0x18000b46f  xor     edi, edi
0x18000b471  mov     [rbp+var_8], dil
0x18000b475  mov     eax, [r9+18h]
0x18000b479  sub     eax, [r9+20h]
0x18000b47d  lea     r8d, [rdi+4]
0x18000b481  cmp     eax, r8d
0x18000b484  jb      loc_18000B788
0x18000b48a  mov     edx, [r9+20h]
0x18000b48e  mov     rax, [r9+10h]
0x18000b492  mov     rcx, [r10+8]
0x18000b496  mov     eax, [rdx+rax]
0x18000b499  mov     [rcx+10h], eax
0x18000b49c  jmp     short loc_18000B4D1
0x18000b49e  cmp     cx, 6
0x18000b4a2  jnz     short loc_18000B4D5
0x18000b4a4  xor     edi, edi
0x18000b4a6  mov     [rbp+var_8], dil
0x18000b4aa  mov     eax, [r9+18h]
0x18000b4ae  sub     eax, [r9+20h]
0x18000b4b2  lea     r8d, [rdi+4]
0x18000b4b6  cmp     eax, r8d
0x18000b4b9  jb      loc_18000B788
0x18000b4bf  mov     edx, [r9+20h]
0x18000b4c3  mov     rax, [r9+10h]
0x18000b4c7  mov     rcx, [r10+8]
0x18000b4cb  mov     eax, [rdx+rax]
0x18000b4ce  mov     [rcx+0Ch], eax
0x18000b4d1  add     [r9+20h], r8d
0x18000b4d5  lea     rcx, [rbp+var_10]
0x18000b4d9  call    ??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b4de  jmp     loc_18000B768
0x18000b4e3  mov     rax, [rbp+arg_20]
0x18000b4e7  mov     [rbp+var_10], rax
0x18000b4eb  mov     [rbp+var_8], 1
0x18000b4ef  lea     rcx, [rbp+var_10]
0x18000b4f3  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b4f8  jmp     loc_18000B768
0x18000b4fd  mov     r9, [rbp+arg_20]
0x18000b501  mov     [rbp+var_10], r9
0x18000b505  mov     [rbp+var_8], 1
0x18000b509  mov     eax, 5
0x18000b50e  cmp     cx, ax
0x18000b511  jnz     short loc_18000B51D
0x18000b513  mov     rdx, [r10+8]
0x18000b517  add     rdx, 8
0x18000b51b  jmp     short loc_18000B530
0x18000b51d  mov     r8d, 4
0x18000b523  cmp     cx, r8w
0x18000b527  jnz     short loc_18000B53F
0x18000b529  mov     rdx, [r10+8]
0x18000b52d  add     rdx, r8
0x18000b530  xor     edi, edi
0x18000b532  mov     [rbp+var_8], dil
0x18000b536  mov     rcx, r9; this
0x18000b539  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x18000b53e  nop
0x18000b53f  lea     rcx, [rbp+var_10]
0x18000b543  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b548  jmp     loc_18000B768
0x18000b54d  mov     r9, [rbp+arg_20]
0x18000b551  mov     [rbp+var_10], r9
0x18000b555  mov     [rbp+var_8], 1
0x18000b559  mov     eax, 5
0x18000b55e  cmp     cx, ax
0x18000b561  jnz     short loc_18000B586
0x18000b563  mov     rbx, [r10+8]
0x18000b567  xor     edi, edi
0x18000b569  mov     [rbp+arg_10], di
0x18000b56d  mov     [rbp+var_8], dil
0x18000b571  lea     rdx, [rbp+arg_10]
0x18000b575  mov     rcx, r9
0x18000b578  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x18000b57d  movzx   eax, [rbp+arg_10]
0x18000b581  mov     [rbx+8], eax
0x18000b584  jmp     short loc_18000B5B3
0x18000b586  mov     r8d, 4
0x18000b58c  cmp     cx, r8w
0x18000b590  jnz     short loc_18000B5B3
0x18000b592  mov     rbx, [r10+8]
0x18000b596  xor     edi, edi
0x18000b598  mov     [rbp+arg_10], di
0x18000b59c  mov     [rbp+var_8], dil
0x18000b5a0  lea     rdx, [rbp+arg_10]
0x18000b5a4  mov     rcx, r9
0x18000b5a7  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x18000b5ac  movzx   eax, [rbp+arg_10]
0x18000b5b0  mov     [rbx+4], eax
0x18000b5b3  lea     rcx, [rbp+var_10]
0x18000b5b7  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b5bc  jmp     loc_18000B768
0x18000b5c1  mov     r9, [rbp+arg_20]
0x18000b5c5  mov     [rbp+var_10], r9
0x18000b5c9  mov     [rbp+var_8], 1
0x18000b5cd  mov     eax, 5
0x18000b5d2  cmp     cx, ax
0x18000b5d5  jnz     short loc_18000B5FA
0x18000b5d7  mov     rbx, [r10+8]
0x18000b5db  xor     edi, edi
0x18000b5dd  mov     byte ptr [rbp+arg_10], dil
0x18000b5e1  mov     [rbp+var_8], dil
0x18000b5e5  lea     rdx, [rbp+arg_10]; unsigned __int8 *
0x18000b5e9  mov     rcx, r9; this
0x18000b5ec  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x18000b5f1  movzx   eax, byte ptr [rbp+arg_10]
0x18000b5f5  mov     [rbx+8], eax
0x18000b5f8  jmp     short loc_18000B627
0x18000b5fa  mov     r8d, 4
0x18000b600  cmp     cx, r8w
0x18000b604  jnz     short loc_18000B627
0x18000b606  mov     rbx, [r10+8]
0x18000b60a  xor     edi, edi
0x18000b60c  mov     byte ptr [rbp+arg_10], dil
0x18000b610  mov     [rbp+var_8], dil
0x18000b614  lea     rdx, [rbp+arg_10]; unsigned __int8 *
0x18000b618  mov     rcx, r9; this
0x18000b61b  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x18000b620  movzx   eax, byte ptr [rbp+arg_10]
0x18000b624  mov     [rbx+4], eax
0x18000b627  lea     rcx, [rbp+var_10]
0x18000b62b  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b630  jmp     loc_18000B768
0x18000b635  mov     r8, [rbp+arg_20]
0x18000b639  mov     [rbp+var_10], r8
0x18000b63d  mov     [rbp+var_8], 1
0x18000b641  cmp     cx, 0Ah
0x18000b645  jnz     short loc_18000B676
0x18000b647  xor     edi, edi
0x18000b649  mov     [rbp+var_8], dil
0x18000b64d  mov     eax, [r8+18h]
0x18000b651  sub     eax, [r8+20h]
0x18000b655  cmp     eax, 1
0x18000b658  jb      loc_18000B77A
0x18000b65e  mov     edx, [r8+20h]
0x18000b662  mov     rax, [r8+10h]
0x18000b666  mov     rcx, [r9+8]
0x18000b66a  mov     al, [rdx+rax]
0x18000b66d  mov     [rcx+16h], al
0x18000b670  inc     dword ptr [r8+20h]
0x18000b674  jmp     short loc_18000B689
0x18000b676  lea     r9, [rbp+var_10]
0x18000b67a  movzx   r8d, cx
0x18000b67e  mov     rcx, r10
0x18000b681  call    ??$AssignToField@U?$l_iter@U?$l_item@U?$long_@$05@mpl@boost@@U?$FieldTemplate@$08Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BF@$1?s_dockedBottom_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$04@mpl@boost@@U?$FieldTemplate@$07Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BE@$1?s_isDwellModeEnabled_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$02$1?s_useAdvancedMouseFeatures_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$01$1?s_useShapeWriting_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$00$1?s_showGazeCursor_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0A@$1?s_eyeControlEnabled_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@V?$value@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@?$To@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@bond@@AEBA_NAEBU?$l_iter@U?$l_item@U?$long_@$05@mpl@boost@@U?$FieldTemplate@$08Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BF@$1?s_dockedBottom_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$04@mpl@boost@@U?$FieldTemplate@$07Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BE@$1?s_isDwellModeEnabled_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$02$1?s_useAdvancedMouseFeatures_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$01$1?s_useShapeWriting_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$00$1?s_showGazeCursor_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0A@$1?s_eyeControlEnabled_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@GAEBV?$value@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@1@@Z
0x18000b686  mov     dil, al
0x18000b689  lea     rcx, [rbp+var_10]
0x18000b68d  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b692  mov     al, dil
0x18000b695  jmp     loc_18000B76A
0x18000b69a  mov     rax, [rbp+arg_20]
0x18000b69e  mov     [rbp+var_10], rax
0x18000b6a2  mov     [rbp+var_8], 1
0x18000b6a6  lea     rcx, [rbp+var_10]
0x18000b6aa  call    ??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b6af  jmp     loc_18000B768
0x18000b6b4  sub     r8d, 9
0x18000b6b8  jz      loc_18000B753
0x18000b6be  sub     r8d, 5
0x18000b6c2  jz      short loc_18000B73C
0x18000b6c4  sub     r8d, 1
0x18000b6c8  jz      short loc_18000B725
0x18000b6ca  sub     r8d, 1
0x18000b6ce  jz      short loc_18000B70E
0x18000b6d0  sub     r8d, 1
0x18000b6d4  jz      short loc_18000B6F7
0x18000b6d6  cmp     r8d, 1
0x18000b6da  jnz     loc_18000B768
0x18000b6e0  mov     rax, [rbp+arg_20]
0x18000b6e4  mov     [rbp+var_10], rax
0x18000b6e8  mov     [rbp+var_8], r8b
0x18000b6ec  lea     rcx, [rbp+var_10]
0x18000b6f0  call    ??1?$value_common@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b6f5  jmp     short loc_18000B768
0x18000b6f7  mov     rax, [rbp+arg_20]
0x18000b6fb  mov     [rbp+var_10], rax
0x18000b6ff  mov     [rbp+var_8], 1
0x18000b703  lea     rcx, [rbp+var_10]
0x18000b707  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b70c  jmp     short loc_18000B768
0x18000b70e  mov     rax, [rbp+arg_20]
0x18000b712  mov     [rbp+var_10], rax
0x18000b716  mov     [rbp+var_8], 1
0x18000b71a  lea     rcx, [rbp+var_10]
0x18000b71e  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b723  jmp     short loc_18000B768
0x18000b725  mov     rax, [rbp+arg_20]
0x18000b729  mov     [rbp+var_10], rax
0x18000b72d  mov     [rbp+var_8], 1
0x18000b731  lea     rcx, [rbp+var_10]
0x18000b735  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b73a  jmp     short loc_18000B768
0x18000b73c  mov     rax, [rbp+arg_20]
0x18000b740  mov     [rbp+var_10], rax
0x18000b744  mov     [rbp+var_8], 1
0x18000b748  lea     rcx, [rbp+var_10]
0x18000b74c  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b751  jmp     short loc_18000B768
0x18000b753  mov     rax, [rbp+arg_20]
0x18000b757  mov     [rbp+var_10], rax
0x18000b75b  mov     [rbp+var_8], 1
0x18000b75f  lea     rcx, [rbp+var_10]
0x18000b763  call    ??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b768  xor     al, al
0x18000b76a  mov     rbx, [rsp+30h+arg_0]
0x18000b76f  mov     rdi, [rsp+30h+arg_8]
0x18000b774  add     rsp, 30h
0x18000b778  pop     rbp
0x18000b779  retn
0x18000b77a  mov     edx, 1; unsigned int
0x18000b77f  mov     rcx, r8; this
0x18000b782  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x18000b788  mov     edx, r8d; unsigned int
0x18000b78b  mov     rcx, r9; this
0x18000b78e  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
```
