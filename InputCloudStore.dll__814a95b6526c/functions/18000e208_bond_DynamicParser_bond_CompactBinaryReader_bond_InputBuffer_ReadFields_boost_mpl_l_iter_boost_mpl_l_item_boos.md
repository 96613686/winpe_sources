# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,21,&bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_dockedBottom_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,22,&bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_keyboardDockedBottom_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,21,&bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_dockedBottom_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,22,&bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_keyboardDockedBottom_metadata>,boost::mpl::l_end>>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>> const &)

- ea: `0x18000e208`
- end: `0x18000e2d3`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$08Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BF@$1?s_dockedBottom_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$09Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BG@$1?s_keyboardDockedBottom_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$08Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BF@$1?s_dockedBottom_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$09Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BG@$1?s_keyboardDockedBottom_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `203`
- prototype: `__int64 __fastcall(bond::InputBuffer **, __int64, _WORD *, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e9c0`

## callees

- `0x18000dd18`
- `0x18000e208`
- `0x1800118cc`
- `0x18001b528`
- `0x18001f55c`
- `0x18002099c`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,21,&private: static bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_dockedBottom_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,22,&private: static bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_keyboardDockedBottom_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>>(
        bond::InputBuffer **a1,
        __int64 a2,
        _WORD *a3,
        unsigned int *a4,
        __int64 a5)
{
  bond::InputBuffer *v8; // r8
  bond::InputBuffer *v10; // [rsp+30h] [rbp-38h] BYREF
  char v11; // [rsp+38h] [rbp-30h]

  do
  {
    if ( *a3 == 9 )
    {
      if ( *a4 == 2 )
      {
        v8 = *a1;
        v10 = v8;
        v11 = 0;
        if ( *((_DWORD *)v8 + 6) == *((_DWORD *)v8 + 8) )
          bond::InputBuffer::EofException(v8, 1u);
        *(_BYTE *)(*(_QWORD *)(a5 + 8) + 21LL) = *(_BYTE *)((unsigned int)(*((_DWORD *)v8 + 8))++ + *((_QWORD *)v8 + 2));
        bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v10);
        goto LABEL_8;
      }
    }
    else if ( *a3 > 9u )
    {
      return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,22,&private: static bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_keyboardDockedBottom_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>>(
               a1,
               a2,
               a3,
               a4,
               a5);
    }
    if ( *a4 <= 1 )
      return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,22,&private: static bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_keyboardDockedBottom_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>>(
               a1,
               a2,
               a3,
               a4,
               a5);
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,21,&private: static bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_dockedBottom_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>>(
      a1,
      a2,
      (unsigned __int16)*a3,
      *a4,
      a5);
LABEL_8:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  while ( *a3 <= 9u && *a4 > 1 );
  return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,22,&private: static bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_keyboardDockedBottom_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>>(
           a1,
           a2,
           a3,
           a4,
           a5);
}

```

## disassembly

```asm
0x18000e208  push    rbx
0x18000e20a  push    rbp
0x18000e20b  push    rsi
0x18000e20c  push    rdi
0x18000e20d  push    r15
0x18000e20f  sub     rsp, 40h
0x18000e213  mov     rbx, r9
0x18000e216  mov     rdi, r8
0x18000e219  mov     rsi, rcx
0x18000e21c  mov     r15d, 9
0x18000e222  mov     rbp, [rsp+68h+arg_20]
0x18000e22a  cmp     r15w, [rdi]
0x18000e22e  jnz     short loc_18000E271
0x18000e230  cmp     dword ptr [rbx], 2
0x18000e233  jnz     short loc_18000E273
0x18000e235  mov     r8, [rsi]
0x18000e238  mov     [rsp+68h+var_38], r8
0x18000e23d  mov     [rsp+68h+var_30], 0
0x18000e242  mov     eax, [r8+18h]
0x18000e246  sub     eax, [r8+20h]
0x18000e24a  cmp     eax, 1
0x18000e24d  jb      short loc_18000E2C5
0x18000e24f  mov     edx, [r8+20h]
0x18000e253  mov     rax, [r8+10h]
0x18000e257  mov     rcx, [rbp+8]
0x18000e25b  mov     al, [rdx+rax]
0x18000e25e  mov     [rcx+15h], al
0x18000e261  inc     dword ptr [r8+20h]
0x18000e265  lea     rcx, [rsp+68h+var_38]
0x18000e26a  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000e26f  jmp     short loc_18000E28C
0x18000e271  jb      short loc_18000E2A5
0x18000e273  cmp     dword ptr [rbx], 1
0x18000e276  jbe     short loc_18000E2A5
0x18000e278  mov     [rsp+68h+var_48], rbp
0x18000e27d  mov     r9d, [rbx]
0x18000e280  movzx   r8d, word ptr [rdi]
0x18000e284  mov     rcx, rsi
0x18000e287  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$08Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BF@$1?s_dockedBottom_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$08Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BF@$1?s_dockedBottom_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,21,&bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_dockedBottom_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>>(bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,21,&bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_dockedBottom_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>> const &)
0x18000e28c  mov     r8, rdi
0x18000e28f  mov     rdx, rbx
0x18000e292  mov     rcx, [rsi]; this
0x18000e295  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000e29a  cmp     r15w, [rdi]
0x18000e29e  jb      short loc_18000E2A5
0x18000e2a0  cmp     dword ptr [rbx], 1
0x18000e2a3  ja      short loc_18000E22A
0x18000e2a5  mov     [rsp+68h+arg_20], rbp
0x18000e2ad  mov     r9, rbx
0x18000e2b0  mov     r8, rdi
0x18000e2b3  mov     rcx, rsi
0x18000e2b6  add     rsp, 40h
0x18000e2ba  pop     r15
0x18000e2bc  pop     rdi
0x18000e2bd  pop     rsi
0x18000e2be  pop     rbp
0x18000e2bf  pop     rbx
0x18000e2c0  jmp     ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$09Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BG@$1?s_keyboardDockedBottom_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$09Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BG@$1?s_keyboardDockedBottom_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,22,&bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_keyboardDockedBottom_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,22,&bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_keyboardDockedBottom_metadata>,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>> const &)
0x18000e2c5  mov     edx, 1; unsigned int
0x18000e2ca  mov     rcx, r8; this
0x18000e2cd  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
```
