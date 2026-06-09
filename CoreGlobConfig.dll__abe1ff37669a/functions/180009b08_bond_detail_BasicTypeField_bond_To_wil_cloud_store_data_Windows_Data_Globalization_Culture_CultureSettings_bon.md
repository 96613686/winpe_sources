# bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)

- ea: `0x180009b08`
- end: `0x180009d1c`
- name: `??$BasicTypeField@V?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z`
- size: `532`
- prototype: `char __fastcall(__int16, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c12c`

## callees

- `0x180009b08`
- `0x18000a094`
- `0x18000a140`
- `0x18000a1ec`
- `0x18001152c`
- `0x18001154c`
- `0x18001156c`
- `0x18001158c`
- `0x1800115ac`
- `0x1800115cc`
- `0x1800115ec`

## pseudocode

```c
char __fastcall bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(
        __int16 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  char v15; // al
  char v16; // bl
  __int64 v18; // [rsp+20h] [rbp-10h] BYREF
  char v19; // [rsp+28h] [rbp-8h]

  if ( a3 <= 8 )
  {
    if ( a3 == 8 )
    {
      v18 = a5;
      v19 = 1;
      bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(&v18);
      return 0;
    }
    v5 = a3 - 2;
    if ( !v5 )
    {
      v18 = a5;
      v19 = 1;
      bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v18);
      return 0;
    }
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            if ( v9 == 1 )
            {
              v18 = a5;
              v19 = 1;
              bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(&v18);
            }
            return 0;
          }
        }
      }
      goto LABEL_10;
    }
LABEL_11:
    v18 = a5;
    v19 = 1;
    bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v18);
    return 0;
  }
  v10 = a3 - 9;
  if ( !v10 )
  {
    v18 = a5;
    v19 = 1;
    bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(&v18);
    return 0;
  }
  v11 = v10 - 5;
  if ( !v11 )
    goto LABEL_11;
  v12 = v11 - 1;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        if ( v14 != 1 )
          return 0;
        v18 = a5;
        v19 = 1;
        if ( a1 == 2 )
        {
          v15 = bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(
                  a4,
                  a2,
                  &v18);
        }
        else if ( a1 == 1 )
        {
          v15 = bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(
                  a4,
                  a2,
                  &v18);
        }
        else
        {
          if ( a1 )
          {
            v16 = 0;
            goto LABEL_28;
          }
          v15 = bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(
                  a4,
                  a2,
                  &v18);
        }
        v16 = v15;
LABEL_28:
        bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(&v18);
        return v16;
      }
    }
  }
LABEL_10:
  v18 = a5;
  v19 = 1;
  bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v18);
  return 0;
}

```

## disassembly

