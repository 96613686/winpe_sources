# bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)

- ea: `0x18000f45c`
- end: `0x18000f637`
- name: `??$BasicTypeField@V?$To@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@bond@@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@bond@@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z`
- size: `475`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010688`
- `0x1800106d8`
- `0x180010728`
- `0x180010778`
- `0x1800107c8`

## callees

- `0x18000f3b8`
- `0x18000f45c`
- `0x18001357c`
- `0x18001359c`
- `0x1800135bc`
- `0x1800135dc`
- `0x1800135fc`
- `0x18001361c`
- `0x18001363c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>>,bond::CompactBinaryReader<bond::InputBuffer>>(
        unsigned __int16 a1,
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
  char v10; // bl
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  int v15; // r8d
  int v16; // r8d
  __int64 v17; // [rsp+20h] [rbp-10h] BYREF
  char v18; // [rsp+28h] [rbp-8h]

  if ( a3 <= 8 )
  {
    if ( a3 == 8 )
    {
      v17 = a5;
      v18 = 1;
      bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
      return 0;
    }
    v5 = a3 - 2;
    if ( !v5 )
    {
      v17 = a5;
      v18 = 1;
      v10 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64 *))bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>>::AssignToField<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<5>,bond::reflection::FieldTemplate<50,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,4,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isMuteNotificationsEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<4>,bond::reflection::FieldTemplate<40,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,3,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarFlashesEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<3>,bond::reflection::FieldTemplate<30,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,2,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarBadgesEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<20,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,1,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isStartFocusTimerEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,0,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isInitialized_metadata>,boost::mpl::l_end>>>>>>,bond::value<bool,bond::CompactBinaryReader<bond::InputBuffer> &,void>>)(
              a4,
              a2,
              a1,
              &v17);
      bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>((__int64)&v17);
      return v10;
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
              v17 = a5;
              v18 = 1;
              bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
            }
            return 0;
          }
        }
      }
      goto LABEL_10;
    }
LABEL_11:
    v17 = a5;
    v18 = 1;
    bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
    return 0;
  }
  v12 = a3 - 9;
  if ( !v12 )
  {
    v17 = a5;
    v18 = 1;
    bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
    return 0;
  }
  v13 = v12 - 5;
  if ( !v13 )
    goto LABEL_11;
  v14 = v13 - 1;
  if ( v14 )
  {
    v15 = v14 - 1;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 )
      {
        if ( v16 == 1 )
        {
          v17 = a5;
          v18 = 1;
          bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
        }
        return 0;
      }
    }
  }
LABEL_10:
  v17 = a5;
  v18 = 1;
  bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
  return 0;
}

