# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,ushort,16,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,ushort,16,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>> const &)

- ea: `0x18000dc54`
- end: `0x18000dd11`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$08Uoptional_field_modifier@reflection@bond@@UTouchpadSettings@Devices@Input@Data@Windows@@G$0BA@$1?s_feedbackIntensity_metadata@Schema@TouchpadSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$08Uoptional_field_modifier@reflection@bond@@UTouchpadSettings@Devices@Input@Data@Windows@@G$0BA@$1?s_feedbackIntensity_metadata@Schema@TouchpadSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `189`
- prototype: `__int64 __fastcall(bond::InputBuffer **, __int64, _WORD *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e134`

## callees

- `0x18000dc54`
- `0x18000f934`
- `0x18001191c`
- `0x18001b488`
- `0x18002099c`
- `0x180022000`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,unsigned short,16,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>>(
        bond::InputBuffer **a1,
        __int64 a2,
        _WORD *a3,
        _DWORD *a4,
        __int64 a5)
{
  __int64 result; // rax
  bond::InputBuffer *v9; // [rsp+30h] [rbp-38h] BYREF
  char v10; // [rsp+38h] [rbp-30h]

  do
  {
    if ( *a3 == 9 )
    {
      if ( *a4 == 4 )
      {
        v9 = *a1;
        v10 = 0;
        bond::InputBuffer::ReadVariableUnsigned<unsigned short>(v9, *(_QWORD *)(a5 + 8) + 16LL);
        bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v9);
        goto LABEL_7;
      }
    }
    else if ( *a3 > 9u )
    {
      break;
    }
    if ( *a4 <= 1u )
      break;
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,unsigned short,16,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_feedbackIntensity_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>>(
      a1,
      a2,
      (unsigned __int16)*a3,
      (unsigned int)*a4,
      a5);
LABEL_7:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  while ( *a3 <= 9u && *a4 > 1u );
  while ( 1 )
  {
    result = (unsigned int)*a4;
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
0x18000dc54  push    rbx
0x18000dc56  push    rbp
0x18000dc57  push    rsi
0x18000dc58  push    rdi
0x18000dc59  push    r14
0x18000dc5b  sub     rsp, 40h
0x18000dc5f  mov     rbx, r9
0x18000dc62  mov     rsi, r8
0x18000dc65  mov     rdi, rcx
0x18000dc68  mov     r14d, 9
0x18000dc6e  mov     rbp, [rsp+68h+arg_20]
0x18000dc76  cmp     r14w, [rsi]
0x18000dc7a  jnz     short loc_18000DCA8
0x18000dc7c  cmp     dword ptr [rbx], 4
0x18000dc7f  jnz     short loc_18000DCAA
0x18000dc81  mov     rcx, [rdi]
0x18000dc84  mov     [rsp+68h+var_38], rcx
0x18000dc89  mov     [rsp+68h+var_30], 0
0x18000dc8e  mov     rdx, [rbp+8]
0x18000dc92  add     rdx, 10h
0x18000dc96  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x18000dc9b  nop
0x18000dc9c  lea     rcx, [rsp+68h+var_38]
0x18000dca1  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000dca6  jmp     short loc_18000DCC3
0x18000dca8  jb      short loc_18000DD00
0x18000dcaa  cmp     dword ptr [rbx], 1
0x18000dcad  jbe     short loc_18000DD00
0x18000dcaf  mov     [rsp+68h+var_48], rbp
0x18000dcb4  mov     r9d, [rbx]
0x18000dcb7  movzx   r8d, word ptr [rsi]
0x18000dcbb  mov     rcx, rdi
0x18000dcbe  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$08Uoptional_field_modifier@reflection@bond@@UTouchpadSettings@Devices@Input@Data@Windows@@G$0BA@$1?s_feedbackIntensity_metadata@Schema@TouchpadSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$08Uoptional_field_modifier@reflection@bond@@UTouchpadSettings@Devices@Input@Data@Windows@@G$0BA@$1?s_feedbackIntensity_metadata@Schema@TouchpadSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,ushort,16,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_feedbackIntensity_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>>(bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,ushort,16,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_feedbackIntensity_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>> const &)
0x18000dcc3  mov     r8, rsi
0x18000dcc6  mov     rdx, rbx
0x18000dcc9  mov     rcx, [rdi]; this
0x18000dccc  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000dcd1  cmp     r14w, [rsi]
0x18000dcd5  jb      short loc_18000DD00
0x18000dcd7  cmp     dword ptr [rbx], 0
0x18000dcda  jz      short loc_18000DD00
0x18000dcdc  cmp     dword ptr [rbx], 1
0x18000dcdf  jnz     short loc_18000DC76
0x18000dce1  jmp     short loc_18000DD00
0x18000dce3  cmp     eax, 1
0x18000dce6  jz      short loc_18000DD06
0x18000dce8  mov     edx, eax
0x18000dcea  mov     rcx, [rdi]; this
0x18000dced  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x18000dcf2  mov     r8, rsi
0x18000dcf5  mov     rdx, rbx
0x18000dcf8  mov     rcx, [rdi]; this
0x18000dcfb  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000dd00  mov     eax, [rbx]
0x18000dd02  test    eax, eax
0x18000dd04  jnz     short loc_18000DCE3
0x18000dd06  add     rsp, 40h
0x18000dd0a  pop     r14
0x18000dd0c  pop     rdi
0x18000dd0d  pop     rsi
0x18000dd0e  pop     rbp
0x18000dd0f  pop     rbx
0x18000dd10  retn
```
