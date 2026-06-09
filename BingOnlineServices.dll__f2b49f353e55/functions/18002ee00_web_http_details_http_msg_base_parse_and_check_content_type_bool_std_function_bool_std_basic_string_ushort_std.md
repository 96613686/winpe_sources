# web::http::details::http_msg_base::parse_and_check_content_type(bool,std::function<bool (std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)> const &)

- ea: `0x18002ee00`
- end: `0x18002efbe`
- name: `?parse_and_check_content_type@http_msg_base@details@http@web@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEBV?$function@$$A6A_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z@6@@Z`
- size: `446`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18002aaa0`
- `0x18002d040`
- `0x18002d4d0`
- `0x18002d8d0`

## callees

- `0x180002c2c`
- `0x180002ca8`
- `0x180002db0`
- `0x180004fa0`
- `0x180005e9c`
- `0x1800096f8`
- `0x180009730`
- `0x180009778`
- `0x180024718`
- `0x180025488`
- `0x18002ee00`
- `0x180030438`
- `0x180050310`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18002ef30`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18002ef30`

## string_xrefs

- `0x18002ef4b`: `Incorrect Content-Type: must be textual to extract_string, JSON to extract_json.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall web::http::details::http_msg_base::parse_and_check_content_type(
        __int64 a1,
        __int64 a2,
        char a3,
        __int64 a4)
{
  char v8; // si
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v14; // rcx
  _BYTE v15[32]; // [rsp+30h] [rbp-99h] BYREF
  _BYTE v16[16]; // [rsp+50h] [rbp-79h] BYREF
  __int64 v17; // [rsp+60h] [rbp-69h]
  _BYTE v18[32]; // [rsp+70h] [rbp-59h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+90h] [rbp-39h] BYREF

  v8 = 0;
  v9 = *(_QWORD *)(a1 + 8);
  if ( !v9 || !*(_QWORD *)(v9 + 8) )
  {
    std::wstring::wstring(v15, L"A stream was set on the message and extraction is not possible");
    web::http::http_exception::http_exception(pExceptionObject, v15);
    throw (web::http::http_exception *)pExceptionObject;
  }
  std::wstring::wstring(v16);
  std::wstring::wstring(v18);
  if ( a3 )
    goto LABEL_16;
  v11 = web::http::http_headers::content_type(a1 + 40, v15);
  web::http::details::parse_content_type_and_charset(v11, v16, v18);
  std::wstring::_Tidy_deallocate(v15);
  if ( !v17
    || (v12 = Concurrency::streams::basic_istream<unsigned char>::streambuf(a1 + 8, v15),
        v8 = 1,
        !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 64LL))(v12)) )
  {
    a3 = 1;
  }
  if ( (v8 & 1) != 0 )
    Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v15);
  if ( !a3 )
  {
    v14 = *(_QWORD *)(a4 + 56);
    if ( !v14 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v14 + 16LL))(v14, v16) )
    {
      std::wstring::wstring(v15, L"Incorrect Content-Type: must be textual to extract_string, JSON to extract_json.");
      web::http::http_exception::http_exception(pExceptionObject, v15);
      throw (web::http::http_exception *)pExceptionObject;
    }
LABEL_16:
    std::wstring::wstring(a2, v18, v10);
    goto LABEL_11;
  }
  std::wstring::wstring(a2);
LABEL_11:
  std::wstring::_Tidy_deallocate(v18);
  std::wstring::_Tidy_deallocate(v16);
  return a2;
}

