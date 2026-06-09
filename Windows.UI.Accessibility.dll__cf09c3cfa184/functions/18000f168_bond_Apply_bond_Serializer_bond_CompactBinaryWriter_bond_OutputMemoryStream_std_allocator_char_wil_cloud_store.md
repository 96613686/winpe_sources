# bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme> const &)

- ea: `0x18000f168`
- end: `0x18000f201`
- name: `??$Apply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@0@AEBV?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@Z`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f640`
- `0x180011d9c`

## callees

- `0x18000f168`
- `0x18000f640`
- `0x18000ff20`
- `0x180010818`
- `0x18001088c`

## pseudocode

```c
char __fastcall bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>(
        __int64 a1,
        __int64 a2)
{
  __int64 *v2; // r8
  unsigned int **v4; // rcx
  bool v6; // zf
  unsigned int *v7; // rdx
  char v8; // di
  __int64 v9; // rcx
  __int64 v10; // [rsp+20h] [rbp-28h] BYREF
  char v11; // [rsp+28h] [rbp-20h]
  bool v12; // [rsp+50h] [rbp+8h] BYREF

  v2 = *(__int64 **)a1;
  v4 = (unsigned int **)(*(_QWORD *)a1 + 8LL);
  if ( *((_WORD *)v2 + 8) == 2 && !*v4 )
    return bond::detail::DoublePassApply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>(a1);
  v6 = *(_BYTE *)(a1 + 8) == 0;
  v10 = a2;
  v11 = 0;
  if ( v6 && *((_WORD *)v2 + 8) == 2 )
  {
    v7 = (*v4)++;
    bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<unsigned int>(*v2, *v7);
  }
  v8 = bond::StaticParser<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme> const &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<5>,bond::reflection::FieldTemplate<10,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,0,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isInitialized_metadata>,boost::mpl::l_item<boost::mpl::long_<4>,bond::reflection::FieldTemplate<20,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,1,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isStartFocusTimerEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<3>,bond::reflection::FieldTemplate<30,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,2,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarBadgesEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<40,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,3,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarFlashesEnabled_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<50,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusSessionActiveTheme,bool,4,&private: static bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isMuteNotificationsEnabled_metadata>,boost::mpl::l_end>>>>>>,bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>>(
         &v10,
         a2,
         a1);
  v9 = **(_QWORD **)a1;
  v12 = *(_BYTE *)(a1 + 8) != 0;
  bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned char>(v9, (char *)&v12);
  return v8;
}

```

## disassembly

```asm
0x18000f168  mov     [rsp+arg_8], rbx
0x18000f16d  push    rdi
0x18000f16e  sub     rsp, 40h
0x18000f172  mov     r8, [rcx]
0x18000f175  mov     eax, 2
0x18000f17a  mov     rbx, rcx
0x18000f17d  lea     rcx, [r8+8]
0x18000f181  cmp     ax, [r8+10h]
0x18000f186  jnz     short loc_18000F198
0x18000f188  cmp     qword ptr [rcx], 0
0x18000f18c  jnz     short loc_18000F198
0x18000f18e  mov     rcx, rbx
0x18000f191  call    ??$DoublePassApply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@detail@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@1@AEBV?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@Z; bond::detail::DoublePassApply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme> const &)
0x18000f196  jmp     short loc_18000F1F6
0x18000f198  cmp     byte ptr [rbx+8], 0
0x18000f19c  mov     [rsp+48h+var_28], rdx
0x18000f1a1  mov     [rsp+48h+var_20], 0
0x18000f1a6  jnz     short loc_18000F1C3
0x18000f1a8  cmp     ax, [r8+10h]
0x18000f1ad  jnz     short loc_18000F1C3
0x18000f1af  mov     rdx, [rcx]
0x18000f1b2  lea     rax, [rdx+4]
0x18000f1b6  mov     [rcx], rax
0x18000f1b9  mov     edx, [rdx]
0x18000f1bb  mov     rcx, [r8]
0x18000f1be  call    ??$WriteVariableUnsigned@I@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXI@Z; bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<uint>(uint)
0x18000f1c3  mov     r8, rbx
0x18000f1c6  lea     rcx, [rsp+48h+var_28]
0x18000f1cb  call    ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$04@mpl@boost@@U?$FieldTemplate@$09Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$0A@$1?s_isInitialized_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$0BE@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$00$1?s_isStartFocusTimerEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$0BO@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$01$1?s_isHideTaskbarBadgesEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0CI@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$02$1?s_isHideTaskbarFlashesEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0DC@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$03$1?s_isMuteNotificationsEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@@?$StaticParser@AEBV?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@bond@@AEAA_NAEBU?$l_iter@U?$l_item@U?$long_@$04@mpl@boost@@U?$FieldTemplate@$09Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$0A@$1?s_isInitialized_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$0BE@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$00$1?s_isStartFocusTimerEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$0BO@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$01$1?s_isHideTaskbarBadgesEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0CI@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$02$1?s_isHideTaskbarFlashesEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0DC@Uoptional_field_modifier@reflection@bond@@UFocusSessionActiveTheme@Shell@Data@Windows@@_N$03$1?s_isMuteNotificationsEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@AEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@1@@Z
0x18000f1d0  cmp     byte ptr [rbx+8], 0
0x18000f1d4  lea     rdx, [rsp+48h+arg_0]
0x18000f1d9  mov     rcx, [rbx]
0x18000f1dc  mov     dil, al
0x18000f1df  mov     [rsp+48h+arg_0], 1
0x18000f1e4  mov     rcx, [rcx]
0x18000f1e7  jnz     short loc_18000F1EE
0x18000f1e9  mov     [rsp+48h+arg_0], 0
0x18000f1ee  call    ??$Write@E@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBE@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<uchar>(uchar const &)
0x18000f1f3  mov     al, dil
0x18000f1f6  mov     rbx, [rsp+48h+arg_8]
0x18000f1fb  add     rsp, 40h
0x18000f1ff  pop     rdi
0x18000f200  retn
```
