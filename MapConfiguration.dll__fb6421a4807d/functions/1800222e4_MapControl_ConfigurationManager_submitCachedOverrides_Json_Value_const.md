# MapControl::ConfigurationManager::submitCachedOverrides(Json::Value const &)

- ea: `0x1800222e4`
- end: `0x1800225d0`
- name: `?submitCachedOverrides@ConfigurationManager@MapControl@@AEAAXAEBVValue@Json@@@Z`
- size: `748`
- prototype: `void __fastcall(MapControl::ConfigurationManager *__hidden this, const struct Json::Value *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800219fc`

## callees

- `0x1800094a0`
- `0x18000b938`
- `0x18000ba50`
- `0x18000bb60`
- `0x18000c2f8`
- `0x18000c354`
- `0x180011ddc`
- `0x18001bbe8`
- `0x18001d6e4`
- `0x18001e3fc`
- `0x1800222e4`
- `0x180022764`
- `0x1800236e0`
- `0x18003417c`
- `0x180034324`
- `0x180034538`
- `0x180034630`
- `0x1800346dc`
- `0x1800348d8`
- `0x180035110`
- `0x180035934`
- `0x180036008`
- `0x18003b4a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall MapControl::ConfigurationManager::submitCachedOverrides(
        MapControl::ConfigurationManager *this,
        const struct Json::Value *a2)
{
  char v4; // r14
  __int64 v5; // r8
  __int64 v6; // r9
  _QWORD *i; // rdi
  const struct Json::Value *v8; // rax
  __int64 v9; // r10
  __int64 v10; // rax
  _BYTE *v11; // rcx
  __int64 v12; // r10
  __int64 v13; // r10
  Json::Value *v14; // rbx
  __int64 v15; // rax
  __int64 ValueString; // rax
  char v17; // bl
  _BYTE *v18; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v19; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v20; // [rsp+40h] [rbp-C0h]
  __int64 v21; // [rsp+48h] [rbp-B8h]
  void *v22; // [rsp+50h] [rbp-B0h] BYREF
  char v23; // [rsp+58h] [rbp-A8h]
  void *v24; // [rsp+78h] [rbp-88h] BYREF
  int v25; // [rsp+80h] [rbp-80h]
  _BYTE v26[40]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v27[16]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v28; // [rsp+D8h] [rbp-28h]
  _BYTE v29[16]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v30; // [rsp+F8h] [rbp-8h]
  _BYTE v31[32]; // [rsp+108h] [rbp+8h] BYREF

  v4 = 0;
  LODWORD(v18) = 0;
  Json::Value::Value((__int64)&v24, 0);
  std::wstring::wstring((__int64)v29);
  std::wstring::wstring((__int64)v27);
  std::wstring::wstring((__int64)v31);
  Json::Value::getMemberNames(a2, &v19);
  for ( i = v19; i != v20; i += 4 )
  {
    v8 = (const struct Json::Value *)Json::Value::operator[](a2, i);
    Json::Value::Value((Json::Value *)&v22, v8);
    if ( v23 != 4 )
      goto LABEL_11;
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(MapControl::StringKeyToEnumKeyMap::kTimestampKey);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v9, i[2]) )
    {
      v10 = Json::Value::asString(&v22, v26);
      v11 = v31;
LABEL_9:
      std::wstring::operator=(v11, v10);
      std::wstring::_Tidy_deallocate(v26);
      goto LABEL_11;
    }
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(MapControl::StringKeyToEnumKeyMap::kRegionKey);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v12, i[2]) )
    {
      v10 = Json::Value::asString(&v22, v26);
      v11 = v29;
      goto LABEL_9;
    }
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(MapControl::StringKeyToEnumKeyMap::kLanguageKey);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v13, i[2]) )
    {
      v10 = Json::Value::asString(&v22, v26);
      v11 = v27;
      goto LABEL_9;
    }
    v18 = v26;
    v14 = Json::Value::Value((Json::Value *)v26, (const struct Json::Value *)&v22);
    v15 = Json::Value::operator[](&v24, i);
    Json::Value::operator=(v15, v14);
LABEL_11:
    Json::Value::~Value(&v22);
  }
  if ( v30
    && v28
    && (ValueString = MapControl::EndPoints::getValueString(v26),
        v4 = 1,
        !(unsigned __int8)Utility::StringUtils::equalCaseInsensitive<unsigned short>(v27, ValueString))
    && ((_BYTE)v25 && (unsigned __int8)(v25 - 6) > 1u || Json::Value::size((Json::Value *)&v24)) )
  {
    v17 = 1;
LABEL_21:
    std::wstring::_Tidy_deallocate(v26);
    if ( v17 )
    {
      Pal::Date::convertStringToDate((Pal::Date *)&v18);
      MapControl::ConfigurationManager::submitOverridesImpl(this, (__int64)v29, (__int64)v27, &v24, &v18, 0);
      Microsoft::WRL::Details::MakeAllocator<ConfigurationManagerAdapter>::~MakeAllocator<ConfigurationManagerAdapter>(&v18);
    }
  }
  else
  {
    v17 = 0;
    if ( (v4 & 1) != 0 )
      goto LABEL_21;
  }
  if ( v19 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v19, v20, v5, v6);
    std::_Deallocate<16>(v19, (v21 - (_QWORD)v19) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  std::wstring::_Tidy_deallocate(v31);
  std::wstring::_Tidy_deallocate(v27);
  std::wstring::_Tidy_deallocate(v29);
  Json::Value::~Value(&v24);
}

```

