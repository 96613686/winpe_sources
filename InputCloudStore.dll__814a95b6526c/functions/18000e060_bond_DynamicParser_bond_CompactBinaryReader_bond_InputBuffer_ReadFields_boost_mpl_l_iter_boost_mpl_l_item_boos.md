# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<5,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,bool,5,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_interactionFeedbackEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,ushort,6,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<5,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,bool,5,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_interactionFeedbackEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,ushort,6,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>> const &)

- ea: `0x18000e060`
- end: `0x18000e12b`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$04Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$04$1?s_interactionFeedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$05Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@G$05$1?s_feedbackIntensity_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$04Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$04$1?s_interactionFeedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$05Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@G$05$1?s_feedbackIntensity_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `203`
- prototype: `__int64 __fastcall(bond::InputBuffer **, int, _WORD *, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e728`

## callees

- `0x18000db90`
- `0x18000e060`
- `0x1800115ac`
- `0x18001b528`
- `0x18001f55c`
- `0x18002099c`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<5,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,bool,5,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_interactionFeedbackEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,unsigned short,6,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>>(
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
    if ( *a3 == 5 )
    {
      if ( *a4 == 2 )
      {
        v8 = *a1;
        v10 = v8;
        v11 = 0;
        if ( *((_DWORD *)v8 + 6) == *((_DWORD *)v8 + 8) )
          bond::InputBuffer::EofException(v8, 1u);
        *(_BYTE *)(*(_QWORD *)(a5 + 8) + 5LL) = *(_BYTE *)((unsigned int)(*((_DWORD *)v8 + 8))++ + *((_QWORD *)v8 + 2));
        bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v10);
        goto LABEL_8;
      }
    }
    else if ( *a3 > 5u )
    {
      return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,unsigned short,6,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>>(
               a1,
               a2,
               a3,
               a4,
               a5);
    }
    if ( *a4 <= 1 )
      return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,unsigned short,6,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>>(
               a1,
               a2,
               a3,
               a4,
               a5);
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<5,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,bool,5,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_interactionFeedbackEnabled_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>>(
      (_DWORD)a1,
      a2,
      (unsigned __int16)*a3,
      *a4,
      a5);
LABEL_8:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  while ( *a3 <= 5u && *a4 > 1 );
  return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,unsigned short,6,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>>(
           a1,
           a2,
           a3,
           a4,
           a5);
}

```

## disassembly

```asm
0x18000e060  push    rbx
0x18000e062  push    rbp
0x18000e063  push    rsi
0x18000e064  push    rdi
0x18000e065  push    r15
0x18000e067  sub     rsp, 40h
0x18000e06b  mov     rbx, r9
0x18000e06e  mov     rdi, r8
0x18000e071  mov     rsi, rcx
0x18000e074  mov     r15d, 5
0x18000e07a  mov     rbp, [rsp+68h+arg_20]
0x18000e082  cmp     r15w, [rdi]
0x18000e086  jnz     short loc_18000E0C9
0x18000e088  cmp     dword ptr [rbx], 2
0x18000e08b  jnz     short loc_18000E0CB
0x18000e08d  mov     r8, [rsi]
0x18000e090  mov     [rsp+68h+var_38], r8
0x18000e095  mov     [rsp+68h+var_30], 0
0x18000e09a  mov     eax, [r8+18h]
0x18000e09e  sub     eax, [r8+20h]
0x18000e0a2  cmp     eax, 1
0x18000e0a5  jb      short loc_18000E11D
0x18000e0a7  mov     edx, [r8+20h]
0x18000e0ab  mov     rax, [r8+10h]
0x18000e0af  mov     rcx, [rbp+8]
0x18000e0b3  mov     al, [rdx+rax]
0x18000e0b6  mov     [rcx+5], al
0x18000e0b9  inc     dword ptr [r8+20h]
0x18000e0bd  lea     rcx, [rsp+68h+var_38]
0x18000e0c2  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000e0c7  jmp     short loc_18000E0E4
0x18000e0c9  jb      short loc_18000E0FD
0x18000e0cb  cmp     dword ptr [rbx], 1
0x18000e0ce  jbe     short loc_18000E0FD
0x18000e0d0  mov     [rsp+68h+var_48], rbp
0x18000e0d5  mov     r9d, [rbx]
0x18000e0d8  movzx   r8d, word ptr [rdi]
0x18000e0dc  mov     rcx, rsi
0x18000e0df  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$04Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$04$1?s_interactionFeedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$04Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$04$1?s_interactionFeedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<5,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,bool,5,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_interactionFeedbackEnabled_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>>(bond::reflection::FieldTemplate<5,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,bool,5,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_interactionFeedbackEnabled_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>> const &)
0x18000e0e4  mov     r8, rdi
0x18000e0e7  mov     rdx, rbx
0x18000e0ea  mov     rcx, [rsi]; this
0x18000e0ed  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000e0f2  cmp     r15w, [rdi]
0x18000e0f6  jb      short loc_18000E0FD
0x18000e0f8  cmp     dword ptr [rbx], 1
0x18000e0fb  ja      short loc_18000E082
0x18000e0fd  mov     [rsp+68h+arg_20], rbp
0x18000e105  mov     r9, rbx
0x18000e108  mov     r8, rdi
0x18000e10b  mov     rcx, rsi
0x18000e10e  add     rsp, 40h
0x18000e112  pop     r15
0x18000e114  pop     rdi
0x18000e115  pop     rsi
0x18000e116  pop     rbp
0x18000e117  pop     rbx
0x18000e118  jmp     ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$05Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@G$05$1?s_feedbackIntensity_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$05Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@G$05$1?s_feedbackIntensity_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,ushort,6,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,ushort,6,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>> const &)
0x18000e11d  mov     edx, 1; unsigned int
0x18000e122  mov     rcx, r8; this
0x18000e125  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
```
