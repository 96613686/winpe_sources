# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfileCost,unsigned __int64,0,&bond::Metadata const Windows::Data::WiFi::WiFiProfileCost::Schema::s_dusmConnectionCost_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfileCost,unsigned __int64,8,&bond::Metadata const Windows::Data::WiFi::WiFiProfileCost::Schema::s_lastModifiedTime_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfileCost,unsigned __int64,0,&bond::Metadata const Windows::Data::WiFi::WiFiProfileCost::Schema::s_dusmConnectionCost_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfileCost,unsigned __int64,8,&bond::Metadata const Windows::Data::WiFi::WiFiProfileCost::Schema::s_lastModifiedTime_metadata>,boost::mpl::l_end>>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>>> const &)

- ea: `0x18000260c`
- end: `0x18000277b`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UWiFiProfileCost@WiFi@Data@Windows@@_K$0A@$1?s_dusmConnectionCost_metadata@Schema@WiFiProfileCost@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UWiFiProfileCost@WiFi@Data@Windows@@_K$07$1?s_lastModifiedTime_metadata@Schema@WiFiProfileCost@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UWiFiProfileCost@WiFi@Data@Windows@@_K$0A@$1?s_dusmConnectionCost_metadata@Schema@WiFiProfileCost@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UWiFiProfileCost@WiFi@Data@Windows@@_K$07$1?s_lastModifiedTime_metadata@Schema@WiFiProfileCost@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `367`
- prototype: `__int64 __fastcall(bond::InputBuffer **, __int64, unsigned __int16 *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002834`

## callees

- `0x18000260c`
- `0x180002a00`
- `0x1800031d4`
- `0x180019b6c`
- `0x180026f0c`
- `0x1800338d0`
- `0x18003396c`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfileCost,unsigned __int64,0,&private: static bond::Metadata const Windows::Data::WiFi::WiFiProfileCost::Schema::s_dusmConnectionCost_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfileCost,unsigned __int64,8,&private: static bond::Metadata const Windows::Data::WiFi::WiFiProfileCost::Schema::s_lastModifiedTime_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>>>>(
        bond::InputBuffer **a1,
        __int64 a2,
        unsigned __int16 *a3,
        _DWORD *a4,
        __int64 a5)
{
  unsigned __int16 v8; // cx
  __int64 result; // rax
  bond::InputBuffer *v10; // [rsp+30h] [rbp-38h] BYREF
  char v11; // [rsp+38h] [rbp-30h]

  while ( 1 )
  {
    if ( !*a3 && *a4 == 6 )
    {
      v10 = *a1;
      v11 = 0;
      bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(v10);
      bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v10);
      goto LABEL_11;
    }
    v8 = *a3;
    if ( *a3 || *a4 < 2u )
      break;
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfileCost,unsigned __int64,0,&private: static bond::Metadata const Windows::Data::WiFi::WiFiProfileCost::Schema::s_dusmConnectionCost_metadata>,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>>>>(
      a1,
      a2,
      0);
LABEL_11:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
    v8 = *a3;
    if ( *a3 || *a4 <= 1u )
      goto LABEL_3;
  }
  do
  {
LABEL_3:
    if ( v8 == 1 )
    {
      if ( *a4 == 6 )
      {
        v10 = *a1;
        v11 = 0;
        bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(v10);
        bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v10);
        goto LABEL_18;
      }
    }
    else if ( v8 > 1u )
    {
      break;
    }
    if ( *a4 <= 1u )
      break;
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfileCost,unsigned __int64,8,&private: static bond::Metadata const Windows::Data::WiFi::WiFiProfileCost::Schema::s_lastModifiedTime_metadata>,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>>>>(
      a1,
      a2,
      v8,
      (unsigned int)*a4,
      a5);
LABEL_18:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
    v8 = *a3;
  }
  while ( *a3 <= 1u && *a4 > 1u );
  while ( 1 )
  {
    result = (unsigned int)*a4;
    if ( (unsigned int)result <= 1 )
      break;
    bond::CompactBinaryReader<bond::InputBuffer>::Skip(*a1);
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  return result;
}

