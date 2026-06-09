# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<8,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,bool,14,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_allowFeedbackEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,ushort,16,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<8,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,bool,14,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_allowFeedbackEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,ushort,16,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>> const &)

- ea: `0x18000e134`
- end: `0x18000e1ff`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$07Uoptional_field_modifier@reflection@bond@@UTouchpadSettings@Devices@Input@Data@Windows@@_N$0O@$1?s_allowFeedbackEnabled_metadata@Schema@TouchpadSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$08Uoptional_field_modifier@reflection@bond@@UTouchpadSettings@Devices@Input@Data@Windows@@G$0BA@$1?s_feedbackIntensity_metadata@Schema@TouchpadSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$07Uoptional_field_modifier@reflection@bond@@UTouchpadSettings@Devices@Input@Data@Windows@@_N$0O@$1?s_allowFeedbackEnabled_metadata@Schema@TouchpadSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$08Uoptional_field_modifier@reflection@bond@@UTouchpadSettings@Devices@Input@Data@Windows@@G$0BA@$1?s_feedbackIntensity_metadata@Schema@TouchpadSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `203`
- prototype: `__int64 __fastcall(bond::InputBuffer **, __int64, _WORD *, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e7fc`

## callees

- `0x18000dc54`
- `0x18000e134`
- `0x18001187c`
- `0x18001b528`
- `0x18001f55c`
- `0x18002099c`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<8,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,bool,14,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_allowFeedbackEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,unsigned short,16,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>>(
        bond::InputBuffer **a1,
        __int64 a2,
        _WORD *a3,
        unsigned int *a4,
        __int64 a5)
{
  bond::InputBuffer *v8; // r8
  bond::InputBuffer *v10; // [rsp+30h] [rbp-38h] BYREF
  char v11; // [rsp+38h] [rbp-30h]

  do
  {
    if ( *a3 == 8 )
    {
      if ( *a4 == 2 )
      {
        v8 = *a1;
        v10 = v8;
        v11 = 0;
        if ( *((_DWORD *)v8 + 6) == *((_DWORD *)v8 + 8) )
          bond::InputBuffer::EofException(v8, 1u);
        *(_BYTE *)(*(_QWORD *)(a5 + 8) + 14LL) = *(_BYTE *)((unsigned int)(*((_DWORD *)v8 + 8))++ + *((_QWORD *)v8 + 2));
        bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v10);
        goto LABEL_8;
      }
    }
    else if ( *a3 > 8u )
    {
      return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,unsigned short,16,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>>(
               a1,
               a2,
               a3,
               a4,
               a5);
    }
    if ( *a4 <= 1 )
      return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,unsigned short,16,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>>(
               a1,
               a2,
               a3,
               a4,
               a5);
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<8,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,bool,14,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_allowFeedbackEnabled_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>>(
      a1,
      a2,
      (unsigned __int16)*a3,
      *a4,
      a5);
LABEL_8:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  while ( *a3 <= 8u && *a4 > 1 );
  return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,unsigned short,16,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>>(
           a1,
           a2,
           a3,
           a4,
           a5);
}

```

## disassembly

```asm
0x18000e134  push    rbx
0x18000e136  push    rbp
0x18000e137  push    rsi
0x18000e138  push    rdi
0x18000e139  push    r15
0x18000e13b  sub     rsp, 40h
0x18000e13f  mov     rbx, r9
0x18000e142  mov     rdi, r8
0x18000e145  mov     rsi, rcx
0x18000e148  mov     r15d, 8
0x18000e14e  mov     rbp, [rsp+68h+arg_20]
0x18000e156  cmp     r15w, [rdi]
0x18000e15a  jnz     short loc_18000E19D
0x18000e15c  cmp     dword ptr [rbx], 2
0x18000e15f  jnz     short loc_18000E19F
0x18000e161  mov     r8, [rsi]
0x18000e164  mov     [rsp+68h+var_38], r8
0x18000e169  mov     [rsp+68h+var_30], 0
0x18000e16e  mov     eax, [r8+18h]
0x18000e172  sub     eax, [r8+20h]
0x18000e176  cmp     eax, 1
0x18000e179  jb      short loc_18000E1F1
0x18000e17b  mov     edx, [r8+20h]
0x18000e17f  mov     rax, [r8+10h]
0x18000e183  mov     rcx, [rbp+8]
0x18000e187  mov     al, [rdx+rax]
0x18000e18a  mov     [rcx+0Eh], al
0x18000e18d  inc     dword ptr [r8+20h]
0x18000e191  lea     rcx, [rsp+68h+var_38]
0x18000e196  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000e19b  jmp     short loc_18000E1B8
0x18000e19d  jb      short loc_18000E1D1
0x18000e19f  cmp     dword ptr [rbx], 1
0x18000e1a2  jbe     short loc_18000E1D1
0x18000e1a4  mov     [rsp+68h+var_48], rbp
0x18000e1a9  mov     r9d, [rbx]
0x18000e1ac  movzx   r8d, word ptr [rdi]
0x18000e1b0  mov     rcx, rsi
0x18000e1b3  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$07Uoptional_field_modifier@reflection@bond@@UTouchpadSettings@Devices@Input@Data@Windows@@_N$0O@$1?s_allowFeedbackEnabled_metadata@Schema@TouchpadSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$07Uoptional_field_modifier@reflection@bond@@UTouchpadSettings@Devices@Input@Data@Windows@@_N$0O@$1?s_allowFeedbackEnabled_metadata@Schema@TouchpadSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<8,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,bool,14,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_allowFeedbackEnabled_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>>(bond::reflection::FieldTemplate<8,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,bool,14,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_allowFeedbackEnabled_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>> const &)
0x18000e1b8  mov     r8, rdi
0x18000e1bb  mov     rdx, rbx
0x18000e1be  mov     rcx, [rsi]; this
0x18000e1c1  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000e1c6  cmp     r15w, [rdi]
0x18000e1ca  jb      short loc_18000E1D1
0x18000e1cc  cmp     dword ptr [rbx], 1
0x18000e1cf  ja      short loc_18000E156
0x18000e1d1  mov     [rsp+68h+arg_20], rbp
0x18000e1d9  mov     r9, rbx
0x18000e1dc  mov     r8, rdi
0x18000e1df  mov     rcx, rsi
0x18000e1e2  add     rsp, 40h
0x18000e1e6  pop     r15
0x18000e1e8  pop     rdi
0x18000e1e9  pop     rsi
0x18000e1ea  pop     rbp
0x18000e1eb  pop     rbx
0x18000e1ec  jmp     ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$08Uoptional_field_modifier@reflection@bond@@UTouchpadSettings@Devices@Input@Data@Windows@@G$0BA@$1?s_feedbackIntensity_metadata@Schema@TouchpadSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$08Uoptional_field_modifier@reflection@bond@@UTouchpadSettings@Devices@Input@Data@Windows@@G$0BA@$1?s_feedbackIntensity_metadata@Schema@TouchpadSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,ushort,16,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<9,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSettings,ushort,16,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>> const &)
0x18000e1f1  mov     edx, 1; unsigned int
0x18000e1f6  mov     rcx, r8; this
0x18000e1f9  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
```
