# bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings> const &)

- ea: `0x18000a0b8`
- end: `0x18000a151`
- name: `??$Apply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@0@AEBV?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@Z`
- size: `153`
- prototype: `char __fastcall(_BYTE *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bfe0`
- `0x180016208`

## callees

- `0x18000a0b8`
- `0x18000bfe0`
- `0x18000f874`
- `0x180011bcc`
- `0x180011cac`

## pseudocode

```c
char __fastcall bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>(
        _BYTE *a1,
        __int64 a2)
{
  _QWORD *v2; // r8
  unsigned int **v4; // rcx
  bool v6; // zf
  unsigned int *v7; // rdx
  char v8; // di
  __int64 v9; // rcx
  __int64 v10; // [rsp+20h] [rbp-28h] BYREF
  char v11; // [rsp+28h] [rbp-20h]
  bool v12; // [rsp+50h] [rbp+8h] BYREF

  v2 = *(_QWORD **)a1;
  v4 = (unsigned int **)(*(_QWORD *)a1 + 8LL);
  if ( *((_WORD *)v2 + 8) == 2 && !*v4 )
    return bond::detail::DoublePassApply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>(a1);
  v6 = a1[8] == 0;
  v10 = a2;
  v11 = 0;
  if ( v6 && *((_WORD *)v2 + 8) == 2 )
  {
    v7 = (*v4)++;
    bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<unsigned int>(*v2, *v7);
  }
  v8 = ___ReadFields_U__l_iter_U__l_item_U__long___06_mpl_boost__U__FieldTemplate__0A_Uoptional_field_modifier_reflection_bond__UPenSettings_Devices_Input_Data_Windows___N_0A__1_s_allowIgnoreTouchWithPen_metadata_Schema_PenSettings_Devices_Input_Data_Windows__0UMetadata_bond__B_reflection_bond__U__l_item_U__long___05_mpl_boost__U__FieldTemplate__00Uoptional_field_modifier_reflection_bond__UPenSettings_Devices_Input_Data_Windows___N_00_1_s_allowPenAsMouse_metadata_Schema_PenSettings_Devices_Input_Data_Windows__0UMetadata_bond__B_reflection_bond__U__l_item_U__long___04_mpl_boost__U__FieldTemplate__01Uoptional_field_modifier_reflection_bond__UPenSettings_Devices_Input_Data_Windows___N_01_1_s_rightMaskEnabled_metadata_Schema_PenSettings_Devices_Input_Data_Windows__0UMetadata_bond__B_reflection_bond__U__l_item_U__long___03_mpl_boost__U__FieldTemplate__02Uoptional_field_modifier_reflection_bond__UPenSettings_Devices_Input_Data_Windows___N_02_1_s_feedbackEnabled_metadata_Schema_PenSettings_Devices_Input_Data_Windows__0UMetadata_bond__B_reflection_bond__U__l_item_U__long___02_mpl_boost__U__FieldTemplate__03Uoptional_field_modifier_reflection_bond__UPenSettings_Devices_Input_Data_Windows___N_03_1_s_inkFeedbackEnabled_metadata_Schema_PenSettings_Devices_Input_Data_Windows__0UMetadata_bond__B_reflection_bond__U__l_item_U__long___01_mpl_boost__U__FieldTemplate__04Uoptional_field_modifier_reflection_bond__UPenSettings_Devices_Input_Data_Windows___N_04_1_s_interactionFeedbackEnabled_metadata_Schema_PenSettings_Devices_Input_Data_Windows__0UMetadata_bond__B_reflection_bond__U__l_item_U__long___00_mpl_boost__U__FieldTemplate__05Uoptional_field_modifier_reflection_bond__UPenSettings_Devices_Input_Data_Windows__G_05_1_s_feedbackIntensity_metadata_Schema_PenSettings_Devices_Input_Data_Windows__0UMetadata_bond__B_reflection_bond__Ul_end_23__23__23__23__23__23__23__mpl_boost___mpl_boost__V__Serializer_V__CompactBinaryWriter_V__OutputMemoryStream_V__allocator_D_std___bond___bond___bond_____StaticParser_AEBV__cloud_store_data_UPenSettings_Devices_Input_Data_Windows___wil___bond__AEAA_NAEBU__l_iter_U__l_item_U__long___06_mpl_boost__U__FieldTemplate__0A_Uoptional_field_modifier_reflection_bond__UPenSettings_Devices_Input_Data_Windows___N_0A__1_s_allowIgnoreTouchWithPen_metadata_Schema_PenSettings_Devices_Input_Data_Windows__0UMetadata_bond__B_reflection_bond__U__l_item_U__long___05_mpl_boost__U__FieldTemplate__00Uoptional_field_modifier_reflection_bond__UPenSettings_Devices_Input_Data_Windows___N_00_1_s_allowPenAsMouse_metadata_Schema_PenSettings_Devices_Input_Data_Windows__0UMetadata_bond__B_reflection_bond__U__l_item_U__long___04_mpl_boost__U__FieldTemplate__01Uoptional_field_modifier_reflection_bond__UPenSettings_Devices_Input_Data_Windows___N_01_1_s_rightMaskEnabled_metadata_Schema_PenSettings_Devices_Input_Data_Windows__0UMetadata_bond__B_reflection_bond__U__l_item_U__long___03_mpl_boost__U__FieldTemplate__02Uoptional_field_modifier_reflection_bond__UPenSettings_Devices_Input_Data_Windows___N_02_1_s_feedbackEnabled_metadata_Schema_PenSettings_Devices_Input_Data_Windows__0UMetadata_bond__B_reflection_bond__U__l_item_U__long___02_mpl_boost__U__FieldTemplate__03Uoptional_field_modifier_reflection_bond__UPenSettings_Devices_Input_Data_Windows___N_03_1_s_inkFeedbackEnabled_metadata_Schema_PenSettings_Devices_Input_Data_Windows__0UMetadata_bond__B_reflection_bond__U__l_item_U__long___01_mpl_boost__U__FieldTemplate__04Uoptional_field_modifier_reflection_bond__UPenSettings_Devices_Input_Data_Windows___N_04_1_s_interactionFeedbackEnabled_metadata_Schema_PenSettings_Devices_Input_Data_Windows__0UMetadata_bond__B_reflection_bond__U__l_item_U__long___00_mpl_boost__U__FieldTemplate__05Uoptional_field_modifier_reflection_bond__UPenSettings_Devices_Input_Data_Windows__G_05_1_s_feedbackIntensity_metadata_Schema_PenSettings_Devices_Input_Data_Windows__0UMetadata_bond__B_reflection_bond__Ul_end_23__23__23__23__23__23__23__mpl_boost___mpl_boost__AEBV__Serializer_V__CompactBinaryWriter_V__OutputMemoryStream_V__allocator_D_std___bond___bond___1__Z(
         &v10,
         a2,
         a1);
  v9 = **(_QWORD **)a1;
  v12 = a1[8] != 0;
  bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned char>(v9, &v12);
  return v8;
}

```

