# bond::detail::DoublePassApply<bond::BuiltInProtocols,bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>,bond::BuiltInProtocols>,wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>,bond::BuiltInProtocols> const &,wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings> const &)

- ea: `0x180009e74`
- end: `0x180009f95`
- name: `??$DoublePassApply@UBuiltInProtocols@bond@@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@UBuiltInProtocols@2@@2@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@detail@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@UBuiltInProtocols@2@@1@AEBV?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@Z`
- size: `289`
- prototype: `char __fastcall(_BYTE *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009958`

## callees

- `0x180002380`
- `0x180009958`
- `0x18000a924`
- `0x180010aec`
- `0x180015f84`
- `0x180015ff4`

## pseudocode

```c
char __fastcall bond::detail::DoublePassApply<bond::BuiltInProtocols,bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>,bond::BuiltInProtocols>,wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>(
        _BYTE *a1,
        __int64 a2)
{
  _BYTE *v3; // rbx
  __int64 v4; // rdx
  _QWORD *v5; // rdi
  int v7; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD *v8; // [rsp+28h] [rbp-D8h] BYREF
  char v9; // [rsp+30h] [rbp-D0h]
  __int64 v10; // [rsp+38h] [rbp-C8h] BYREF
  char v11; // [rsp+40h] [rbp-C0h]
  _QWORD v12[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v13; // [rsp+60h] [rbp-A0h]
  int v14; // [rsp+68h] [rbp-98h]
  int v15; // [rsp+6Ch] [rbp-94h]
  char v16; // [rsp+70h] [rbp-90h] BYREF
  char *v17; // [rsp+170h] [rbp+70h]
  int v18; // [rsp+178h] [rbp+78h]
  int v19; // [rsp+17Ch] [rbp+7Ch]
  char v20; // [rsp+180h] [rbp+80h] BYREF
  char *v21; // [rsp+280h] [rbp+180h]

  v3 = a1;
  v7 = 0;
  v12[0] = &v7;
  v13 = *(_WORD *)(*(_QWORD *)a1 + 16LL);
  v14 = 0;
  v15 = 64;
  v17 = &v16;
  v18 = 0;
  v19 = 64;
  v21 = &v20;
  v8 = v12;
  v9 = 0;
  v10 = a2;
  v11 = 0;
  bond::CompactBinaryWriter<bond::CompactBinaryCounter::type>::LengthBegin(v12, &v7);
  bond::StaticParser<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings> const &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<3>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type,boost::mpl::l_item<boost::mpl::long_<2>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>>>,bond::Serializer<bond::CompactBinaryWriter<bond::CompactBinaryCounter::type>,bond::BuiltInProtocols>,wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings> const &,0>(
    &v10,
    v4,
    &v8);
  ++*(_DWORD *)v12[0];
  bond::CompactBinaryWriter<bond::CompactBinaryCounter::type>::LengthEnd(v12, v12[0]);
  v5 = *(_QWORD **)v3;
  v5[1] = v21;
  v8 = v5;
  LOBYTE(v3) = bond::detail::ApplyTransform<bond::BuiltInProtocols,bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>,bond::BuiltInProtocols>,wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>(
                 v3,
                 a2);
  v5[1] = 0;
  bond::CompactBinaryWriter<bond::CompactBinaryCounter::type>::~CompactBinaryWriter<bond::CompactBinaryCounter::type>(v12);
  return (char)v3;
}

```

## disassembly

