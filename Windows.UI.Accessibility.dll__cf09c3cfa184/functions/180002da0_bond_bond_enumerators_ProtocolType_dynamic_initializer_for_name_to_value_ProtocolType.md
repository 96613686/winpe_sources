# bond::_bond_enumerators::ProtocolType::_dynamic_initializer_for___name_to_value_ProtocolType__

- ea: `0x180002da0`
- end: `0x180002f21`
- name: `bond::_bond_enumerators::ProtocolType::_dynamic_initializer_for___name_to_value_ProtocolType__`
- size: `385`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003980`
- `0x180003e70`
- `0x18000d170`
- `0x1800125f4`
- `0x18001263c`
- `0x180016730`
- `0x18002e858`
- `0x180030520`
- `0x180030988`
- `0x180030d00`
- `0x180031908`

## string_xrefs

- `0x180002e26`: `MAFIA_PROTOCOL`
- `0x180002dbc`: `MARSHALED_PROTOCOL`
- `0x180002e6e`: `JSON_PROTOCOL`
- `0x180002e4a`: `COMPACT_PROTOCOL`
- `0x180002eb6`: `SIMPLE_PROTOCOL`
- `0x180002e92`: `PRETTY_JSON_PROTOCOL`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int bond::_bond_enumerators::ProtocolType::_dynamic_initializer_for___name_to_value_ProtocolType__()
{
  _BYTE v1[32]; // [rsp+28h] [rbp-51h] BYREF
  int v2; // [rsp+48h] [rbp-31h]
  _OWORD v3[2]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v4; // [rsp+70h] [rbp-9h]
  _BYTE v5[40]; // [rsp+78h] [rbp-1h] BYREF
  _BYTE v6[32]; // [rsp+A0h] [rbp+27h] BYREF

  std::string::string(v6, "MARSHALED_PROTOCOL");
  memset(v3, 0, sizeof(v3));
  v4 = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(v3);
  std::string::string(v1, v6);
  v2 = 0;
  boost::assign_detail::generic_list<std::pair<std::string,enum bond::_bond_enumerators::Modifier::Modifier>>::push_back(
    v3,
    v1);
  std::deque<std::pair<std::string,enum bond::_bond_enumerators::Modifier::Modifier>>::deque<std::pair<std::string,enum bond::_bond_enumerators::Modifier::Modifier>>(
    v5,
    v3);
  std::deque<std::pair<std::string,enum bond::_bond_enumerators::ProtocolType::ProtocolType>>::~deque<std::pair<std::string,enum bond::_bond_enumerators::ProtocolType::ProtocolType>>(v3);
  std::string::string(v1, "MAFIA_PROTOCOL");
  v2 = 17997;
  boost::assign_detail::generic_list<std::pair<std::string,enum bond::_bond_enumerators::Modifier::Modifier>>::push_back(
    v5,
    v1);
  std::string::string(v1, "COMPACT_PROTOCOL");
  v2 = 16963;
  boost::assign_detail::generic_list<std::pair<std::string,enum bond::_bond_enumerators::Modifier::Modifier>>::push_back(
    v5,
    v1);
  std::string::string(v1, "JSON_PROTOCOL");
  v2 = 21322;
  boost::assign_detail::generic_list<std::pair<std::string,enum bond::_bond_enumerators::Modifier::Modifier>>::push_back(
    v5,
    v1);
  std::string::string(v1, "PRETTY_JSON_PROTOCOL");
  v2 = 20554;
  boost::assign_detail::generic_list<std::pair<std::string,enum bond::_bond_enumerators::Modifier::Modifier>>::push_back(
    v5,
    v1);
  std::string::string(v1, "SIMPLE_PROTOCOL");
  v2 = 20563;
  boost::assign_detail::generic_list<std::pair<std::string,enum bond::_bond_enumerators::Modifier::Modifier>>::push_back(
    v5,
    v1);
  boost::assign_detail::converter<boost::assign_detail::generic_list<std::pair<std::string,enum bond::_bond_enumerators::ProtocolType::ProtocolType>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::pair<std::string,enum bond::_bond_enumerators::ProtocolType::ProtocolType>>>>>::convert_to_container<std::map<std::string,enum bond::_bond_enumerators::ProtocolType::ProtocolType>>(v5);
  std::deque<std::pair<std::string,enum bond::_bond_enumerators::ProtocolType::ProtocolType>>::~deque<std::pair<std::string,enum bond::_bond_enumerators::ProtocolType::ProtocolType>>(v5);
  std::string::_Tidy_deallocate(v6);
  wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(v6);
  return atexit(bond::_bond_enumerators::ProtocolType::_dynamic_atexit_destructor_for___name_to_value_ProtocolType__);
}

```

