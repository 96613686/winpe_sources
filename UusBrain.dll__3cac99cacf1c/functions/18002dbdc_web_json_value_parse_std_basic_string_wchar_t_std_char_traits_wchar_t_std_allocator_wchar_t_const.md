# web::json::value::parse(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18002dbdc`
- end: `0x18002dd80`
- name: `?parse@value@json@web@@SA?AV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180009f40`

## callees

- `0x18000f8cc`
- `0x18002769c`
- `0x180029644`
- `0x18002dbdc`
- `0x18002e0cc`
- `0x18002e198`
- `0x18002f6a4`
- `0x1800322e8`
- `0x1800427d0`
- `0x180047a30`

## string_xrefs

- `0x18002dd0b`: `Left-over characters in stream after parsing a JSON value`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall web::json::value::parse(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v3; // rcx
  __int64 *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  _BYTE v12[8]; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD *v13; // [rsp+30h] [rbp-D0h]
  _BYTE v14[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v15[40]; // [rsp+58h] [rbp-A8h] BYREF
  int v16; // [rsp+80h] [rbp-80h] BYREF
  __int128 v17; // [rsp+88h] [rbp-78h] BYREF
  __int64 v18; // [rsp+98h] [rbp-68h]
  __int64 v19; // [rsp+A0h] [rbp-60h]
  int v20; // [rsp+C8h] [rbp-38h] BYREF
  void ***v21; // [rsp+D0h] [rbp-30h]
  _QWORD v22[7]; // [rsp+E0h] [rbp-20h] BYREF

  v13 = a1;
  v22[1] = 1;
  v22[2] = 1;
  v22[3] = 0;
  v22[0] = &web::json::details::JSON_StringParser<wchar_t>::`vftable';
  v3 = a2;
  if ( a2[3] > 7u )
    v3 = (_QWORD *)*a2;
  v22[4] = v3;
  v22[5] = v3;
  v22[6] = (char *)v3 + 2 * a2[2];
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 7;
  LOWORD(v17) = 0;
  v20 = 0;
  v21 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  web::json::details::JSON_Parser<wchar_t>::GetNextToken(v22, &v16);
  if ( v20 )
  {
    v8 = std::error_code::message(&v20, v14);
    v9 = utility::conversions::to_string_t(v15, v8);
    web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(&v16, v9);
  }
  *a1 = 0;
  v4 = (__int64 *)web::json::details::JSON_Parser<wchar_t>::_ParseValue(v22, v12, &v16);
  v5 = *v4;
  *v4 = 0;
  *a1 = v5;
  v6 = *v4;
  if ( v6 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 192LL))(v6, 1);
  if ( v20 )
  {
    v10 = std::error_code::message(&v20, v15);
    v11 = utility::conversions::to_string_t(v14, v10);
    web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(&v16, v11);
  }
  if ( v16 )
  {
    std::wstring::wstring(v14, L"Left-over characters in stream after parsing a JSON value");
    web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(&v16, v14);
  }
  std::wstring::_Tidy_deallocate(&v17);
  return a1;
}

```

## disassembly

```asm
0x18002dbdc  mov     [rsp-8+arg_8], rbx
0x18002dbe1  mov     [rsp-8+arg_10], rdi
0x18002dbe6  push    rbp
0x18002dbe7  lea     rbp, [rsp-20h]
0x18002dbec  sub     rsp, 120h
0x18002dbf3  mov     rax, cs:__security_cookie
0x18002dbfa  xor     rax, rsp
0x18002dbfd  mov     [rbp+20h+var_8], rax
0x18002dc01  mov     rbx, rcx
0x18002dc04  mov     [rsp+120h+var_F0], rcx
0x18002dc09  xor     edi, edi
0x18002dc0b  mov     [rsp+120h+var_100], edi
0x18002dc0f  mov     [rbp+20h+var_38], 1
0x18002dc17  mov     [rbp+20h+var_30], 1
0x18002dc1f  mov     [rbp+20h+var_28], rdi
0x18002dc23  lea     rax, ??_7?$JSON_StringParser@_W@details@json@web@@6B@; const web::json::details::JSON_StringParser<wchar_t>::`vftable'
0x18002dc2a  mov     [rbp+20h+var_40], rax
0x18002dc2e  mov     rcx, rdx
0x18002dc31  cmp     qword ptr [rdx+18h], 7
0x18002dc36  jbe     short loc_18002DC3B
0x18002dc38  mov     rcx, [rdx]
0x18002dc3b  mov     [rbp+20h+var_20], rcx
0x18002dc3f  mov     [rbp+20h+var_18], rcx
0x18002dc43  mov     rax, [rdx+10h]
0x18002dc47  lea     rcx, [rcx+rax*2]
0x18002dc4b  mov     [rbp+20h+var_10], rcx
0x18002dc4f  mov     [rbp+20h+var_A0], edi
0x18002dc52  xorps   xmm0, xmm0
0x18002dc55  movups  [rbp+20h+var_98], xmm0
0x18002dc59  mov     [rbp+20h+var_88], rdi
0x18002dc5d  mov     [rbp+20h+var_80], 7
0x18002dc65  mov     word ptr [rbp+20h+var_98], di
0x18002dc69  mov     [rbp+20h+var_58], edi
0x18002dc6c  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18002dc73  mov     [rbp+20h+var_50], rax
0x18002dc77  lea     rdx, [rbp+20h+var_A0]
0x18002dc7b  lea     rcx, [rbp+20h+var_40]
0x18002dc7f  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18002dc84  cmp     [rbp+20h+var_58], edi
0x18002dc87  jnz     loc_18002DD2C
0x18002dc8d  xor     eax, eax
0x18002dc8f  mov     [rbx], rax
0x18002dc92  lea     r8, [rbp+20h+var_A0]
0x18002dc96  lea     rdx, [rsp+120h+var_F8]
0x18002dc9b  lea     rcx, [rbp+20h+var_40]
0x18002dc9f  call    ?_ParseValue@?$JSON_Parser@_W@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::_ParseValue(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18002dca4  mov     rcx, rax
0x18002dca7  mov     rax, [rax]
0x18002dcaa  mov     [rcx], rdi
0x18002dcad  mov     [rbx], rax
0x18002dcb0  mov     rcx, [rcx]
0x18002dcb3  test    rcx, rcx
0x18002dcb6  jz      short loc_18002DCCC
0x18002dcb8  mov     rax, [rcx]
0x18002dcbb  mov     edx, 1
0x18002dcc0  mov     rax, [rax+0C0h]
0x18002dcc7  call    _guard_dispatch_icall
0x18002dccc  mov     [rsp+120h+var_100], 3
0x18002dcd4  cmp     [rbp+20h+var_58], edi
0x18002dcd7  jnz     short loc_18002DD56
0x18002dcd9  cmp     [rbp+20h+var_A0], edi
0x18002dcdc  jnz     short loc_18002DD0B
0x18002dcde  lea     rcx, [rbp+20h+var_98]
0x18002dce2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dce7  mov     rax, rbx
0x18002dcea  mov     rcx, [rbp+20h+var_8]
0x18002dcee  xor     rcx, rsp; StackCookie
0x18002dcf1  call    __security_check_cookie
0x18002dcf6  lea     r11, [rsp+120h+var_s0]
0x18002dcfe  mov     rbx, [r11+18h]
0x18002dd02  mov     rdi, [r11+20h]
0x18002dd06  mov     rsp, r11
0x18002dd09  pop     rbp
0x18002dd0a  retn
0x18002dd0b  lea     rdx, aLeftOverCharac; "Left-over characters in stream after pa"...
0x18002dd12  lea     rcx, [rsp+120h+var_E8]
0x18002dd17  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002dd1c  nop
0x18002dd1d  lea     rdx, [rsp+120h+var_E8]
0x18002dd22  lea     rcx, [rbp+20h+var_A0]
0x18002dd26  call    ??$CreateException@UToken@?$JSON_Parser@D@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@D@012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(web::json::details::JSON_Parser<char>::Token const &,std::wstring const &)
0x18002dd2c  lea     rdx, [rsp+120h+var_E8]
0x18002dd31  lea     rcx, [rbp+20h+var_58]
0x18002dd35  call    ?message@error_code@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::error_code::message(void)
0x18002dd3a  nop
0x18002dd3b  mov     rdx, rax
0x18002dd3e  lea     rcx, [rsp+120h+var_C8]
0x18002dd43  call    ?to_string_t@conversions@utility@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; utility::conversions::to_string_t(std::string &&)
0x18002dd48  nop
0x18002dd49  mov     rdx, rax
0x18002dd4c  lea     rcx, [rbp+20h+var_A0]
0x18002dd50  call    ??$CreateException@UToken@?$JSON_Parser@D@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@D@012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(web::json::details::JSON_Parser<char>::Token const &,std::wstring const &)
0x18002dd56  lea     rdx, [rsp+120h+var_C8]
0x18002dd5b  lea     rcx, [rbp+20h+var_58]
0x18002dd5f  call    ?message@error_code@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::error_code::message(void)
0x18002dd64  nop
0x18002dd65  mov     rdx, rax
0x18002dd68  lea     rcx, [rsp+120h+var_E8]
0x18002dd6d  call    ?to_string_t@conversions@utility@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; utility::conversions::to_string_t(std::string &&)
0x18002dd72  nop
0x18002dd73  mov     rdx, rax
0x18002dd76  lea     rcx, [rbp+20h+var_A0]
0x18002dd7a  call    ??$CreateException@UToken@?$JSON_Parser@D@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@D@012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(web::json::details::JSON_Parser<char>::Token const &,std::wstring const &)
```
