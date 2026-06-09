# web::uri::decode(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003d6d0`
- end: `0x18003d82b`
- name: `?decode@uri@web@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z`
- size: `347`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18003d090`
- `0x180048d24`
- `0x18004ee50`

## callees

- `0x180004fa0`
- `0x180005e9c`
- `0x180009698`
- `0x1800096d4`
- `0x18000e5a8`
- `0x18000eca4`
- `0x18003b8ac`
- `0x18003bfb0`
- `0x18003ce48`
- `0x18003d6d0`
- `0x18003db98`

## string_xrefs

- `0x18003d794`: `Invalid URI string, two hexidecimal digits must follow '%'`
- `0x18003d7c1`: `Invalid URI string, two hexidecimal digits must follow '%'`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall web::uri::decode(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  unsigned __int16 *i; // rbx
  __int64 v6; // rax
  __int64 v7; // rdx
  unsigned __int16 *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rdx
  char v11; // r14
  char v12; // al
  __int64 v13; // rax
  __int64 v14; // rax
  _BYTE v16[32]; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v17[32]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+70h] [rbp+7h] BYREF

  std::string::string(v17);
  for ( i = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4); ; ++i )
  {
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    if ( i == (unsigned __int16 *)(v7 + v6) )
      break;
    if ( *i == 37 )
    {
      v8 = i + 1;
      v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      if ( v8 == (unsigned __int16 *)(v10 + v9) )
      {
        v14 = std::string::string(v16, "Invalid URI string, two hexidecimal digits must follow '%'");
        web::uri_exception::uri_exception(pExceptionObject, v14);
        throw (web::uri_exception *)pExceptionObject;
      }
      v11 = web::hex_char_digit_to_decimal_char(*v8);
      i = v8 + 1;
      if ( i == (unsigned __int16 *)(std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2)
                                   + 2LL * *(_QWORD *)(a2 + 16)) )
      {
        v13 = std::string::string(v16, "Invalid URI string, two hexidecimal digits must follow '%'");
        web::uri_exception::uri_exception(pExceptionObject, v13);
        throw (web::uri_exception *)pExceptionObject;
      }
      v12 = 16 * v11 + web::hex_char_digit_to_decimal_char(*i);
    }
    else
    {
      v12 = *(_BYTE *)i;
    }
    LOBYTE(v7) = v12;
    std::string::push_back(v17, v7);
  }
  utility::conversions::to_string_t(a1, v17);
  std::string::_Tidy_deallocate(v17);
  return a1;
}

```

## disassembly

```asm
0x18003d6d0  mov     [rsp-8+arg_8], rbx
0x18003d6d5  mov     [rsp-8+arg_10], rsi
0x18003d6da  push    rbp
0x18003d6db  push    rdi
0x18003d6dc  push    r14
0x18003d6de  lea     rbp, [rsp-47h]
0x18003d6e3  sub     rsp, 0B0h
0x18003d6ea  mov     rax, cs:__security_cookie
0x18003d6f1  xor     rax, rsp
0x18003d6f4  mov     [rbp+57h+var_18], rax
0x18003d6f8  mov     rdi, rdx
0x18003d6fb  mov     rsi, rcx
0x18003d6fe  mov     [rbp+57h+var_A0], rcx
0x18003d702  lea     rcx, [rbp+57h+var_70]
0x18003d706  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18003d70b  nop
0x18003d70c  mov     rcx, rdx
0x18003d70f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003d714  mov     rbx, rax
0x18003d717  mov     rdx, [rdi+10h]
0x18003d71b  add     rdx, rdx
0x18003d71e  mov     rcx, rdi
0x18003d721  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003d726  add     rax, rdx
0x18003d729  cmp     rbx, rax
0x18003d72c  jz      loc_18003D7EE
0x18003d732  cmp     word ptr [rbx], 25h ; '%'
0x18003d736  jnz     short loc_18003D781
0x18003d738  add     rbx, 2
0x18003d73c  mov     rcx, rdi
0x18003d73f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003d744  add     rax, rdx
0x18003d747  cmp     rbx, rax
0x18003d74a  jz      short loc_18003D7C1
0x18003d74c  movzx   ecx, word ptr [rbx]
0x18003d74f  call    web__hex_char_digit_to_decimal_char
0x18003d754  mov     r14d, eax
0x18003d757  add     rbx, 2
0x18003d75b  mov     rcx, rdi
0x18003d75e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003d763  mov     rcx, [rdi+10h]
0x18003d767  lea     rdx, [rax+rcx*2]
0x18003d76b  cmp     rbx, rdx
0x18003d76e  jz      short loc_18003D794
0x18003d770  movzx   ecx, word ptr [rbx]
0x18003d773  call    web__hex_char_digit_to_decimal_char
0x18003d778  shl     r14b, 4
0x18003d77c  add     al, r14b
0x18003d77f  jmp     short loc_18003D783
0x18003d781  mov     al, [rbx]
0x18003d783  mov     dl, al
0x18003d785  lea     rcx, [rbp+57h+var_70]
0x18003d789  call    ?push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z; std::string::push_back(char)
0x18003d78e  add     rbx, 2
0x18003d792  jmp     short loc_18003D717
0x18003d794  lea     rdx, aInvalidUriStri; "Invalid URI string, two hexidecimal dig"...
0x18003d79b  lea     rcx, [rbp+57h+var_90]
0x18003d79f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003d7a4  mov     rdx, rax
0x18003d7a7  lea     rcx, [rbp+57h+pExceptionObject]
0x18003d7ab  call    ??0uri_exception@web@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::uri_exception::uri_exception(std::string)
0x18003d7b0  lea     rdx, _TI2?AVuri_exception@web@@; pThrowInfo
0x18003d7b7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003d7bb  call    _CxxThrowException_0
0x18003d7c1  lea     rdx, aInvalidUriStri; "Invalid URI string, two hexidecimal dig"...
0x18003d7c8  lea     rcx, [rbp+57h+var_90]
0x18003d7cc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003d7d1  mov     rdx, rax
0x18003d7d4  lea     rcx, [rbp+57h+pExceptionObject]
0x18003d7d8  call    ??0uri_exception@web@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::uri_exception::uri_exception(std::string)
0x18003d7dd  lea     rdx, _TI2?AVuri_exception@web@@; pThrowInfo
0x18003d7e4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003d7e8  call    _CxxThrowException_0
0x18003d7ee  lea     rdx, [rbp+57h+var_70]
0x18003d7f2  mov     rcx, rsi
0x18003d7f5  call    ?to_string_t@conversions@utility@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; utility::conversions::to_string_t(std::string &&)
0x18003d7fa  nop
0x18003d7fb  lea     rcx, [rbp+57h+var_70]
0x18003d7ff  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003d804  mov     rax, rsi
0x18003d807  mov     rcx, [rbp+57h+var_18]
0x18003d80b  xor     rcx, rsp; StackCookie
0x18003d80e  call    __security_check_cookie
0x18003d813  lea     r11, [rsp+0C0h+var_10]
0x18003d81b  mov     rbx, [r11+28h]
0x18003d81f  mov     rsi, [r11+30h]
0x18003d823  mov     rsp, r11
0x18003d826  pop     r14
0x18003d828  pop     rdi
0x18003d829  pop     rbp
0x18003d82a  retn
```