## disassembly

```asm
0x180002da0  push    rbp
0x180002da2  lea     rbp, [rsp-57h]
0x180002da7  sub     rsp, 0D0h
0x180002dae  mov     rax, cs:__security_cookie
0x180002db5  xor     rax, rsp
0x180002db8  mov     [rbp+57h+var_10], rax
0x180002dbc  lea     rdx, aMarshaledProto; "MARSHALED_PROTOCOL"
0x180002dc3  lea     rcx, [rbp+57h+var_30]
0x180002dc7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180002dcc  nop
0x180002dcd  xorps   xmm0, xmm0
0x180002dd0  xor     eax, eax
0x180002dd2  movdqu  [rbp+57h+var_80], xmm0
0x180002dd7  xorps   xmm1, xmm1
0x180002dda  movdqu  [rbp+57h+var_70], xmm1
0x180002ddf  mov     [rbp+57h+var_60], rax
0x180002de3  lea     rcx, [rbp+57h+var_80]
0x180002de7  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x180002dec  nop
0x180002ded  lea     rdx, [rbp+57h+var_30]
0x180002df1  lea     rcx, [rbp+57h+var_A8]
0x180002df5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180002dfa  mov     [rbp+57h+var_88], 0
0x180002e01  lea     rdx, [rbp+57h+var_A8]
0x180002e05  lea     rcx, [rbp+57h+var_80]
0x180002e09  call    ?push_back@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@assign_detail@boost@@AEAAXU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@Z; boost::assign_detail::generic_list<std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>>::push_back(std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>)
0x180002e0e  lea     rdx, [rbp+57h+var_80]
0x180002e12  lea     rcx, [rbp+57h+var_58]
0x180002e16  call    ??0?$deque@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@V?$allocator@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::deque<std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>>::deque<std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>>(std::deque<std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>> const &)
0x180002e1b  nop
0x180002e1c  lea     rcx, [rbp+57h+var_80]
0x180002e20  call    ??1?$deque@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@V?$allocator@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@@2@@std@@QEAA@XZ; std::deque<std::pair<std::string,bond::_bond_enumerators::ProtocolType::ProtocolType>>::~deque<std::pair<std::string,bond::_bond_enumerators::ProtocolType::ProtocolType>>(void)
0x180002e25  nop
0x180002e26  lea     rdx, aMafiaProtocol; "MAFIA_PROTOCOL"
0x180002e2d  lea     rcx, [rbp+57h+var_A8]
0x180002e31  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180002e36  mov     [rbp+57h+var_88], 464Dh
0x180002e3d  lea     rdx, [rbp+57h+var_A8]
0x180002e41  lea     rcx, [rbp+57h+var_58]
0x180002e45  call    ?push_back@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@assign_detail@boost@@AEAAXU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@Z; boost::assign_detail::generic_list<std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>>::push_back(std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>)
0x180002e4a  lea     rdx, aCompactProtoco; "COMPACT_PROTOCOL"
0x180002e51  lea     rcx, [rbp+57h+var_A8]
0x180002e55  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180002e5a  mov     [rbp+57h+var_88], 4243h
0x180002e61  lea     rdx, [rbp+57h+var_A8]
0x180002e65  lea     rcx, [rbp+57h+var_58]
0x180002e69  call    ?push_back@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@assign_detail@boost@@AEAAXU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@Z; boost::assign_detail::generic_list<std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>>::push_back(std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>)
0x180002e6e  lea     rdx, aJsonProtocol; "JSON_PROTOCOL"
0x180002e75  lea     rcx, [rbp+57h+var_A8]
0x180002e79  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180002e7e  mov     [rbp+57h+var_88], 534Ah
0x180002e85  lea     rdx, [rbp+57h+var_A8]
0x180002e89  lea     rcx, [rbp+57h+var_58]
0x180002e8d  call    ?push_back@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@assign_detail@boost@@AEAAXU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@Z; boost::assign_detail::generic_list<std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>>::push_back(std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>)
0x180002e92  lea     rdx, aPrettyJsonProt; "PRETTY_JSON_PROTOCOL"
0x180002e99  lea     rcx, [rbp+57h+var_A8]
0x180002e9d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180002ea2  mov     [rbp+57h+var_88], 504Ah
0x180002ea9  lea     rdx, [rbp+57h+var_A8]
0x180002ead  lea     rcx, [rbp+57h+var_58]
0x180002eb1  call    ?push_back@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@assign_detail@boost@@AEAAXU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@Z; boost::assign_detail::generic_list<std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>>::push_back(std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>)
0x180002eb6  lea     rdx, aSimpleProtocol; "SIMPLE_PROTOCOL"
0x180002ebd  lea     rcx, [rbp+57h+var_A8]
0x180002ec1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180002ec6  mov     [rbp+57h+var_88], 5053h
0x180002ecd  lea     rdx, [rbp+57h+var_A8]
0x180002ed1  lea     rcx, [rbp+57h+var_58]
0x180002ed5  call    ?push_back@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@assign_detail@boost@@AEAAXU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Modifier@3_bond_enumerators@bond@@@std@@@Z; boost::assign_detail::generic_list<std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>>::push_back(std::pair<std::string,bond::_bond_enumerators::Modifier::Modifier>)
0x180002eda  lea     rcx, [rbp+57h+var_58]
0x180002ede  call    ??$convert_to_container@V?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@@2@@std@@@?$converter@V?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@@assign_detail@boost@@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@@std@@@std@@@std@@@assign_detail@boost@@QEBA?AV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@@2@@std@@XZ; boost::assign_detail::converter<boost::assign_detail::generic_list<std::pair<std::string,bond::_bond_enumerators::ProtocolType::ProtocolType>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::pair<std::string,bond::_bond_enumerators::ProtocolType::ProtocolType>>>>>::convert_to_container<std::map<std::string,bond::_bond_enumerators::ProtocolType::ProtocolType>>(void)
0x180002ee3  nop
0x180002ee4  lea     rcx, [rbp+57h+var_58]
0x180002ee8  call    ??1?$deque@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@V?$allocator@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ProtocolType@3_bond_enumerators@bond@@@std@@@2@@std@@QEAA@XZ; std::deque<std::pair<std::string,bond::_bond_enumerators::ProtocolType::ProtocolType>>::~deque<std::pair<std::string,bond::_bond_enumerators::ProtocolType::ProtocolType>>(void)
0x180002eed  nop
0x180002eee  lea     rcx, [rbp+57h+var_30]
0x180002ef2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180002ef7  lea     rcx, [rbp+57h+var_30]
0x180002efb  call    ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180002f00  lea     rcx, bond___bond_enumerators__ProtocolType___dynamic_atexit_destructor_for___name_to_value_ProtocolType__; void (__cdecl *)()
0x180002f07  call    atexit
0x180002f0c  mov     rcx, [rbp+57h+var_10]
0x180002f10  xor     rcx, rsp; StackCookie
0x180002f13  call    __security_check_cookie
0x180002f18  add     rsp, 0D0h
0x180002f1f  pop     rbp
0x180002f20  retn
```
