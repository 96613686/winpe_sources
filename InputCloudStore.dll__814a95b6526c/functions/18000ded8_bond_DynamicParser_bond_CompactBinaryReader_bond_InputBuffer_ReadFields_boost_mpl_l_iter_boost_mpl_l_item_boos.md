# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<2,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,ushort,4,&bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_scrollLines_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,6,&bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<2,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,ushort,4,&bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_scrollLines_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,6,&bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata>,boost::mpl::l_end>>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>> const &)

- ea: `0x18000ded8`
- end: `0x18000df85`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@G$03$1?s_scrollLines_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@_N$05$1?s_allowScrollInactiveWindows_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@G$03$1?s_scrollLines_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@_N$05$1?s_allowScrollInactiveWindows_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `173`
- prototype: `__int64 __fastcall(bond::InputBuffer **, __int64, _WORD *, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e3a4`

## callees

- `0x18000d9c4`
- `0x18000ded8`
- `0x18000f934`
- `0x180011160`
- `0x18001b488`
- `0x18002099c`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<2,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,unsigned short,4,&private: static bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_scrollLines_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,6,&private: static bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>>(
        bond::InputBuffer **a1,
        __int64 a2,
        _WORD *a3,
        unsigned int *a4,
        __int64 a5)
{
  bond::InputBuffer *v9; // [rsp+30h] [rbp-38h] BYREF
  char v10; // [rsp+38h] [rbp-30h]

  do
  {
    if ( *a3 == 2 )
    {
      if ( *a4 == 4 )
      {
        v9 = *a1;
        v10 = 0;
        bond::InputBuffer::ReadVariableUnsigned<unsigned short>(v9, *(_QWORD *)(a5 + 8) + 4LL);
        bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v9);
        goto LABEL_7;
      }
    }
    else if ( *a3 > 2u )
    {
      return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,6,&private: static bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>>(
               a1,
               a2,
               a3,
               a4,
               a5);
    }
    if ( *a4 <= 1 )
      return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,6,&private: static bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>>(
               a1,
               a2,
               a3,
               a4,
               a5);
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<2,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,unsigned short,4,&private: static bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_scrollLines_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>>(
      a1,
      a2,
      (unsigned __int16)*a3,
      *a4,
      a5);
LABEL_7:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  while ( *a3 <= 2u && *a4 > 1 );
  return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,6,&private: static bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>>(
           a1,
           a2,
           a3,
           a4,
           a5);
}

```

## disassembly

```asm
0x18000ded8  push    rbx
0x18000deda  push    rbp
0x18000dedb  push    rsi
0x18000dedc  push    rdi
0x18000dedd  push    r14
0x18000dedf  sub     rsp, 40h
0x18000dee3  mov     rbx, r9
0x18000dee6  mov     rdi, r8
0x18000dee9  mov     rsi, rcx
0x18000deec  mov     r14d, 2
0x18000def2  mov     rbp, [rsp+68h+arg_20]
0x18000defa  cmp     r14w, [rdi]
0x18000defe  jnz     short loc_18000DF2C
0x18000df00  cmp     dword ptr [rbx], 4
0x18000df03  jnz     short loc_18000DF2E
0x18000df05  mov     rcx, [rsi]
0x18000df08  mov     [rsp+68h+var_38], rcx
0x18000df0d  mov     [rsp+68h+var_30], 0
0x18000df12  mov     rdx, [rbp+8]
0x18000df16  add     rdx, 4
0x18000df1a  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x18000df1f  nop
0x18000df20  lea     rcx, [rsp+68h+var_38]
0x18000df25  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000df2a  jmp     short loc_18000DF47
0x18000df2c  jb      short loc_18000DF65
0x18000df2e  cmp     dword ptr [rbx], 1
0x18000df31  jbe     short loc_18000DF65
0x18000df33  mov     [rsp+68h+var_48], rbp
0x18000df38  mov     r9d, [rbx]
0x18000df3b  movzx   r8d, word ptr [rdi]
0x18000df3f  mov     rcx, rsi
0x18000df42  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@G$03$1?s_scrollLines_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@G$03$1?s_scrollLines_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<2,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,ushort,4,&bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_scrollLines_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>>(bond::reflection::FieldTemplate<2,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,ushort,4,&bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_scrollLines_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>> const &)
0x18000df47  mov     r8, rdi
0x18000df4a  mov     rdx, rbx
0x18000df4d  mov     rcx, [rsi]; this
0x18000df50  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000df55  cmp     r14w, [rdi]
0x18000df59  jb      short loc_18000DF65
0x18000df5b  cmp     dword ptr [rbx], 0
0x18000df5e  jz      short loc_18000DF65
0x18000df60  cmp     dword ptr [rbx], 1
0x18000df63  jnz     short loc_18000DEFA
0x18000df65  mov     [rsp+68h+arg_20], rbp
0x18000df6d  mov     r9, rbx
0x18000df70  mov     r8, rdi
0x18000df73  mov     rcx, rsi
0x18000df76  add     rsp, 40h
0x18000df7a  pop     r14
0x18000df7c  pop     rdi
0x18000df7d  pop     rsi
0x18000df7e  pop     rbp
0x18000df7f  pop     rbx
0x18000df80  jmp     ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@_N$05$1?s_allowScrollInactiveWindows_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@_N$05$1?s_allowScrollInactiveWindows_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,6,&bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,6,&bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata>,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>> const &)
```
