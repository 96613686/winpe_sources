# bond::Deserialize<bond::BuiltInProtocols,bond::CompactBinaryReader<bond::InputBuffer>,wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>(bond::CompactBinaryReader<bond::InputBuffer>,wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings> &)

- ea: `0x180009dd8`
- end: `0x180009e6d`
- name: `??$Deserialize@UBuiltInProtocols@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@bond@@YAXV?$CompactBinaryReader@VInputBuffer@bond@@@0@AEAV?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@Z`
- size: `149`
- prototype: `void __fastcall(bond::InputBuffer *this, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ef9c`

## callees

- `0x18000aa0c`
- `0x18000ff68`
- `0x180011018`
- `0x18001199c`
- `0x180012070`
- `0x1800176f4`

## pseudocode

```c
void __fastcall bond::Deserialize<bond::BuiltInProtocols,bond::CompactBinaryReader<bond::InputBuffer>,wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>(
        bond::InputBuffer *this,
        __int64 a2)
{
  __int64 v3; // rdx
  __int16 v4; // [rsp+20h] [rbp-60h] BYREF
  __int64 v5; // [rsp+28h] [rbp-58h]
  bond::InputBuffer *v6; // [rsp+30h] [rbp-50h] BYREF
  char v7; // [rsp+38h] [rbp-48h]
  bond::InputBuffer *v8; // [rsp+48h] [rbp-38h] BYREF
  __int128 v9; // [rsp+50h] [rbp-30h]
  __int128 v10; // [rsp+60h] [rbp-20h]
  __int16 v11; // [rsp+70h] [rbp-10h]
  char v12; // [rsp+98h] [rbp+18h] BYREF

  v8 = this;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v5 = a2;
  v6 = this;
  v7 = 0;
  bond::detail::RecursionGuard::RecursionGuard((bond::detail::RecursionGuard *)&v12);
  bond::CompactBinaryReader<bond::InputBuffer>::ReadStructBegin(this);
  v4 = -1;
  bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<3>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type,boost::mpl::l_item<boost::mpl::long_<2>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>>>,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(
    &v6,
    v3,
    &v4);
  bond::detail::RecursionGuard::~RecursionGuard((bond::detail::RecursionGuard *)&v12);
  bond::bonded<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::CompactBinaryReader<bond::InputBuffer> &>::~bonded<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::CompactBinaryReader<bond::InputBuffer> &>(&v8);
  boost::detail::shared_count::~shared_count((bond::InputBuffer *)((char *)this + 8));
}

```

## disassembly

```asm
0x180009dd8  mov     [rsp-8+arg_10], rbx
0x180009ddd  mov     [rsp-8+arg_0], rcx
0x180009de2  push    rbp
0x180009de3  mov     rbp, rsp
0x180009de6  sub     rsp, 80h
0x180009ded  mov     rbx, rcx
0x180009df0  mov     [rbp+var_38], rcx
0x180009df4  xorps   xmm0, xmm0
0x180009df7  movdqu  [rbp+var_30], xmm0
0x180009dfc  xorps   xmm1, xmm1
0x180009dff  movdqu  [rbp+var_20], xmm1
0x180009e04  xor     eax, eax
0x180009e06  mov     [rbp+var_10], ax
0x180009e0a  mov     [rbp+var_58], rdx
0x180009e0e  mov     [rbp+var_50], rcx
0x180009e12  mov     [rbp+var_48], al
0x180009e15  lea     rcx, [rbp+arg_8]; this
0x180009e19  call    ??0RecursionGuard@detail@bond@@QEAA@XZ; bond::detail::RecursionGuard::RecursionGuard(void)
0x180009e1e  nop
0x180009e1f  xor     edx, edx
0x180009e21  mov     rcx, rbx; this
0x180009e24  call    ?ReadStructBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAX_N@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadStructBegin(bool)
0x180009e29  mov     eax, 0FFFFh
0x180009e2e  mov     [rbp+var_60], ax
0x180009e32  lea     r8, [rbp+var_60]
0x180009e36  lea     rcx, [rbp+var_50]
0x180009e3a  call    ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$02@mpl@boost@@UlanguageProfile_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$01@mpl@boost@@Uregion_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$00@mpl@boost@@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@Ul_end@23@@23@@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$l_iter@U?$l_item@U?$long_@$02@mpl@boost@@UlanguageProfile_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$01@mpl@boost@@Uregion_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@U?$l_item@U?$long_@$00@mpl@boost@@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@Ul_end@23@@23@@23@@mpl@boost@@@mpl@boost@@AEBV?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<3>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type,boost::mpl::l_item<boost::mpl::long_<2>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>>>,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<3>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type,boost::mpl::l_item<boost::mpl::long_<2>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::region_type,boost::mpl::l_item<boost::mpl::long_<1>,Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,boost::mpl::l_end>>>> const &,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>> const &)
0x180009e3f  nop
0x180009e40  lea     rcx, [rbp+arg_8]; this
0x180009e44  call    ??1RecursionGuard@detail@bond@@QEAA@XZ; bond::detail::RecursionGuard::~RecursionGuard(void)
0x180009e49  nop
0x180009e4a  lea     rcx, [rbp+var_38]
0x180009e4e  call    ??1?$bonded@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::bonded<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::CompactBinaryReader<bond::InputBuffer> &>::~bonded<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180009e53  nop
0x180009e54  lea     rcx, [rbx+8]; this
0x180009e58  mov     rbx, [rsp+80h+arg_10]
0x180009e60  add     rsp, 80h
0x180009e67  pop     rbp
0x180009e68  jmp     ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
```
