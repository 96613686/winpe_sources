# web::json::value::parse(std::basic_istream<char,std::char_traits<char>> &)

- ea: `0x18002df20`
- end: `0x18002e0c4`
- name: `?parse@value@json@web@@SA?AV123@AEAV?$basic_istream@DU?$char_traits@D@std@@@std@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000b638`

## callees

- `0x18000f8cc`
- `0x18002769c`
- `0x180028514`
- `0x18002df20`
- `0x18002e0cc`
- `0x18002e6b0`
- `0x18003008c`
- `0x1800322e8`
- `0x1800427d0`
- `0x180047a30`

## string_xrefs

- `0x18002e04f`: `Left-over characters in stream after parsing a JSON value`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall web::json::value::parse(_QWORD *a1, __int64 a2)
{
  __int64 *v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  _BYTE v11[8]; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD *v12; // [rsp+30h] [rbp-D0h]
  _BYTE v13[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v14[40]; // [rsp+58h] [rbp-A8h] BYREF
  int v15; // [rsp+80h] [rbp-80h] BYREF
  __int128 v16; // [rsp+88h] [rbp-78h] BYREF
  __int64 v17; // [rsp+98h] [rbp-68h]
  __int64 v18; // [rsp+A0h] [rbp-60h]
  int v19; // [rsp+C8h] [rbp-38h] BYREF
  void ***v20; // [rsp+D0h] [rbp-30h]
  _QWORD v21[5]; // [rsp+E0h] [rbp-20h] BYREF

  v12 = a1;
  v21[1] = 1;
  v21[2] = 1;
  v21[3] = 0;
  v21[0] = &web::json::details::JSON_StreamParser<char>::`vftable';
  v21[4] = *(_QWORD *)(*(int *)(*(_QWORD *)a2 + 4LL) + a2 + 72);
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 15;
  LOBYTE(v16) = 0;
  v19 = 0;
  v20 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  web::json::details::JSON_Parser<char>::GetNextToken(v21, &v15);
  if ( v19 )
  {
    v7 = std::error_code::message(&v19, v13);
    v8 = utility::conversions::to_string_t(v14, v7);
    web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(&v15, v8);
  }
  *a1 = 0;
  v3 = (__int64 *)web::json::details::JSON_Parser<char>::_ParseValue(v21, v11, &v15);
  v4 = *v3;
  *v3 = 0;
  *a1 = v4;
  v5 = *v3;
  if ( v5 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 192LL))(v5, 1);
  if ( v19 )
  {
    v9 = std::error_code::message(&v19, v14);
    v10 = utility::conversions::to_string_t(v13, v9);
    web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(&v15, v10);
  }
  if ( v15 )
  {
    std::wstring::wstring(v13, L"Left-over characters in stream after parsing a JSON value");
    web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(&v15, v13);
  }
  std::string::~string(&v16);
  return a1;
}

```

## disassembly

```asm
0x18002df20  mov     [rsp-8+arg_8], rbx
0x18002df25  push    rbp
0x18002df26  lea     rbp, [rsp-10h]
0x18002df2b  sub     rsp, 110h
0x18002df32  mov     rax, cs:__security_cookie
0x18002df39  xor     rax, rsp
0x18002df3c  mov     [rbp+10h+var_8], rax
0x18002df40  mov     rbx, rcx
0x18002df43  mov     [rsp+110h+var_E0], rcx
0x18002df48  mov     [rsp+110h+var_F0], 0
0x18002df50  mov     [rbp+10h+var_28], 1
0x18002df58  mov     [rbp+10h+var_20], 1
0x18002df60  mov     [rbp+10h+var_18], 0
0x18002df68  lea     rax, ??_7?$JSON_StreamParser@D@details@json@web@@6B@; const web::json::details::JSON_StreamParser<char>::`vftable'
0x18002df6f  mov     [rbp+10h+var_30], rax
0x18002df73  mov     rax, [rdx]
0x18002df76  movsxd  rcx, dword ptr [rax+4]
0x18002df7a  mov     rax, [rcx+rdx+48h]
0x18002df7f  mov     [rbp+10h+var_10], rax
0x18002df83  mov     [rbp+10h+var_90], 0
0x18002df8a  xorps   xmm0, xmm0
0x18002df8d  movups  [rbp+10h+var_88], xmm0
0x18002df91  mov     [rbp+10h+var_78], 0
0x18002df99  mov     [rbp+10h+var_70], 0Fh
0x18002dfa1  mov     byte ptr [rbp+10h+var_88], 0
0x18002dfa5  mov     [rbp+10h+var_48], 0
0x18002dfac  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18002dfb3  mov     [rbp+10h+var_40], rax
0x18002dfb7  lea     rdx, [rbp+10h+var_90]
0x18002dfbb  lea     rcx, [rbp+10h+var_30]
0x18002dfbf  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x18002dfc4  cmp     [rbp+10h+var_48], 0
0x18002dfc8  jnz     loc_18002E070
0x18002dfce  xor     eax, eax
0x18002dfd0  mov     [rbx], rax
0x18002dfd3  lea     r8, [rbp+10h+var_90]
0x18002dfd7  lea     rdx, [rsp+110h+var_E8]
0x18002dfdc  lea     rcx, [rbp+10h+var_30]
0x18002dfe0  call    ?_ParseValue@?$JSON_Parser@D@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::_ParseValue(web::json::details::JSON_Parser<char>::Token &)
0x18002dfe5  mov     rcx, rax
0x18002dfe8  mov     rax, [rax]
0x18002dfeb  mov     qword ptr [rcx], 0
0x18002dff2  mov     [rbx], rax
0x18002dff5  mov     rcx, [rcx]
0x18002dff8  test    rcx, rcx
0x18002dffb  jz      short loc_18002E011
0x18002dffd  mov     rax, [rcx]
0x18002e000  mov     edx, 1
0x18002e005  mov     rax, [rax+0C0h]
0x18002e00c  call    _guard_dispatch_icall
0x18002e011  mov     [rsp+110h+var_F0], 6
0x18002e019  cmp     [rbp+10h+var_48], 0
0x18002e01d  jnz     short loc_18002E09A
0x18002e01f  cmp     [rbp+10h+var_90], 0
0x18002e023  jnz     short loc_18002E04F
0x18002e025  lea     rcx, [rbp+10h+var_88]
0x18002e029  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002e02e  nop
0x18002e02f  mov     rax, rbx
0x18002e032  mov     rcx, [rbp+10h+var_8]
0x18002e036  xor     rcx, rsp; StackCookie
0x18002e039  call    __security_check_cookie
0x18002e03e  mov     rbx, [rsp+110h+arg_8]
0x18002e046  add     rsp, 110h
0x18002e04d  pop     rbp
0x18002e04e  retn
0x18002e04f  lea     rdx, aLeftOverCharac; "Left-over characters in stream after pa"...
0x18002e056  lea     rcx, [rsp+110h+var_D8]
0x18002e05b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002e060  nop
0x18002e061  lea     rdx, [rsp+110h+var_D8]
0x18002e066  lea     rcx, [rbp+10h+var_90]
0x18002e06a  call    ??$CreateException@UToken@?$JSON_Parser@D@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@D@012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(web::json::details::JSON_Parser<char>::Token const &,std::wstring const &)
0x18002e070  lea     rdx, [rsp+110h+var_D8]
0x18002e075  lea     rcx, [rbp+10h+var_48]
0x18002e079  call    ?message@error_code@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::error_code::message(void)
0x18002e07e  nop
0x18002e07f  mov     rdx, rax
0x18002e082  lea     rcx, [rsp+110h+var_B8]
0x18002e087  call    ?to_string_t@conversions@utility@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; utility::conversions::to_string_t(std::string &&)
0x18002e08c  nop
0x18002e08d  mov     rdx, rax
0x18002e090  lea     rcx, [rbp+10h+var_90]
0x18002e094  call    ??$CreateException@UToken@?$JSON_Parser@D@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@D@012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(web::json::details::JSON_Parser<char>::Token const &,std::wstring const &)
0x18002e09a  lea     rdx, [rsp+110h+var_B8]
0x18002e09f  lea     rcx, [rbp+10h+var_48]
0x18002e0a3  call    ?message@error_code@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::error_code::message(void)
0x18002e0a8  nop
0x18002e0a9  mov     rdx, rax
0x18002e0ac  lea     rcx, [rsp+110h+var_D8]
0x18002e0b1  call    ?to_string_t@conversions@utility@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; utility::conversions::to_string_t(std::string &&)
0x18002e0b6  nop
0x18002e0b7  mov     rdx, rax
0x18002e0ba  lea     rcx, [rbp+10h+var_90]
0x18002e0be  call    ??$CreateException@UToken@?$JSON_Parser@D@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@D@012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(web::json::details::JSON_Parser<char>::Token const &,std::wstring const &)
```
