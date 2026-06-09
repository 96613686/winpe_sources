# Json::Value::getMemberNames(void)

- ea: `0x180035934`
- end: `0x180035a7b`
- name: `?getMemberNames@Value@Json@@QEBA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `327`
- prototype: ``
- caller_count: `6`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1800210ac`
- `0x1800219fc`
- `0x1800222e4`
- `0x1800225d8`
- `0x180022764`
- `0x18003a7e0`

## callees

- `0x1800094a0`
- `0x18000b938`
- `0x18000c354`
- `0x18000cb0c`
- `0x18000cd80`
- `0x180012158`
- `0x18001a7a8`
- `0x18001d6e4`
- `0x18002f858`
- `0x1800339c0`
- `0x180033fb0`
- `0x180033fe4`
- `0x180035934`
- `0x180035ce0`
- `0x1800360f0`

## string_xrefs

- `0x18003597e`: `in Json::Value::getMemberNames(), value must be objectValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Json::Value::getMemberNames(_BYTE *a1, _QWORD *a2)
{
  char v4; // al
  _QWORD *v5; // rdi
  _QWORD *v6; // rdx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  _QWORD *v11; // [rsp+20h] [rbp-E0h] BYREF
  void *v12[5]; // [rsp+28h] [rbp-D8h] BYREF
  char v13[8]; // [rsp+50h] [rbp-B0h] BYREF
  char v14[232]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v15[32]; // [rsp+140h] [rbp+40h] BYREF

  v11 = a2;
  v4 = a1[8];
  if ( v4 )
  {
    if ( v4 != 7 )
    {
      std::ostringstream::ostringstream((__int64)v13);
      std::operator<<<std::char_traits<char>>(
        (__int64)v13,
        (__int64)"in Json::Value::getMemberNames(), value must be objectValue");
      std::stringbuf::str(v14, v15);
      Json::throwLogicError(v15);
    }
    std::vector<std::map<enum MapControl::ConfigurationKeys,std::wstring>>::vector<std::map<enum MapControl::ConfigurationKeys,std::wstring>>(v12);
    std::vector<std::wstring>::reserve(v12, *(_QWORD *)(*(_QWORD *)a1 + 8LL));
    v5 = **(_QWORD ***)a1;
    v6 = (_QWORD *)*v5;
    v11 = (_QWORD *)*v5;
    while ( v6 != v5 )
    {
      v7 = std::wstring::wstring(v15, v6[4], (unsigned __int64)*((unsigned int *)v6 + 10) >> 2);
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(v12, v7);
      std::wstring::_Tidy_deallocate(v15);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>>,std::_Iterator_base0>::operator++(&v11);
      v6 = v11;
    }
    std::vector<std::wstring>::vector<std::wstring>(a2, v12);
    if ( v12[0] )
    {
      std::_Destroy_range<std::allocator<std::wstring>>(v12[0], v12[1], v8, v9);
      std::_Deallocate<16>(v12[0], ((char *)v12[2] - (char *)v12[0]) & 0xFFFFFFFFFFFFFFE0uLL);
    }
  }
  else
  {
    std::vector<std::map<enum MapControl::ConfigurationKeys,std::wstring>>::vector<std::map<enum MapControl::ConfigurationKeys,std::wstring>>(a2);
  }
  return a2;
}

```

## disassembly

