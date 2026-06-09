# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,3,&bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_allowDisplayKeysWithPen_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,3,&bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_allowDisplayKeysWithPen_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata>,boost::mpl::l_end>>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>> const &)

- ea: `0x18000df8c`
- end: `0x18000e057`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$02$1?s_allowDisplayKeysWithPen_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$03$1?s_eraseEnabled_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$02$1?s_allowDisplayKeysWithPen_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$03$1?s_eraseEnabled_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `203`
- prototype: `__int64 __fastcall(bond::InputBuffer **, int, _WORD *, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e564`

## callees

- `0x18000daa8`
- `0x18000df8c`
- `0x180011388`
- `0x18001b528`
- `0x18001f55c`
- `0x18002099c`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,3,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_allowDisplayKeysWithPen_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>>>(
        bond::InputBuffer **a1,
        int a2,
        _WORD *a3,
        unsigned int *a4,
        __int64 a5)
{
  bond::InputBuffer *v8; // r8
  bond::InputBuffer *v10; // [rsp+30h] [rbp-38h] BYREF
  char v11; // [rsp+38h] [rbp-30h]

  do
  {
    if ( *a3 == 3 )
    {
      if ( *a4 == 2 )
      {
        v8 = *a1;
        v10 = v8;
        v11 = 0;
        if ( *((_DWORD *)v8 + 6) == *((_DWORD *)v8 + 8) )
          bond::InputBuffer::EofException(v8, 1u);
        *(_BYTE *)(*(_QWORD *)(a5 + 8) + 3LL) = *(_BYTE *)((unsigned int)(*((_DWORD *)v8 + 8))++ + *((_QWORD *)v8 + 2));
        bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v10);
        goto LABEL_8;
      }
    }
    else if ( *a3 > 3u )
    {
      return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>>>(
               a1,
               a2,
               a3,
               a4,
               a5);
    }
    if ( *a4 <= 1 )
      return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>>>(
               a1,
               a2,
               a3,
               a4,
               a5);
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,3,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_allowDisplayKeysWithPen_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>>>(
      (_DWORD)a1,
      a2,
      (unsigned __int16)*a3,
      *a4,
      a5);
LABEL_8:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  while ( *a3 <= 3u && *a4 > 1 );
  return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>>>(
           a1,
           a2,
           a3,
           a4,
           a5);
}

```

## disassembly

```asm
0x18000df8c  push    rbx
0x18000df8e  push    rbp
0x18000df8f  push    rsi
0x18000df90  push    rdi
0x18000df91  push    r15
0x18000df93  sub     rsp, 40h
0x18000df97  mov     rbx, r9
0x18000df9a  mov     rdi, r8
0x18000df9d  mov     rsi, rcx
0x18000dfa0  mov     r15d, 3
0x18000dfa6  mov     rbp, [rsp+68h+arg_20]
0x18000dfae  cmp     r15w, [rdi]
0x18000dfb2  jnz     short loc_18000DFF5
0x18000dfb4  cmp     dword ptr [rbx], 2
0x18000dfb7  jnz     short loc_18000DFF7
0x18000dfb9  mov     r8, [rsi]
0x18000dfbc  mov     [rsp+68h+var_38], r8
0x18000dfc1  mov     [rsp+68h+var_30], 0
0x18000dfc6  mov     eax, [r8+18h]
0x18000dfca  sub     eax, [r8+20h]
0x18000dfce  cmp     eax, 1
0x18000dfd1  jb      short loc_18000E049
0x18000dfd3  mov     edx, [r8+20h]
0x18000dfd7  mov     rax, [r8+10h]
0x18000dfdb  mov     rcx, [rbp+8]
0x18000dfdf  mov     al, [rdx+rax]
0x18000dfe2  mov     [rcx+3], al
0x18000dfe5  inc     dword ptr [r8+20h]
0x18000dfe9  lea     rcx, [rsp+68h+var_38]
0x18000dfee  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000dff3  jmp     short loc_18000E010
0x18000dff5  jb      short loc_18000E029
0x18000dff7  cmp     dword ptr [rbx], 1
0x18000dffa  jbe     short loc_18000E029
0x18000dffc  mov     [rsp+68h+var_48], rbp
0x18000e001  mov     r9d, [rbx]
0x18000e004  movzx   r8d, word ptr [rdi]
0x18000e008  mov     rcx, rsi
0x18000e00b  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$02$1?s_allowDisplayKeysWithPen_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$02$1?s_allowDisplayKeysWithPen_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,3,&bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_allowDisplayKeysWithPen_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>>>(bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,3,&bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_allowDisplayKeysWithPen_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>> const &)
0x18000e010  mov     r8, rdi
0x18000e013  mov     rdx, rbx
0x18000e016  mov     rcx, [rsi]; this
0x18000e019  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000e01e  cmp     r15w, [rdi]
0x18000e022  jb      short loc_18000E029
0x18000e024  cmp     dword ptr [rbx], 1
0x18000e027  ja      short loc_18000DFAE
0x18000e029  mov     [rsp+68h+arg_20], rbp
0x18000e031  mov     r9, rbx
0x18000e034  mov     r8, rdi
0x18000e037  mov     rcx, rsi
0x18000e03a  add     rsp, 40h
0x18000e03e  pop     r15
0x18000e040  pop     rdi
0x18000e041  pop     rsi
0x18000e042  pop     rbp
0x18000e043  pop     rbx
0x18000e044  jmp     ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$03$1?s_eraseEnabled_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$03$1?s_eraseEnabled_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata>,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>> const &)
0x18000e049  mov     edx, 1; unsigned int
0x18000e04e  mov     rcx, r8; this
0x18000e051  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
```