```

## disassembly

```asm
0x18000f45c  mov     [rsp-8+arg_0], rbx
0x18000f461  push    rbp
0x18000f462  mov     rbp, rsp
0x18000f465  sub     rsp, 30h
0x18000f469  mov     r10, r9
0x18000f46c  cmp     r8d, 8
0x18000f470  jg      loc_18000F576
0x18000f476  jz      loc_18000F55C
0x18000f47c  sub     r8d, 2
0x18000f480  jz      loc_18000F52E
0x18000f486  sub     r8d, 1
0x18000f48a  jz      loc_18000F514
0x18000f490  sub     r8d, 1
0x18000f494  jz      short loc_18000F4FA
0x18000f496  sub     r8d, 1
0x18000f49a  jz      short loc_18000F4E0
0x18000f49c  sub     r8d, 1
0x18000f4a0  jz      short loc_18000F4C6
0x18000f4a2  cmp     r8d, 1
0x18000f4a6  jnz     loc_18000F62A
0x18000f4ac  mov     rax, [rbp+arg_20]
0x18000f4b0  mov     [rbp+var_10], rax
0x18000f4b4  mov     [rbp+var_8], r8b
0x18000f4b8  lea     rcx, [rbp+var_10]
0x18000f4bc  call    ??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000f4c1  jmp     loc_18000F62A
0x18000f4c6  mov     rax, [rbp+arg_20]
0x18000f4ca  mov     [rbp+var_10], rax
0x18000f4ce  mov     [rbp+var_8], 1
0x18000f4d2  lea     rcx, [rbp+var_10]
0x18000f4d6  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000f4db  jmp     loc_18000F62A
0x18000f4e0  mov     rax, [rbp+arg_20]
0x18000f4e4  mov     [rbp+var_10], rax
0x18000f4e8  mov     [rbp+var_8], 1
0x18000f4ec  lea     rcx, [rbp+var_10]
0x18000f4f0  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000f4f5  jmp     loc_18000F62A
0x18000f4fa  mov     rax, [rbp+arg_20]
0x18000f4fe  mov     [rbp+var_10], rax
0x18000f502  mov     [rbp+var_8], 1
0x18000f506  lea     rcx, [rbp+var_10]
0x18000f50a  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000f50f  jmp     loc_18000F62A
0x18000f514  mov     rax, [rbp+arg_20]
0x18000f518  mov     [rbp+var_10], rax
0x18000f51c  mov     [rbp+var_8], 1
0x18000f520  lea     rcx, [rbp+var_10]
0x18000f524  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000f529  jmp     loc_18000F62A
0x18000f52e  mov     rax, [rbp+arg_20]
0x18000f532  mov     [rbp+var_10], rax
0x18000f536  mov     [rbp+var_8], 1
0x18000f53a  lea     r9, [rbp+var_10]
0x18000f53e  movzx   r8d, cx
0x18000f542  mov     rcx, r10
0x18000f545  call    ??$AssignToField@U?$l_iter@U?$l_item@U?$long_@$04@mpl@boost@@U?$FieldTemplate@$0DC@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$03$1?s_isMuteNotificationsEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$0CI@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$02$1?s_isHideTaskbarFlashesEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$0BO@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$01$1?s_isHideTaskbarBadgesEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0BE@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$00$1?s_isStartFocusTimerEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$09Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$0A@$1?s_isInitialized_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@V?$value@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@?$To@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@bond@@@bond@@AEBA_NAEBU?$l_iter@U?$l_item@U?$long_@$04@mpl@boost@@U?$FieldTemplate@$0DC@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$03$1?s_isMuteNotificationsEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$0CI@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$02$1?s_isHideTaskbarFlashesEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$0BO@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$01$1?s_isHideTaskbarBadgesEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0BE@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$00$1?s_isStartFocusTimerEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$09Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$0A@$1?s_isInitialized_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@GAEBV?$value@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@1@@Z
0x18000f54a  mov     bl, al
0x18000f54c  lea     rcx, [rbp+var_10]
0x18000f550  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000f555  mov     al, bl
0x18000f557  jmp     loc_18000F62C
0x18000f55c  mov     rax, [rbp+arg_20]
0x18000f560  mov     [rbp+var_10], rax
0x18000f564  mov     [rbp+var_8], 1
0x18000f568  lea     rcx, [rbp+var_10]
0x18000f56c  call    ??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000f571  jmp     loc_18000F62A
0x18000f576  sub     r8d, 9
0x18000f57a  jz      loc_18000F615
0x18000f580  sub     r8d, 5
0x18000f584  jz      short loc_18000F5FE
0x18000f586  sub     r8d, 1
0x18000f58a  jz      short loc_18000F5E7
0x18000f58c  sub     r8d, 1
0x18000f590  jz      short loc_18000F5D0
0x18000f592  sub     r8d, 1
0x18000f596  jz      short loc_18000F5B9
0x18000f598  cmp     r8d, 1
0x18000f59c  jnz     loc_18000F62A
0x18000f5a2  mov     rax, [rbp+arg_20]
0x18000f5a6  mov     [rbp+var_10], rax
0x18000f5aa  mov     [rbp+var_8], r8b
0x18000f5ae  lea     rcx, [rbp+var_10]
0x18000f5b2  call    ??1?$value_common@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000f5b7  jmp     short loc_18000F62A
0x18000f5b9  mov     rax, [rbp+arg_20]
0x18000f5bd  mov     [rbp+var_10], rax
0x18000f5c1  mov     [rbp+var_8], 1
0x18000f5c5  lea     rcx, [rbp+var_10]
0x18000f5c9  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000f5ce  jmp     short loc_18000F62A
0x18000f5d0  mov     rax, [rbp+arg_20]
0x18000f5d4  mov     [rbp+var_10], rax
0x18000f5d8  mov     [rbp+var_8], 1
0x18000f5dc  lea     rcx, [rbp+var_10]
0x18000f5e0  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000f5e5  jmp     short loc_18000F62A
0x18000f5e7  mov     rax, [rbp+arg_20]
0x18000f5eb  mov     [rbp+var_10], rax
0x18000f5ef  mov     [rbp+var_8], 1
0x18000f5f3  lea     rcx, [rbp+var_10]
0x18000f5f7  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000f5fc  jmp     short loc_18000F62A
0x18000f5fe  mov     rax, [rbp+arg_20]
0x18000f602  mov     [rbp+var_10], rax
0x18000f606  mov     [rbp+var_8], 1
0x18000f60a  lea     rcx, [rbp+var_10]
0x18000f60e  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000f613  jmp     short loc_18000F62A
0x18000f615  mov     rax, [rbp+arg_20]
0x18000f619  mov     [rbp+var_10], rax
0x18000f61d  mov     [rbp+var_8], 1
0x18000f621  lea     rcx, [rbp+var_10]
0x18000f625  call    ??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000f62a  xor     al, al
0x18000f62c  mov     rbx, [rsp+30h+arg_0]
0x18000f631  add     rsp, 30h
0x18000f635  pop     rbp
0x18000f636  retn
```
