# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,0,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchGestures_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,0,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchGestures_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata>,boost::mpl::l_end>>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>> const &)

- ea: `0x18000e2dc`
- end: `0x18000e39d`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_allowTouchGestures_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowTouchScreenWake_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_allowTouchGestures_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowTouchScreenWake_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `193`
- prototype: `__int64 __fastcall(bond::InputBuffer **, __int64, unsigned __int16 *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009e90`

## callees

- `0x18000d8e4`
- `0x18000e2dc`
- `0x180011b34`
- `0x18001b528`
- `0x18001f55c`
- `0x18002099c`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,0,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchGestures_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>>(
        bond::InputBuffer **a1,
        __int64 a2,
        unsigned __int16 *a3,
        _DWORD *a4,
        __int64 a5)
{
  bond::InputBuffer *v8; // r8
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
        return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>>(
                 a1,
                 a2,
                 a3,
                 a4,
                 a5);
      bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,0,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchGestures_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>>(
        a1,
        a2,
        *a3,
        (unsigned int)*a4,
        a5);
    }
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
    if ( *a3 )
      break;
  }
  while ( *a4 > 1u );
  return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>>(
           a1,
           a2,
           a3,
           a4,
           a5);
}

```

## disassembly

```asm
0x18000e2dc  push    rbx
0x18000e2de  push    rbp
0x18000e2df  push    rsi
0x18000e2e0  push    rdi
0x18000e2e1  sub     rsp, 48h
0x18000e2e5  mov     rbx, r9
0x18000e2e8  mov     rdi, r8
0x18000e2eb  mov     rsi, rcx
0x18000e2ee  mov     rbp, [rsp+68h+arg_20]
0x18000e2f6  xor     eax, eax
0x18000e2f8  cmp     ax, [rdi]
0x18000e2fb  jnz     short loc_18000E33C
0x18000e2fd  cmp     dword ptr [rbx], 2
0x18000e300  jnz     short loc_18000E33E
0x18000e302  mov     r8, [rsi]
0x18000e305  mov     [rsp+68h+var_38], r8
0x18000e30a  mov     [rsp+68h+var_30], al
0x18000e30e  mov     eax, [r8+18h]
0x18000e312  sub     eax, [r8+20h]
0x18000e316  cmp     eax, 1
0x18000e319  jb      short loc_18000E38F
0x18000e31b  mov     edx, [r8+20h]
0x18000e31f  mov     rax, [r8+10h]
0x18000e323  mov     rcx, [rbp+8]
0x18000e327  mov     al, [rdx+rax]
0x18000e32a  mov     [rcx], al
0x18000e32c  inc     dword ptr [r8+20h]
0x18000e330  lea     rcx, [rsp+68h+var_38]
0x18000e335  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000e33a  jmp     short loc_18000E357
0x18000e33c  jb      short loc_18000E371
0x18000e33e  cmp     dword ptr [rbx], 1
0x18000e341  jbe     short loc_18000E371
0x18000e343  mov     [rsp+68h+var_48], rbp
0x18000e348  mov     r9d, [rbx]
0x18000e34b  movzx   r8d, word ptr [rdi]
0x18000e34f  mov     rcx, rsi
0x18000e352  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_allowTouchGestures_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_allowTouchGestures_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,0,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchGestures_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>>(bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,0,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchGestures_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>> const &)
0x18000e357  mov     r8, rdi
0x18000e35a  mov     rdx, rbx
0x18000e35d  mov     rcx, [rsi]; this
0x18000e360  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000e365  xor     eax, eax
0x18000e367  cmp     ax, [rdi]
0x18000e36a  jb      short loc_18000E371
0x18000e36c  cmp     dword ptr [rbx], 1
0x18000e36f  ja      short loc_18000E2F6
0x18000e371  mov     [rsp+68h+arg_20], rbp
0x18000e379  mov     r9, rbx
0x18000e37c  mov     r8, rdi
0x18000e37f  mov     rcx, rsi
0x18000e382  add     rsp, 48h
0x18000e386  pop     rdi
0x18000e387  pop     rsi
0x18000e388  pop     rbp
0x18000e389  pop     rbx
0x18000e38a  jmp     ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowTouchScreenWake_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowTouchScreenWake_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata>,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>> const &)
0x18000e38f  mov     edx, 1; unsigned int
0x18000e394  mov     rcx, r8; this
0x18000e397  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
```