## disassembly

```asm
0x1800222e4  mov     [rsp-8+arg_10], rbx
0x1800222e9  push    rbp
0x1800222ea  push    rdi
0x1800222eb  push    r12
0x1800222ed  push    r13
0x1800222ef  push    r14
0x1800222f1  lea     rbp, [rsp-30h]
0x1800222f6  sub     rsp, 130h
0x1800222fd  mov     rax, cs:__security_cookie
0x180022304  xor     rax, rsp
0x180022307  mov     [rbp+50h+var_28], rax
0x18002230b  mov     r12, rdx
0x18002230e  mov     r13, rcx
0x180022311  xor     r14d, r14d
0x180022314  mov     dword ptr [rsp+150h+var_120], r14d
0x180022319  xor     edx, edx
0x18002231b  lea     rcx, [rsp+150h+var_D8]
0x180022320  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x180022325  nop
0x180022326  lea     rcx, [rbp+50h+var_68]
0x18002232a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002232f  nop
0x180022330  lea     rcx, [rbp+50h+var_88]
0x180022334  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180022339  nop
0x18002233a  lea     rcx, [rbp+50h+var_48]
0x18002233e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180022343  nop
0x180022344  lea     rdx, [rsp+150h+var_118]
0x180022349  mov     rcx, r12
0x18002234c  call    ?getMemberNames@Value@Json@@QEBA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; Json::Value::getMemberNames(void)
0x180022351  nop
0x180022352  mov     rdi, [rsp+150h+var_118]
0x180022357  jmp     loc_1800224A4
0x18002235c  mov     rdx, rdi
0x18002235f  mov     rcx, r12
0x180022362  call    ??AValue@Json@@QEBAAEBV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Json::Value::operator[](std::wstring const &)
0x180022367  mov     rdx, rax; struct Json::Value *
0x18002236a  lea     rcx, [rsp+150h+var_100]; this
0x18002236f  call    ??0Value@Json@@QEAA@AEBV01@@Z; Json::Value::Value(Json::Value const &)
0x180022374  nop
0x180022375  cmp     [rsp+150h+var_F8], 4
0x18002237a  jnz     loc_180022496
0x180022380  mov     rcx, rdi
0x180022383  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022388  mov     r10, rax
0x18002238b  lea     rcx, ?kTimestampKey@StringKeyToEnumKeyMap@MapControl@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const MapControl::StringKeyToEnumKeyMap::kTimestampKey
0x180022392  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022397  mov     r8, rax
0x18002239a  mov     r9, cs:qword_18007BAE0
0x1800223a1  mov     rdx, [rdi+10h]
0x1800223a5  mov     rcx, r10
0x1800223a8  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800223ad  test    al, al
0x1800223af  jz      short loc_1800223C8
0x1800223b1  lea     rdx, [rbp+50h+var_B0]
0x1800223b5  lea     rcx, [rsp+150h+var_100]
0x1800223ba  call    ?asString@Value@Json@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Json::Value::asString(void)
0x1800223bf  lea     rcx, [rbp+50h+var_48]
0x1800223c3  jmp     loc_180022450
0x1800223c8  mov     rcx, rdi
0x1800223cb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800223d0  mov     r10, rax
0x1800223d3  lea     rcx, ?kRegionKey@StringKeyToEnumKeyMap@MapControl@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const MapControl::StringKeyToEnumKeyMap::kRegionKey
0x1800223da  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800223df  mov     r8, rax
0x1800223e2  mov     r9, cs:qword_18007BB00
0x1800223e9  mov     rdx, [rdi+10h]
0x1800223ed  mov     rcx, r10
0x1800223f0  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800223f5  test    al, al
0x1800223f7  jz      short loc_18002240D
0x1800223f9  lea     rdx, [rbp+50h+var_B0]
0x1800223fd  lea     rcx, [rsp+150h+var_100]
0x180022402  call    ?asString@Value@Json@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Json::Value::asString(void)
0x180022407  lea     rcx, [rbp+50h+var_68]
0x18002240b  jmp     short loc_180022450
0x18002240d  mov     rcx, rdi
0x180022410  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022415  mov     r10, rax
0x180022418  lea     rcx, ?kLanguageKey@StringKeyToEnumKeyMap@MapControl@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const MapControl::StringKeyToEnumKeyMap::kLanguageKey
0x18002241f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022424  mov     r8, rax
0x180022427  mov     r9, cs:qword_18007BB20
0x18002242e  mov     rdx, [rdi+10h]
0x180022432  mov     rcx, r10
0x180022435  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002243a  test    al, al
0x18002243c  jz      short loc_180022463
0x18002243e  lea     rdx, [rbp+50h+var_B0]
0x180022442  lea     rcx, [rsp+150h+var_100]
0x180022447  call    ?asString@Value@Json@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Json::Value::asString(void)
0x18002244c  lea     rcx, [rbp+50h+var_88]
0x180022450  mov     rdx, rax
0x180022453  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180022458  lea     rcx, [rbp+50h+var_B0]
0x18002245c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022461  jmp     short loc_180022496
0x180022463  lea     rax, [rbp+50h+var_B0]
0x180022467  mov     [rsp+150h+var_120], rax
0x18002246c  lea     rdx, [rsp+150h+var_100]; struct Json::Value *
0x180022471  lea     rcx, [rbp+50h+var_B0]; this
0x180022475  call    ??0Value@Json@@QEAA@AEBV01@@Z; Json::Value::Value(Json::Value const &)
0x18002247a  mov     rbx, rax
0x18002247d  mov     rdx, rdi
0x180022480  lea     rcx, [rsp+150h+var_D8]
0x180022485  call    ??AValue@Json@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Json::Value::operator[](std::wstring const &)
0x18002248a  mov     rcx, rax
0x18002248d  mov     rdx, rbx
0x180022490  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x180022495  nop
0x180022496  lea     rcx, [rsp+150h+var_100]; this
0x18002249b  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x1800224a0  add     rdi, 20h ; ' '
0x1800224a4  cmp     rdi, [rsp+150h+var_110]
0x1800224a9  jnz     loc_18002235C
0x1800224af  cmp     [rbp+50h+var_58], 0
0x1800224b4  jz      short loc_1800224FD
0x1800224b6  cmp     [rbp+50h+var_78], 0
0x1800224bb  jz      short loc_1800224FD
0x1800224bd  lea     rcx, [rbp+50h+var_B0]
0x1800224c1  call    ?getValueString@EndPoints@MapControl@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ConfigurationKeys@2@@Z; MapControl::EndPoints::getValueString(MapControl::ConfigurationKeys)
0x1800224c6  mov     r14d, 1
0x1800224cc  mov     rdx, rax
0x1800224cf  lea     rcx, [rbp+50h+var_88]
0x1800224d3  call    ??$equalCaseInsensitive@G@StringUtils@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Utility::StringUtils::equalCaseInsensitive<ushort>(std::wstring const &,std::wstring const &)
0x1800224d8  test    al, al
0x1800224da  jnz     short loc_1800224FD
0x1800224dc  mov     eax, [rbp+50h+var_D0]
0x1800224df  test    al, al
0x1800224e1  jz      short loc_1800224EA
0x1800224e3  sub     al, 6
0x1800224e5  cmp     al, r14b
0x1800224e8  ja      short loc_1800224F8
0x1800224ea  lea     rcx, [rsp+150h+var_D8]; this
0x1800224ef  call    ?size@Value@Json@@QEBAIXZ; Json::Value::size(void)
0x1800224f4  test    eax, eax
0x1800224f6  jz      short loc_1800224FD
0x1800224f8  mov     bl, r14b
0x1800224fb  jmp     short loc_180022505
0x1800224fd  xor     bl, bl
0x1800224ff  test    r14b, 1
0x180022503  jz      short loc_180022554
0x180022505  lea     rcx, [rbp+50h+var_B0]
0x180022509  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002250e  test    bl, bl
0x180022510  jz      short loc_180022554
0x180022512  lea     rdx, [rbp+50h+var_48]
0x180022516  lea     rcx, [rsp+150h+var_120]; this
0x18002251b  call    ?convertStringToDate@Date@Pal@@SA?AV12@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::Date::convertStringToDate(std::wstring const &)
0x180022520  nop
0x180022521  mov     [rsp+150h+var_128], 0
0x180022529  lea     rax, [rsp+150h+var_120]
0x18002252e  mov     [rsp+150h+var_130], rax
0x180022533  lea     r9, [rsp+150h+var_D8]
0x180022538  lea     r8, [rbp+50h+var_88]
0x18002253c  lea     rdx, [rbp+50h+var_68]
0x180022540  mov     rcx, r13
0x180022543  call    ?submitOverridesImpl@ConfigurationManager@MapControl@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBVValue@Json@@AEBVDate@Pal@@W4OverridesSource@12@@Z; MapControl::ConfigurationManager::submitOverridesImpl(std::wstring const &,std::wstring const &,Json::Value const &,Pal::Date const &,MapControl::ConfigurationManager::OverridesSource)
0x180022548  nop
0x180022549  lea     rcx, [rsp+150h+var_120]
0x18002254e  call    ??1?$MakeAllocator@VConfigurationManagerAdapter@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<ConfigurationManagerAdapter>::~MakeAllocator<ConfigurationManagerAdapter>(void)
0x180022553  nop
0x180022554  cmp     [rsp+150h+var_118], 0
0x18002255a  jz      short loc_180022584
0x18002255c  mov     rdx, [rsp+150h+var_110]
0x180022561  mov     rcx, [rsp+150h+var_118]
0x180022566  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002256b  mov     rdx, [rsp+150h+var_108]
0x180022570  sub     rdx, [rsp+150h+var_118]
0x180022575  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180022579  mov     rcx, [rsp+150h+var_118]
0x18002257e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180022583  nop
0x180022584  lea     rcx, [rbp+50h+var_48]
0x180022588  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002258d  nop
0x18002258e  lea     rcx, [rbp+50h+var_88]
0x180022592  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022597  nop
0x180022598  lea     rcx, [rbp+50h+var_68]
0x18002259c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800225a1  nop
0x1800225a2  lea     rcx, [rsp+150h+var_D8]; this
0x1800225a7  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x1800225ac  mov     rcx, [rbp+50h+var_28]
0x1800225b0  xor     rcx, rsp; StackCookie
0x1800225b3  call    __security_check_cookie
0x1800225b8  mov     rbx, [rsp+150h+arg_10]
0x1800225c0  add     rsp, 130h
0x1800225c7  pop     r14
0x1800225c9  pop     r13
0x1800225cb  pop     r12
0x1800225cd  pop     rdi
0x1800225ce  pop     rbp
0x1800225cf  retn
```