```

## disassembly

```asm
0x18000260c  push    rbx
0x18000260e  push    rbp
0x18000260f  push    rsi
0x180002610  push    rdi
0x180002611  push    r15
0x180002613  sub     rsp, 40h
0x180002617  mov     rbx, r9
0x18000261a  mov     rsi, r8
0x18000261d  mov     rdi, rcx
0x180002620  mov     r15d, 1
0x180002626  mov     rbp, [rsp+68h+arg_20]
0x18000262e  xor     eax, eax
0x180002630  cmp     ax, [rsi]
0x180002633  jz      short loc_180002662
0x180002635  movzx   ecx, word ptr [rsi]
0x180002638  cmp     ax, cx
0x18000263b  jnb     short loc_18000268A
0x18000263d  cmp     r15w, cx
0x180002641  jz      loc_1800026DA
0x180002647  jnb     loc_180002706
0x18000264d  mov     eax, [rbx]
0x18000264f  test    eax, eax
0x180002651  jnz     loc_180002755
0x180002657  add     rsp, 40h
0x18000265b  pop     r15
0x18000265d  pop     rdi
0x18000265e  pop     rsi
0x18000265f  pop     rbp
0x180002660  pop     rbx
0x180002661  retn
0x180002662  cmp     dword ptr [rbx], 6
0x180002665  jnz     short loc_180002635
0x180002667  mov     rcx, [rdi]; this
0x18000266a  mov     [rsp+68h+var_38], rcx
0x18000266f  mov     [rsp+68h+var_30], 0
0x180002674  mov     rdx, [rbp+8]
0x180002678  call    ??$ReadVariableUnsigned@_K@InputBuffer@bond@@QEAAXAEA_K@Z; bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(unsigned __int64 &)
0x18000267d  nop
0x18000267e  lea     rcx, [rsp+68h+var_38]
0x180002683  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180002688  jmp     short loc_1800026A8
0x18000268a  mov     r9d, [rbx]
0x18000268d  test    r9d, r9d
0x180002690  jz      short loc_18000263D
0x180002692  cmp     r9d, r15d
0x180002695  jz      short loc_18000263D
0x180002697  mov     [rsp+68h+var_48], rbp
0x18000269c  movzx   r8d, cx
0x1800026a0  mov     rcx, rdi
0x1800026a3  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UWiFiProfileCost@WiFi@Data@Windows@@_K$0A@$1?s_dusmConnectionCost_metadata@Schema@WiFiProfileCost@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UWiFiProfileCost@WiFi@Data@Windows@@_K$0A@$1?s_dusmConnectionCost_metadata@Schema@WiFiProfileCost@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfileCost,unsigned __int64,0,&bond::Metadata const Windows::Data::WiFi::WiFiProfileCost::Schema::s_dusmConnectionCost_metadata>,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>>>>(bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfileCost,unsigned __int64,0,&bond::Metadata const Windows::Data::WiFi::WiFiProfileCost::Schema::s_dusmConnectionCost_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>>> const &)
0x1800026a8  mov     r8, rsi
0x1800026ab  mov     rdx, rbx
0x1800026ae  mov     rcx, [rdi]; this
0x1800026b1  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x1800026b6  movzx   ecx, word ptr [rsi]
0x1800026b9  xor     eax, eax
0x1800026bb  cmp     ax, cx
0x1800026be  jb      loc_18000263D
0x1800026c4  cmp     [rbx], eax
0x1800026c6  jz      loc_18000263D
0x1800026cc  cmp     [rbx], r15d
0x1800026cf  jnz     loc_18000262E
0x1800026d5  jmp     loc_18000263D
0x1800026da  cmp     dword ptr [rbx], 6
0x1800026dd  jnz     short loc_180002706
0x1800026df  mov     rcx, [rdi]; this
0x1800026e2  mov     [rsp+68h+var_38], rcx
0x1800026e7  mov     [rsp+68h+var_30], 0
0x1800026ec  mov     rdx, [rbp+8]
0x1800026f0  add     rdx, 8
0x1800026f4  call    ??$ReadVariableUnsigned@_K@InputBuffer@bond@@QEAAXAEA_K@Z; bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(unsigned __int64 &)
0x1800026f9  nop
0x1800026fa  lea     rcx, [rsp+68h+var_38]
0x1800026ff  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180002704  jmp     short loc_180002723
0x180002706  cmp     [rbx], r15d
0x180002709  jbe     loc_18000264D
0x18000270f  mov     [rsp+68h+var_48], rbp
0x180002714  mov     r9d, [rbx]
0x180002717  movzx   r8d, cx
0x18000271b  mov     rcx, rdi
0x18000271e  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UWiFiProfileCost@WiFi@Data@Windows@@_K$07$1?s_lastModifiedTime_metadata@Schema@WiFiProfileCost@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UWiFiProfileCost@WiFi@Data@Windows@@_K$07$1?s_lastModifiedTime_metadata@Schema@WiFiProfileCost@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfileCost,unsigned __int64,8,&bond::Metadata const Windows::Data::WiFi::WiFiProfileCost::Schema::s_lastModifiedTime_metadata>,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>>>>(bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfileCost,unsigned __int64,8,&bond::Metadata const Windows::Data::WiFi::WiFiProfileCost::Schema::s_lastModifiedTime_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>>> const &)
0x180002723  mov     r8, rsi
0x180002726  mov     rdx, rbx
0x180002729  mov     rcx, [rdi]; this
0x18000272c  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180002731  movzx   ecx, word ptr [rsi]
0x180002734  cmp     r15w, cx
0x180002738  jb      loc_18000264D
0x18000273e  cmp     dword ptr [rbx], 0
0x180002741  jz      loc_18000264D
0x180002747  cmp     [rbx], r15d
0x18000274a  jnz     loc_18000263D
0x180002750  jmp     loc_18000264D
0x180002755  cmp     eax, r15d
0x180002758  jz      loc_180002657
0x18000275e  mov     edx, eax
0x180002760  mov     rcx, [rdi]; this
0x180002763  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180002768  mov     r8, rsi
0x18000276b  mov     rdx, rbx
0x18000276e  mov     rcx, [rdi]; this
0x180002771  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180002776  jmp     loc_18000264D
```