```asm
0x180009b08  mov     [rsp-8+arg_0], rbx
0x180009b0d  push    rbp
0x180009b0e  mov     rbp, rsp
0x180009b11  sub     rsp, 30h
0x180009b15  cmp     r8d, 8
0x180009b19  jg      loc_180009C0B
0x180009b1f  jz      loc_180009BF1
0x180009b25  sub     r8d, 2
0x180009b29  jz      loc_180009BD7
0x180009b2f  sub     r8d, 1
0x180009b33  jz      loc_180009BBD
0x180009b39  sub     r8d, 1
0x180009b3d  jz      short loc_180009BA3
0x180009b3f  sub     r8d, 1
0x180009b43  jz      short loc_180009B89
0x180009b45  sub     r8d, 1
0x180009b49  jz      short loc_180009B6F
0x180009b4b  cmp     r8d, 1
0x180009b4f  jnz     loc_180009D0F
0x180009b55  mov     rax, [rbp+arg_20]
0x180009b59  mov     [rbp+var_10], rax
0x180009b5d  mov     [rbp+var_8], r8b
0x180009b61  lea     rcx, [rbp+var_10]
0x180009b65  call    ??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180009b6a  jmp     loc_180009D0F
0x180009b6f  mov     rax, [rbp+arg_20]
0x180009b73  mov     [rbp+var_10], rax
0x180009b77  mov     [rbp+var_8], 1
0x180009b7b  lea     rcx, [rbp+var_10]
0x180009b7f  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180009b84  jmp     loc_180009D0F
0x180009b89  mov     rax, [rbp+arg_20]
0x180009b8d  mov     [rbp+var_10], rax
0x180009b91  mov     [rbp+var_8], 1
0x180009b95  lea     rcx, [rbp+var_10]
0x180009b99  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180009b9e  jmp     loc_180009D0F
0x180009ba3  mov     rax, [rbp+arg_20]
0x180009ba7  mov     [rbp+var_10], rax
0x180009bab  mov     [rbp+var_8], 1
0x180009baf  lea     rcx, [rbp+var_10]
0x180009bb3  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180009bb8  jmp     loc_180009D0F
0x180009bbd  mov     rax, [rbp+arg_20]
0x180009bc1  mov     [rbp+var_10], rax
0x180009bc5  mov     [rbp+var_8], 1
0x180009bc9  lea     rcx, [rbp+var_10]
0x180009bcd  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180009bd2  jmp     loc_180009D0F
0x180009bd7  mov     rax, [rbp+arg_20]
0x180009bdb  mov     [rbp+var_10], rax
0x180009bdf  mov     [rbp+var_8], 1
0x180009be3  lea     rcx, [rbp+var_10]
0x180009be7  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180009bec  jmp     loc_180009D0F
0x180009bf1  mov     rax, [rbp+arg_20]
0x180009bf5  mov     [rbp+var_10], rax
0x180009bf9  mov     [rbp+var_8], 1
0x180009bfd  lea     rcx, [rbp+var_10]
0x180009c01  call    ??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180009c06  jmp     loc_180009D0F
0x180009c0b  sub     r8d, 9
0x180009c0f  jz      loc_180009CFA
0x180009c15  sub     r8d, 5
0x180009c19  jz      loc_180009CE3
0x180009c1f  sub     r8d, 1
0x180009c23  jz      loc_180009CCC
0x180009c29  sub     r8d, 1
0x180009c2d  jz      loc_180009CB5
0x180009c33  sub     r8d, 1
0x180009c37  jz      short loc_180009C9E
0x180009c39  cmp     r8d, 1
0x180009c3d  jnz     loc_180009D0F
0x180009c43  mov     rax, [rbp+arg_20]
0x180009c47  mov     [rbp+var_10], rax
0x180009c4b  mov     [rbp+var_8], r8b
0x180009c4f  lea     eax, [r8+1]
0x180009c53  cmp     cx, ax
0x180009c56  jnz     short loc_180009C68
0x180009c58  lea     r8, [rbp+var_10]
0x180009c5c  mov     rcx, r9
0x180009c5f  call    ??$Field@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@V?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@QEBA_NAEBUlocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@AEBV?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@1@@Z; bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type const &,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void> const &)
0x180009c64  mov     bl, al
0x180009c66  jmp     short loc_180009C91
0x180009c68  cmp     cx, 1
0x180009c6c  jnz     short loc_180009C7C
0x180009c6e  lea     r8, [rbp+var_10]
0x180009c72  mov     rcx, r9
0x180009c75  call    ??$Field@Uregion_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@V?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@QEBA_NAEBUregion_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@AEBV?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@1@@Z; bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type const &,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void> const &)
0x180009c7a  jmp     short loc_180009C64
0x180009c7c  test    cx, cx
0x180009c7f  jnz     short loc_180009C8F
0x180009c81  lea     r8, [rbp+var_10]
0x180009c85  mov     rcx, r9
0x180009c88  call    ??$Field@UlanguageProfile_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@V?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@QEBA_NAEBUlanguageProfile_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@AEBV?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@1@@Z; bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type const &,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void> const &)
0x180009c8d  jmp     short loc_180009C64
0x180009c8f  xor     bl, bl
0x180009c91  lea     rcx, [rbp+var_10]
0x180009c95  call    ??1?$value_common@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180009c9a  mov     al, bl
0x180009c9c  jmp     short loc_180009D11
0x180009c9e  mov     rax, [rbp+arg_20]
0x180009ca2  mov     [rbp+var_10], rax
0x180009ca6  mov     [rbp+var_8], 1
0x180009caa  lea     rcx, [rbp+var_10]
0x180009cae  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180009cb3  jmp     short loc_180009D0F
0x180009cb5  mov     rax, [rbp+arg_20]
0x180009cb9  mov     [rbp+var_10], rax
0x180009cbd  mov     [rbp+var_8], 1
0x180009cc1  lea     rcx, [rbp+var_10]
0x180009cc5  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180009cca  jmp     short loc_180009D0F
0x180009ccc  mov     rax, [rbp+arg_20]
0x180009cd0  mov     [rbp+var_10], rax
0x180009cd4  mov     [rbp+var_8], 1
0x180009cd8  lea     rcx, [rbp+var_10]
0x180009cdc  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180009ce1  jmp     short loc_180009D0F
0x180009ce3  mov     rax, [rbp+arg_20]
0x180009ce7  mov     [rbp+var_10], rax
0x180009ceb  mov     [rbp+var_8], 1
0x180009cef  lea     rcx, [rbp+var_10]
0x180009cf3  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180009cf8  jmp     short loc_180009D0F
0x180009cfa  mov     rax, [rbp+arg_20]
0x180009cfe  mov     [rbp+var_10], rax
0x180009d02  mov     [rbp+var_8], 1
0x180009d06  lea     rcx, [rbp+var_10]
0x180009d0a  call    ??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180009d0f  xor     al, al
0x180009d11  mov     rbx, [rsp+30h+arg_0]
0x180009d16  add     rsp, 30h
0x180009d1a  pop     rbp
0x180009d1b  retn
```
