# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<40,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,3,&bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarFlashesEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<50,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,4,&bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isMuteNotificationsEnabled_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<40,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,3,&bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarFlashesEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<50,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,4,&bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isMuteNotificationsEnabled_metadata>,boost::mpl::l_end>>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>> const &)

- ea: `0x18000fca4`
- end: `0x18000fd6f`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0CI@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$02$1?s_isHideTaskbarFlashesEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0DC@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$03$1?s_isMuteNotificationsEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0CI@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$02$1?s_isHideTaskbarFlashesEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0DC@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$03$1?s_isMuteNotificationsEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fd78`

## callees

- `0x18000fbc0`
- `0x18000fca4`
- `0x180010778`
- `0x18001363c`
- `0x180014278`
- `0x1800155b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<40,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,3,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarFlashesEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<50,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,4,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isMuteNotificationsEnabled_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>>>(
        bond::InputBuffer **a1,
        int a2,
        unsigned __int8 *a3,
        int *a4,
        __int64 a5)
{
  bond::InputBuffer *v8; // r8
  bond::InputBuffer *v10; // [rsp+30h] [rbp-38h] BYREF
  char v11; // [rsp+38h] [rbp-30h]

  do
  {
    if ( *(_WORD *)a3 == 40 )
    {
      if ( *a4 == 2 )
      {
        v8 = *a1;
        v10 = v8;
        v11 = 0;
        if ( *((_DWORD *)v8 + 6) == *((_DWORD *)v8 + 8) )
          bond::InputBuffer::EofException(v8, 1u);
        *(_BYTE *)(*(_QWORD *)(a5 + 8) + 3LL) = *(_BYTE *)((unsigned int)(*((_DWORD *)v8 + 8))++ + *((_QWORD *)v8 + 2));
        bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>((__int64)&v10);
        goto LABEL_8;
      }
    }
    else if ( *(_WORD *)a3 > 0x28u )
    {
      return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<50,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,4,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isMuteNotificationsEnabled_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>>>(
               a1,
               a2,
               a3,
               a4,
               a5);
    }
    if ( (unsigned int)*a4 <= 1 )
      return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<50,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,4,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isMuteNotificationsEnabled_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>>>(
               a1,
               a2,
               a3,
               a4,
               a5);
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<40,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,3,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarFlashesEnabled_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>>>(
      (_DWORD)a1,
      a2,
      *(unsigned __int16 *)a3,
      *a4,
      a5);
LABEL_8:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1, a4, a3);
  }
  while ( *(_WORD *)a3 <= 0x28u && (unsigned int)*a4 > 1 );
  return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<50,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,4,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isMuteNotificationsEnabled_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>>>(
           a1,
           a2,
           a3,
           a4,
           a5);
}

```

## disassembly

```asm
0x18000fca4  push    rbx
0x18000fca6  push    rbp
0x18000fca7  push    rsi
0x18000fca8  push    rdi
0x18000fca9  push    r15
0x18000fcab  sub     rsp, 40h
0x18000fcaf  mov     rbx, r9
0x18000fcb2  mov     rdi, r8
0x18000fcb5  mov     rsi, rcx
0x18000fcb8  mov     r15d, 28h ; '('
0x18000fcbe  mov     rbp, [rsp+68h+arg_20]
0x18000fcc6  cmp     r15w, [rdi]
0x18000fcca  jnz     short loc_18000FD0D
0x18000fccc  cmp     dword ptr [rbx], 2
0x18000fccf  jnz     short loc_18000FD0F
0x18000fcd1  mov     r8, [rsi]
0x18000fcd4  mov     [rsp+68h+var_38], r8
0x18000fcd9  mov     [rsp+68h+var_30], 0
0x18000fcde  mov     eax, [r8+18h]
0x18000fce2  sub     eax, [r8+20h]
0x18000fce6  cmp     eax, 1
0x18000fce9  jb      short loc_18000FD61
0x18000fceb  mov     edx, [r8+20h]
0x18000fcef  mov     rax, [r8+10h]
0x18000fcf3  mov     rcx, [rbp+8]
0x18000fcf7  mov     al, [rdx+rax]
0x18000fcfa  mov     [rcx+3], al
0x18000fcfd  inc     dword ptr [r8+20h]
0x18000fd01  lea     rcx, [rsp+68h+var_38]
0x18000fd06  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000fd0b  jmp     short loc_18000FD28
0x18000fd0d  jb      short loc_18000FD41
0x18000fd0f  cmp     dword ptr [rbx], 1
0x18000fd12  jbe     short loc_18000FD41
0x18000fd14  mov     [rsp+68h+var_48], rbp
0x18000fd19  mov     r9d, [rbx]
0x18000fd1c  movzx   r8d, word ptr [rdi]
0x18000fd20  mov     rcx, rsi
0x18000fd23  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$0CI@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$02$1?s_isHideTaskbarFlashesEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$0CI@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$02$1?s_isHideTaskbarFlashesEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<40,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,3,&bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarFlashesEnabled_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>>>(bond::reflection::FieldTemplate<40,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,3,&bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarFlashesEnabled_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>> const &)
0x18000fd28  mov     r8, rdi
0x18000fd2b  mov     rdx, rbx
0x18000fd2e  mov     rcx, [rsi]; this
0x18000fd31  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000fd36  cmp     r15w, [rdi]
0x18000fd3a  jb      short loc_18000FD41
0x18000fd3c  cmp     dword ptr [rbx], 1
0x18000fd3f  ja      short loc_18000FCC6
0x18000fd41  mov     [rsp+68h+arg_20], rbp
0x18000fd49  mov     r9, rbx
0x18000fd4c  mov     r8, rdi
0x18000fd4f  mov     rcx, rsi
0x18000fd52  add     rsp, 40h
0x18000fd56  pop     r15
0x18000fd58  pop     rdi
0x18000fd59  pop     rsi
0x18000fd5a  pop     rbp
0x18000fd5b  pop     rbx
0x18000fd5c  jmp     ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0DC@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$03$1?s_isMuteNotificationsEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0DC@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$03$1?s_isMuteNotificationsEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<50,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,4,&bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isMuteNotificationsEnabled_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<50,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,4,&bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isMuteNotificationsEnabled_metadata>,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>> const &)
0x18000fd61  mov     edx, 1; unsigned int
0x18000fd66  mov     rcx, r8; this
0x18000fd69  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
```
