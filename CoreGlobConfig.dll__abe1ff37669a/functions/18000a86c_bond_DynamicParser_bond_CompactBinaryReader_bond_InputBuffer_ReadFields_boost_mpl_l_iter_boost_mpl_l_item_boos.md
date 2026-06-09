# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>> const &)

- ea: `0x18000a86c`
- end: `0x18000a91d`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@Uregion_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$00@mpl@boost@@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@Uregion_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$00@mpl@boost@@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@1@@Z`
- size: `177`
- prototype: `__int64 __fastcall(bond::InputBuffer **, __int64, unsigned __int16 *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000aa0c`

## callees

- `0x18000a1ec`
- `0x18000a7a4`
- `0x18000a86c`
- `0x18000c12c`
- `0x1800115cc`
- `0x180017664`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(
        bond::InputBuffer **a1,
        __int64 a2,
        unsigned __int16 *a3,
        _DWORD *a4,
        __int64 a5)
{
  unsigned __int16 v8; // bx
  __int64 v10; // [rsp+20h] [rbp-58h]
  bond::InputBuffer *v11; // [rsp+30h] [rbp-48h] BYREF
  char v12; // [rsp+38h] [rbp-40h]

  do
  {
    v8 = *a3;
    if ( *a3 == 1 )
    {
      if ( *a4 == 18 )
      {
        v11 = *a1;
        v12 = 1;
        bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(
          a5,
          a2,
          (__int64)&v11);
        bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(&v11);
        goto LABEL_7;
      }
    }
    else if ( v8 > 1u )
    {
      return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(
               a1,
               a2,
               a3,
               a4,
               a5);
    }
    if ( *a4 <= 1u )
      return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(
               a1,
               a2,
               a3,
               a4,
               a5);
    LODWORD(v10) = *a4;
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<1,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(
      (_DWORD)a1,
      1,
      (_DWORD)a3,
      v8,
      v10,
      a5);
LABEL_7:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  while ( !v8 );
  return bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(
           a1,
           a2,
           a3,
           a4,
           a5);
}

```

## disassembly

```asm
0x18000a86c  push    rbx
0x18000a86e  push    rbp
0x18000a86f  push    rsi
0x18000a870  push    rdi
0x18000a871  push    r14
0x18000a873  push    r15
0x18000a875  sub     rsp, 48h
0x18000a879  mov     rdi, r9
0x18000a87c  mov     r14, r8
0x18000a87f  mov     rsi, rcx
0x18000a882  mov     r15d, 1
0x18000a888  mov     rbp, [rsp+78h+arg_20]
0x18000a890  movzx   ebx, word ptr [r14]
0x18000a894  cmp     r15w, bx
0x18000a898  jnz     short loc_18000A8C6
0x18000a89a  cmp     dword ptr [rdi], 12h
0x18000a89d  jnz     short loc_18000A8C8
0x18000a89f  mov     rax, [rsi]
0x18000a8a2  mov     [rsp+78h+var_48], rax
0x18000a8a7  mov     [rsp+78h+var_40], r15b
0x18000a8ac  lea     r8, [rsp+78h+var_48]
0x18000a8b1  mov     rcx, rbp
0x18000a8b4  call    ??$Field@Uregion_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@V?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@QEBA_NAEBUregion_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@AEBV?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@1@@Z; bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type const &,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void> const &)
0x18000a8b9  nop
0x18000a8ba  lea     rcx, [rsp+78h+var_48]
0x18000a8bf  call    ??1?$value_common@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000a8c4  jmp     short loc_18000A8E7
0x18000a8c6  jb      short loc_18000A8FB
0x18000a8c8  mov     eax, [rdi]
0x18000a8ca  cmp     eax, r15d
0x18000a8cd  jbe     short loc_18000A8FB
0x18000a8cf  mov     edx, r15d
0x18000a8d2  mov     [rsp+78h+var_50], rbp
0x18000a8d7  mov     dword ptr [rsp+78h+var_58], eax
0x18000a8db  movzx   r9d, bx
0x18000a8df  mov     rcx, rsi
0x18000a8e2  call    ??$UnknownFieldOrTypeMismatch@$00V?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NGAEBUMetadata@1@GW4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<1,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(ushort,bond::Metadata const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>> const &)
0x18000a8e7  mov     r8, r14
0x18000a8ea  mov     rdx, rdi
0x18000a8ed  mov     rcx, [rsi]; this
0x18000a8f0  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000a8f5  cmp     r15w, bx
0x18000a8f9  ja      short loc_18000A890
0x18000a8fb  mov     [rsp+78h+arg_20], rbp
0x18000a903  mov     r9, rdi
0x18000a906  mov     r8, r14
0x18000a909  mov     rcx, rsi
0x18000a90c  add     rsp, 48h
0x18000a910  pop     r15
0x18000a912  pop     r14
0x18000a914  pop     rdi
0x18000a915  pop     rsi
0x18000a916  pop     rbp
0x18000a917  pop     rbx
0x18000a918  jmp     ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>> const &)
```
