# bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings> const &)

- ea: `0x18000a158`
- end: `0x18000a1f1`
- name: `??$Apply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@0@AEBV?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@Z`
- size: `153`
- prototype: `char __fastcall(_BYTE *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c0e4`
- `0x18001630c`

## callees

- `0x18000a158`
- `0x18000c0e4`
- `0x18000f408`
- `0x180011bcc`
- `0x180011cac`

## pseudocode

```c
char __fastcall bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>(
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
    return bond::detail::DoublePassApply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>(a1);
  v6 = a1[8] == 0;
  v10 = a2;
  v11 = 0;
  if ( v6 && *((_WORD *)v2 + 8) == 2 )
  {
    v7 = (*v4)++;
    bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<unsigned int>(*v2, *v7);
  }
  v8 = bond::StaticParser<wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings> const &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<5>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,0,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_leftHanded_metadata>,boost::mpl::l_item<boost::mpl::long_<4>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,1,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_allowVisualEffects_metadata>,boost::mpl::l_item<boost::mpl::long_<3>,bond::reflection::FieldTemplate<2,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,2,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_allowPenCursor_metadata>,boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,3,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_allowDisplayKeysWithPen_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<4,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::PenSyncedSettings,bool,4,&private: static bond::Metadata const Windows::Data::Input::Devices::PenSyncedSettings::Schema::s_eraseEnabled_metadata>,boost::mpl::l_end>>>>>>,bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>>(
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
0x18000a158  mov     [rsp+arg_8], rbx
0x18000a15d  push    rdi
0x18000a15e  sub     rsp, 40h
0x18000a162  mov     r8, [rcx]
0x18000a165  mov     eax, 2
0x18000a16a  mov     rbx, rcx
0x18000a16d  lea     rcx, [r8+8]
0x18000a171  cmp     ax, [r8+10h]
0x18000a176  jnz     short loc_18000A188
0x18000a178  cmp     qword ptr [rcx], 0
0x18000a17c  jnz     short loc_18000A188
0x18000a17e  mov     rcx, rbx
0x18000a181  call    ??$DoublePassApply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@detail@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@1@AEBV?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@Z; bond::detail::DoublePassApply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Input::Devices::PenSyncedSettings> const &)
0x18000a186  jmp     short loc_18000A1E6
0x18000a188  cmp     byte ptr [rbx+8], 0
0x18000a18c  mov     [rsp+48h+var_28], rdx
0x18000a191  mov     [rsp+48h+var_20], 0
0x18000a196  jnz     short loc_18000A1B3
0x18000a198  cmp     ax, [r8+10h]
0x18000a19d  jnz     short loc_18000A1B3
0x18000a19f  mov     rdx, [rcx]
0x18000a1a2  lea     rax, [rdx+4]
0x18000a1a6  mov     [rcx], rax
0x18000a1a9  mov     edx, [rdx]
0x18000a1ab  mov     rcx, [r8]
0x18000a1ae  call    ??$WriteVariableUnsigned@I@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXI@Z; bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<uint>(uint)
0x18000a1b3  mov     r8, rbx
0x18000a1b6  lea     rcx, [rsp+48h+var_28]
0x18000a1bb  call    ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$04@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_leftHanded_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowVisualEffects_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$01$1?s_allowPenCursor_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$02$1?s_allowDisplayKeysWithPen_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$03$1?s_eraseEnabled_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@@?$StaticParser@AEBV?$cloud_store_data@UPenSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@AEAA_NAEBU?$l_iter@U?$l_item@U?$long_@$04@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_leftHanded_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowVisualEffects_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$01$1?s_allowPenCursor_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$02$1?s_allowDisplayKeysWithPen_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$03Uoptional_field_modifier@reflection@bond@@UPenSyncedSettings@Devices@Input@Data@Windows@@_N$03$1?s_eraseEnabled_metadata@Schema@PenSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@AEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@1@@Z
0x18000a1c0  cmp     byte ptr [rbx+8], 0
0x18000a1c4  lea     rdx, [rsp+48h+arg_0]
0x18000a1c9  mov     rcx, [rbx]
0x18000a1cc  mov     dil, al
0x18000a1cf  mov     [rsp+48h+arg_0], 1
0x18000a1d4  mov     rcx, [rcx]
0x18000a1d7  jnz     short loc_18000A1DE
0x18000a1d9  mov     [rsp+48h+arg_0], 0
0x18000a1de  call    ??$Write@E@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBE@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<uchar>(uchar const &)
0x18000a1e3  mov     al, dil
0x18000a1e6  mov     rbx, [rsp+48h+arg_8]
0x18000a1eb  add     rsp, 40h
0x18000a1ef  pop     rdi
0x18000a1f0  retn
```
