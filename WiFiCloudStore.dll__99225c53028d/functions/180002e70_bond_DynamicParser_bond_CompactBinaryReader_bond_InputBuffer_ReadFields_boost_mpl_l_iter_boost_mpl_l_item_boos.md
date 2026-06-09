# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,0,&bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_profileXml_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,unsigned __int64,32,&bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_lastModifiedTime_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,0,&bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_profileXml_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,unsigned __int64,32,&bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_lastModifiedTime_metadata>,boost::mpl::l_end>>> const &,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>> const &)

- ea: `0x180002e70`
- end: `0x1800031cc`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UWiFiProfile@WiFi@Data@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@$1?s_profileXml_metadata@Schema@WiFiProfile@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UWiFiProfile@WiFi@Data@Windows@@_K$0CA@$1?s_lastModifiedTime_metadata@Schema@WiFiProfile@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UWiFiProfile@WiFi@Data@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@$1?s_profileXml_metadata@Schema@WiFiProfile@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UWiFiProfile@WiFi@Data@Windows@@_K$0CA@$1?s_lastModifiedTime_metadata@Schema@WiFiProfile@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@AEBV?$To@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `860`
- prototype: `char __fastcall(bond::InputBuffer **, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003350`

## callees

- `0x180002a00`
- `0x180002b30`
- `0x180002e70`
- `0x1800031d4`
- `0x180019b6c`
- `0x18001aa20`
- `0x18003071c`
- `0x180033880`
- `0x180033920`

## pseudocode

