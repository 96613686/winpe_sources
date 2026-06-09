# web::http::details::_http_request::relative_uri(void)

- ea: `0x18004ee50`
- end: `0x18004effb`
- name: `?relative_uri@_http_request@details@http@web@@QEBA?AVuri@4@XZ`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180039a30`

## callees

- `0x180002c2c`
- `0x180002ca8`
- `0x180004fa0`
- `0x180005e9c`
- `0x1800086b0`
- `0x18000e5a8`
- `0x18000f584`
- `0x180015914`
- `0x18001adbc`
- `0x18001d928`
- `0x18001df98`
- `0x180024718`
- `0x180037f18`
- `0x18003cc20`
- `0x18003d6d0`
- `0x18003d9b0`
- `0x18003dfa0`
- `0x18004ee50`

## string_xrefs

- `0x18004ef96`: `Error: request was not prefixed with listener uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall web::http::details::_http_request::relative_uri(__int64 a1, __int64 a2)
{
  __int64 v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r10
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rax
  _BYTE v14[16]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h]
  _BYTE v16[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h]
  _BYTE v18[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v19[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v21[240]; // [rsp+100h] [rbp+0h] BYREF

  v4 = a1 + 616;
  if ( !*(_QWORD *)(a1 + 632)
    || (std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 616),
        v5 = std::_WChar_traits<unsigned short>::length(L"/"),
        (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v7, v6, L"/", v5)) )
  {
    web::uri::resource(a1 + 384, a2);
  }
  else
  {
    web::uri::decode((__int64)v16, v4);
    v8 = web::uri::resource(a1 + 384, v21);
    v9 = web::uri::to_string(v8, v19);
    web::uri::decode((__int64)v14, v9);
    std::wstring::_Tidy_deallocate(v19);
    web::uri::~uri((web::uri *)v21);
    if ( !v15 )
      std::wstring::assign(v14, L"/");
    if ( std::wstring::find(v14, v16, 0) )
    {
      std::wstring::wstring(v18, L"Error: request was not prefixed with listener uri");
      web::http::http_exception::http_exception(pExceptionObject, v18);
      throw (web::http::http_exception *)pExceptionObject;
    }
    v11 = std::wstring::erase(v14, v10, v17);
    v12 = web::uri::encode_uri(v18, v11, 5);
    web::uri::uri(a2, v12);
    std::wstring::_Tidy_deallocate(v18);
    std::wstring::_Tidy_deallocate(v14);
    std::wstring::_Tidy_deallocate(v16);
  }
  return a2;
}

