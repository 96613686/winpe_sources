# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<3>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type,boost::mpl::l_item<boost::mpl::long_<2>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>>>,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<3>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type,boost::mpl::l_item<boost::mpl::long_<2>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>>> const &,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>> const &)

- ea: `0x18000aa0c`
- end: `0x18000aafe`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$02@mpl@boost@@UlanguageProfile_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$01@mpl@boost@@Uregion_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$00@mpl@boost@@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@Ul_end@23@@23@@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$l_iter@U?$l_item@U?$long_@$02@mpl@boost@@UlanguageProfile_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$01@mpl@boost@@Uregion_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$00@mpl@boost@@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@Ul_end@23@@23@@23@@mpl@boost@@@mpl@boost@@AEBV?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@1@@Z`
- size: `242`
- prototype: `bool __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009dd8`

## callees

- `0x18000a094`
- `0x18000a86c`
- `0x18000aa0c`
- `0x18000ba24`
- `0x18000c12c`
- `0x1800115cc`
- `0x180017664`

## pseudocode

```c
bool __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<3>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type,boost::mpl::l_item<boost::mpl::long_<2>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>>>,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // rdx
  int v6; // r8d
  bool result; // al
  bond::InputBuffer *v8; // [rsp+30h] [rbp-10h] BYREF
  char v9; // [rsp+38h] [rbp-8h]
  unsigned int v10; // [rsp+50h] [rbp+10h] BYREF
  __int64 v11; // [rsp+58h] [rbp+18h] BYREF

  v11 = a2;
  LOWORD(v11) = 0;
  v10 = 0;
  bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*(bond::InputBuffer **)a1);
  if ( !(_WORD)v11 )
  {
    if ( v10 == 18 )
    {
      v8 = *(bond::InputBuffer **)a1;
      v9 = 1;
      bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(
        a3,
        v5,
        (__int64)&v8);
      bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(&v8);
    }
    else
    {
      if ( v10 <= 1 )
        goto LABEL_8;
      bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<1,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(
        a1,
        0,
        v6,
        (unsigned __int16)v11,
        v10,
        a3);
    }
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*(bond::InputBuffer **)a1);
  }
LABEL_8:
  bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(
    (bond::InputBuffer **)a1,
    v5,
    (unsigned __int16 *)&v11,
    &v10,
    a3);
  if ( *(_BYTE *)(a1 + 8) )
    return v10 == 0;
  while ( 1 )
  {
    result = v10;
    if ( !v10 )
      break;
    if ( v10 != 1 )
      bond::CompactBinaryReader<bond::InputBuffer>::SkipType<>(*(bond::InputBuffer **)a1);
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*(bond::InputBuffer **)a1);
  }
  return result;
}

```

## disassembly

```asm
0x18000aa0c  mov     [rsp-8+arg_10], rbx
0x18000aa11  mov     [rsp-8+arg_18], rdi
0x18000aa16  mov     [rsp-8+arg_8], rdx
0x18000aa1b  push    rbp
0x18000aa1c  mov     rbp, rsp
0x18000aa1f  sub     rsp, 40h
0x18000aa23  mov     rdi, r8
0x18000aa26  mov     rbx, rcx
0x18000aa29  xor     eax, eax
0x18000aa2b  mov     word ptr [rbp+arg_8], ax
0x18000aa2f  mov     [rbp+arg_0], eax
0x18000aa32  lea     r8, [rbp+arg_8]
0x18000aa36  lea     rdx, [rbp+arg_0]
0x18000aa3a  mov     rcx, [rcx]; this
0x18000aa3d  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000aa42  xor     eax, eax
0x18000aa44  mov     ecx, [rbp+arg_0]
0x18000aa47  movzx   r9d, word ptr [rbp+arg_8]
0x18000aa4c  cmp     ax, r9w
0x18000aa50  jnz     short loc_18000AA7A
0x18000aa52  cmp     ecx, 12h
0x18000aa55  jnz     short loc_18000AA7C
0x18000aa57  mov     rax, [rbx]
0x18000aa5a  mov     [rbp+var_10], rax
0x18000aa5e  mov     [rbp+var_8], 1
0x18000aa62  lea     r8, [rbp+var_10]
0x18000aa66  mov     rcx, rdi
0x18000aa69  call    ??$Field@UlanguageProfile_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@V?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@QEBA_NAEBUlanguageProfile_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@AEBV?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@1@@Z; bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type const &,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void> const &)
0x18000aa6e  nop
0x18000aa6f  lea     rcx, [rbp+var_10]
0x18000aa73  call    ??1?$value_common@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000aa78  jmp     short loc_18000AA94
0x18000aa7a  jb      short loc_18000AAA4
0x18000aa7c  cmp     ecx, 1
0x18000aa7f  jbe     short loc_18000AAA4
0x18000aa81  xor     edx, edx
0x18000aa83  mov     [rsp+40h+var_18], rdi
0x18000aa88  mov     dword ptr [rsp+40h+var_20], ecx
0x18000aa8c  mov     rcx, rbx
0x18000aa8f  call    ??$UnknownFieldOrTypeMismatch@$00V?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NGAEBUMetadata@1@GW4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<1,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(ushort,bond::Metadata const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>> const &)
0x18000aa94  lea     r8, [rbp+arg_8]
0x18000aa98  lea     rdx, [rbp+arg_0]
0x18000aa9c  mov     rcx, [rbx]; this
0x18000aa9f  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000aaa4  mov     [rsp+40h+var_20], rdi
0x18000aaa9  lea     r9, [rbp+arg_0]
0x18000aaad  lea     r8, [rbp+arg_8]
0x18000aab1  mov     rcx, rbx
0x18000aab4  call    ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@Uregion_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$00@mpl@boost@@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@Uregion_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$00@mpl@boost@@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>> const &)
0x18000aab9  cmp     byte ptr [rbx+8], 0
0x18000aabd  jz      short loc_18000AAF5
0x18000aabf  cmp     [rbp+arg_0], 0
0x18000aac3  setz    al
0x18000aac6  mov     rbx, [rsp+40h+arg_10]
0x18000aacb  mov     rdi, [rsp+40h+arg_18]
0x18000aad0  add     rsp, 40h
0x18000aad4  pop     rbp
0x18000aad5  retn
0x18000aad6  cmp     eax, 1
0x18000aad9  jz      short loc_18000AAE5
0x18000aadb  mov     edx, eax
0x18000aadd  mov     rcx, [rbx]; this
0x18000aae0  call    ??$SkipType@$$V@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXW4BondDataType@2_bond_enumerators@1@@Z; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<>(bond::_bond_enumerators::BondDataType::BondDataType)
0x18000aae5  lea     r8, [rbp+arg_8]
0x18000aae9  lea     rdx, [rbp+arg_0]
0x18000aaed  mov     rcx, [rbx]; this
0x18000aaf0  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000aaf5  mov     eax, [rbp+arg_0]
0x18000aaf8  test    eax, eax
0x18000aafa  jnz     short loc_18000AAD6
0x18000aafc  jmp     short loc_18000AAC6
```