```c
char __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,std::wstring,0,&private: static bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_profileXml_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,unsigned __int64,32,&private: static bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_lastModifiedTime_metadata>,boost::mpl::l_end>>>,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>>>(
        bond::InputBuffer **a1,
        __int64 a2,
        __int64 a3)
{
  bond::InputBuffer *v5; // r9
  __int64 v6; // r10
  __int64 v7; // rdx
  __int64 v8; // r11
  char v9; // cl
  __int64 v10; // r10
  unsigned int v11; // ebx
  unsigned __int8 v12; // cl
  __int64 v13; // r8
  bond::InputBuffer *v14; // r9
  __int64 v15; // r10
  __int64 v16; // r11
  char v17; // cl
  __int64 v18; // r10
  unsigned __int8 v19; // cl
  bond::InputBuffer *v20; // r9
  __int64 v21; // r10
  __int64 v22; // r11
  char v23; // cl
  __int64 v24; // r10
  unsigned __int8 v25; // cl
  unsigned int v27; // [rsp+70h] [rbp+30h]
  __int64 v28; // [rsp+78h] [rbp+38h] BYREF

  v28 = a2;
  v5 = *a1;
  v6 = *((unsigned int *)*a1 + 8);
  v7 = *((unsigned int *)*a1 + 6);
  if ( (_DWORD)v7 == (_DWORD)v6 )
    bond::InputBuffer::EofException(*a1, 1u);
  v8 = *((_QWORD *)v5 + 2);
  v9 = *(_BYTE *)(v6 + v8);
  v10 = (unsigned int)(v6 + 1);
  *((_DWORD *)v5 + 8) = v10;
  v11 = v9 & 0x1F;
  v27 = v11;
  v12 = v9 & 0xE0;
  v13 = v12;
  LOWORD(v28) = v12;
  if ( v12 == 224 )
  {
    v7 = (unsigned int)(v7 - v10);
    if ( (unsigned int)v7 < 2 )
      bond::InputBuffer::EofException(v5, 2u);
    v13 = *(unsigned __int16 *)(v10 + v8);
    *((_DWORD *)v5 + 8) = v10 + 2;
    goto LABEL_5;
  }
  if ( v12 != 192 )
  {
    LOWORD(v13) = v12 >> 5;
LABEL_5:
    LOWORD(v28) = v13;
    goto LABEL_6;
  }
  bond::InputBuffer::Read(v5, (unsigned __int8 *)&v28);
  v13 = (unsigned __int16)v28;
  do
  {
LABEL_6:
    if ( (_WORD)v13 )
      goto LABEL_15;
    if ( v11 == 18 )
    {
      bond::CompactBinaryReader<bond::InputBuffer>::Read<std::wstring>(*a1, *(bond::InputBuffer **)(a3 + 8));
    }
    else
    {
      if ( v11 <= 1 )
        goto LABEL_15;
      bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,std::wstring,0,&private: static bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_profileXml_metadata>,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>>>(
        a1,
        v7,
        v13,
        v11,
        a3);
    }
    v14 = *a1;
    v15 = *((unsigned int *)*a1 + 8);
    v7 = *((unsigned int *)*a1 + 6);
    if ( (_DWORD)v7 == (_DWORD)v15 )
      bond::InputBuffer::EofException(*a1, 1u);
    v16 = *((_QWORD *)v14 + 2);
    v17 = *(_BYTE *)(v15 + v16);
    v18 = (unsigned int)(v15 + 1);
    *((_DWORD *)v14 + 8) = v18;
    v11 = v17 & 0x1F;
    v27 = v11;
    v19 = v17 & 0xE0;
    v13 = v19;
    LOWORD(v28) = v19;
    if ( v19 == 224 )
    {
      v7 = (unsigned int)(v7 - v18);
      if ( (unsigned int)v7 < 2 )
        bond::InputBuffer::EofException(v14, 2u);
      v13 = *(unsigned __int16 *)(v18 + v16);
      *((_DWORD *)v14 + 8) = v18 + 2;
    }
    else
    {
      if ( v19 == 192 )
      {
        bond::InputBuffer::Read(v14, (unsigned __int8 *)&v28);
        v13 = (unsigned __int16)v28;
        continue;
      }
      LOWORD(v13) = v19 >> 5;
    }
    LOWORD(v28) = v13;
  }
  while ( !(_WORD)v13 && v11 >= 2 );
  do
  {
LABEL_15:
    if ( (_WORD)v13 == 1 )
    {
      if ( v11 == 6 )
      {
        bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(*a1);
        goto LABEL_18;
      }
    }
    else if ( (unsigned __int16)v13 > 1u )
    {
      break;
    }
    if ( !v11 )
      goto LABEL_28;
    if ( v11 == 1 )
      break;
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,unsigned __int64,32,&private: static bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_lastModifiedTime_metadata>,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>>>(
      a1,
      v7,
      v13,
      v11,
      a3);
LABEL_18:
    v20 = *a1;
    v21 = *((unsigned int *)*a1 + 8);
    v7 = *((unsigned int *)*a1 + 6);
    if ( (_DWORD)v7 == (_DWORD)v21 )
      bond::InputBuffer::EofException(*a1, 1u);
    v22 = *((_QWORD *)v20 + 2);
    v23 = *(_BYTE *)(v21 + v22);
    v24 = (unsigned int)(v21 + 1);
    *((_DWORD *)v20 + 8) = v24;
    v11 = v23 & 0x1F;
    v27 = v11;
    v25 = v23 & 0xE0;
    v13 = v25;
    LOWORD(v28) = v25;
    if ( v25 == 224 )
    {
      v7 = (unsigned int)(v7 - v24);
      if ( (unsigned int)v7 < 2 )
        bond::InputBuffer::EofException(v20, 2u);
      v13 = *(unsigned __int16 *)(v24 + v22);
      *((_DWORD *)v20 + 8) = v24 + 2;
      goto LABEL_22;
    }
    if ( v25 != 192 )
    {
      LOWORD(v13) = v25 >> 5;
LABEL_22:
      LOWORD(v28) = v13;
      continue;
    }
    bond::InputBuffer::Read(v20, (unsigned __int8 *)&v28);
    v13 = (unsigned __int16)v28;
  }
  while ( (unsigned __int16)v13 <= 1u && v11 >= 2 );
  while ( v11 > 1 )
  {
    bond::CompactBinaryReader<bond::InputBuffer>::Skip(*a1);
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
    v11 = v27;
  }
LABEL_28:
  if ( !*((_BYTE *)a1 + 8) )
  {
    while ( v11 )
    {
      if ( v11 != 1 )
        bond::CompactBinaryReader<bond::InputBuffer>::Skip(*a1);
      bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
      v11 = v27;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180002e70  mov     [rsp-28h+arg_10], rbx
0x180002e75  mov     [rsp-28h+arg_8], rdx
0x180002e7a  push    rbp
0x180002e7b  push    rsi
0x180002e7c  push    rdi
0x180002e7d  push    r13
0x180002e7f  push    r14
0x180002e81  mov     rbp, rsp
0x180002e84  sub     rsp, 40h
0x180002e88  mov     r14, r8
0x180002e8b  mov     rsi, rcx
0x180002e8e  mov     r9, [rcx]
0x180002e91  mov     r10d, [r9+20h]
0x180002e95  mov     edx, [r9+18h]
0x180002e99  cmp     edx, r10d
0x180002e9c  jz      loc_1800030DE
0x180002ea2  mov     r11, [r9+10h]
0x180002ea6  movzx   ecx, byte ptr [r10+r11]
0x180002eab  inc     r10d
0x180002eae  mov     [r9+20h], r10d
0x180002eb2  mov     ebx, ecx
0x180002eb4  and     ebx, 1Fh
0x180002eb7  mov     [rbp+arg_0], ebx
0x180002eba  mov     eax, 0E0h
0x180002ebf  and     cl, al
0x180002ec1  movzx   r8d, cl
0x180002ec5  mov     word ptr [rbp+arg_8], r8w
0x180002eca  lea     r13d, [rax-20h]
0x180002ece  cmp     r8w, ax
0x180002ed2  jz      loc_1800030AA
0x180002ed8  cmp     r8w, r13w
0x180002edc  jz      loc_1800030FA
0x180002ee2  shr     r8w, 5
0x180002ee7  mov     word ptr [rbp+arg_8], r8w
0x180002eec  mov     edi, 1
0x180002ef1  xor     eax, eax
0x180002ef3  cmp     ax, r8w
0x180002ef7  jnz     loc_180003079
0x180002efd  cmp     ebx, 12h
0x180002f00  jnz     loc_18000307F
0x180002f06  mov     rcx, [rsi]; this
0x180002f09  mov     [rbp+var_10], rcx
0x180002f0d  mov     [rbp+var_8], al
0x180002f10  mov     rdx, [r14+8]; bond::InputBuffer *
0x180002f14  call    ??$Read@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Read<std::wstring>(std::wstring &)
0x180002f19  nop
0x180002f1a  mov     r9, [rsi]
0x180002f1d  mov     r10d, [r9+20h]
0x180002f21  mov     edx, [r9+18h]
0x180002f25  cmp     edx, r10d
0x180002f28  jz      loc_180003134
0x180002f2e  mov     r11, [r9+10h]
0x180002f32  movzx   ecx, byte ptr [r10+r11]
0x180002f37  inc     r10d
0x180002f3a  mov     [r9+20h], r10d
0x180002f3e  mov     ebx, ecx
0x180002f40  and     ebx, 1Fh
0x180002f43  mov     [rbp+arg_0], ebx
0x180002f46  mov     eax, 0E0h
0x180002f4b  and     cl, al
0x180002f4d  movzx   r8d, cl
0x180002f51  mov     word ptr [rbp+arg_8], r8w
0x180002f56  cmp     r8w, ax
0x180002f5a  jz      loc_1800030C4
0x180002f60  cmp     r8w, r13w
0x180002f64  jz      loc_180003110
0x180002f6a  shr     r8w, 5
0x180002f6f  mov     word ptr [rbp+arg_8], r8w
0x180002f74  xor     eax, eax
0x180002f76  cmp     ax, r8w
0x180002f7a  jnb     loc_18000309C
0x180002f80  cmp     di, r8w
0x180002f84  jnz     loc_180003013
0x180002f8a  cmp     ebx, 6
0x180002f8d  jnz     loc_18000313F
0x180002f93  mov     rcx, [rsi]; this
0x180002f96  mov     [rbp+var_10], rcx
0x180002f9a  mov     [rbp+var_8], 0
0x180002f9e  mov     rdx, [r14+8]
0x180002fa2  add     rdx, 20h ; ' '
0x180002fa6  call    ??$ReadVariableUnsigned@_K@InputBuffer@bond@@QEAAXAEA_K@Z; bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(unsigned __int64 &)
0x180002fab  nop
0x180002fac  mov     r9, [rsi]
0x180002faf  mov     r10d, [r9+20h]
0x180002fb3  mov     edx, [r9+18h]
0x180002fb7  cmp     edx, r10d
0x180002fba  jz      loc_180003188
0x180002fc0  mov     r11, [r9+10h]
0x180002fc4  movzx   ecx, byte ptr [r10+r11]
0x180002fc9  inc     r10d
0x180002fcc  mov     [r9+20h], r10d
0x180002fd0  mov     ebx, ecx
0x180002fd2  and     ebx, 1Fh
0x180002fd5  mov     [rbp+arg_0], ebx
0x180002fd8  mov     eax, 0E0h
0x180002fdd  and     cl, al
0x180002fdf  movzx   r8d, cl
0x180002fe3  mov     word ptr [rbp+arg_8], r8w
0x180002fe8  cmp     r8w, ax
0x180002fec  jz      short loc_18000305E
0x180002fee  cmp     r8w, r13w
0x180002ff2  jz      loc_180003164
0x180002ff8  shr     r8w, 5
0x180002ffd  mov     word ptr [rbp+arg_8], r8w
0x180003002  cmp     di, r8w
0x180003006  jb      short loc_180003019
0x180003008  cmp     ebx, 2
0x18000300b  jnb     loc_180002F80
0x180003011  jmp     short loc_180003019
0x180003013  jnb     loc_18000313F
0x180003019  test    ebx, ebx
0x18000301b  jnz     loc_180003193
0x180003021  cmp     byte ptr [rsi+8], 0
0x180003025  jz      short loc_180003058
0x180003027  xor     al, al
0x180003029  mov     rbx, [rsp+40h+arg_10]
0x180003031  add     rsp, 40h
0x180003035  pop     r14
0x180003037  pop     r13
0x180003039  pop     rdi
0x18000303a  pop     rsi
0x18000303b  pop     rbp
0x18000303c  retn
0x18000303d  cmp     ebx, edi
0x18000303f  jnz     loc_1800031BD
0x180003045  lea     r8, [rbp+arg_8]
0x180003049  lea     rdx, [rbp+arg_0]
0x18000304d  mov     rcx, [rsi]; this
0x180003050  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180003055  mov     ebx, [rbp+arg_0]
0x180003058  test    ebx, ebx
0x18000305a  jz      short loc_180003027
0x18000305c  jmp     short loc_18000303D
0x18000305e  sub     edx, r10d
0x180003061  cmp     edx, 2
0x180003064  jb      loc_18000317A
0x18000306a  movzx   r8d, word ptr [r10+r11]
0x18000306f  lea     eax, [r10+2]
0x180003073  mov     [r9+20h], eax
0x180003077  jmp     short loc_180002FFD
0x180003079  jb      loc_180002F80
0x18000307f  cmp     ebx, edi
0x180003081  jbe     loc_180002F80
0x180003087  mov     [rsp+40h+var_20], r14
0x18000308c  mov     r9d, ebx
0x18000308f  mov     rcx, rsi
0x180003092  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UWiFiProfile@WiFi@Data@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@$1?s_profileXml_metadata@Schema@WiFiProfile@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UWiFiProfile@WiFi@Data@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@$1?s_profileXml_metadata@Schema@WiFiProfile@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,std::wstring,0,&bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_profileXml_metadata>,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>>>(bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,std::wstring,0,&bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_profileXml_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>> const &)
0x180003097  jmp     loc_180002F1A
0x18000309c  cmp     ebx, 2
0x18000309f  jnb     loc_180002EF1
0x1800030a5  jmp     loc_180002F80
0x1800030aa  sub     edx, r10d
0x1800030ad  cmp     edx, 2
0x1800030b0  jb      short loc_1800030EC
0x1800030b2  movzx   r8d, word ptr [r10+r11]
0x1800030b7  lea     eax, [r10+2]
0x1800030bb  mov     [r9+20h], eax
0x1800030bf  jmp     loc_180002EE7
0x1800030c4  sub     edx, r10d
0x1800030c7  cmp     edx, 2
0x1800030ca  jb      short loc_180003126
0x1800030cc  movzx   r8d, word ptr [r10+r11]
0x1800030d1  lea     eax, [r10+2]
0x1800030d5  mov     [r9+20h], eax
0x1800030d9  jmp     loc_180002F6F
0x1800030de  mov     edx, 1; unsigned int
0x1800030e3  mov     rcx, r9; this
0x1800030e6  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x1800030ec  mov     edx, 2; unsigned int
0x1800030f1  mov     rcx, r9; this
0x1800030f4  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x1800030fa  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x1800030fe  mov     rcx, r9; this
0x180003101  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x180003106  movzx   r8d, word ptr [rbp+arg_8]
0x18000310b  jmp     loc_180002EEC
0x180003110  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x180003114  mov     rcx, r9; this
0x180003117  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x18000311c  movzx   r8d, word ptr [rbp+arg_8]
0x180003121  jmp     loc_180002F74
0x180003126  mov     edx, 2; unsigned int
0x18000312b  mov     rcx, r9; this
0x18000312e  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x180003134  mov     edx, edi; unsigned int
0x180003136  mov     rcx, r9; this
0x180003139  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x18000313f  test    ebx, ebx
0x180003141  jz      loc_180003021
0x180003147  cmp     ebx, edi
0x180003149  jz      loc_180003019
0x18000314f  mov     [rsp+40h+var_20], r14
0x180003154  mov     r9d, ebx
0x180003157  mov     rcx, rsi
0x18000315a  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UWiFiProfile@WiFi@Data@Windows@@_K$0CA@$1?s_lastModifiedTime_metadata@Schema@WiFiProfile@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UWiFiProfile@WiFi@Data@Windows@@_K$0CA@$1?s_lastModifiedTime_metadata@Schema@WiFiProfile@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,unsigned __int64,32,&bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_lastModifiedTime_metadata>,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>>>(bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,unsigned __int64,32,&bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_lastModifiedTime_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>> const &)
0x18000315f  jmp     loc_180002FAC
0x180003164  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x180003168  mov     rcx, r9; this
0x18000316b  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x180003170  movzx   r8d, word ptr [rbp+arg_8]
0x180003175  jmp     loc_180003002
0x18000317a  mov     edx, 2; unsigned int
0x18000317f  mov     rcx, r9; this
0x180003182  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x180003188  mov     edx, edi; unsigned int
0x18000318a  mov     rcx, r9; this
0x18000318d  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x180003193  cmp     ebx, edi
0x180003195  jz      loc_180003021
0x18000319b  mov     edx, ebx
0x18000319d  mov     rcx, [rsi]; this
0x1800031a0  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x1800031a5  lea     r8, [rbp+arg_8]
0x1800031a9  lea     rdx, [rbp+arg_0]
0x1800031ad  mov     rcx, [rsi]; this
0x1800031b0  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x1800031b5  mov     ebx, [rbp+arg_0]
0x1800031b8  jmp     loc_180003019
0x1800031bd  mov     edx, ebx
0x1800031bf  mov     rcx, [rsi]; this
0x1800031c2  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x1800031c7  jmp     loc_180003045
```
