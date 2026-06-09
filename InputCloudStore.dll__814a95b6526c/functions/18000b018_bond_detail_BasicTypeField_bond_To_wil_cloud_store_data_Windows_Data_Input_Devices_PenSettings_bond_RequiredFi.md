# bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)

- ea: `0x18000b018`
- end: `0x18000b211`
- name: `??$BasicTypeField@V?$To@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z`
- size: `505`
- prototype: `char __fastcall(__int16, __int64, int, __int64, __int64)`
- caller_count: `7`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010fd0`
- `0x1800111b0`
- `0x18001133c`
- `0x18001146c`
- `0x1800115ac`
- `0x18001169c`
- `0x180011a50`

## callees

- `0x18000a440`
- `0x18000a480`
- `0x18000a9f0`
- `0x18000b018`
- `0x18001b468`
- `0x18001b488`
- `0x18001b4a8`
- `0x18001b4c8`
- `0x18001b4e8`
- `0x18001b508`
- `0x18001b528`

## pseudocode

```c
char __fastcall bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(
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

  if ( a3 > 8 )
  {
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
    {
      v17 = a5;
      v18 = 1;
      bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
      return 0;
    }
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
    goto LABEL_24;
  }
  if ( a3 != 8 )
  {
    v5 = a3 - 2;
    if ( v5 )
    {
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
LABEL_24:
          v17 = a5;
          v18 = 1;
          bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
          return 0;
        }
        v17 = a5;
        v18 = 1;
        v10 = bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>::AssignToField<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,unsigned short,6,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::value<unsigned short,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(
                a4,
                a2,
                a1,
                &v17);
        bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
      }
      else
      {
        v17 = a5;
        v18 = 1;
        v10 = bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>::AssignToField<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,unsigned short,6,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::value<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(
                a4,
                a2,
                a1,
                (__int64)&v17);
        bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
      }
    }
    else
    {
      v17 = a5;
      v18 = 1;
      v10 = bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>::AssignToField<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<6>,bond::reflection::FieldTemplate<5,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,bool,5,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_interactionFeedbackEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<5>,bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,bool,4,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_inkFeedbackEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<4>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,bool,3,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<3>,bond::reflection::FieldTemplate<2,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,bool,2,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_rightMaskEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,bool,1,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_allowPenAsMouse_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,bool,0,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_allowIgnoreTouchWithPen_metadata>,boost::mpl::l_end>>>>>>>,bond::value<bool,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(
              a4,
              a2,
              a1,
              (__int64)&v17);
      bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
    }
    return v10;
  }
  v17 = a5;
  v18 = 1;
  bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
  return 0;
}

