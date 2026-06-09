# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,22,&bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_keyboardDockedBottom_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,22,&bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_keyboardDockedBottom_metadata>,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>> const &)

- ea: `0x18000dd18`
- end: `0x18000ddf7`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$09Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BG@$1?s_keyboardDockedBottom_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$09Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BG@$1?s_keyboardDockedBottom_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `223`
- prototype: `__int64 __fastcall(bond::InputBuffer **, __int64, _WORD *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e208`

## callees

- `0x18000dd18`
- `0x18001196c`
- `0x18001b528`
- `0x18001f55c`
- `0x18002099c`
- `0x180022000`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,22,&private: static bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_keyboardDockedBottom_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>>(
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
    if ( *a3 == 10 )
    {
      if ( *a4 == 2 )
      {
        v8 = *a1;
        v10 = v8;
        v11 = 0;
        if ( *((_DWORD *)v8 + 6) == *((_DWORD *)v8 + 8) )
          bond::InputBuffer::EofException(v8, 1u);
        *(_BYTE *)(*(_QWORD *)(a5 + 8) + 22LL) = *(_BYTE *)((unsigned int)(*((_DWORD *)v8 + 8))++ + *((_QWORD *)v8 + 2));
        bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v10);
        goto LABEL_8;
      }
    }
    else if ( *a3 > 0xAu )
    {
      break;
    }
    if ( *a4 <= 1u )
      break;
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,22,&private: static bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_keyboardDockedBottom_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>>(
      a1,
      a2,
      (unsigned __int16)*a3,
      (unsigned int)*a4,
      a5);
LABEL_8:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  while ( *a3 <= 0xAu && *a4 > 1u );
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
0x18000dd18  push    rbx
0x18000dd1a  push    rbp
0x18000dd1b  push    rsi
0x18000dd1c  push    rdi
0x18000dd1d  push    r15
0x18000dd1f  sub     rsp, 40h
0x18000dd23  mov     rbx, r9
0x18000dd26  mov     rsi, r8
0x18000dd29  mov     rdi, rcx
0x18000dd2c  mov     r15d, 0Ah
0x18000dd32  mov     rbp, [rsp+68h+arg_20]
0x18000dd3a  cmp     r15w, [rsi]
0x18000dd3e  jnz     short loc_18000DD85
0x18000dd40  cmp     dword ptr [rbx], 2
0x18000dd43  jnz     short loc_18000DD87
0x18000dd45  mov     r8, [rdi]
0x18000dd48  mov     [rsp+68h+var_38], r8
0x18000dd4d  mov     [rsp+68h+var_30], 0
0x18000dd52  mov     eax, [r8+18h]
0x18000dd56  sub     eax, [r8+20h]
0x18000dd5a  cmp     eax, 1
0x18000dd5d  jb      loc_18000DDE9
0x18000dd63  mov     edx, [r8+20h]
0x18000dd67  mov     rax, [r8+10h]
0x18000dd6b  mov     rcx, [rbp+8]
0x18000dd6f  mov     al, [rdx+rax]
0x18000dd72  mov     [rcx+16h], al
0x18000dd75  inc     dword ptr [r8+20h]
0x18000dd79  lea     rcx, [rsp+68h+var_38]
0x18000dd7e  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000dd83  jmp     short loc_18000DDA0
0x18000dd85  jb      short loc_18000DDD8
0x18000dd87  cmp     dword ptr [rbx], 1
0x18000dd8a  jbe     short loc_18000DDD8
0x18000dd8c  mov     [rsp+68h+var_48], rbp
0x18000dd91  mov     r9d, [rbx]
0x18000dd94  movzx   r8d, word ptr [rsi]
0x18000dd98  mov     rcx, rdi
0x18000dd9b  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$09Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BG@$1?s_keyboardDockedBottom_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$09Uoptional_field_modifier@reflection@bond@@USyncedSettings@EyeControl@Accessibility@Data@Windows@@_N$0BG@$1?s_keyboardDockedBottom_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,22,&bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_keyboardDockedBottom_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>>(bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Accessibility::EyeControl::SyncedSettings,bool,22,&bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_keyboardDockedBottom_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>> const &)
0x18000dda0  mov     r8, rsi
0x18000dda3  mov     rdx, rbx
0x18000dda6  mov     rcx, [rdi]; this
0x18000dda9  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000ddae  cmp     r15w, [rsi]
0x18000ddb2  jb      short loc_18000DDD8
0x18000ddb4  cmp     dword ptr [rbx], 1
0x18000ddb7  ja      short loc_18000DD3A
0x18000ddb9  jmp     short loc_18000DDD8
0x18000ddbb  cmp     eax, 1
0x18000ddbe  jz      short loc_18000DDDE
0x18000ddc0  mov     edx, eax
0x18000ddc2  mov     rcx, [rdi]; this
0x18000ddc5  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x18000ddca  mov     r8, rsi
0x18000ddcd  mov     rdx, rbx
0x18000ddd0  mov     rcx, [rdi]; this
0x18000ddd3  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000ddd8  mov     eax, [rbx]
0x18000ddda  test    eax, eax
0x18000dddc  jnz     short loc_18000DDBB
0x18000ddde  add     rsp, 40h
0x18000dde2  pop     r15
0x18000dde4  pop     rdi
0x18000dde5  pop     rsi
0x18000dde6  pop     rbp
0x18000dde7  pop     rbx
0x18000dde8  retn
0x18000dde9  mov     edx, 1; unsigned int
0x18000ddee  mov     rcx, r8; this
0x18000ddf1  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
```
