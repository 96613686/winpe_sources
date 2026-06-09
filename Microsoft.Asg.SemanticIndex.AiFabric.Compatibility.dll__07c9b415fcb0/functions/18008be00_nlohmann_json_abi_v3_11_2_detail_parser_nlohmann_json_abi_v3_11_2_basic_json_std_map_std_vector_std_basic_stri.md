# nlohmann::json_abi_v3_11_2::detail::parser<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_view_iterator<std::char_traits<char8_t>>>>::exception_message(nlohmann::json_abi_v3_11_2::detail::lexer_base<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>::token_type,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18008be00`
- end: `0x18008c5bb`
- name: `?exception_message@?$parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@V?$iterator_input_adapter@V?$_String_view_iterator@U?$char_traits@_Q@std@@@std@@@detail@23@@detail@json_abi_v3_11_2@nlohmann@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4token_type@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@234@AEBV56@@Z`
- size: `1979`
- prototype: ``
- caller_count: `6`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x180084770`
- `0x1800853d0`
- `0x18008ce40`
- `0x1801c2480`
- `0x1801c30e0`
- `0x1801c4bd0`

## callees

- `0x180007c20`
- `0x180045a70`
- `0x180045b90`
- `0x180045ce0`
- `0x180045d70`
- `0x18008be00`
- `0x18008c780`
- `0x18008f920`
- `0x1801f7160`
- `0x180206ec0`
- `0x1802421a0`
- `0x180242d80`

## string_xrefs

- `0x18008c0f3`: `; last read: '`
- `0x18008c111`: `; last read: '`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall nlohmann::json_abi_v3_11_2::detail::parser<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_view_iterator<std::char_traits<char8_t>>>>::exception_message(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        _QWORD *a4)
{
  __int64 v8; // rcx
  __int128 *p_Src; // rbx
  _BYTE *v10; // rbx
  size_t v11; // rsi
  __int64 v12; // r15
  __int128 *v13; // rbx
  void *v14; // rcx
  _QWORD *token_string; // rsi
  const char *v16; // r15
  size_t v17; // rdi
  __int64 v18; // rcx
  __int128 *v19; // rbx
  char *v20; // rbx
  __int64 v21; // rcx
  __int128 *v22; // rbx
  _BYTE *v23; // rbx
  size_t v24; // rdi
  __int64 v25; // rcx
  __int128 *v26; // rbx
  char *v27; // rbx
  void *v28; // rcx
  _BYTE *v29; // rcx
  const char *v30; // rsi
  __int64 v31; // rcx
  __int128 *v32; // rbx
  _BYTE *v33; // rbx
  size_t v34; // rdi
  __int64 v35; // rcx
  __int128 *v36; // rbx
  char *v37; // rbx
  void *v38; // rcx
  const char *v39; // rsi
  __int64 v40; // rcx
  __int128 *v41; // rbx
  _BYTE *v42; // rbx
  size_t v43; // rdi
  __int64 v44; // rcx
  __int128 *v45; // rbx
  char *v46; // rbx
  void *v47; // rcx
  __int128 Src; // [rsp+38h] [rbp-41h] BYREF
  __int64 v50; // [rsp+48h] [rbp-31h]
  unsigned __int64 v51; // [rsp+50h] [rbp-29h]
  int v52; // [rsp+58h] [rbp-21h]
  _BYTE *v53; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int64 v54; // [rsp+78h] [rbp-1h]
  _QWORD *v55; // [rsp+80h] [rbp+7h]

  v55 = a2;
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 0;
  std::basic_string<char8_t>::_Construct<1,char8_t const *>(a2, "syntax error ", 13);
  v52 = 1;
  if ( a4[2] )
  {
    Src = 0;
    v50 = 0;
    v51 = 15;
    LOBYTE(Src) = 0;
    v52 = 3;
    std::string::reserve(&Src);
    v8 = v50;
    if ( v51 - v50 < 0xE )
    {
      ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEBD0_Z_PEBD_K_Z(
        &Src,
        0xEu);
    }
    else
    {
      v50 += 14;
      p_Src = &Src;
      if ( v51 > 0xF )
        p_Src = (__int128 *)Src;
      v10 = (char *)p_Src + v8;
      memmove(v10, "while parsing ", 0xEu);
      v10[14] = 0;
    }
    v11 = a4[2];
    if ( a4[3] > 0xFu )
      a4 = (_QWORD *)*a4;
    v12 = v50;
    if ( v11 > v51 - v50 )
    {
      _mm_lfence();
      ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEBD0_Z_PEBD_K_Z(
        &Src,
        v11);
    }
    else
    {
      v50 += v11;
      v13 = &Src;
      if ( v51 > 0xF )
        v13 = (__int128 *)Src;
      memmove((char *)v13 + v12, a4, v11);
      *((_BYTE *)v13 + v11 + v12) = 0;
    }
    std::string::push_back(&Src);
    std::string::append(a2);
    v52 = 1;
    if ( v51 > 0xF )
    {
      v14 = (void *)Src;
      if ( v51 + 1 >= 0x1000 )
      {
        v14 = *(void **)(Src - 8);
        if ( (unsigned __int64)(Src - (_QWORD)v14 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      _mm_lfence();
      operator delete(v14);
    }
    v50 = 0;
    v51 = 15;
    LOBYTE(Src) = 0;
  }
  std::string::append(a2);
  if ( *(_DWORD *)(a1 + 64) == 14 )
  {
    token_string = (_QWORD *)nlohmann::json_abi_v3_11_2::detail::lexer<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_view_iterator<std::char_traits<char8_t>>>>::get_token_string(
                               a1 + 72,
                               &v53);
    v16 = *(const char **)(a1 + 184);
    Src = 0;
    v50 = 0;
    v51 = 15;
    LOBYTE(Src) = 0;
    v52 = 5;
    strlen(v16);
    std::string::reserve(&Src);
    v17 = strlen(v16);
    v18 = v50;
    if ( v17 > v51 - v50 )
    {
      _mm_lfence();
      ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEBD0_Z_PEBD_K_Z(
        &Src,
        v17);
    }
    else
    {
      v50 += v17;
      v19 = &Src;
      if ( v51 > 0xF )
        v19 = (__int128 *)Src;
      v20 = (char *)v19 + v18;
      _mm_lfence();
      memmove(v20, v16, v17);
      v20[v17] = 0;
    }
    v21 = v50;
    if ( v51 - v50 < 0xE )
    {
      ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEBD0_Z_PEBD_K_Z(
        &Src,
        0xEu);
    }
    else
    {
      v50 += 14;
      v22 = &Src;
      if ( v51 > 0xF )
        v22 = (__int128 *)Src;
      v23 = (char *)v22 + v21;
      memmove(v23, "; last read: '", 0xEu);
      v23[14] = 0;
    }
    v24 = token_string[2];
    if ( token_string[3] > 0xFu )
      token_string = (_QWORD *)*token_string;
    v25 = v50;
    if ( v24 > v51 - v50 )
    {
      _mm_lfence();
      ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEBD0_Z_PEBD_K_Z(
        &Src,
        v24);
    }
    else
    {
      v50 += v24;
      v26 = &Src;
      if ( v51 > 0xF )
        v26 = (__int128 *)Src;
      v27 = (char *)v26 + v25;
      memmove(v27, token_string, v24);
      v27[v24] = 0;
    }
    std::string::push_back(&Src);
    std::string::append(a2);
    if ( v51 > 0xF )
    {
      v28 = (void *)Src;
      if ( v51 + 1 >= 0x1000 )
      {
        v28 = *(void **)(Src - 8);
        if ( (unsigned __int64)(Src - (_QWORD)v28 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      _mm_lfence();
      operator delete(v28);
    }
    v50 = 0;
    v51 = 15;
    LOBYTE(Src) = 0;
    if ( v54 > 0xF )
    {
      v29 = v53;
      if ( v54 + 1 >= 0x1000 )
      {
        v29 = (_BYTE *)*((_QWORD *)v53 - 1);
        if ( (unsigned __int64)(v53 - v29 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      _mm_lfence();
      operator delete(v29);
    }
    LOBYTE(v53) = 0;
  }
  else
  {
    v30 = (const char *)((__int64 (*)(void))nlohmann::json_abi_v3_11_2::detail::lexer_base<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::token_type_name)();
    Src = 0;
    v50 = 0;
    v51 = 15;
    LOBYTE(Src) = 0;
    v52 = 9;
    strlen(v30);
    std::string::reserve(&Src);
    v31 = v50;
    if ( v51 - v50 < 0xB )
    {
      ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEBD0_Z_PEBD_K_Z(
        &Src,
        0xBu);
    }
    else
    {
      v50 += 11;
      v32 = &Src;
      if ( v51 > 0xF )
        v32 = (__int128 *)Src;
      v33 = (char *)v32 + v31;
      memmove(v33, "unexpected ", 0xBu);
      v33[11] = 0;
    }
    v34 = strlen(v30);
    v35 = v50;
    if ( v34 > v51 - v50 )
    {
      _mm_lfence();
      ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEBD0_Z_PEBD_K_Z(
        &Src,
        v34);
    }
    else
    {
      v50 += v34;
      v36 = &Src;
      if ( v51 > 0xF )
        v36 = (__int128 *)Src;
      v37 = (char *)v36 + v35;
      _mm_lfence();
      memmove(v37, v30, v34);
      v37[v34] = 0;
    }
    std::string::append(a2);
    if ( v51 > 0xF )
    {
      v38 = (void *)Src;
      if ( v51 + 1 >= 0x1000 )
      {
        v38 = *(void **)(Src - 8);
        if ( (unsigned __int64)(Src - (_QWORD)v38 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      _mm_lfence();
      operator delete(v38);
    }
    v50 = 0;
    v51 = 15;
    LOBYTE(Src) = 0;
  }
  if ( a3 )
  {
    v39 = (const char *)nlohmann::json_abi_v3_11_2::detail::lexer_base<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::token_type_name(a3);
    Src = 0;
    v50 = 0;
    v51 = 15;
    LOBYTE(Src) = 0;
    v52 = 17;
    strlen(v39);
    std::string::reserve(&Src);
    v40 = v50;
    if ( v51 - v50 < 0xB )
    {
      ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEBD0_Z_PEBD_K_Z(
        &Src,
        0xBu);
    }
    else
    {
      v50 += 11;
      v41 = &Src;
      if ( v51 > 0xF )
        v41 = (__int128 *)Src;
      v42 = (char *)v41 + v40;
      memmove(v42, "; expected ", 0xBu);
      v42[11] = 0;
    }
    v43 = strlen(v39);
    v44 = v50;
    if ( v43 > v51 - v50 )
    {
      _mm_lfence();
      ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEBD0_Z_PEBD_K_Z(
        &Src,
        v43);
    }
    else
    {
      v50 += v43;
      v45 = &Src;
      if ( v51 > 0xF )
        v45 = (__int128 *)Src;
      v46 = (char *)v45 + v44;
      _mm_lfence();
      memmove(v46, v39, v43);
      v46[v43] = 0;
    }
    std::string::append(a2);
    if ( v51 > 0xF )
    {
      v47 = (void *)Src;
      if ( v51 + 1 >= 0x1000 )
      {
        v47 = *(void **)(Src - 8);
        if ( (unsigned __int64)(Src - (_QWORD)v47 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      _mm_lfence();
      operator delete(v47);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18008be00  push    rbp
0x18008be02  push    rbx
0x18008be03  push    rsi
0x18008be04  push    rdi
0x18008be05  push    r12
0x18008be07  push    r13
0x18008be09  push    r14
0x18008be0b  push    r15
0x18008be0d  lea     rbp, [rsp-1Fh]
0x18008be12  sub     rsp, 98h
0x18008be19  mov     rdi, r9
0x18008be1c  mov     r12d, r8d
0x18008be1f  mov     r14, rdx
0x18008be22  mov     r13, rcx
0x18008be25  mov     [rbp+57h+var_50], rdx
0x18008be29  xor     r15d, r15d
0x18008be2c  mov     [rbp+57h+var_78], r15d
0x18008be30  xorps   xmm0, xmm0
0x18008be33  movups  xmmword ptr [rdx], xmm0
0x18008be36  mov     [rdx+10h], r15
0x18008be3a  mov     [rdx+18h], r15
0x18008be3e  mov     r8d, 0Dh
0x18008be44  lea     rdx, aSyntaxError; "syntax error "
0x18008be4b  mov     rcx, r14
0x18008be4e  call    ??$_Construct@$00PEB_Q@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@AEAAXQEB_Q_K@Z; std::basic_string<char8_t>::_Construct<1,char8_t const *>(char8_t const * const,unsigned __int64)
0x18008be53  mov     [rbp+57h+var_78], 1
0x18008be5a  mov     rdx, [rdi+10h]
0x18008be5e  test    rdx, rdx
0x18008be61  jz      loc_18008BFE5
0x18008be67  xorps   xmm0, xmm0
0x18008be6a  movups  [rbp+57h+Src], xmm0
0x18008be6e  mov     [rbp+57h+var_88], r15
0x18008be72  mov     [rbp+57h+var_80], 0Fh
0x18008be7a  mov     byte ptr [rbp+57h+Src], r15b
0x18008be7e  mov     [rbp+57h+var_78], 3
0x18008be85  add     rdx, 0Fh
0x18008be89  lea     rcx, [rbp+57h+Src]; Src
0x18008be8d  call    ?reserve@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z; std::string::reserve(unsigned __int64)
0x18008be92  mov     rcx, [rbp+57h+var_88]
0x18008be96  mov     rdx, [rbp+57h+var_80]
0x18008be9a  mov     rax, rdx
0x18008be9d  sub     rax, rcx
0x18008bea0  cmp     rax, 0Eh
0x18008bea4  jb      short loc_18008BED9
0x18008bea6  lea     rax, [rcx+0Eh]
0x18008beaa  mov     [rbp+57h+var_88], rax
0x18008beae  lea     rbx, [rbp+57h+Src]
0x18008beb2  cmp     rdx, 0Fh
0x18008beb6  cmova   rbx, qword ptr [rbp+57h+Src]
0x18008bebb  add     rbx, rcx
0x18008bebe  mov     r8d, 0Eh; Size
0x18008bec4  lea     rdx, aWhileParsing; "while parsing "
0x18008becb  mov     rcx, rbx; void *
0x18008bece  call    memmove
0x18008bed3  mov     [rbx+0Eh], r15b
0x18008bed7  jmp     short loc_18008BEFC
0x18008bed9  mov     [rsp+0D0h+Reserved], 0Eh; Size
0x18008bee2  lea     r9, aWhileParsing; "while parsing "
0x18008bee9  movzx   r8d, [rbp+57h+var_A0]
0x18008beee  mov     edx, 0Eh
0x18008bef3  lea     rcx, [rbp+57h+Src]; Src
0x18008bef7  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV34@QEBD_K@Z@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEBD0@Z@PEBD_K@Z; std::string::_Reallocate_grow_by<`std::string::append(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64>(unsigned __int64,`std::string::append(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64)
0x18008befc  mov     rsi, [rdi+10h]
0x18008bf00  cmp     qword ptr [rdi+18h], 0Fh
0x18008bf05  jbe     short loc_18008BF0A
0x18008bf07  mov     rdi, [rdi]
0x18008bf0a  mov     r15, [rbp+57h+var_88]
0x18008bf0e  mov     rcx, [rbp+57h+var_80]
0x18008bf12  mov     rax, rcx
0x18008bf15  sub     rax, r15
0x18008bf18  cmp     rsi, rax
0x18008bf1b  ja      short loc_18008BF4C
0x18008bf1d  lea     rax, [r15+rsi]
0x18008bf21  mov     [rbp+57h+var_88], rax
0x18008bf25  lea     rbx, [rbp+57h+Src]
0x18008bf29  cmp     rcx, 0Fh
0x18008bf2d  cmova   rbx, qword ptr [rbp+57h+Src]
0x18008bf32  lea     rcx, [rbx+r15]; void *
0x18008bf36  mov     r8, rsi; Size
0x18008bf39  mov     rdx, rdi; Src
0x18008bf3c  call    memmove
0x18008bf41  lea     rax, [rsi+rbx]
0x18008bf45  mov     byte ptr [rax+r15], 0
0x18008bf4a  jmp     short loc_18008BF68
0x18008bf4c  lfence
0x18008bf4f  mov     [rsp+0D0h+Reserved], rsi; Size
0x18008bf54  mov     r9, rdi
0x18008bf57  movzx   r8d, [rbp+57h+var_A0]
0x18008bf5c  mov     rdx, rsi
0x18008bf5f  lea     rcx, [rbp+57h+Src]; Src
0x18008bf63  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV34@QEBD_K@Z@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEBD0@Z@PEBD_K@Z; std::string::_Reallocate_grow_by<`std::string::append(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64>(unsigned __int64,`std::string::append(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64)
0x18008bf68  mov     dl, 20h ; ' '
0x18008bf6a  lea     rcx, [rbp+57h+Src]; Src
0x18008bf6e  call    ?push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z; std::string::push_back(char)
0x18008bf73  lea     rdx, [rbp+57h+Src]
0x18008bf77  cmp     [rbp+57h+var_80], 0Fh
0x18008bf7c  cmova   rdx, qword ptr [rbp+57h+Src]
0x18008bf81  mov     r8, [rbp+57h+var_88]
0x18008bf85  mov     rcx, r14; Src
0x18008bf88  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x18008bf8d  mov     [rbp+57h+var_78], 1
0x18008bf94  mov     rdx, [rbp+57h+var_80]
0x18008bf98  cmp     rdx, 0Fh
0x18008bf9c  jbe     short loc_18008BFD2
0x18008bf9e  inc     rdx
0x18008bfa1  mov     rcx, qword ptr [rbp+57h+Src]
0x18008bfa5  mov     rax, rcx
0x18008bfa8  cmp     rdx, 1000h
0x18008bfaf  jb      short loc_18008BFCA
0x18008bfb1  add     rdx, 27h ; '''
0x18008bfb5  mov     rcx, [rcx-8]; Block
0x18008bfb9  sub     rax, rcx
0x18008bfbc  sub     rax, 8
0x18008bfc0  cmp     rax, 1Fh
0x18008bfc4  ja      loc_18008C564
0x18008bfca  lfence
0x18008bfcd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18008bfd2  xor     r15d, r15d
0x18008bfd5  mov     [rbp+57h+var_88], r15
0x18008bfd9  mov     [rbp+57h+var_80], 0Fh
0x18008bfe1  mov     byte ptr [rbp+57h+Src], r15b
0x18008bfe5  mov     r8d, 2
0x18008bfeb  lea     rdx, asc_180269E58; "- "
0x18008bff2  mov     rcx, r14; Src
0x18008bff5  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x18008bffa  mov     ecx, [r13+40h]
0x18008bffe  cmp     ecx, 0Eh
0x18008c001  jnz     loc_18008C252
0x18008c007  lea     rcx, [r13+48h]
0x18008c00b  lea     rdx, [rbp+57h+var_70]
0x18008c00f  call    ?get_token_string@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@V?$iterator_input_adapter@V?$_String_view_iterator@U?$char_traits@_Q@std@@@std@@@detail@23@@detail@json_abi_v3_11_2@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; nlohmann::json_abi_v3_11_2::detail::lexer<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_view_iterator<std::char_traits<char8_t>>>>::get_token_string(void)
0x18008c014  mov     rsi, rax
0x18008c017  mov     r15, [r13+0B8h]
0x18008c01e  xorps   xmm0, xmm0
0x18008c021  movups  [rbp+57h+Src], xmm0
0x18008c025  xor     r13d, r13d
0x18008c028  mov     [rbp+57h+var_88], r13
0x18008c02c  mov     [rbp+57h+var_80], 0Fh
0x18008c034  mov     byte ptr [rbp+57h+Src], r13b
0x18008c038  mov     [rbp+57h+var_78], 5
0x18008c03f  mov     rcx, r15; Str
0x18008c042  call    strlen
0x18008c047  lea     rdx, [rax+0Fh]
0x18008c04b  add     rdx, [rsi+10h]
0x18008c04f  lea     rcx, [rbp+57h+Src]; Src
0x18008c053  call    ?reserve@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z; std::string::reserve(unsigned __int64)
0x18008c058  mov     rcx, r15; Str
0x18008c05b  call    strlen
0x18008c060  mov     rdi, rax
0x18008c063  mov     rcx, [rbp+57h+var_88]
0x18008c067  mov     rdx, [rbp+57h+var_80]
0x18008c06b  mov     rax, rdx
0x18008c06e  sub     rax, rcx
0x18008c071  cmp     rdi, rax
0x18008c074  ja      short loc_18008C0A5
0x18008c076  lea     rax, [rcx+rdi]
0x18008c07a  mov     [rbp+57h+var_88], rax
0x18008c07e  lea     rbx, [rbp+57h+Src]
0x18008c082  cmp     rdx, 0Fh
0x18008c086  cmova   rbx, qword ptr [rbp+57h+Src]
0x18008c08b  add     rbx, rcx
0x18008c08e  lfence
0x18008c091  mov     r8, rdi; Size
0x18008c094  mov     rdx, r15; Src
0x18008c097  mov     rcx, rbx; void *
0x18008c09a  call    memmove
0x18008c09f  mov     [rbx+rdi], r13b
0x18008c0a3  jmp     short loc_18008C0C1
0x18008c0a5  lfence
0x18008c0a8  mov     [rsp+0D0h+Reserved], rdi; Size
0x18008c0ad  mov     r9, r15
0x18008c0b0  movzx   r8d, [rbp+57h+var_A0]
0x18008c0b5  mov     rdx, rdi
0x18008c0b8  lea     rcx, [rbp+57h+Src]; Src
0x18008c0bc  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV34@QEBD_K@Z@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEBD0@Z@PEBD_K@Z; std::string::_Reallocate_grow_by<`std::string::append(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64>(unsigned __int64,`std::string::append(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64)
0x18008c0c1  mov     rcx, [rbp+57h+var_88]
0x18008c0c5  mov     rdx, [rbp+57h+var_80]
0x18008c0c9  mov     rax, rdx
0x18008c0cc  sub     rax, rcx
0x18008c0cf  cmp     rax, 0Eh
0x18008c0d3  jb      short loc_18008C108
0x18008c0d5  lea     rax, [rcx+0Eh]
0x18008c0d9  mov     [rbp+57h+var_88], rax
0x18008c0dd  lea     rbx, [rbp+57h+Src]
0x18008c0e1  cmp     rdx, 0Fh
0x18008c0e5  cmova   rbx, qword ptr [rbp+57h+Src]
0x18008c0ea  add     rbx, rcx
0x18008c0ed  mov     r8d, 0Eh; Size
0x18008c0f3  lea     rdx, aLastRead; "; last read: '"
0x18008c0fa  mov     rcx, rbx; void *
0x18008c0fd  call    memmove
0x18008c102  mov     [rbx+0Eh], r13b
0x18008c106  jmp     short loc_18008C12B
0x18008c108  mov     [rsp+0D0h+Reserved], 0Eh; Size
0x18008c111  lea     r9, aLastRead; "; last read: '"
0x18008c118  movzx   r8d, [rbp+57h+var_A0]
0x18008c11d  mov     edx, 0Eh
0x18008c122  lea     rcx, [rbp+57h+Src]; Src
0x18008c126  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV34@QEBD_K@Z@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEBD0@Z@PEBD_K@Z; std::string::_Reallocate_grow_by<`std::string::append(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64>(unsigned __int64,`std::string::append(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64)
0x18008c12b  mov     rdi, [rsi+10h]
0x18008c12f  cmp     qword ptr [rsi+18h], 0Fh
0x18008c134  jbe     short loc_18008C139
0x18008c136  mov     rsi, [rsi]
0x18008c139  mov     rcx, [rbp+57h+var_88]
0x18008c13d  mov     rdx, [rbp+57h+var_80]
0x18008c141  mov     rax, rdx
0x18008c144  sub     rax, rcx
0x18008c147  cmp     rdi, rax
0x18008c14a  ja      short loc_18008C178
0x18008c14c  lea     rax, [rcx+rdi]
0x18008c150  mov     [rbp+57h+var_88], rax
0x18008c154  lea     rbx, [rbp+57h+Src]
0x18008c158  cmp     rdx, 0Fh
0x18008c15c  cmova   rbx, qword ptr [rbp+57h+Src]
0x18008c161  add     rbx, rcx
0x18008c164  mov     r8, rdi; Size
0x18008c167  mov     rdx, rsi; Src
0x18008c16a  mov     rcx, rbx; void *
0x18008c16d  call    memmove
0x18008c172  mov     [rbx+rdi], r13b
0x18008c176  jmp     short loc_18008C194
0x18008c178  lfence
0x18008c17b  mov     [rsp+0D0h+Reserved], rdi; Size
0x18008c180  mov     r9, rsi
0x18008c183  movzx   r8d, [rbp+57h+var_A0]
0x18008c188  mov     rdx, rdi
0x18008c18b  lea     rcx, [rbp+57h+Src]; Src
0x18008c18f  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV34@QEBD_K@Z@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEBD0@Z@PEBD_K@Z; std::string::_Reallocate_grow_by<`std::string::append(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64>(unsigned __int64,`std::string::append(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64)
0x18008c194  mov     dl, 27h ; '''
0x18008c196  lea     rcx, [rbp+57h+Src]; Src
0x18008c19a  call    ?push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z; std::string::push_back(char)
0x18008c19f  lea     rdx, [rbp+57h+Src]
0x18008c1a3  cmp     [rbp+57h+var_80], 0Fh
0x18008c1a8  cmova   rdx, qword ptr [rbp+57h+Src]
0x18008c1ad  mov     r8, [rbp+57h+var_88]
0x18008c1b1  mov     rcx, r14; Src
0x18008c1b4  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x18008c1b9  nop
0x18008c1ba  mov     rdx, [rbp+57h+var_80]
0x18008c1be  cmp     rdx, 0Fh
0x18008c1c2  jbe     short loc_18008C1F8
0x18008c1c4  inc     rdx
0x18008c1c7  mov     rcx, qword ptr [rbp+57h+Src]
0x18008c1cb  mov     rax, rcx
0x18008c1ce  cmp     rdx, 1000h
0x18008c1d5  jb      short loc_18008C1F0
0x18008c1d7  add     rdx, 27h ; '''
0x18008c1db  mov     rcx, [rcx-8]; Block
0x18008c1df  sub     rax, rcx
0x18008c1e2  sub     rax, 8
0x18008c1e6  cmp     rax, 1Fh
0x18008c1ea  ja      loc_18008C57C
0x18008c1f0  lfence
0x18008c1f3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18008c1f8  xor     r15d, r15d
0x18008c1fb  mov     [rbp+57h+var_88], r15
0x18008c1ff  mov     [rbp+57h+var_80], 0Fh
0x18008c207  mov     byte ptr [rbp+57h+Src], r15b
0x18008c20b  mov     rdx, [rbp+57h+var_58]
0x18008c20f  cmp     rdx, 0Fh
0x18008c213  jbe     short loc_18008C249
0x18008c215  inc     rdx
0x18008c218  mov     rcx, [rbp+57h+var_70]
0x18008c21c  mov     rax, rcx
0x18008c21f  cmp     rdx, 1000h
0x18008c226  jb      short loc_18008C241
0x18008c228  add     rdx, 27h ; '''
0x18008c22c  mov     rcx, [rcx-8]; Block
0x18008c230  sub     rax, rcx
0x18008c233  sub     rax, 8
0x18008c237  cmp     rax, 1Fh
0x18008c23b  ja      loc_18008C591
0x18008c241  lfence
0x18008c244  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18008c249  mov     byte ptr [rbp+57h+var_70], 0
0x18008c24d  jmp     loc_18008C3C9
0x18008c252  call    ?token_type_name@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@detail@json_abi_v3_11_2@nlohmann@@SAPEBDW4token_type@1234@@Z; nlohmann::json_abi_v3_11_2::detail::lexer_base<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>>::token_type_name(nlohmann::json_abi_v3_11_2::detail::lexer_base<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>>::token_type)
0x18008c257  mov     rsi, rax
0x18008c25a  xorps   xmm0, xmm0
0x18008c25d  movups  [rbp+57h+Src], xmm0
0x18008c261  mov     [rbp+57h+var_88], r15
0x18008c265  mov     [rbp+57h+var_80], 0Fh
0x18008c26d  mov     byte ptr [rbp+57h+Src], 0
0x18008c271  mov     [rbp+57h+var_78], 9
0x18008c278  mov     rcx, rax; Str
0x18008c27b  call    strlen
0x18008c280  lea     rdx, [rax+0Bh]
0x18008c284  lea     rcx, [rbp+57h+Src]; Src
0x18008c288  call    ?reserve@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z; std::string::reserve(unsigned __int64)
0x18008c28d  mov     rcx, [rbp+57h+var_88]
0x18008c291  mov     rdx, [rbp+57h+var_80]
0x18008c295  mov     rax, rdx
0x18008c298  sub     rax, rcx
0x18008c29b  cmp     rax, 0Bh
0x18008c29f  jb      short loc_18008C2D4
0x18008c2a1  lea     rax, [rcx+0Bh]
0x18008c2a5  mov     [rbp+57h+var_88], rax
0x18008c2a9  lea     rbx, [rbp+57h+Src]
0x18008c2ad  cmp     rdx, 0Fh
0x18008c2b1  cmova   rbx, qword ptr [rbp+57h+Src]
  ... truncated ...
```