```

## disassembly

```asm
0x18000b018  mov     [rsp-8+arg_0], rbx
0x18000b01d  push    rbp
0x18000b01e  mov     rbp, rsp
0x18000b021  sub     rsp, 30h
0x18000b025  mov     r10, r9
0x18000b028  cmp     r8d, 8
0x18000b02c  jg      loc_18000B150
0x18000b032  jz      loc_18000B136
0x18000b038  sub     r8d, 2
0x18000b03c  jz      loc_18000B108
0x18000b042  sub     r8d, 1
0x18000b046  jz      loc_18000B0DF
0x18000b04c  sub     r8d, 1
0x18000b050  jz      short loc_18000B0B6
0x18000b052  sub     r8d, 1
0x18000b056  jz      short loc_18000B09C
0x18000b058  sub     r8d, 1
0x18000b05c  jz      short loc_18000B082
0x18000b05e  cmp     r8d, 1
0x18000b062  jnz     loc_18000B204
0x18000b068  mov     rax, [rbp+arg_20]
0x18000b06c  mov     [rbp+var_10], rax
0x18000b070  mov     [rbp+var_8], r8b
0x18000b074  lea     rcx, [rbp+var_10]
0x18000b078  call    ??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b07d  jmp     loc_18000B204
0x18000b082  mov     rax, [rbp+arg_20]
0x18000b086  mov     [rbp+var_10], rax
0x18000b08a  mov     [rbp+var_8], 1
0x18000b08e  lea     rcx, [rbp+var_10]
0x18000b092  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b097  jmp     loc_18000B204
0x18000b09c  mov     rax, [rbp+arg_20]
0x18000b0a0  mov     [rbp+var_10], rax
0x18000b0a4  mov     [rbp+var_8], 1
0x18000b0a8  lea     rcx, [rbp+var_10]
0x18000b0ac  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b0b1  jmp     loc_18000B204
0x18000b0b6  mov     rax, [rbp+arg_20]
0x18000b0ba  mov     [rbp+var_10], rax
0x18000b0be  mov     [rbp+var_8], 1
0x18000b0c2  lea     r9, [rbp+var_10]
0x18000b0c6  movzx   r8d, cx
0x18000b0ca  mov     rcx, r10
0x18000b0cd  call    ??$AssignToField@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$05Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@G$05$1?s_feedbackIntensity_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$value@GAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@?$To@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@AEBA_NAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$05Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@G$05$1?s_feedbackIntensity_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@GAEBV?$value@GAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@1@@Z; bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>::AssignToField<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,ushort,6,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::value<ushort,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,ushort,6,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>> const &,ushort,bond::value<ushort,bond::CompactBinaryReader<bond::InputBuffer> &,void> const &)
0x18000b0d2  mov     bl, al
0x18000b0d4  lea     rcx, [rbp+var_10]
0x18000b0d8  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b0dd  jmp     short loc_18000B12F
0x18000b0df  mov     rax, [rbp+arg_20]
0x18000b0e3  mov     [rbp+var_10], rax
0x18000b0e7  mov     [rbp+var_8], 1
0x18000b0eb  lea     r9, [rbp+var_10]
0x18000b0ef  movzx   r8d, cx
0x18000b0f3  mov     rcx, r10
0x18000b0f6  call    ??$AssignToField@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$05Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@G$05$1?s_feedbackIntensity_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$value@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@?$To@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@AEBA_NAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$05Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@G$05$1?s_feedbackIntensity_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@GAEBV?$value@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@1@@Z; bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>>::AssignToField<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,ushort,6,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>>,bond::value<uchar,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<6,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSettings,ushort,6,&bond::Metadata const Windows::Data::Input::Devices::PenSettings::Schema::s_feedbackIntensity_metadata>,boost::mpl::l_end>> const &,ushort,bond::value<uchar,bond::CompactBinaryReader<bond::InputBuffer> &,void> const &)
0x18000b0fb  mov     bl, al
0x18000b0fd  lea     rcx, [rbp+var_10]
0x18000b101  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b106  jmp     short loc_18000B12F
0x18000b108  mov     rax, [rbp+arg_20]
0x18000b10c  mov     [rbp+var_10], rax
0x18000b110  mov     [rbp+var_8], 1
0x18000b114  lea     r9, [rbp+var_10]
0x18000b118  movzx   r8d, cx
0x18000b11c  mov     rcx, r10
0x18000b11f  call    ??$AssignToField@U?$l_iter@U?$l_item@U?$long_@$05@mpl@boost@@U?$FieldTemplate@$04Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$04$1?s_interactionFeedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$04@mpl@boost@@U?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$03$1?s_inkFeedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$02$1?s_feedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$01$1?s_rightMaskEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowPenAsMouse_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_allowIgnoreTouchWithPen_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@V?$value@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@?$To@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@AEBA_NAEBU?$l_iter@U?$l_item@U?$long_@$05@mpl@boost@@U?$FieldTemplate@$04Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$04$1?s_interactionFeedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$04@mpl@boost@@U?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$03$1?s_inkFeedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$02$1?s_feedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$01$1?s_rightMaskEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowPenAsMouse_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_allowIgnoreTouchWithPen_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@GAEBV?$value@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@1@@Z
0x18000b124  mov     bl, al
0x18000b126  lea     rcx, [rbp+var_10]
0x18000b12a  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b12f  mov     al, bl
0x18000b131  jmp     loc_18000B206
0x18000b136  mov     rax, [rbp+arg_20]
0x18000b13a  mov     [rbp+var_10], rax
0x18000b13e  mov     [rbp+var_8], 1
0x18000b142  lea     rcx, [rbp+var_10]
0x18000b146  call    ??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b14b  jmp     loc_18000B204
0x18000b150  sub     r8d, 9
0x18000b154  jz      loc_18000B1EF
0x18000b15a  sub     r8d, 5
0x18000b15e  jz      short loc_18000B1D8
0x18000b160  sub     r8d, 1
0x18000b164  jz      short loc_18000B1C1
0x18000b166  sub     r8d, 1
0x18000b16a  jz      short loc_18000B1AA
0x18000b16c  sub     r8d, 1
0x18000b170  jz      short loc_18000B193
0x18000b172  cmp     r8d, 1
0x18000b176  jnz     loc_18000B204
0x18000b17c  mov     rax, [rbp+arg_20]
0x18000b180  mov     [rbp+var_10], rax
0x18000b184  mov     [rbp+var_8], r8b
0x18000b188  lea     rcx, [rbp+var_10]
0x18000b18c  call    ??1?$value_common@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b191  jmp     short loc_18000B204
0x18000b193  mov     rax, [rbp+arg_20]
0x18000b197  mov     [rbp+var_10], rax
0x18000b19b  mov     [rbp+var_8], 1
0x18000b19f  lea     rcx, [rbp+var_10]
0x18000b1a3  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b1a8  jmp     short loc_18000B204
0x18000b1aa  mov     rax, [rbp+arg_20]
0x18000b1ae  mov     [rbp+var_10], rax
0x18000b1b2  mov     [rbp+var_8], 1
0x18000b1b6  lea     rcx, [rbp+var_10]
0x18000b1ba  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b1bf  jmp     short loc_18000B204
0x18000b1c1  mov     rax, [rbp+arg_20]
0x18000b1c5  mov     [rbp+var_10], rax
0x18000b1c9  mov     [rbp+var_8], 1
0x18000b1cd  lea     rcx, [rbp+var_10]
0x18000b1d1  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b1d6  jmp     short loc_18000B204
0x18000b1d8  mov     rax, [rbp+arg_20]
0x18000b1dc  mov     [rbp+var_10], rax
0x18000b1e0  mov     [rbp+var_8], 1
0x18000b1e4  lea     rcx, [rbp+var_10]
0x18000b1e8  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b1ed  jmp     short loc_18000B204
0x18000b1ef  mov     rax, [rbp+arg_20]
0x18000b1f3  mov     [rbp+var_10], rax
0x18000b1f7  mov     [rbp+var_8], 1
0x18000b1fb  lea     rcx, [rbp+var_10]
0x18000b1ff  call    ??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b204  xor     al, al
0x18000b206  mov     rbx, [rsp+30h+arg_0]
0x18000b20b  add     rsp, 30h
0x18000b20f  pop     rbp
0x18000b210  retn
```
