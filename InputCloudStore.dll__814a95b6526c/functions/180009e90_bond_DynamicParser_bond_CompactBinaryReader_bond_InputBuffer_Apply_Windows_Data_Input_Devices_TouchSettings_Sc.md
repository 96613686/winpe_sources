# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::Apply<Windows::Data::Input::Devices::TouchSettings::Schema,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>>(bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>> const &,Windows::Data::Input::Devices::TouchSettings::Schema const &)

- ea: `0x180009e90`
- end: `0x180009f27`
- name: `??$Apply@USchema@TouchSettings@Devices@Input@Data@Windows@@V?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA_NAEBV?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@AEBUSchema@TouchSettings@Devices@Input@Data@Windows@@@Z`
- size: `151`
- prototype: `char __fastcall(__int64, _WORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018f98`

## callees

- `0x180009e90`
- `0x18000e2dc`
- `0x18002099c`
- `0x180020a28`
- `0x180022000`

## pseudocode

```c
char __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::Apply<Windows::Data::Input::Devices::TouchSettings::Schema,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>>(
        __int64 a1,
        _WORD *a2,
        __int64 a3)
{
  _WORD *v3; // rbx
  bond::InputBuffer *v5; // rcx
  int v6; // edx
  int v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = a3;
  v3 = a2;
  LOBYTE(a2) = *(_BYTE *)(a1 + 8);
  bond::CompactBinaryReader<bond::InputBuffer>::ReadStructBegin(*(_QWORD *)a1, a2);
  *v3 = -1;
  v5 = *(bond::InputBuffer **)a1;
  LOWORD(v9) = 0;
  v8 = 0;
  bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(v5);
  bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,0,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchGestures_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>>(
    a1,
    v6,
    (unsigned int)&v9,
    (unsigned int)&v8,
    (__int64)v3);
  if ( !*(_BYTE *)(a1 + 8) )
  {
    while ( v8 )
    {
      if ( v8 != 1 )
        bond::CompactBinaryReader<bond::InputBuffer>::Skip(*(bond::InputBuffer **)a1);
      bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*(bond::InputBuffer **)a1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009e90  mov     [rsp+arg_8], rbx
0x180009e95  mov     [rsp+arg_10], r8
0x180009e9a  push    rdi
0x180009e9b  sub     rsp, 30h
0x180009e9f  mov     rbx, rdx
0x180009ea2  mov     rdi, rcx
0x180009ea5  mov     dl, [rcx+8]
0x180009ea8  mov     rcx, [rcx]
0x180009eab  call    ?ReadStructBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAX_N@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadStructBegin(bool)
0x180009eb0  xor     eax, eax
0x180009eb2  mov     word ptr [rbx], 0FFFFh
0x180009eb7  mov     rcx, [rdi]; this
0x180009eba  lea     r8, [rsp+38h+arg_10]
0x180009ebf  lea     rdx, [rsp+38h+arg_0]
0x180009ec4  mov     word ptr [rsp+38h+arg_10], ax
0x180009ec9  mov     [rsp+38h+arg_0], eax
0x180009ecd  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180009ed2  lea     r9, [rsp+38h+arg_0]
0x180009ed7  mov     [rsp+38h+var_18], rbx
0x180009edc  lea     r8, [rsp+38h+arg_10]
0x180009ee1  mov     rcx, rdi
0x180009ee4  call    ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_allowTouchGestures_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowTouchScreenWake_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_allowTouchGestures_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowTouchScreenWake_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,0,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchGestures_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,0,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchGestures_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata>,boost::mpl::l_end>>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>> const &)
0x180009ee9  cmp     byte ptr [rdi+8], 0
0x180009eed  jnz     short loc_180009F1A
0x180009eef  jmp     short loc_180009F12
0x180009ef1  cmp     eax, 1
0x180009ef4  jz      short loc_180009F00
0x180009ef6  mov     rcx, [rdi]; this
0x180009ef9  mov     edx, eax
0x180009efb  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180009f00  mov     rcx, [rdi]; this
0x180009f03  lea     r8, [rsp+38h+arg_10]
0x180009f08  lea     rdx, [rsp+38h+arg_0]
0x180009f0d  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180009f12  mov     eax, [rsp+38h+arg_0]
0x180009f16  test    eax, eax
0x180009f18  jnz     short loc_180009EF1
0x180009f1a  mov     rbx, [rsp+38h+arg_8]
0x180009f1f  xor     al, al
0x180009f21  add     rsp, 30h
0x180009f25  pop     rdi
0x180009f26  retn
```
