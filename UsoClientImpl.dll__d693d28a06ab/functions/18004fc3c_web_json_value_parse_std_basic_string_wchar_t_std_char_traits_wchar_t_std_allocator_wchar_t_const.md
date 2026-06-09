# web::json::value::parse(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18004fc3c`
- end: `0x18004fde0`
- name: `?parse@value@json@web@@SA?AV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `420`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800403f4`
- `0x180040a9c`
- `0x180042174`

## callees

- `0x180009380`
- `0x1800317bc`
- `0x180033974`
- `0x18004fc3c`
- `0x18004fde8`
- `0x18004feb4`
- `0x180050e88`
- `0x1800529e8`
- `0x180056500`
- `0x18005c5e0`

## string_xrefs

- `0x18004fd6b`: `Left-over characters in stream after parsing a JSON value`

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
    web::json::details::CreateException<web::json::details::JSON_Parser<wchar_t>::Token>(&v16, v9);
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
    web::json::details::CreateException<web::json::details::JSON_Parser<wchar_t>::Token>(&v16, v11);
  }
  if ( v16 )
  {
    std::wstring::wstring(v14, L"Left-over characters in stream after parsing a JSON value");
    web::json::details::CreateException<web::json::details::JSON_Parser<wchar_t>::Token>(&v16, v14);
  }
  std::wstring::~wstring(&v17);
  return a1;
}