```

## disassembly

```asm
0x18002ee00  push    rbp
0x18002ee02  push    rbx
0x18002ee03  push    rsi
0x18002ee04  push    rdi
0x18002ee05  push    r12
0x18002ee07  push    r14
0x18002ee09  push    r15
0x18002ee0b  lea     rbp, [rsp-27h]
0x18002ee10  sub     rsp, 0F0h
0x18002ee17  mov     rax, cs:__security_cookie
0x18002ee1e  xor     rax, rsp
0x18002ee21  mov     [rbp+57h+var_40], rax
0x18002ee25  mov     r15, r9
0x18002ee28  mov     dil, r8b
0x18002ee2b  mov     rbx, rdx
0x18002ee2e  mov     r14, rcx
0x18002ee31  mov     [rsp+120h+var_F8], rdx
0x18002ee36  xor     esi, esi
0x18002ee38  mov     [rsp+120h+var_100], esi
0x18002ee3c  mov     rax, [rcx+8]
0x18002ee40  test    rax, rax
0x18002ee43  jz      loc_18002EF8D
0x18002ee49  cmp     [rax+8], rsi
0x18002ee4d  jz      loc_18002EF8D
0x18002ee53  lea     rcx, [rbp+57h+var_D0]
0x18002ee57  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002ee5c  nop
0x18002ee5d  lea     rdx, ?utf8@charset_types@details@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::details::charset_types::utf8
0x18002ee64  lea     rcx, [rbp+57h+var_B0]
0x18002ee68  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002ee6d  nop
0x18002ee6e  test    dil, dil
0x18002ee71  jnz     loc_18002EF7C
0x18002ee77  lea     rcx, [r14+28h]
0x18002ee7b  lea     rdx, [rsp+120h+var_F0]
0x18002ee80  call    ?content_type@http_headers@http@web@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::http::http_headers::content_type(void)
0x18002ee85  nop
0x18002ee86  lea     r8, [rbp+57h+var_B0]
0x18002ee8a  lea     rdx, [rbp+57h+var_D0]
0x18002ee8e  mov     rcx, rax
0x18002ee91  call    ?parse_content_type_and_charset@details@http@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV45@1@Z; web::http::details::parse_content_type_and_charset(std::wstring const &,std::wstring &,std::wstring &)
0x18002ee96  nop
0x18002ee97  lea     rcx, [rsp+120h+var_F0]
0x18002ee9c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002eea1  cmp     [rbp+57h+var_C0], rsi
0x18002eea5  jz      short loc_18002EED2
0x18002eea7  lea     rdx, [rsp+120h+var_F0]
0x18002eeac  lea     rcx, [r14+8]
0x18002eeb0  call    ?streambuf@?$basic_istream@E@streams@Concurrency@@QEBA?AV?$streambuf@E@23@XZ; Concurrency::streams::basic_istream<uchar>::streambuf(void)
0x18002eeb5  mov     rcx, rax
0x18002eeb8  mov     esi, 1
0x18002eebd  mov     [rsp+120h+var_100], esi
0x18002eec1  mov     rax, [rax]
0x18002eec4  mov     rax, [rax+40h]
0x18002eec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eecd  test    rax, rax
0x18002eed0  jnz     short loc_18002EED5
0x18002eed2  mov     dil, 1
0x18002eed5  test    sil, 1
0x18002eed9  jz      short loc_18002EEE5
0x18002eedb  lea     rcx, [rsp+120h+var_F0]
0x18002eee0  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x18002eee5  test    dil, dil
0x18002eee8  jz      short loc_18002EF27
0x18002eeea  mov     rcx, rbx
0x18002eeed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002eef2  nop
0x18002eef3  lea     rcx, [rbp+57h+var_B0]
0x18002eef7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002eefc  nop
0x18002eefd  lea     rcx, [rbp+57h+var_D0]
0x18002ef01  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ef06  mov     rax, rbx
0x18002ef09  mov     rcx, [rbp+57h+var_40]
0x18002ef0d  xor     rcx, rsp; StackCookie
0x18002ef10  call    __security_check_cookie
0x18002ef15  add     rsp, 0F0h
0x18002ef1c  pop     r15
0x18002ef1e  pop     r14
0x18002ef20  pop     r12
0x18002ef22  pop     rdi
0x18002ef23  pop     rsi
0x18002ef24  pop     rbx
0x18002ef25  pop     rbp
0x18002ef26  retn
0x18002ef27  mov     rcx, [r15+38h]
0x18002ef2b  test    rcx, rcx
0x18002ef2e  jnz     short loc_18002EF37
0x18002ef30  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18002ef36  int     3; Trap to Debugger
0x18002ef37  mov     rax, [rcx]
0x18002ef3a  lea     rdx, [rbp+57h+var_D0]
0x18002ef3e  mov     rax, [rax+10h]
0x18002ef42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef47  test    al, al
0x18002ef49  jnz     short loc_18002EF7C
0x18002ef4b  lea     rdx, aIncorrectConte; "Incorrect Content-Type: must be textual"...
0x18002ef52  lea     rcx, [rsp+120h+var_F0]
0x18002ef57  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ef5c  nop
0x18002ef5d  lea     rdx, [rsp+120h+var_F0]
0x18002ef62  lea     rcx, [rbp+57h+pExceptionObject]
0x18002ef66  call    ??0http_exception@http@web@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::http_exception::http_exception(std::wstring const &)
0x18002ef6b  lea     rdx, _TI2?AVhttp_exception@http@web@@; pThrowInfo
0x18002ef72  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002ef76  call    _CxxThrowException_0
0x18002ef7c  lea     rdx, [rbp+57h+var_B0]
0x18002ef80  mov     rcx, rbx
0x18002ef83  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18002ef88  jmp     loc_18002EEF3
0x18002ef8d  lea     rdx, aAStreamWasSetO; "A stream was set on the message and ext"...
0x18002ef94  lea     rcx, [rsp+120h+var_F0]
0x18002ef99  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ef9e  nop
0x18002ef9f  lea     rdx, [rsp+120h+var_F0]
0x18002efa4  lea     rcx, [rbp+57h+pExceptionObject]
0x18002efa8  call    ??0http_exception@http@web@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::http_exception::http_exception(std::wstring const &)
0x18002efad  lea     rdx, _TI2?AVhttp_exception@http@web@@; pThrowInfo
0x18002efb4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002efb8  call    _CxxThrowException_0
```
