# bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)

- ea: `0x18000b218`
- end: `0x18000b3f3`
- name: `??$BasicTypeField@V?$To@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z`
- size: `475`
- prototype: `char __fastcall(__int16, __int64, int, __int64, __int64)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011020`
- `0x180011200`
- `0x180011388`
- `0x1800114bc`
- `0x180011a9c`

## callees

- `0x18000a8a8`
- `0x18000b218`
- `0x18001b468`
- `0x18001b488`
- `0x18001b4a8`
- `0x18001b4c8`
- `0x18001b4e8`
- `0x18001b508`
- `0x18001b528`

## pseudocode

```c
char __fastcall bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(
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
      v10 = bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>>::AssignToField<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<5>,bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<4>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,3,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_allowDisplayKeysWithPen_metadata>,boost::mpl::l_item<boost::mpl::long_<3>,bond::reflection::FieldTemplate<2,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,2,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_allowPenCursor_metadata>,boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,1,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_allowVisualEffects_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,0,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_leftHanded_metadata>,boost::mpl::l_end>>>>>>,bond::value<bool,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(
              a4,
              a2,
              a1,
              (__int64)&v17);
      bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
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
0x18000b218  mov     [rsp-8+arg_0], rbx
0x18000b21d  push    rbp
0x18000b21e  mov     rbp, rsp
0x18000b221  sub     rsp, 30h
0x18000b225  mov     r10, r9
0x18000b228  cmp     r8d, 8
0x18000b22c  jg      loc_18000B332
0x18000b232  jz      loc_18000B318
0x18000b238  sub     r8d, 2
0x18000b23c  jz      loc_18000B2EA
0x18000b242  sub     r8d, 1
0x18000b246  jz      loc_18000B2D0
0x18000b24c  sub     r8d, 1
0x18000b250  jz      short loc_18000B2B6
0x18000b252  sub     r8d, 1
0x18000b256  jz      short loc_18000B29C
0x18000b258  sub     r8d, 1
0x18000b25c  jz      short loc_18000B282
0x18000b25e  cmp     r8d, 1
0x18000b262  jnz     loc_18000B3E6
0x18000b268  mov     rax, [rbp+arg_20]
0x18000b26c  mov     [rbp+var_10], rax
0x18000b270  mov     [rbp+var_8], r8b
0x18000b274  lea     rcx, [rbp+var_10]
0x18000b278  call    ??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b27d  jmp     loc_18000B3E6
0x18000b282  mov     rax, [rbp+arg_20]
0x18000b286  mov     [rbp+var_10], rax
0x18000b28a  mov     [rbp+var_8], 1
0x18000b28e  lea     rcx, [rbp+var_10]
0x18000b292  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b297  jmp     loc_18000B3E6
0x18000b29c  mov     rax, [rbp+arg_20]
0x18000b2a0  mov     [rbp+var_10], rax
0x18000b2a4  mov     [rbp+var_8], 1
0x18000b2a8  lea     rcx, [rbp+var_10]
0x18000b2ac  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b2b1  jmp     loc_18000B3E6
0x18000b2b6  mov     rax, [rbp+arg_20]
0x18000b2ba  mov     [rbp+var_10], rax
0x18000b2be  mov     [rbp+var_8], 1
0x18000b2c2  lea     rcx, [rbp+var_10]
0x18000b2c6  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b2cb  jmp     loc_18000B3E6
0x18000b2d0  mov     rax, [rbp+arg_20]
0x18000b2d4  mov     [rbp+var_10], rax
0x18000b2d8  mov     [rbp+var_8], 1
0x18000b2dc  lea     rcx, [rbp+var_10]
0x18000b2e0  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b2e5  jmp     loc_18000B3E6
0x18000b2ea  mov     rax, [rbp+arg_20]
0x18000b2ee  mov     [rbp+var_10], rax
0x18000b2f2  mov     [rbp+var_8], 1
0x18000b2f6  lea     r9, [rbp+var_10]
0x18000b2fa  movzx   r8d, cx
0x18000b2fe  mov     rcx, r10
0x18000b301  call    ??$AssignToField@U?$l_iter@U?$l_item@U?$long_@$04@mpl@boost@@U?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$03$1?s_eraseEnabled_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$02$1?s_allowDisplayKeysWithPen_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$01$1?s_allowPenCursor_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowVisualEffects_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_leftHanded_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@V?$value@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@?$To@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@AEBA_NAEBU?$l_iter@U?$l_item@U?$long_@$04@mpl@boost@@U?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$03$1?s_eraseEnabled_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$02$1?s_allowDisplayKeysWithPen_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$01$1?s_allowPenCursor_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowVisualEffects_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_leftHanded_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@GAEBV?$value@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@1@@Z
0x18000b306  mov     bl, al
0x18000b308  lea     rcx, [rbp+var_10]
0x18000b30c  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b311  mov     al, bl
0x18000b313  jmp     loc_18000B3E8
0x18000b318  mov     rax, [rbp+arg_20]
0x18000b31c  mov     [rbp+var_10], rax
0x18000b320  mov     [rbp+var_8], 1
0x18000b324  lea     rcx, [rbp+var_10]
0x18000b328  call    ??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b32d  jmp     loc_18000B3E6
0x18000b332  sub     r8d, 9
0x18000b336  jz      loc_18000B3D1
0x18000b33c  sub     r8d, 5
0x18000b340  jz      short loc_18000B3BA
0x18000b342  sub     r8d, 1
0x18000b346  jz      short loc_18000B3A3
0x18000b348  sub     r8d, 1
0x18000b34c  jz      short loc_18000B38C
0x18000b34e  sub     r8d, 1
0x18000b352  jz      short loc_18000B375
0x18000b354  cmp     r8d, 1
0x18000b358  jnz     loc_18000B3E6
0x18000b35e  mov     rax, [rbp+arg_20]
0x18000b362  mov     [rbp+var_10], rax
0x18000b366  mov     [rbp+var_8], r8b
0x18000b36a  lea     rcx, [rbp+var_10]
0x18000b36e  call    ??1?$value_common@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b373  jmp     short loc_18000B3E6
0x18000b375  mov     rax, [rbp+arg_20]
0x18000b379  mov     [rbp+var_10], rax
0x18000b37d  mov     [rbp+var_8], 1
0x18000b381  lea     rcx, [rbp+var_10]
0x18000b385  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b38a  jmp     short loc_18000B3E6
0x18000b38c  mov     rax, [rbp+arg_20]
0x18000b390  mov     [rbp+var_10], rax
0x18000b394  mov     [rbp+var_8], 1
0x18000b398  lea     rcx, [rbp+var_10]
0x18000b39c  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b3a1  jmp     short loc_18000B3E6
0x18000b3a3  mov     rax, [rbp+arg_20]
0x18000b3a7  mov     [rbp+var_10], rax
0x18000b3ab  mov     [rbp+var_8], 1
0x18000b3af  lea     rcx, [rbp+var_10]
0x18000b3b3  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b3b8  jmp     short loc_18000B3E6
0x18000b3ba  mov     rax, [rbp+arg_20]
0x18000b3be  mov     [rbp+var_10], rax
0x18000b3c2  mov     [rbp+var_8], 1
0x18000b3c6  lea     rcx, [rbp+var_10]
0x18000b3ca  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b3cf  jmp     short loc_18000B3E6
0x18000b3d1  mov     rax, [rbp+arg_20]
0x18000b3d5  mov     [rbp+var_10], rax
0x18000b3d9  mov     [rbp+var_8], 1
0x18000b3dd  lea     rcx, [rbp+var_10]
0x18000b3e1  call    ??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b3e6  xor     al, al
0x18000b3e8  mov     rbx, [rsp+30h+arg_0]
0x18000b3ed  add     rsp, 30h
0x18000b3f1  pop     rbp
0x18000b3f2  retn
```
