# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,6,&bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,6,&bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata>,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>> const &)

- ea: `0x18000d9c4`
- end: `0x18000da9f`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@_N$05$1?s_allowScrollInactiveWindows_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@_N$05$1?s_allowScrollInactiveWindows_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `219`
- prototype: `__int64 __fastcall(bond::InputBuffer **, __int64, _WORD *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ded8`

## callees

- `0x18000d9c4`
- `0x1800112f0`
- `0x18001b528`
- `0x18001f55c`
- `0x18002099c`
- `0x180022000`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,6,&private: static bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>>(
        bond::InputBuffer **a1,
        __int64 a2,
        _WORD *a3,
        _DWORD *a4,
        __int64 a5)
{
  bond::InputBuffer *v8; // r8
  __int64 result; // rax
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
        *(_BYTE *)(*(_QWORD *)(a5 + 8) + 6LL) = *(_BYTE *)((unsigned int)(*((_DWORD *)v8 + 8))++ + *((_QWORD *)v8 + 2));
        bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v10);
        goto LABEL_8;
      }
    }
    else if ( *a3 > 3u )
    {
      break;
    }
    if ( *a4 <= 1u )
      break;
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,6,&private: static bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>>(
      a1,
      a2,
      (unsigned __int16)*a3,
      (unsigned int)*a4,
      a5);
LABEL_8:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  while ( *a3 <= 3u && *a4 > 1u );
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
0x18000d9c4  push    rbx
0x18000d9c6  push    rbp
0x18000d9c7  push    rsi
0x18000d9c8  push    rdi
0x18000d9c9  push    r15
0x18000d9cb  sub     rsp, 40h
0x18000d9cf  mov     rbx, r9
0x18000d9d2  mov     rsi, r8
0x18000d9d5  mov     rdi, rcx
0x18000d9d8  mov     r15d, 3
0x18000d9de  mov     rbp, [rsp+68h+arg_20]
0x18000d9e6  cmp     r15w, [rsi]
0x18000d9ea  jnz     short loc_18000DA2D
0x18000d9ec  cmp     dword ptr [rbx], 2
0x18000d9ef  jnz     short loc_18000DA2F
0x18000d9f1  mov     r8, [rdi]
0x18000d9f4  mov     [rsp+68h+var_38], r8
0x18000d9f9  mov     [rsp+68h+var_30], 0
0x18000d9fe  mov     eax, [r8+18h]
0x18000da02  sub     eax, [r8+20h]
0x18000da06  cmp     eax, 1
0x18000da09  jb      short loc_18000DA63
0x18000da0b  mov     edx, [r8+20h]
0x18000da0f  mov     rax, [r8+10h]
0x18000da13  mov     rcx, [rbp+8]
0x18000da17  mov     al, [rdx+rax]
0x18000da1a  mov     [rcx+6], al
0x18000da1d  inc     dword ptr [r8+20h]
0x18000da21  lea     rcx, [rsp+68h+var_38]
0x18000da26  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000da2b  jmp     short loc_18000DA48
0x18000da2d  jb      short loc_18000DA8E
0x18000da2f  cmp     dword ptr [rbx], 1
0x18000da32  jbe     short loc_18000DA8E
0x18000da34  mov     [rsp+68h+var_48], rbp
0x18000da39  mov     r9d, [rbx]
0x18000da3c  movzx   r8d, word ptr [rsi]
0x18000da40  mov     rcx, rdi
0x18000da43  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@_N$05$1?s_allowScrollInactiveWindows_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@_N$05$1?s_allowScrollInactiveWindows_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,6,&bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>>(bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,6,&bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>> const &)
0x18000da48  mov     r8, rsi
0x18000da4b  mov     rdx, rbx
0x18000da4e  mov     rcx, [rdi]; this
0x18000da51  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000da56  cmp     r15w, [rsi]
0x18000da5a  jb      short loc_18000DA8E
0x18000da5c  cmp     dword ptr [rbx], 1
0x18000da5f  ja      short loc_18000D9E6
0x18000da61  jmp     short loc_18000DA8E
0x18000da63  mov     edx, 1; unsigned int
0x18000da68  mov     rcx, r8; this
0x18000da6b  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x18000da71  cmp     eax, 1
0x18000da74  jz      short loc_18000DA94
0x18000da76  mov     edx, eax
0x18000da78  mov     rcx, [rdi]; this
0x18000da7b  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x18000da80  mov     r8, rsi
0x18000da83  mov     rdx, rbx
0x18000da86  mov     rcx, [rdi]; this
0x18000da89  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000da8e  mov     eax, [rbx]
0x18000da90  test    eax, eax
0x18000da92  jnz     short loc_18000DA71
0x18000da94  add     rsp, 40h
0x18000da98  pop     r15
0x18000da9a  pop     rdi
0x18000da9b  pop     rsi
0x18000da9c  pop     rbp
0x18000da9d  pop     rbx
0x18000da9e  retn
```
