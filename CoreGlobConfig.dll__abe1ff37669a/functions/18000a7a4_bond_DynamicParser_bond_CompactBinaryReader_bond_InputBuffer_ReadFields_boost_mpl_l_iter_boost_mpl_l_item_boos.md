# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>> const &)

- ea: `0x18000a7a4`
- end: `0x18000a865`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@1@@Z`
- size: `193`
- prototype: `__int64 __fastcall(bond::InputBuffer **, __int64, unsigned __int16 *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a86c`

## callees

- `0x18000a140`
- `0x18000a7a4`
- `0x18000ba24`
- `0x18000c12c`
- `0x1800115cc`
- `0x180017664`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(
        bond::InputBuffer **a1,
        __int64 a2,
        unsigned __int16 *a3,
        _DWORD *a4,
        __int64 a5)
{
  unsigned __int16 v8; // di
  __int64 result; // rax
  __int64 v10; // [rsp+20h] [rbp-58h]
  bond::InputBuffer *v11; // [rsp+30h] [rbp-48h] BYREF
  char v12; // [rsp+38h] [rbp-40h]

  do
  {
    v8 = *a3;
    if ( *a3 == 2 )
    {
      if ( *a4 == 18 )
      {
        v11 = *a1;
        v12 = 1;
        bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(
          a5,
          a2,
          (__int64)&v11);
        bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(&v11);
        goto LABEL_7;
      }
    }
    else if ( v8 > 2u )
    {
      break;
    }
    if ( *a4 <= 1u )
      break;
    LODWORD(v10) = *a4;
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<1,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(
      (_DWORD)a1,
      2,
      (_DWORD)a3,
      v8,
      v10,
      a5);
LABEL_7:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  while ( v8 < 2u );
  while ( 1 )
  {
    result = (unsigned int)*a4;
    if ( (unsigned int)result <= 1 )
      break;
    bond::CompactBinaryReader<bond::InputBuffer>::SkipType<>(*a1);
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  return result;
}

```

## disassembly

```asm
0x18000a7a4  push    rbx
0x18000a7a6  push    rbp
0x18000a7a7  push    rsi
0x18000a7a8  push    rdi
0x18000a7a9  push    r14
0x18000a7ab  push    r15
0x18000a7ad  sub     rsp, 48h
0x18000a7b1  mov     rbx, r9
0x18000a7b4  mov     r14, r8
0x18000a7b7  mov     rsi, rcx
0x18000a7ba  mov     r15d, 2
0x18000a7c0  mov     rbp, [rsp+78h+arg_20]
0x18000a7c8  movzx   edi, word ptr [r14]
0x18000a7cc  cmp     r15w, di
0x18000a7d0  jnz     short loc_18000A7FE
0x18000a7d2  cmp     dword ptr [rbx], 12h
0x18000a7d5  jnz     short loc_18000A800
0x18000a7d7  mov     rax, [rsi]
0x18000a7da  mov     [rsp+78h+var_48], rax
0x18000a7df  mov     [rsp+78h+var_40], 1
0x18000a7e4  lea     r8, [rsp+78h+var_48]
0x18000a7e9  mov     rcx, rbp
0x18000a7ec  call    ??$Field@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@V?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@QEBA_NAEBUlocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@AEBV?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@1@@Z; bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type const &,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void> const &)
0x18000a7f1  nop
0x18000a7f2  lea     rcx, [rsp+78h+var_48]
0x18000a7f7  call    ??1?$value_common@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000a7fc  jmp     short loc_18000A81F
0x18000a7fe  jb      short loc_18000A852
0x18000a800  mov     eax, [rbx]
0x18000a802  cmp     eax, 1
0x18000a805  jbe     short loc_18000A852
0x18000a807  mov     edx, r15d
0x18000a80a  mov     [rsp+78h+var_50], rbp
0x18000a80f  mov     dword ptr [rsp+78h+var_58], eax
0x18000a813  movzx   r9d, di
0x18000a817  mov     rcx, rsi
0x18000a81a  call    ??$UnknownFieldOrTypeMismatch@$00V?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NGAEBUMetadata@1@GW4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<1,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(ushort,bond::Metadata const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>> const &)
0x18000a81f  mov     r8, r14
0x18000a822  mov     rdx, rbx
0x18000a825  mov     rcx, [rsi]; this
0x18000a828  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000a82d  cmp     r15w, di
0x18000a831  ja      short loc_18000A7C8
0x18000a833  jmp     short loc_18000A852
0x18000a835  cmp     eax, 1
0x18000a838  jz      short loc_18000A858
0x18000a83a  mov     edx, eax
0x18000a83c  mov     rcx, [rsi]; this
0x18000a83f  call    ??$SkipType@$$V@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXW4BondDataType@2_bond_enumerators@1@@Z; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<>(bond::_bond_enumerators::BondDataType::BondDataType)
0x18000a844  mov     r8, r14
0x18000a847  mov     rdx, rbx
0x18000a84a  mov     rcx, [rsi]; this
0x18000a84d  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000a852  mov     eax, [rbx]
0x18000a854  test    eax, eax
0x18000a856  jnz     short loc_18000A835
0x18000a858  add     rsp, 48h
0x18000a85c  pop     r15
0x18000a85e  pop     r14
0x18000a860  pop     rdi
0x18000a861  pop     rsi
0x18000a862  pop     rbp
0x18000a863  pop     rbx
0x18000a864  retn
```
