# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata>,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>> const &)

- ea: `0x18000daa8`
- end: `0x18000db87`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$03$1?s_eraseEnabled_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$03$1?s_eraseEnabled_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `223`
- prototype: `__int64 __fastcall(bond::InputBuffer **, int, _WORD *, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000df8c`

## callees

- `0x18000daa8`
- `0x1800114bc`
- `0x18001b528`
- `0x18001f55c`
- `0x18002099c`
- `0x180022000`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>>>(
        bond::InputBuffer **a1,
        int a2,
        _WORD *a3,
        unsigned int *a4,
        __int64 a5)
{
  bond::InputBuffer *v8; // r8
  __int64 result; // rax
  bond::InputBuffer *v10; // [rsp+30h] [rbp-38h] BYREF
  char v11; // [rsp+38h] [rbp-30h]

  do
  {
    if ( *a3 == 4 )
    {
      if ( *a4 == 2 )
      {
        v8 = *a1;
        v10 = v8;
        v11 = 0;
        if ( *((_DWORD *)v8 + 6) == *((_DWORD *)v8 + 8) )
          bond::InputBuffer::EofException(v8, 1u);
        *(_BYTE *)(*(_QWORD *)(a5 + 8) + 4LL) = *(_BYTE *)((unsigned int)(*((_DWORD *)v8 + 8))++ + *((_QWORD *)v8 + 2));
        bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v10);
        goto LABEL_8;
      }
    }
    else if ( *a3 > 4u )
    {
      break;
    }
    if ( *a4 <= 1 )
      break;
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>>>(
      (_DWORD)a1,
      a2,
      (unsigned __int16)*a3,
      *a4,
      a5);
LABEL_8:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  while ( *a3 <= 4u && *a4 > 1 );
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
0x18000daa8  push    rbx
0x18000daaa  push    rbp
0x18000daab  push    rsi
0x18000daac  push    rdi
0x18000daad  push    r15
0x18000daaf  sub     rsp, 40h
0x18000dab3  mov     rbx, r9
0x18000dab6  mov     rsi, r8
0x18000dab9  mov     rdi, rcx
0x18000dabc  mov     r15d, 4
0x18000dac2  mov     rbp, [rsp+68h+arg_20]
0x18000daca  cmp     r15w, [rsi]
0x18000dace  jnz     short loc_18000DB15
0x18000dad0  cmp     dword ptr [rbx], 2
0x18000dad3  jnz     short loc_18000DB17
0x18000dad5  mov     r8, [rdi]
0x18000dad8  mov     [rsp+68h+var_38], r8
0x18000dadd  mov     [rsp+68h+var_30], 0
0x18000dae2  mov     eax, [r8+18h]
0x18000dae6  sub     eax, [r8+20h]
0x18000daea  cmp     eax, 1
0x18000daed  jb      loc_18000DB79
0x18000daf3  mov     edx, [r8+20h]
0x18000daf7  mov     rax, [r8+10h]
0x18000dafb  mov     rcx, [rbp+8]
0x18000daff  mov     al, [rdx+rax]
0x18000db02  mov     [rcx+4], al
0x18000db05  inc     dword ptr [r8+20h]
0x18000db09  lea     rcx, [rsp+68h+var_38]
0x18000db0e  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000db13  jmp     short loc_18000DB30
0x18000db15  jb      short loc_18000DB68
0x18000db17  cmp     dword ptr [rbx], 1
0x18000db1a  jbe     short loc_18000DB68
0x18000db1c  mov     [rsp+68h+var_48], rbp
0x18000db21  mov     r9d, [rbx]
0x18000db24  movzx   r8d, word ptr [rsi]
0x18000db28  mov     rcx, rdi
0x18000db2b  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$03$1?s_eraseEnabled_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$03$1?s_eraseEnabled_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>>>(bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>> const &)
0x18000db30  mov     r8, rsi
0x18000db33  mov     rdx, rbx
0x18000db36  mov     rcx, [rdi]; this
0x18000db39  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000db3e  cmp     r15w, [rsi]
0x18000db42  jb      short loc_18000DB68
0x18000db44  cmp     dword ptr [rbx], 1
0x18000db47  ja      short loc_18000DACA
0x18000db49  jmp     short loc_18000DB68
0x18000db4b  cmp     eax, 1
0x18000db4e  jz      short loc_18000DB6E
0x18000db50  mov     edx, eax
0x18000db52  mov     rcx, [rdi]; this
0x18000db55  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x18000db5a  mov     r8, rsi
0x18000db5d  mov     rdx, rbx
0x18000db60  mov     rcx, [rdi]; this
0x18000db63  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000db68  mov     eax, [rbx]
0x18000db6a  test    eax, eax
0x18000db6c  jnz     short loc_18000DB4B
0x18000db6e  add     rsp, 40h
0x18000db72  pop     r15
0x18000db74  pop     rdi
0x18000db75  pop     rsi
0x18000db76  pop     rbp
0x18000db77  pop     rbx
0x18000db78  retn
0x18000db79  mov     edx, 1; unsigned int
0x18000db7e  mov     rcx, r8; this
0x18000db81  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
```
