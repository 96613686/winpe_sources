# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::Apply<Windows::Data::Input::Devices::MouseSyncedSettings::Schema,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>>>>(bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>>> const &,Windows::Data::Input::Devices::MouseSyncedSettings::Schema const &)

- ea: `0x180009d50`
- end: `0x180009de7`
- name: `??$Apply@USchema@MouseSyncedSettings@Devices@Input@Data@Windows@@V?$To@V?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA_NAEBV?$To@V?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@AEBUSchema@MouseSyncedSettings@Devices@Input@Data@Windows@@@Z`
- size: `151`
- prototype: `char __fastcall(__int64, _WORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800184c0`

## callees

- `0x180009d50`
- `0x18000de00`
- `0x18002099c`
- `0x180020a28`
- `0x180022000`

## pseudocode

```c
char __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::Apply<Windows::Data::Input::Devices::MouseSyncedSettings::Schema,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>>>>(
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
  bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSyncedSettings,bool,0,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchpadSyncedSettings::Schema::s_scrollInverted_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>>>>(
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
0x180009d50  mov     [rsp+arg_8], rbx
0x180009d55  mov     [rsp+arg_10], r8
0x180009d5a  push    rdi
0x180009d5b  sub     rsp, 30h
0x180009d5f  mov     rbx, rdx
0x180009d62  mov     rdi, rcx
0x180009d65  mov     dl, [rcx+8]
0x180009d68  mov     rcx, [rcx]
0x180009d6b  call    ?ReadStructBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAX_N@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadStructBegin(bool)
0x180009d70  xor     eax, eax
0x180009d72  mov     word ptr [rbx], 0FFFFh
0x180009d77  mov     rcx, [rdi]; this
0x180009d7a  lea     r8, [rsp+38h+arg_10]
0x180009d7f  lea     rdx, [rsp+38h+arg_0]
0x180009d84  mov     word ptr [rsp+38h+arg_10], ax
0x180009d89  mov     [rsp+38h+arg_0], eax
0x180009d8d  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180009d92  lea     r9, [rsp+38h+arg_0]
0x180009d97  mov     [rsp+38h+var_18], rbx
0x180009d9c  lea     r8, [rsp+38h+arg_10]
0x180009da1  mov     rcx, rdi
0x180009da4  call    ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_scrollInverted_metadata@Schema@TouchpadSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@_N$0A@$1?s_scrollInverted_metadata@Schema@TouchpadSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSyncedSettings,bool,0,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSyncedSettings::Schema::s_scrollInverted_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchpadSyncedSettings,bool,0,&bond::Metadata const Windows::Data::Input::Devices::TouchpadSyncedSettings::Schema::s_scrollInverted_metadata>,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>>> const &)
0x180009da9  cmp     byte ptr [rdi+8], 0
0x180009dad  jnz     short loc_180009DDA
0x180009daf  jmp     short loc_180009DD2
0x180009db1  cmp     eax, 1
0x180009db4  jz      short loc_180009DC0
0x180009db6  mov     rcx, [rdi]; this
0x180009db9  mov     edx, eax
0x180009dbb  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180009dc0  mov     rcx, [rdi]; this
0x180009dc3  lea     r8, [rsp+38h+arg_10]
0x180009dc8  lea     rdx, [rsp+38h+arg_0]
0x180009dcd  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180009dd2  mov     eax, [rsp+38h+arg_0]
0x180009dd6  test    eax, eax
0x180009dd8  jnz     short loc_180009DB1
0x180009dda  mov     rbx, [rsp+38h+arg_8]
0x180009ddf  xor     al, al
0x180009de1  add     rsp, 30h
0x180009de5  pop     rdi
0x180009de6  retn
```