```asm
0x180009e74  mov     [rsp-8+arg_10], rbx
0x180009e79  push    rbp
0x180009e7a  push    rsi
0x180009e7b  push    rdi
0x180009e7c  lea     rbp, [rsp-1A0h]
0x180009e84  sub     rsp, 2A0h
0x180009e8b  mov     rax, cs:__security_cookie
0x180009e92  xor     rax, rsp
0x180009e95  mov     [rbp+1B0h+var_20], rax
0x180009e9c  mov     rsi, rdx
0x180009e9f  mov     rbx, rcx
0x180009ea2  mov     [rsp+2B0h+var_290], 0
0x180009eaa  lea     rax, [rsp+2B0h+var_290]
0x180009eaf  mov     [rsp+2B0h+var_260], rax
0x180009eb4  mov     rax, [rcx]
0x180009eb7  movzx   ecx, word ptr [rax+10h]
0x180009ebb  mov     [rsp+2B0h+var_250], cx
0x180009ec0  mov     [rsp+2B0h+var_248], 0
0x180009ec8  mov     ecx, 40h ; '@'
0x180009ecd  mov     [rsp+2B0h+var_244], ecx
0x180009ed1  lea     rax, [rsp+2B0h+var_240]
0x180009ed6  mov     [rbp+1B0h+var_140], rax
0x180009eda  mov     [rbp+1B0h+var_138], 0
0x180009ee1  mov     [rbp+1B0h+var_134], ecx
0x180009ee4  lea     rax, [rbp+1B0h+var_130]
0x180009eeb  mov     [rbp+1B0h+var_30], rax
0x180009ef2  lea     rax, [rsp+2B0h+var_260]
0x180009ef7  mov     [rsp+2B0h+var_288], rax
0x180009efc  mov     [rsp+2B0h+var_280], 0
0x180009f01  mov     [rsp+2B0h+var_278], rdx
0x180009f06  mov     [rsp+2B0h+var_270], 0
0x180009f0b  lea     rdx, [rsp+2B0h+var_290]
0x180009f10  lea     rcx, [rsp+2B0h+var_260]
0x180009f15  call    ?LengthBegin@?$CompactBinaryWriter@Utype@CompactBinaryCounter@bond@@@bond@@IEAAXAEAUtype@CompactBinaryCounter@2@@Z; bond::CompactBinaryWriter<bond::CompactBinaryCounter::type>::LengthBegin(bond::CompactBinaryCounter::type &)
0x180009f1a  lea     r8, [rsp+2B0h+var_288]
0x180009f1f  lea     rcx, [rsp+2B0h+var_278]
0x180009f24  call    ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$02@mpl@boost@@UlanguageProfile_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$01@mpl@boost@@Uregion_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$00@mpl@boost@@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@Ul_end@23@@23@@23@@mpl@boost@@@mpl@boost@@V?$Serializer@V?$CompactBinaryWriter@Utype@CompactBinaryCounter@bond@@@bond@@UBuiltInProtocols@2@@bond@@AEBV?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@$0A@@?$StaticParser@AEBV?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@bond@@AEAA_NAEBU?$l_iter@U?$l_item@U?$long_@$02@mpl@boost@@UlanguageProfile_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$01@mpl@boost@@Uregion_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$00@mpl@boost@@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@Ul_end@23@@23@@23@@mpl@boost@@@mpl@boost@@AEBV?$Serializer@V?$CompactBinaryWriter@Utype@CompactBinaryCounter@bond@@@bond@@UBuiltInProtocols@2@@1@@Z; bond::StaticParser<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings> const &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<3>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type,boost::mpl::l_item<boost::mpl::long_<2>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>>>,bond::Serializer<bond::CompactBinaryWriter<bond::CompactBinaryCounter::type>,bond::BuiltInProtocols>,wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings> const &,0>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<3>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type,boost::mpl::l_item<boost::mpl::long_<2>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>>> const &,bond::Serializer<bond::CompactBinaryWriter<bond::CompactBinaryCounter::type>,bond::BuiltInProtocols> const &)
0x180009f29  mov     rax, [rsp+2B0h+var_260]
0x180009f2e  inc     dword ptr [rax]
0x180009f30  mov     rdx, [rsp+2B0h+var_260]
0x180009f35  lea     rcx, [rsp+2B0h+var_260]
0x180009f3a  call    ?LengthEnd@?$CompactBinaryWriter@Utype@CompactBinaryCounter@bond@@@bond@@IEAAXAEAUtype@CompactBinaryCounter@2@@Z; bond::CompactBinaryWriter<bond::CompactBinaryCounter::type>::LengthEnd(bond::CompactBinaryCounter::type &)
0x180009f3f  mov     rdi, [rbx]
0x180009f42  mov     rax, [rbp+1B0h+var_30]
0x180009f49  mov     [rdi+8], rax
0x180009f4d  mov     [rsp+2B0h+var_288], rdi
0x180009f52  mov     rdx, rsi
0x180009f55  mov     rcx, rbx
0x180009f58  call    ??$ApplyTransform@UBuiltInProtocols@bond@@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@UBuiltInProtocols@2@@2@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@detail@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@UBuiltInProtocols@2@@1@AEBV?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@Z; bond::detail::ApplyTransform<bond::BuiltInProtocols,bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>,bond::BuiltInProtocols>,wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>,bond::BuiltInProtocols> const &,wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings> const &)
0x180009f5d  mov     bl, al
0x180009f5f  mov     qword ptr [rdi+8], 0
0x180009f67  lea     rcx, [rsp+2B0h+var_260]
0x180009f6c  call    ??1?$CompactBinaryWriter@Utype@CompactBinaryCounter@bond@@@bond@@QEAA@XZ; bond::CompactBinaryWriter<bond::CompactBinaryCounter::type>::~CompactBinaryWriter<bond::CompactBinaryCounter::type>(void)
0x180009f71  mov     al, bl
0x180009f73  mov     rcx, [rbp+1B0h+var_20]
0x180009f7a  xor     rcx, rsp; StackCookie
0x180009f7d  call    __security_check_cookie
0x180009f82  mov     rbx, [rsp+2B0h+arg_10]
0x180009f8a  add     rsp, 2A0h
0x180009f91  pop     rdi
0x180009f92  pop     rsi
0x180009f93  pop     rbp
0x180009f94  retn
```