```

## disassembly

```asm
0x18004ee50  mov     [rsp-8+arg_10], rbx
0x18004ee55  push    rbp
0x18004ee56  push    rsi
0x18004ee57  push    rdi
0x18004ee58  lea     rbp, [rsp-100h]
0x18004ee60  sub     rsp, 200h
0x18004ee67  mov     rax, cs:__security_cookie
0x18004ee6e  xor     rax, rsp
0x18004ee71  mov     [rbp+110h+var_20], rax
0x18004ee78  mov     rbx, rdx
0x18004ee7b  mov     rdi, rcx
0x18004ee7e  mov     [rsp+210h+var_1E8], rdx
0x18004ee83  lea     rsi, [rcx+268h]
0x18004ee8a  mov     rdx, [rsi+10h]
0x18004ee8e  test    rdx, rdx
0x18004ee91  jz      loc_18004EFC7
0x18004ee97  mov     rcx, rsi
0x18004ee9a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ee9f  mov     r10, rax
0x18004eea2  lea     rcx, asc_180068A6C; "/"
0x18004eea9  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18004eeae  mov     r9, rax
0x18004eeb1  lea     r8, asc_180068A6C; "/"
0x18004eeb8  mov     rcx, r10
0x18004eebb  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004eec0  test    al, al
0x18004eec2  jnz     loc_18004EFC7
0x18004eec8  mov     rdx, rsi
0x18004eecb  lea     rcx, [rsp+210h+var_1C0]
0x18004eed0  call    ?decode@uri@web@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; web::uri::decode(std::wstring const &)
0x18004eed5  nop
0x18004eed6  lea     rcx, [rdi+180h]
0x18004eedd  lea     rdx, [rbp+110h+var_110]
0x18004eee1  call    ?resource@uri@web@@QEBA?AV12@XZ; web::uri::resource(void)
0x18004eee6  nop
0x18004eee7  lea     rdx, [rbp+110h+var_180]
0x18004eeeb  mov     rcx, rax
0x18004eeee  call    ?to_string@uri@web@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::uri::to_string(void)
0x18004eef3  nop
0x18004eef4  mov     rdx, rax
0x18004eef7  lea     rcx, [rsp+210h+var_1E0]
0x18004eefc  call    ?decode@uri@web@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; web::uri::decode(std::wstring const &)
0x18004ef01  nop
0x18004ef02  lea     rcx, [rbp+110h+var_180]
0x18004ef06  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ef0b  nop
0x18004ef0c  lea     rcx, [rbp+110h+var_110]; this
0x18004ef10  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x18004ef15  cmp     [rsp+210h+var_1D0], 0
0x18004ef1b  jnz     short loc_18004EF2E
0x18004ef1d  lea     rdx, asc_180068A6C; "/"
0x18004ef24  lea     rcx, [rsp+210h+var_1E0]
0x18004ef29  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18004ef2e  xor     r8d, r8d
0x18004ef31  lea     rdx, [rsp+210h+var_1C0]
0x18004ef36  lea     rcx, [rsp+210h+var_1E0]
0x18004ef3b  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x18004ef40  test    rax, rax
0x18004ef43  jnz     short loc_18004EF96
0x18004ef45  mov     r8, [rsp+210h+var_1B0]
0x18004ef4a  lea     rcx, [rsp+210h+var_1E0]
0x18004ef4f  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x18004ef54  mov     rdx, rax
0x18004ef57  mov     r8d, 5
0x18004ef5d  lea     rcx, [rsp+210h+var_1A0]
0x18004ef62  call    ?encode_uri@uri@web@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@W4component@components@12@@Z; web::uri::encode_uri(std::wstring const &,web::uri::components::component)
0x18004ef67  nop
0x18004ef68  mov     rdx, rax
0x18004ef6b  mov     rcx, rbx
0x18004ef6e  call    ??0uri@web@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::uri::uri(std::wstring const &)
0x18004ef73  nop
0x18004ef74  lea     rcx, [rsp+210h+var_1A0]
0x18004ef79  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ef7e  nop
0x18004ef7f  lea     rcx, [rsp+210h+var_1E0]
0x18004ef84  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ef89  nop
0x18004ef8a  lea     rcx, [rsp+210h+var_1C0]
0x18004ef8f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ef94  jmp     short loc_18004EFD6
0x18004ef96  lea     rdx, aErrorRequestWa; "Error: request was not prefixed with li"...
0x18004ef9d  lea     rcx, [rsp+210h+var_1A0]
0x18004efa2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004efa7  nop
0x18004efa8  lea     rdx, [rsp+210h+var_1A0]
0x18004efad  lea     rcx, [rbp+110h+pExceptionObject]
0x18004efb1  call    ??0http_exception@http@web@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::http_exception::http_exception(std::wstring const &)
0x18004efb6  lea     rdx, _TI2?AVhttp_exception@http@web@@; pThrowInfo
0x18004efbd  lea     rcx, [rbp+110h+pExceptionObject]; pExceptionObject
0x18004efc1  call    _CxxThrowException_0
0x18004efc7  lea     rcx, [rdi+180h]
0x18004efce  mov     rdx, rbx
0x18004efd1  call    ?resource@uri@web@@QEBA?AV12@XZ; web::uri::resource(void)
0x18004efd6  mov     rax, rbx
0x18004efd9  mov     rcx, [rbp+110h+var_20]
0x18004efe0  xor     rcx, rsp; StackCookie
0x18004efe3  call    __security_check_cookie
0x18004efe8  mov     rbx, [rsp+210h+arg_10]
0x18004eff0  add     rsp, 200h
0x18004eff7  pop     rdi
0x18004eff8  pop     rsi
0x18004eff9  pop     rbp
0x18004effa  retn
```
