# bond::detail::DoublePassApply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile> const &)

- ea: `0x180023308`
- end: `0x18002343c`
- name: `??$DoublePassApply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@@detail@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@1@AEBV?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@@Z`
- size: `308`
- prototype: `char __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800235f4`

## callees

- `0x18001fa54`
- `0x180023444`
- `0x1800234d8`
- `0x180023588`
- `0x1800235f4`
- `0x18002a030`

## pseudocode

```c
char __fastcall bond::detail::DoublePassApply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>(
        _QWORD *a1,
        __int64 a2)
{
  _QWORD *v3; // rbx
  __int64 v4; // rdx
  _QWORD *v5; // rdi
  unsigned int v7; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD *v8; // [rsp+28h] [rbp-D8h] BYREF
  char v9; // [rsp+30h] [rbp-D0h]
  __int64 v10; // [rsp+38h] [rbp-C8h] BYREF
  char v11; // [rsp+40h] [rbp-C0h]
  _QWORD v12[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v13; // [rsp+60h] [rbp-A0h]
  _DWORD v14[2]; // [rsp+68h] [rbp-98h] BYREF
  char v15; // [rsp+70h] [rbp-90h] BYREF
  char *v16; // [rsp+170h] [rbp+70h]
  _DWORD v17[2]; // [rsp+178h] [rbp+78h] BYREF
  char v18; // [rsp+180h] [rbp+80h] BYREF
  char *v19; // [rsp+280h] [rbp+180h]

  v3 = a1;
  v7 = 0;
  v12[0] = &v7;
  v13 = *(_WORD *)(*a1 + 16LL);
  v14[0] = 0;
  v14[1] = 64;
  v16 = &v15;
  v17[0] = 0;
  v17[1] = 64;
  v19 = &v18;
  v8 = v12;
  v9 = 0;
  v10 = a2;
  v11 = 0;
  bond::detail::SimpleArray<unsigned int,64>::push(v14, 0);
  bond::detail::SimpleArray<unsigned int,64>::push(v17, v7);
  bond::StaticParser<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile> const &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,std::wstring,0,&private: static bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_profileXml_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,unsigned __int64,32,&private: static bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_lastModifiedTime_metadata>,boost::mpl::l_end>>>,bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>>(
    &v10,
    v4,
    &v8);
  ++*(_DWORD *)v12[0];
  bond::CompactBinaryWriter<bond::OutputCounter>::LengthEnd(v12, v12[0]);
  v5 = (_QWORD *)*v3;
  v5[1] = v19;
  v8 = v5;
  LOBYTE(v3) = bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>(
                 (__int64)v3,
                 a2);
  v5[1] = 0;
  bond::detail::SimpleArray<unsigned int,64>::memfree(v17);
  bond::detail::SimpleArray<unsigned int,64>::memfree(v14);
  return (char)v3;
}

```

## disassembly

