# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::Apply<Windows::Data::Input::Devices::MouseSettings::Schema,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>>(bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>> const &,Windows::Data::Input::Devices::MouseSettings::Schema const &)

- ea: `0x180009cb0`
- end: `0x180009d47`
- name: `??$Apply@USchema@MouseSettings@Devices@Input@Data@Windows@@V?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA_NAEBV?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@AEBUSchema@MouseSettings@Devices@Input@Data@Windows@@@Z`
- size: `151`
- prototype: `char __fastcall(__int64, _WORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800181fc`

## callees

- `0x180009cb0`
- `0x18000ede0`
- `0x18002099c`
- `0x180020a28`
- `0x180022000`

## pseudocode

```c
char __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::Apply<Windows::Data::Input::Devices::MouseSettings::Schema,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>>(
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
  bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<4>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,unsigned short,0,&private: static bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_mousePointerSpeed_metadata>,boost::mpl::l_item<boost::mpl::long_<3>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,2,&private: static bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollPage_metadata>,boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<2,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,unsigned short,4,&private: static bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_scrollLines_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::MouseSettings,bool,6,&private: static bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata>,boost::mpl::l_end>>>>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>>(
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
0x180009cb0  mov     [rsp+arg_8], rbx
0x180009cb5  mov     [rsp+arg_10], r8
0x180009cba  push    rdi
0x180009cbb  sub     rsp, 30h
0x180009cbf  mov     rbx, rdx
0x180009cc2  mov     rdi, rcx
0x180009cc5  mov     dl, [rcx+8]
0x180009cc8  mov     rcx, [rcx]
0x180009ccb  call    ?ReadStructBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAX_N@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadStructBegin(bool)
0x180009cd0  xor     eax, eax
0x180009cd2  mov     word ptr [rbx], 0FFFFh
0x180009cd7  mov     rcx, [rdi]; this
0x180009cda  lea     r8, [rsp+38h+arg_10]
0x180009cdf  lea     rdx, [rsp+38h+arg_0]
0x180009ce4  mov     word ptr [rsp+38h+arg_10], ax
0x180009ce9  mov     [rsp+38h+arg_0], eax
0x180009ced  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180009cf2  lea     r9, [rsp+38h+arg_0]
0x180009cf7  mov     [rsp+38h+var_18], rbx
0x180009cfc  lea     r8, [rsp+38h+arg_10]
0x180009d01  mov     rcx, rdi
0x180009d04  call    ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@G$0A@$1?s_mousePointerSpeed_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@_N$01$1?s_allowScrollPage_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@G$03$1?s_scrollLines_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@_N$05$1?s_allowScrollInactiveWindows_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@G$0A@$1?s_mousePointerSpeed_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@_N$01$1?s_allowScrollPage_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@G$03$1?s_scrollLines_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UMouseSettings@Devices@Input@Data@Windows@@_N$05$1?s_allowScrollInactiveWindows_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z
0x180009d09  cmp     byte ptr [rdi+8], 0
0x180009d0d  jnz     short loc_180009D3A
0x180009d0f  jmp     short loc_180009D32
0x180009d11  cmp     eax, 1
0x180009d14  jz      short loc_180009D20
0x180009d16  mov     rcx, [rdi]; this
0x180009d19  mov     edx, eax
0x180009d1b  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180009d20  mov     rcx, [rdi]; this
0x180009d23  lea     r8, [rsp+38h+arg_10]
0x180009d28  lea     rdx, [rsp+38h+arg_0]
0x180009d2d  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180009d32  mov     eax, [rsp+38h+arg_0]
0x180009d36  test    eax, eax
0x180009d38  jnz     short loc_180009D11
0x180009d3a  mov     rbx, [rsp+38h+arg_8]
0x180009d3f  xor     al, al
0x180009d41  add     rsp, 30h
0x180009d45  pop     rdi
0x180009d46  retn
```