## disassembly

```asm
0x18000a0b8  mov     [rsp+arg_8], rbx
0x18000a0bd  push    rdi
0x18000a0be  sub     rsp, 40h
0x18000a0c2  mov     r8, [rcx]
0x18000a0c5  mov     eax, 2
0x18000a0ca  mov     rbx, rcx
0x18000a0cd  lea     rcx, [r8+8]
0x18000a0d1  cmp     ax, [r8+10h]
0x18000a0d6  jnz     short loc_18000A0E8
0x18000a0d8  cmp     qword ptr [rcx], 0
0x18000a0dc  jnz     short loc_18000A0E8
0x18000a0de  mov     rcx, rbx
0x18000a0e1  call    ??$DoublePassApply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@detail@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@1@AEBV?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@Z; bond::detail::DoublePassApply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Input::Devices::PenSettings> const &)
0x18000a0e6  jmp     short loc_18000A146
0x18000a0e8  cmp     byte ptr [rbx+8], 0
0x18000a0ec  mov     [rsp+48h+var_28], rdx
0x18000a0f1  mov     [rsp+48h+var_20], 0
0x18000a0f6  jnz     short loc_18000A113
0x18000a0f8  cmp     ax, [r8+10h]
0x18000a0fd  jnz     short loc_18000A113
0x18000a0ff  mov     rdx, [rcx]
0x18000a102  lea     rax, [rdx+4]
0x18000a106  mov     [rcx], rax
0x18000a109  mov     edx, [rdx]
0x18000a10b  mov     rcx, [r8]
0x18000a10e  call    ??$WriteVariableUnsigned@I@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXI@Z; bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<uint>(uint)
0x18000a113  mov     r8, rbx
0x18000a116  lea     rcx, [rsp+48h+var_28]
0x18000a11b  call    ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$06@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_allowIgnoreTouchWithPen_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$05@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowPenAsMouse_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$04@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$01$1?s_rightMaskEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$02$1?s_feedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$03$1?s_inkFeedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$04Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$04$1?s_interactionFeedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$05Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@G$05$1?s_feedbackIntensity_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@@?$StaticParser@AEBV?$cloud_store_data@UPenSettings@Devices@Input@Data@Windows@@@wil@@@bond@@AEAA_NAEBU?$l_iter@U?$l_item@U?$long_@$06@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_allowIgnoreTouchWithPen_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$05@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowPenAsMouse_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$04@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$01$1?s_rightMaskEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$02$1?s_feedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$03$1?s_inkFeedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$04Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@_N$04$1?s_interactionFeedbackEnabled_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$05Uoptional_field_modifier@reflection@bond@@UPenSettings@Devices@Input@Data@Windows@@G$05$1?s_feedbackIntensity_metadata@Schema@PenSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@AEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@1@@Z
0x18000a120  cmp     byte ptr [rbx+8], 0
0x18000a124  lea     rdx, [rsp+48h+arg_0]
0x18000a129  mov     rcx, [rbx]
0x18000a12c  mov     dil, al
0x18000a12f  mov     [rsp+48h+arg_0], 1
0x18000a134  mov     rcx, [rcx]
0x18000a137  jnz     short loc_18000A13E
0x18000a139  mov     [rsp+48h+arg_0], 0
0x18000a13e  call    ??$Write@E@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBE@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<uchar>(uchar const &)
0x18000a143  mov     al, dil
0x18000a146  mov     rbx, [rsp+48h+arg_8]
0x18000a14b  add     rsp, 40h
0x18000a14f  pop     rdi
0x18000a150  retn
```