```asm
0x180023308  mov     [rsp-8+arg_10], rbx
0x18002330d  push    rbp
0x18002330e  push    rsi
0x18002330f  push    rdi
0x180023310  lea     rbp, [rsp-1A0h]
0x180023318  sub     rsp, 2A0h
0x18002331f  mov     rax, cs:__security_cookie
0x180023326  xor     rax, rsp
0x180023329  mov     [rbp+1B0h+var_20], rax
0x180023330  mov     rsi, rdx
0x180023333  mov     rbx, rcx
0x180023336  mov     [rsp+2B0h+var_290], 0
0x18002333e  lea     rax, [rsp+2B0h+var_290]
0x180023343  mov     [rsp+2B0h+var_260], rax
0x180023348  mov     rax, [rcx]
0x18002334b  movzx   ecx, word ptr [rax+10h]
0x18002334f  mov     [rsp+2B0h+var_250], cx
0x180023354  mov     [rsp+2B0h+var_248], 0
0x18002335c  mov     ecx, 40h ; '@'
0x180023361  mov     [rsp+2B0h+var_244], ecx
0x180023365  lea     rax, [rsp+2B0h+var_240]
0x18002336a  mov     [rbp+1B0h+var_140], rax
0x18002336e  mov     [rbp+1B0h+var_138], 0
0x180023375  mov     [rbp+1B0h+var_134], ecx
0x180023378  lea     rax, [rbp+1B0h+var_130]
0x18002337f  mov     [rbp+1B0h+var_30], rax
0x180023386  lea     rax, [rsp+2B0h+var_260]
0x18002338b  mov     [rsp+2B0h+var_288], rax
0x180023390  mov     [rsp+2B0h+var_280], 0
0x180023395  mov     [rsp+2B0h+var_278], rdx
0x18002339a  mov     [rsp+2B0h+var_270], 0
0x18002339f  xor     edx, edx
0x1800233a1  lea     rcx, [rsp+2B0h+var_248]
0x1800233a6  call    ?push@?$SimpleArray@I$0EA@@detail@bond@@QEAAXI@Z; bond::detail::SimpleArray<uint,64>::push(uint)
0x1800233ab  mov     edx, [rsp+2B0h+var_290]
0x1800233af  lea     rcx, [rbp+1B0h+var_138]
0x1800233b3  call    ?push@?$SimpleArray@I$0EA@@detail@bond@@QEAAXI@Z; bond::detail::SimpleArray<uint,64>::push(uint)
0x1800233b8  lea     r8, [rsp+2B0h+var_288]
0x1800233bd  lea     rcx, [rsp+2B0h+var_278]
0x1800233c2  call    ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UWiFiProfile@WiFi@Data@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@$1?s_profileXml_metadata@Schema@WiFiProfile@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UWiFiProfile@WiFi@Data@Windows@@_K$0CA@$1?s_lastModifiedTime_metadata@Schema@WiFiProfile@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@V?$Serializer@V?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@@bond@@@?$StaticParser@AEBV?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@@bond@@AEAA_NAEBU?$l_iter@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UWiFiProfile@WiFi@Data@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@$1?s_profileXml_metadata@Schema@WiFiProfile@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UWiFiProfile@WiFi@Data@Windows@@_K$0CA@$1?s_lastModifiedTime_metadata@Schema@WiFiProfile@WiFi@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@23@@mpl@boost@@@mpl@boost@@AEBV?$Serializer@V?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@@1@@Z; bond::StaticParser<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile> const &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,std::wstring,0,&bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_profileXml_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,unsigned __int64,32,&bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_lastModifiedTime_metadata>,boost::mpl::l_end>>>,bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,std::wstring,0,&bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_profileXml_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::WiFi::WiFiProfile,unsigned __int64,32,&bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_lastModifiedTime_metadata>,boost::mpl::l_end>>> const &,bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>> const &)
0x1800233c7  mov     rax, [rsp+2B0h+var_260]
0x1800233cc  inc     dword ptr [rax]
0x1800233ce  mov     rdx, [rsp+2B0h+var_260]
0x1800233d3  lea     rcx, [rsp+2B0h+var_260]
0x1800233d8  call    ?LengthEnd@?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@IEAAXAEAVOutputCounter@2@@Z; bond::CompactBinaryWriter<bond::OutputCounter>::LengthEnd(bond::OutputCounter &)
0x1800233dd  mov     rdi, [rbx]
0x1800233e0  mov     rax, [rbp+1B0h+var_30]
0x1800233e7  mov     [rdi+8], rax
0x1800233eb  mov     [rsp+2B0h+var_288], rdi
0x1800233f0  mov     rdx, rsi
0x1800233f3  mov     rcx, rbx
0x1800233f6  call    ??$Apply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@0@AEBV?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@@Z; bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile> const &)
0x1800233fb  mov     bl, al
0x1800233fd  mov     qword ptr [rdi+8], 0
0x180023405  lea     rcx, [rbp+1B0h+var_138]
0x180023409  call    ?memfree@?$SimpleArray@I$0EA@@detail@bond@@AEAAXXZ; bond::detail::SimpleArray<uint,64>::memfree(void)
0x18002340e  lea     rcx, [rsp+2B0h+var_248]
0x180023413  call    ?memfree@?$SimpleArray@I$0EA@@detail@bond@@AEAAXXZ; bond::detail::SimpleArray<uint,64>::memfree(void)
0x180023418  mov     al, bl
0x18002341a  mov     rcx, [rbp+1B0h+var_20]
0x180023421  xor     rcx, rsp; StackCookie
0x180023424  call    __security_check_cookie
0x180023429  mov     rbx, [rsp+2B0h+arg_10]
0x180023431  add     rsp, 2A0h
0x180023438  pop     rdi
0x180023439  pop     rsi
0x18002343a  pop     rbp
0x18002343b  retn
```
