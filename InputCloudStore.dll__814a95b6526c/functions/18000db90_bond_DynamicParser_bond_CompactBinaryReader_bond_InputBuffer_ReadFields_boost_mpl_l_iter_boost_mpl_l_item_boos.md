# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,ushort,6,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,ushort,6,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>> const &)

- ea: `0x18000db90`
- end: `0x18000dc4c`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$05Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@G$05$1?s_feedbackIntensity_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$05Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@G$05$1?s_feedbackIntensity_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `188`
- prototype: `__int64 __fastcall(bond::InputBuffer **, int, _WORD *, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e060`

## callees

- `0x18000db90`
- `0x18000f934`
- `0x18001169c`
- `0x18001b488`
- `0x18002099c`
- `0x180022000`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,unsigned short,6,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>>(
        bond::InputBuffer **a1,
        int a2,
        _WORD *a3,
        unsigned int *a4,
        __int64 a5)
{
  __int64 result; // rax
  bond::InputBuffer *v9; // [rsp+30h] [rbp-38h] BYREF
  char v10; // [rsp+38h] [rbp-30h]

  do
  {
    if ( *a3 == 6 )
    {
      if ( *a4 == 4 )
      {
        v9 = *a1;
        v10 = 0;
        bond::InputBuffer::ReadVariableUnsigned<unsigned short>(v9, *(_QWORD *)(a5 + 8) + 6LL);
        bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v9);
        goto LABEL_7;
      }
    }
    else if ( *a3 > 6u )
    {
      break;
    }
    if ( *a4 <= 1 )
      break;
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,unsigned short,6,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>>(
      (_DWORD)a1,
      a2,
      (unsigned __int16)*a3,
      *a4,
      a5);
LABEL_7:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  while ( *a3 <= 6u && *a4 > 1 );
  while ( 1 )
  {
    result = *a4;
    if ( (unsigned int)result <= 1 )
      break;
    bond::CompactBinaryReader<bond::InputBuffer>::Skip(*a1);
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  return result;
}

```

## disassembly

```asm
0x18000db90  push    rbx
0x18000db92  push    rbp
0x18000db93  push    rsi
0x18000db94  push    rdi
0x18000db95  push    r14
0x18000db97  sub     rsp, 40h
0x18000db9b  mov     rbx, r9
0x18000db9e  mov     rsi, r8
0x18000dba1  mov     rdi, rcx
0x18000dba4  mov     r14d, 6
0x18000dbaa  mov     rbp, [rsp+68h+arg_20]
0x18000dbb2  cmp     r14w, [rsi]
0x18000dbb6  jnz     short loc_18000DBE3
0x18000dbb8  cmp     dword ptr [rbx], 4
0x18000dbbb  jnz     short loc_18000DBE5
0x18000dbbd  mov     rcx, [rdi]
0x18000dbc0  mov     [rsp+68h+var_38], rcx
0x18000dbc5  mov     [rsp+68h+var_30], 0
0x18000dbca  mov     rdx, [rbp+8]
0x18000dbce  add     rdx, r14
0x18000dbd1  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x18000dbd6  nop
0x18000dbd7  lea     rcx, [rsp+68h+var_38]
0x18000dbdc  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000dbe1  jmp     short loc_18000DBFE
0x18000dbe3  jb      short loc_18000DC3B
0x18000dbe5  cmp     dword ptr [rbx], 1
0x18000dbe8  jbe     short loc_18000DC3B
0x18000dbea  mov     [rsp+68h+var_48], rbp
0x18000dbef  mov     r9d, [rbx]
0x18000dbf2  movzx   r8d, word ptr [rsi]
0x18000dbf6  mov     rcx, rdi
0x18000dbf9  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$05Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@G$05$1?s_feedbackIntensity_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$05Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@G$05$1?s_feedbackIntensity_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,ushort,6,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>>(bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,ushort,6,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>> const &)
0x18000dbfe  mov     r8, rsi
0x18000dc01  mov     rdx, rbx
0x18000dc04  mov     rcx, [rdi]; this
0x18000dc07  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000dc0c  cmp     r14w, [rsi]
0x18000dc10  jb      short loc_18000DC3B
0x18000dc12  cmp     dword ptr [rbx], 0
0x18000dc15  jz      short loc_18000DC3B
0x18000dc17  cmp     dword ptr [rbx], 1
0x18000dc1a  jnz     short loc_18000DBB2
0x18000dc1c  jmp     short loc_18000DC3B
0x18000dc1e  cmp     eax, 1
0x18000dc21  jz      short loc_18000DC41
0x18000dc23  mov     edx, eax
0x18000dc25  mov     rcx, [rdi]; this
0x18000dc28  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x18000dc2d  mov     r8, rsi
0x18000dc30  mov     rdx, rbx
0x18000dc33  mov     rcx, [rdi]; this
0x18000dc36  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000dc3b  mov     eax, [rbx]
0x18000dc3d  test    eax, eax
0x18000dc3f  jnz     short loc_18000DC1E
0x18000dc41  add     rsp, 40h
0x18000dc45  pop     r14
0x18000dc47  pop     rdi
0x18000dc48  pop     rsi
0x18000dc49  pop     rbp
0x18000dc4a  pop     rbx
0x18000dc4b  retn
```
