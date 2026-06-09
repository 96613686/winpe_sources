# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSyncedSettings,bool,0,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSyncedSettings::Schema::s_scrollInverted_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSyncedSettings,bool,0,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSyncedSettings::Schema::s_scrollInverted_metadata>,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>>> const &)

- ea: `0x18000de00`
- end: `0x18000ded1`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_scrollInverted_metadata@Schema@TouchpadSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_scrollInverted_metadata@Schema@TouchpadSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `209`
- prototype: `__int64 __fastcall(bond::InputBuffer **, __int64, _WORD *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009d50`

## callees

- `0x18000de00`
- `0x180011a08`
- `0x18001b528`
- `0x18001f55c`
- `0x18002099c`
- `0x180022000`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSyncedSettings,bool,0,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchpadSyncedSettings::Schema::s_scrollInverted_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>>>>(
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
    if ( *a3 )
      break;
    if ( *a4 == 2 )
    {
      v8 = *a1;
      v10 = v8;
      v11 = 0;
      if ( *((_DWORD *)v8 + 6) == *((_DWORD *)v8 + 8) )
        bond::InputBuffer::EofException(v8, 1u);
      **(_BYTE **)(a5 + 8) = *(_BYTE *)((unsigned int)(*((_DWORD *)v8 + 8))++ + *((_QWORD *)v8 + 2));
      bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v10);
    }
    else
    {
      if ( *a4 <= 1u )
        break;
      bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSyncedSettings,bool,0,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchpadSyncedSettings::Schema::s_scrollInverted_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>>>>(
        a1,
        a2,
        (unsigned __int16)*a3,
        (unsigned int)*a4,
        a5);
    }
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
    if ( *a3 )
      break;
  }
  while ( *a4 > 1u );
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
0x18000de00  push    rbx
0x18000de02  push    rbp
0x18000de03  push    rsi
0x18000de04  push    rdi
0x18000de05  sub     rsp, 48h
0x18000de09  mov     rbx, r9
0x18000de0c  mov     rsi, r8
0x18000de0f  mov     rdi, rcx
0x18000de12  mov     rbp, [rsp+68h+arg_20]
0x18000de1a  xor     eax, eax
0x18000de1c  cmp     ax, [rsi]
0x18000de1f  jnz     short loc_18000DE60
0x18000de21  cmp     dword ptr [rbx], 2
0x18000de24  jnz     short loc_18000DE62
0x18000de26  mov     r8, [rdi]
0x18000de29  mov     [rsp+68h+var_38], r8
0x18000de2e  mov     [rsp+68h+var_30], al
0x18000de32  mov     eax, [r8+18h]
0x18000de36  sub     eax, [r8+20h]
0x18000de3a  cmp     eax, 1
0x18000de3d  jb      short loc_18000DE97
0x18000de3f  mov     edx, [r8+20h]
0x18000de43  mov     rax, [r8+10h]
0x18000de47  mov     rcx, [rbp+8]
0x18000de4b  mov     al, [rdx+rax]
0x18000de4e  mov     [rcx], al
0x18000de50  inc     dword ptr [r8+20h]
0x18000de54  lea     rcx, [rsp+68h+var_38]
0x18000de59  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000de5e  jmp     short loc_18000DE7B
0x18000de60  jb      short loc_18000DEC2
0x18000de62  cmp     dword ptr [rbx], 1
0x18000de65  jbe     short loc_18000DEC2
0x18000de67  mov     [rsp+68h+var_48], rbp
0x18000de6c  mov     r9d, [rbx]
0x18000de6f  movzx   r8d, word ptr [rsi]
0x18000de73  mov     rcx, rdi
0x18000de76  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_scrollInverted_metadata@Schema@TouchpadSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_scrollInverted_metadata@Schema@TouchpadSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSyncedSettings,bool,0,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSyncedSettings::Schema::s_scrollInverted_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>>>>(bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSyncedSettings,bool,0,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSyncedSettings::Schema::s_scrollInverted_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>>> const &)
0x18000de7b  mov     r8, rsi
0x18000de7e  mov     rdx, rbx
0x18000de81  mov     rcx, [rdi]; this
0x18000de84  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000de89  xor     eax, eax
0x18000de8b  cmp     ax, [rsi]
0x18000de8e  jb      short loc_18000DEC2
0x18000de90  cmp     dword ptr [rbx], 1
0x18000de93  ja      short loc_18000DE1A
0x18000de95  jmp     short loc_18000DEC2
0x18000de97  mov     edx, 1; unsigned int
0x18000de9c  mov     rcx, r8; this
0x18000de9f  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x18000dea5  cmp     eax, 1
0x18000dea8  jz      short loc_18000DEC8
0x18000deaa  mov     edx, eax
0x18000deac  mov     rcx, [rdi]; this
0x18000deaf  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x18000deb4  mov     r8, rsi
0x18000deb7  mov     rdx, rbx
0x18000deba  mov     rcx, [rdi]; this
0x18000debd  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000dec2  mov     eax, [rbx]
0x18000dec4  test    eax, eax
0x18000dec6  jnz     short loc_18000DEA5
0x18000dec8  add     rsp, 48h
0x18000decc  pop     rdi
0x18000decd  pop     rsi
0x18000dece  pop     rbp
0x18000decf  pop     rbx
0x18000ded0  retn
```