```asm
0x180035934  mov     [rsp-8+arg_10], rbx
0x180035939  mov     [rsp-8+arg_18], rdi
0x18003593e  push    rbp
0x18003593f  lea     rbp, [rsp-70h]
0x180035944  sub     rsp, 170h
0x18003594b  mov     rax, cs:__security_cookie
0x180035952  xor     rax, rsp
0x180035955  mov     [rbp+70h+var_10], rax
0x180035959  mov     rbx, rdx
0x18003595c  mov     rdi, rcx
0x18003595f  mov     [rsp+170h+var_150], rdx
0x180035964  mov     al, [rcx+8]
0x180035967  test    al, al
0x180035969  jz      loc_180035A4F
0x18003596f  cmp     al, 7
0x180035971  jz      short loc_1800359A8
0x180035973  lea     rcx, [rsp+170h+var_120]
0x180035978  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18003597d  nop
0x18003597e  lea     rdx, aInJsonValueGet; "in Json::Value::getMemberNames(), value"...
0x180035985  lea     rcx, [rsp+170h+var_120]
0x18003598a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18003598f  lea     rdx, [rbp+70h+var_30]
0x180035993  lea     rcx, [rsp+170h+var_118]
0x180035998  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18003599d  nop
0x18003599e  lea     rcx, [rbp+70h+var_30]
0x1800359a2  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x1800359a8  lea     rcx, [rsp+170h+var_148]
0x1800359ad  call    ??0?$vector@V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@V?$allocator@V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@@2@@std@@QEAA@XZ; std::vector<std::map<MapControl::ConfigurationKeys,std::wstring>>::vector<std::map<MapControl::ConfigurationKeys,std::wstring>>(void)
0x1800359b2  nop
0x1800359b3  mov     rdx, [rdi]
0x1800359b6  mov     rdx, [rdx+8]
0x1800359ba  lea     rcx, [rsp+170h+var_148]
0x1800359bf  call    ?reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX_K@Z; std::vector<std::wstring>::reserve(unsigned __int64)
0x1800359c4  mov     rax, [rdi]
0x1800359c7  mov     rdi, [rax]
0x1800359ca  mov     rdx, [rdi]
0x1800359cd  mov     [rsp+170h+var_150], rdx
0x1800359d2  cmp     rdx, rdi
0x1800359d5  jz      short loc_180035A15
0x1800359d7  mov     r8d, [rdx+28h]
0x1800359db  shr     r8, 2
0x1800359df  mov     rdx, [rdx+20h]
0x1800359e3  lea     rcx, [rbp+70h+var_30]
0x1800359e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x1800359ec  nop
0x1800359ed  mov     rdx, rax
0x1800359f0  lea     rcx, [rsp+170h+var_148]
0x1800359f5  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x1800359fa  nop
0x1800359fb  lea     rcx, [rbp+70h+var_30]
0x1800359ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035a04  lea     rcx, [rsp+170h+var_150]
0x180035a09  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<MapControl::ConfigurationKeys const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x180035a0e  mov     rdx, [rsp+170h+var_150]
0x180035a13  jmp     short loc_1800359D2
0x180035a15  lea     rdx, [rsp+170h+var_148]
0x180035a1a  mov     rcx, rbx
0x180035a1d  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> &&)
0x180035a22  nop
0x180035a23  mov     rcx, [rsp+170h+var_148]
0x180035a28  test    rcx, rcx
0x180035a2b  jz      short loc_180035A57
0x180035a2d  mov     rdx, [rsp+170h+var_140]
0x180035a32  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180035a37  mov     rcx, [rsp+170h+var_148]
0x180035a3c  mov     rdx, [rsp+170h+var_138]
0x180035a41  sub     rdx, rcx
0x180035a44  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180035a48  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180035a4d  jmp     short loc_180035A57
0x180035a4f  mov     rcx, rbx
0x180035a52  call    ??0?$vector@V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@V?$allocator@V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@@2@@std@@QEAA@XZ; std::vector<std::map<MapControl::ConfigurationKeys,std::wstring>>::vector<std::map<MapControl::ConfigurationKeys,std::wstring>>(void)
0x180035a57  mov     rax, rbx
0x180035a5a  mov     rcx, [rbp+70h+var_10]
0x180035a5e  xor     rcx, rsp; StackCookie
0x180035a61  call    __security_check_cookie
0x180035a66  lea     r11, [rsp+170h+var_s0]
0x180035a6e  mov     rbx, [r11+20h]
0x180035a72  mov     rdi, [r11+28h]
0x180035a76  mov     rsp, r11
0x180035a79  pop     rbp
0x180035a7a  retn
```