```

## disassembly

```asm
0x18004fc3c  mov     [rsp-8+arg_8], rbx
0x18004fc41  mov     [rsp-8+arg_10], rdi
0x18004fc46  push    rbp
0x18004fc47  lea     rbp, [rsp-20h]
0x18004fc4c  sub     rsp, 120h
0x18004fc53  mov     rax, cs:__security_cookie
0x18004fc5a  xor     rax, rsp
0x18004fc5d  mov     [rbp+20h+var_8], rax
0x18004fc61  mov     rbx, rcx
0x18004fc64  mov     [rsp+120h+var_F0], rcx
0x18004fc69  xor     edi, edi
0x18004fc6b  mov     [rsp+120h+var_100], edi
0x18004fc6f  mov     [rbp+20h+var_38], 1
0x18004fc77  mov     [rbp+20h+var_30], 1
0x18004fc7f  mov     [rbp+20h+var_28], rdi
0x18004fc83  lea     rax, ??_7?$JSON_StringParser@_W@details@json@web@@6B@; const web::json::details::JSON_StringParser<wchar_t>::`vftable'
0x18004fc8a  mov     [rbp+20h+var_40], rax
0x18004fc8e  mov     rcx, rdx
0x18004fc91  cmp     qword ptr [rdx+18h], 7
0x18004fc96  jbe     short loc_18004FC9B
0x18004fc98  mov     rcx, [rdx]
0x18004fc9b  mov     [rbp+20h+var_20], rcx
0x18004fc9f  mov     [rbp+20h+var_18], rcx
0x18004fca3  mov     rax, [rdx+10h]
0x18004fca7  lea     rcx, [rcx+rax*2]
0x18004fcab  mov     [rbp+20h+var_10], rcx
0x18004fcaf  mov     [rbp+20h+var_A0], edi
0x18004fcb2  xorps   xmm0, xmm0
0x18004fcb5  movups  [rbp+20h+var_98], xmm0
0x18004fcb9  mov     [rbp+20h+var_88], rdi
0x18004fcbd  mov     [rbp+20h+var_80], 7
0x18004fcc5  mov     word ptr [rbp+20h+var_98], di
0x18004fcc9  mov     [rbp+20h+var_58], edi
0x18004fccc  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18004fcd3  mov     [rbp+20h+var_50], rax
0x18004fcd7  lea     rdx, [rbp+20h+var_A0]
0x18004fcdb  lea     rcx, [rbp+20h+var_40]
0x18004fcdf  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18004fce4  cmp     [rbp+20h+var_58], edi
0x18004fce7  jnz     loc_18004FD8C
0x18004fced  xor     eax, eax
0x18004fcef  mov     [rbx], rax
0x18004fcf2  lea     r8, [rbp+20h+var_A0]
0x18004fcf6  lea     rdx, [rsp+120h+var_F8]
0x18004fcfb  lea     rcx, [rbp+20h+var_40]
0x18004fcff  call    ?_ParseValue@?$JSON_Parser@_W@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::_ParseValue(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18004fd04  mov     rcx, rax
0x18004fd07  mov     rax, [rax]
0x18004fd0a  mov     [rcx], rdi
0x18004fd0d  mov     [rbx], rax
0x18004fd10  mov     rcx, [rcx]
0x18004fd13  test    rcx, rcx
0x18004fd16  jz      short loc_18004FD2C
0x18004fd18  mov     rax, [rcx]
0x18004fd1b  mov     edx, 1
0x18004fd20  mov     rax, [rax+0C0h]
0x18004fd27  call    _guard_dispatch_icall
0x18004fd2c  mov     [rsp+120h+var_100], 3
0x18004fd34  cmp     [rbp+20h+var_58], edi
0x18004fd37  jnz     short loc_18004FDB6
0x18004fd39  cmp     [rbp+20h+var_A0], edi
0x18004fd3c  jnz     short loc_18004FD6B
0x18004fd3e  lea     rcx, [rbp+20h+var_98]; void *
0x18004fd42  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004fd47  mov     rax, rbx
0x18004fd4a  mov     rcx, [rbp+20h+var_8]
0x18004fd4e  xor     rcx, rsp; StackCookie
0x18004fd51  call    __security_check_cookie
0x18004fd56  lea     r11, [rsp+120h+var_s0]
0x18004fd5e  mov     rbx, [r11+18h]
0x18004fd62  mov     rdi, [r11+20h]
0x18004fd66  mov     rsp, r11
0x18004fd69  pop     rbp
0x18004fd6a  retn
0x18004fd6b  lea     rdx, aLeftOverCharac; "Left-over characters in stream after pa"...
0x18004fd72  lea     rcx, [rsp+120h+var_E8]
0x18004fd77  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18004fd7c  nop
0x18004fd7d  lea     rdx, [rsp+120h+var_E8]
0x18004fd82  lea     rcx, [rbp+20h+var_A0]
0x18004fd86  call    ??$CreateException@UToken@?$JSON_Parser@_W@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@_W@012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::details::CreateException<web::json::details::JSON_Parser<wchar_t>::Token>(web::json::details::JSON_Parser<wchar_t>::Token const &,std::wstring const &)
0x18004fd8c  lea     rdx, [rsp+120h+var_E8]
0x18004fd91  lea     rcx, [rbp+20h+var_58]
0x18004fd95  call    ?message@error_code@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::error_code::message(void)
0x18004fd9a  nop
0x18004fd9b  mov     rdx, rax
0x18004fd9e  lea     rcx, [rsp+120h+var_C8]
0x18004fda3  call    ?to_string_t@conversions@utility@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; utility::conversions::to_string_t(std::string &&)
0x18004fda8  nop
0x18004fda9  mov     rdx, rax
0x18004fdac  lea     rcx, [rbp+20h+var_A0]
0x18004fdb0  call    ??$CreateException@UToken@?$JSON_Parser@_W@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@_W@012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::details::CreateException<web::json::details::JSON_Parser<wchar_t>::Token>(web::json::details::JSON_Parser<wchar_t>::Token const &,std::wstring const &)
0x18004fdb6  lea     rdx, [rsp+120h+var_C8]
0x18004fdbb  lea     rcx, [rbp+20h+var_58]
0x18004fdbf  call    ?message@error_code@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::error_code::message(void)
0x18004fdc4  nop
0x18004fdc5  mov     rdx, rax
0x18004fdc8  lea     rcx, [rsp+120h+var_E8]
0x18004fdcd  call    ?to_string_t@conversions@utility@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; utility::conversions::to_string_t(std::string &&)
0x18004fdd2  nop
0x18004fdd3  mov     rdx, rax
0x18004fdd6  lea     rcx, [rbp+20h+var_A0]
0x18004fdda  call    ??$CreateException@UToken@?$JSON_Parser@_W@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@_W@012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::details::CreateException<web::json::details::JSON_Parser<wchar_t>::Token>(web::json::details::JSON_Parser<wchar_t>::Token const &,std::wstring const &)
```
