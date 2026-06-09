# regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,regex::perl_syntax<ushort>>::_find_next_group(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,regex::perl_syntax<ushort> &,std::vector<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,std::allocator<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *>> &)

- ea: `0x180019cb0`
- end: `0x18001a5ba`
- name: `?_find_next_group@?$basic_rpattern_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$perl_syntax@G@regex@@@regex@@IEAAPEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@PEAV342@AEAV?$perl_syntax@G@2@AEAV?$vector@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@V?$allocator@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@@6@@Z`
- size: `2314`
- prototype: ``
- caller_count: `3`
- callee_count: `32`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019cb0`
- `0x18001a5c0`
- `0x1800ae6e8`

## callees

- `0x1800198bc`
- `0x180019978`
- `0x180019cb0`
- `0x18001a5c0`
- `0x18001b008`
- `0x18001b41c`
- `0x18001b604`
- `0x18001b9ac`
- `0x18001c34c`
- `0x18001d3f4`
- `0x18001f038`
- `0x18003d83c`
- `0x18004e0ec`
- `0x18004e16c`
- `0x180050c84`
- `0x180050db0`
- `0x1800517d8`
- `0x180051888`
- `0x180052b70`
- `0x1800550d4`
- `0x18005c984`
- `0x180061320`
- `0x180062344`
- `0x18007a808`
- `0x1800ac160`
- `0x1800ac290`
- `0x1800ac894`
- `0x1800ac9bc`
- `0x1800ac9fc`
- `0x1800acc08`
- `0x1800af398`
- `0x1800c0010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001a278`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001a278`

## string_xrefs

- `0x180019e45`: `bad extension sequence`
- `0x180019f7c`: `bad extension sequence`
- `0x18001a069`: `Expecting end of comment`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::perl_syntax<unsigned short>>::_find_next_group(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        _DWORD *a4,
        __int64 *a5)
{
  _QWORD *v8; // rbx
  _QWORD *v9; // r15
  _QWORD *v10; // rcx
  _QWORD *v11; // rdx
  _QWORD *v12; // rax
  __int64 v13; // r9
  int v14; // esi
  __int64 v15; // r8
  _QWORD *v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // r8
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  _QWORD *v21; // rax
  _DWORD *v22; // r15
  __int64 v23; // r8
  int v24; // esi
  int v25; // esi
  int v26; // esi
  int v27; // esi
  int v28; // esi
  int v29; // esi
  int v30; // esi
  __int64 v31; // rbx
  size_t v32; // rax
  _QWORD *v33; // rax
  _QWORD *v34; // rcx
  __int64 v35; // r8
  _QWORD *v36; // rax
  __int64 v37; // r8
  _QWORD *v38; // rax
  __int64 v39; // rcx
  _QWORD *v40; // rax
  int v41; // eax
  int v42; // eax
  __int64 next_group; // rax
  __int64 v44; // rcx
  char v45; // r13
  _QWORD *v46; // rax
  int v47; // eax
  __int64 v48; // r8
  _QWORD *v49; // rax
  __int64 v50; // r9
  __int64 v51; // rbx
  size_t v52; // rax
  _QWORD *v53; // rax
  _QWORD *v54; // rcx
  _QWORD *v55; // rax
  _QWORD *v56; // rax
  __int64 v57; // r9
  __int64 v58; // r8
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rbx
  size_t size_of; // rax
  _QWORD *v66; // rax
  _QWORD *v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rdx
  __int64 v70; // rsi
  unsigned __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // rdx
  __int64 v74; // rdx
  __int64 i; // rcx
  _QWORD *v76; // rax
  unsigned __int64 v77; // rcx
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // rax
  unsigned __int64 v81; // rdx
  __int64 v82; // r8
  unsigned __int64 v83; // rcx
  unsigned __int64 v84; // rdx
  __int64 v85; // rax
  __int64 v86; // rax
  _QWORD *v88; // [rsp+38h] [rbp-79h] BYREF
  _QWORD *v89; // [rsp+40h] [rbp-71h] BYREF
  _DWORD *v90; // [rsp+48h] [rbp-69h] BYREF
  _QWORD *pExceptionObject; // [rsp+50h] [rbp-61h] BYREF
  __int64 v92; // [rsp+58h] [rbp-59h]
  int v93; // [rsp+68h] [rbp-49h]
  _QWORD *v94; // [rsp+70h] [rbp-41h] BYREF
  char v95[8]; // [rsp+78h] [rbp-39h] BYREF
  __int64 v96; // [rsp+80h] [rbp-31h]
  __int64 v97; // [rsp+88h] [rbp-29h]
  __int64 v98; // [rsp+90h] [rbp-21h]
  _BYTE v99[32]; // [rsp+98h] [rbp-19h] BYREF

  v90 = a4;
  v94 = (_QWORD *)a1;
  v8 = 0;
  v89 = 0;
  v9 = (_QWORD *)*a2;
  v93 = *a4;
  v94 = *(_QWORD **)(a1 + 24);
  v10 = *(_QWORD **)(a1 + 64);
  if ( v10[3] <= 7u )
    v11 = v10;
  else
    v11 = (_QWORD *)*v10;
  if ( (_QWORD *)((char *)v11 + 2 * v10[2]) == v9
    || (v12 = (_QWORD *)std::wstring::end(v10, &v88, 1),
        (v14 = regex::perl_syntax<unsigned short>::ext_token(v13, a2, *v12)) == 0) )
  {
    pExceptionObject = 0;
    if ( !is_mul_ok(0x60u, 1u) )
      IntSafeWrapperRtlAssertFailure(-2147024362, 0x60u, 1u);
    v70 = *(_QWORD *)(a1 + 8);
    if ( !*(_QWORD *)v70 )
      goto LABEL_72;
    v71 = **(_QWORD **)v70;
    if ( v71 + 96 < v71 )
      IntSafeWrapperRtlAssertFailure(-2147024362, v71, 0x60u);
    if ( v71 + 96 > *(_QWORD *)(v70 + 8) )
LABEL_72:
      regex::detail::pool_impl<std::allocator<char>>::new_block(*(_QWORD *)(a1 + 8), 96, 1);
    v72 = **(_QWORD **)v70 + *(_QWORD *)v70 + 24LL;
    **(_QWORD **)v70 += 96LL;
    if ( v72 )
    {
      v73 = *(_QWORD *)(a1 + 24);
      *(_QWORD *)(a1 + 24) = v73 + 1;
      v8 = (_QWORD *)regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                       v72,
                       v73,
                       a1 + 8);
    }
    else
    {
      v8 = 0;
    }
    v89 = v8;
    ++*(_QWORD *)(a1 + 32);
    v22 = v90;
    goto LABEL_78;
  }
  v16 = *(_QWORD **)(a1 + 64);
  if ( v16[3] <= 7u )
    v17 = *(_QWORD **)(a1 + 64);
  else
    v17 = (_QWORD *)*v16;
  if ( v17 == v9 || *(_QWORD *)std::wstring::end(v16, &v88, v15) == *a2 )
  {
    std::string::string(v99, "ill-formed regular expression");
    regex::bad_regexpr::bad_regexpr(v95, v99);
    throw (regex::bad_regexpr *)v95;
  }
  if ( v14 == 82 )
  {
    v19 = (_QWORD *)regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 16);
    v20 = v19;
    v88 = v19;
    if ( v19 )
    {
      v19[1] = 0;
      *v19 = &regex::detail::match_recurse<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
    }
    else
    {
      v20 = 0;
    }
    **(_QWORD **)(a3 + 56) = v20;
    *(_QWORD *)(a3 + 56) = v20 + 1;
    *(_BYTE *)(a1 + 18) = 0;
  }
  v21 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &pExceptionObject, v18);
  v88 = (_QWORD *)*a2;
  v22 = v90;
  if ( (unsigned int)regex::perl_syntax<unsigned short>::reg_token(v90, &v88, *v21) == 2 )
  {
    *a2 = v88;
    goto LABEL_78;
  }
  v24 = v14 - 74;
  if ( !v24 )
  {
    if ( *(_QWORD *)(a1 + 112) == 0xAAAAAAAAAAAAAAALL )
      goto LABEL_61;
    v64 = *(_QWORD *)(a1 + 104);
    pExceptionObject = (_QWORD *)(a1 + 104);
    v92 = 0;
    size_of = std::_Get_size_of_n<24>(1);
    v66 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    v66[2] = *(_QWORD *)(a1 + 24);
    ++*(_QWORD *)(a1 + 112);
    v67 = *(_QWORD **)(v64 + 8);
    *v66 = v64;
    v66[1] = v67;
    v92 = 0;
    *(_QWORD *)(v64 + 8) = v66;
    *v67 = v66;
    std::_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned __int64,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned __int64,void *>>>(&pExceptionObject);
    v68 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 96);
    pExceptionObject = (_QWORD *)v68;
    if ( v68 )
    {
      v69 = *(_QWORD *)(a1 + 24);
      *(_QWORD *)(a1 + 24) = v69 + 1;
      v61 = regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
              v68,
              v69,
              a1 + 8);
    }
    else
    {
      v61 = 0;
    }
    goto LABEL_65;
  }
  v25 = v24 - 1;
  if ( !v25 )
  {
    v62 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 120);
    pExceptionObject = (_QWORD *)v62;
    if ( v62 )
    {
      LOBYTE(v63) = 1;
      goto LABEL_56;
    }
LABEL_57:
    v61 = 0;
    goto LABEL_65;
  }
  v26 = v25 - 1;
  if ( !v26 )
  {
    v62 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 120);
    pExceptionObject = (_QWORD *)v62;
    if ( v62 )
    {
      v63 = 0;
LABEL_56:
      v61 = regex::detail::lookahead_assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::lookahead_assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
              v62,
              v63,
              a1 + 8);
      goto LABEL_65;
    }
    goto LABEL_57;
  }
  v27 = v26 - 1;
  if ( !v27 )
  {
    v59 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 112);
    pExceptionObject = (_QWORD *)v59;
    if ( v59 )
    {
      LOBYTE(v60) = 1;
      goto LABEL_50;
    }
LABEL_51:
    v61 = 0;
    goto LABEL_65;
  }
  v28 = v27 - 1;
  if ( !v28 )
  {
    v59 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 112);
    pExceptionObject = (_QWORD *)v59;
    if ( v59 )
    {
      v60 = 0;
LABEL_50:
      v61 = regex::detail::lookbehind_assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::lookbehind_assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
              v59,
              v60,
              a1 + 8);
LABEL_65:
      regex::detail::reset_auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(
        &v89,
        v61);
LABEL_47:
      v8 = v89;
LABEL_78:
      v45 = 0;
      goto LABEL_79;
    }
    goto LABEL_51;
  }
  v29 = v28 - 1;
  if ( !v29 )
  {
    if ( *(_QWORD *)(a1 + 112) == 0xAAAAAAAAAAAAAAALL )
      goto LABEL_61;
    v51 = *(_QWORD *)(a1 + 104);
    pExceptionObject = (_QWORD *)(a1 + 104);
    v92 = 0;
    v52 = std::_Get_size_of_n<24>(1);
    v53 = std::_Allocate<16,std::_Default_allocate_traits>(v52);
    v53[2] = *(_QWORD *)(a1 + 24);
    ++*(_QWORD *)(a1 + 112);
    v54 = *(_QWORD **)(v51 + 8);
    *v53 = v51;
    v53[1] = v54;
    v92 = 0;
    *(_QWORD *)(v51 + 8) = v53;
    *v54 = v53;
    std::_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned __int64,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned __int64,void *>>>(&pExceptionObject);
    v55 = (_QWORD *)regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 120);
    pExceptionObject = v55;
    if ( v55 )
    {
      ++*(_QWORD *)(a1 + 24);
      v55[1] = 0;
      *v55 = &regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
      v90 = *(_DWORD **)(a1 + 8);
      v56 = (_QWORD *)regex::detail::convert_allocator<regex::detail::slist<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>> *,regex::detail::arena_allocator<char,std::allocator<char>>>::cons,regex::detail::arena_allocator<char,std::allocator<char>>>(
                        &v90,
                        0);
      *(_QWORD *)(v57 + 16) = *v56;
      *(_QWORD *)(v57 + 24) = 0;
      *(_QWORD *)(v57 + 32) = v58;
      *(_QWORD *)(v57 + 40) = -1;
      *(_QWORD *)(v57 + 48) = -1;
      *(_QWORD *)(v57 + 56) = 0;
      *(_QWORD *)(v57 + 64) = 0;
      *(_BYTE *)(v57 + 72) = 1;
      *(_QWORD *)(v57 + 80) = 0;
      *(_QWORD *)(v57 + 88) = 0;
      *(_QWORD *)v57 = &regex::detail::independent_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
      *(_QWORD *)(v57 + 104) = 0;
      *(_QWORD *)(v57 + 96) = &regex::detail::independent_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::end_group::`vftable';
      *(_QWORD *)(v57 + 112) = v57;
    }
    else
    {
      v57 = 0;
    }
    v88 = (_QWORD *)v57;
    std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::operator=(
      &v89,
      &v88);
    std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(&v88);
    goto LABEL_47;
  }
  v30 = v29 - 1;
  if ( !v30 )
  {
    while ( 1 )
    {
      v46 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &pExceptionObject, v23);
      v47 = regex::perl_syntax<unsigned short>::reg_token(v22, a2, *v46);
      if ( v47 == 2 )
        break;
      if ( !v47 )
      {
        v49 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &v94, v48);
        if ( *v49 != v50 )
          *a2 = v50 + 2;
      }
      if ( *(_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &v90, v48) == *a2 )
      {
        std::string::string(v99, "Expecting end of comment");
        regex::bad_regexpr::bad_regexpr(v95, v99);
        throw (regex::bad_regexpr *)v95;
      }
    }
    return v8;
  }
  if ( v30 != 1 )
  {
    std::string::string(v95, "bad extension sequence");
    regex::bad_regexpr::bad_regexpr(&pExceptionObject, v95);
    throw (regex::bad_regexpr *)&pExceptionObject;
  }
  if ( *(_QWORD *)(a1 + 112) == 0xAAAAAAAAAAAAAAALL )
LABEL_61:
    std::_Xlength_error("list too long");
  v31 = *(_QWORD *)(a1 + 104);
  pExceptionObject = (_QWORD *)(a1 + 104);
  v92 = 0;
  v32 = std::_Get_size_of_n<24>(1);
  v33 = std::_Allocate<16,std::_Default_allocate_traits>(v32);
  v33[2] = *(_QWORD *)(a1 + 24);
  ++*(_QWORD *)(a1 + 112);
  v34 = *(_QWORD **)(v31 + 8);
  *v33 = v31;
  v33[1] = v34;
  v92 = 0;
  *(_QWORD *)(v31 + 8) = v33;
  *v34 = v33;
  std::_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned __int64,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned __int64,void *>>>(&pExceptionObject);
  v36 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &pExceptionObject, v35);
  if ( regex::detail::parse_int<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
         a2,
         *v36,
         -1)
    && (v38 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &v90, v37),
        (unsigned int)regex::perl_syntax<unsigned short>::reg_token(v22, a2, *v38) == 2) )
  {
    v39 = *(_QWORD *)(a1 + 24);
    *(_QWORD *)(a1 + 24) = v39 + 1;
    v88 = regex::detail::create_backref_conditional<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
            v39,
            1,
            a1 + 8);
    std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::operator=(
      &v89,
      &v88);
  }
  else
  {
    v40 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &pExceptionObject, v37);
    v88 = (_QWORD *)*a2;
    v41 = regex::perl_syntax<unsigned short>::ext_token(v22, &v88, *v40) - 75;
    if ( v41 )
    {
      v42 = v41 - 1;
      if ( v42 )
      {
        if ( (unsigned int)(v42 - 1) >= 2 )
        {
          std::string::string(v99, "bad extension sequence");
          regex::bad_regexpr::bad_regexpr(v95, v99);
          throw (regex::bad_regexpr *)v95;
        }
      }
    }
    next_group = regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::perl_syntax<unsigned short>>::_find_next_group(
                   a1,
                   (_DWORD)a2,
                   0,
                   (_DWORD)v22,
                   (__int64)a5);
    v88 = (_QWORD *)next_group;
    v44 = *(_QWORD *)(a1 + 24);
    *(_QWORD *)(a1 + 24) = v44 + 1;
    v88 = regex::detail::create_assertion_conditional<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
            v44,
            next_group,
            a1 + 8);
    std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::operator=(
      &v89,
      &v88);
    std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(&v88);
    v88 = 0;
  }
  std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(&v88);
  v45 = 1;
  v8 = v89;
LABEL_79:
  if ( v8 )
  {
    regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::add_alternate(v8);
    while ( (unsigned __int8)regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::perl_syntax<unsigned short>>::_find_next(
                               a1,
                               (_DWORD)a2,
                               (_DWORD)v8,
                               (_DWORD)v22,
                               (__int64)a5) )
      ;
    regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::end_alternate(v8);
    v74 = 0;
    for ( i = v8[3]; i; v8[3] = i )
    {
      v76 = (_QWORD *)(i + 8);
      i = *(_QWORD *)(i + 8);
      *v76 = v74;
      v74 = v8[3];
    }
    v8[3] = v74;
    regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::get_peek_chars(
      v8,
      v95,
      a1 + 8);
    if ( v45 )
    {
      v77 = 0;
      v78 = v8[3];
      if ( v78 )
      {
        do
        {
          v78 = *(_QWORD *)(v78 + 8);
          ++v77;
        }
        while ( v78 );
        if ( v77 > 2 )
        {
          std::string::string(v99, "Too many alternates in conditional subexpression");
          regex::bad_regexpr::bad_regexpr(v95, v99);
          throw (regex::bad_regexpr *)v95;
        }
      }
    }
    if ( v95[0] && !v8[4] )
    {
      v79 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 288);
      pExceptionObject = (_QWORD *)v79;
      if ( v79 )
        v80 = regex::detail::boyer_moore<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::boyer_moore<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                v79,
                v96,
                v97,
                v98);
      else
        v80 = 0;
      *(_QWORD *)(a1 + 120) = v80;
    }
    v81 = v8[4];
    if ( v81 == -1 )
      goto LABEL_106;
    v82 = *a5;
    v83 = (a5[1] - *a5) >> 3;
    if ( v81 >= v83 )
    {
      v90 = 0;
      v84 = v81 + 1;
      if ( v84 < v83 )
      {
        v85 = v82 + 8 * v84;
LABEL_104:
        a5[1] = v85;
        goto LABEL_105;
      }
      if ( v84 > v83 )
      {
        if ( v84 <= (a5[2] - v82) >> 3 )
        {
          v85 = std::_Uninitialized_fill_n<std::allocator<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>> *>>((void *)a5[1]);
          goto LABEL_104;
        }
        std::vector<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>> *,std::allocator<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>> *>>::_Resize_reallocate<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>> *>(
          a5,
          v84,
          &v90);
      }
    }
LABEL_105:
    *(_QWORD *)(*a5 + 8LL * v8[4]) = v8;
LABEL_106:
    v86 = *v8;
    pExceptionObject = v94;
    v92 = *(_QWORD *)(a1 + 24) - (_QWORD)v94;
    (*(void (__fastcall **)(_QWORD *, _QWORD **))(v86 + 104))(v8, &pExceptionObject);
    *v22 = v93;
  }
  return v8;
}

```

## disassembly

```asm
0x180019cb0  push    rbp
0x180019cb2  push    rbx
0x180019cb3  push    rsi
0x180019cb4  push    rdi
0x180019cb5  push    r12
0x180019cb7  push    r13
0x180019cb9  push    r14
0x180019cbb  push    r15
0x180019cbd  lea     rbp, [rsp-17h]
0x180019cc2  sub     rsp, 0C8h
0x180019cc9  mov     rax, cs:__security_cookie
0x180019cd0  xor     rax, rsp
0x180019cd3  mov     [rbp+4Fh+var_48], rax
0x180019cd7  mov     [rbp+4Fh+var_B8], r9
0x180019cdb  mov     r13, r8
0x180019cde  mov     r14, rdx
0x180019ce1  mov     rdi, rcx
0x180019ce4  mov     r12, [rbp+4Fh+arg_20]
0x180019ce8  mov     [rbp+4Fh+var_90], rcx
0x180019cec  xor     ebx, ebx
0x180019cee  mov     [rbp+4Fh+var_C0], rbx
0x180019cf2  mov     r15, [rdx]
0x180019cf5  mov     eax, [r9]
0x180019cf8  mov     [rbp+4Fh+var_98], eax
0x180019cfb  mov     rax, [rcx+18h]
0x180019cff  mov     [rbp+4Fh+var_90], rax
0x180019d03  mov     [rsp+100h+var_D0], bl
0x180019d07  mov     rcx, [rcx+40h]
0x180019d0b  cmp     qword ptr [rcx+18h], 7
0x180019d10  jbe     short loc_180019D17
0x180019d12  mov     rdx, [rcx]
0x180019d15  jmp     short loc_180019D1A
0x180019d17  mov     rdx, rcx
0x180019d1a  mov     rax, [rcx+10h]
0x180019d1e  lea     rdx, [rdx+rax*2]
0x180019d22  mov     r8d, 1
0x180019d28  cmp     rdx, r15
0x180019d2b  jz      loc_18001A34D
0x180019d31  lea     rdx, [rbp+4Fh+var_C8]
0x180019d35  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x180019d3a  mov     r8, [rax]
0x180019d3d  mov     rdx, r14
0x180019d40  mov     rcx, r9
0x180019d43  call    ?ext_token@?$perl_syntax@G@regex@@QEAA?AW4TOKEN@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@5@@Z; regex::perl_syntax<ushort>::ext_token(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x180019d48  mov     esi, eax
0x180019d4a  test    eax, eax
0x180019d4c  jz      loc_18001A347
0x180019d52  mov     rcx, [rdi+40h]
0x180019d56  cmp     qword ptr [rcx+18h], 7
0x180019d5b  jbe     short loc_180019D62
0x180019d5d  mov     rax, [rcx]
0x180019d60  jmp     short loc_180019D65
0x180019d62  mov     rax, rcx
0x180019d65  cmp     rax, r15
0x180019d68  jz      loc_18001A318
0x180019d6e  lea     rdx, [rbp+4Fh+var_C8]
0x180019d72  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x180019d77  mov     rcx, [r14]
0x180019d7a  cmp     [rax], rcx
0x180019d7d  jz      loc_18001A318
0x180019d83  cmp     esi, 52h ; 'R'
0x180019d86  jnz     short loc_180019DCE
0x180019d88  lea     rcx, [rdi+8]
0x180019d8c  lea     edx, [rsi-42h]
0x180019d8f  call    ?allocate@?$arena_allocator@DV?$allocator@D@std@@@detail@regex@@QEAAPEAD_KPEBX@Z; regex::detail::arena_allocator<char,std::allocator<char>>::allocate(unsigned __int64,void const *)
0x180019d94  mov     rcx, rax
0x180019d97  mov     [rbp+4Fh+var_C8], rax
0x180019d9b  test    rax, rax
0x180019d9e  jz      short loc_180019DB4
0x180019da0  mov     qword ptr [rax+8], 0
0x180019da8  lea     rax, ??_7?$match_recurse@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@6B@; const regex::detail::match_recurse<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::`vftable'
0x180019daf  mov     [rcx], rax
0x180019db2  jmp     short loc_180019DB6
0x180019db4  xor     ecx, ecx
0x180019db6  mov     rax, [r13+38h]
0x180019dba  mov     [rax], rcx
0x180019dbd  lea     rax, [rcx+8]
0x180019dc1  mov     [r13+38h], rax
0x180019dc5  xor     r13d, r13d
0x180019dc8  mov     [rdi+12h], r13b
0x180019dcc  jmp     short loc_180019DD1
0x180019dce  xor     r13d, r13d
0x180019dd1  lea     rdx, [rbp+4Fh+pExceptionObject]
0x180019dd5  mov     rcx, [rdi+40h]
0x180019dd9  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x180019dde  mov     rcx, [r14]
0x180019de1  mov     [rbp+4Fh+var_C8], rcx
0x180019de5  mov     r8, [rax]
0x180019de8  lea     rdx, [rbp+4Fh+var_C8]
0x180019dec  mov     r15, [rbp+4Fh+var_B8]
0x180019df0  mov     rcx, r15
0x180019df3  call    ?reg_token@?$perl_syntax@G@regex@@QEAA?AW4TOKEN@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@5@@Z; regex::perl_syntax<ushort>::reg_token(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x180019df8  cmp     eax, 2
0x180019dfb  jz      loc_18001A30C
0x180019e01  sub     esi, 4Ah ; 'J'
0x180019e04  jz      loc_18001A25D
0x180019e0a  sub     esi, 1
0x180019e0d  jz      loc_18001A242
0x180019e13  sub     esi, 1
0x180019e16  jz      loc_18001A207
0x180019e1c  sub     esi, 1
0x180019e1f  jz      loc_18001A1EC
0x180019e25  sub     esi, 1
0x180019e28  jz      loc_18001A1B4
0x180019e2e  sub     esi, 1
0x180019e31  jz      loc_18001A098
0x180019e37  sub     esi, 1
0x180019e3a  jz      loc_18001A010
0x180019e40  cmp     esi, 1
0x180019e43  jz      short loc_180019E74
0x180019e45  lea     rdx, aBadExtensionSe; "bad extension sequence"
0x180019e4c  lea     rcx, [rbp+4Fh+var_88]
0x180019e50  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180019e55  nop
0x180019e56  lea     rdx, [rbp+4Fh+var_88]
0x180019e5a  lea     rcx, [rbp+4Fh+pExceptionObject]
0x180019e5e  call    ??0bad_regexpr@regex@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; regex::bad_regexpr::bad_regexpr(std::string const &)
0x180019e63  lea     rdx, _TI4?AVbad_regexpr@regex@@; pThrowInfo
0x180019e6a  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180019e6e  call    _CxxThrowException_0
0x180019e74  lea     rsi, [rdi+68h]
0x180019e78  mov     rax, 0AAAAAAAAAAAAAAAh
0x180019e82  cmp     [rsi+8], rax
0x180019e86  jz      loc_18001A271
0x180019e8c  mov     rbx, [rsi]
0x180019e8f  mov     [rbp+4Fh+pExceptionObject], rsi
0x180019e93  mov     [rbp+4Fh+var_A8], r13
0x180019e97  mov     ecx, 1
0x180019e9c  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x180019ea1  mov     rcx, rax
0x180019ea4  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180019ea9  mov     rcx, [rdi+18h]
0x180019ead  mov     [rax+10h], rcx
0x180019eb1  inc     qword ptr [rsi+8]
0x180019eb5  mov     rcx, [rbx+8]
0x180019eb9  mov     [rax], rbx
0x180019ebc  mov     [rax+8], rcx
0x180019ec0  mov     [rbp+4Fh+var_A8], r13
0x180019ec4  mov     [rbx+8], rax
0x180019ec8  mov     [rcx], rax
0x180019ecb  lea     rcx, [rbp+4Fh+pExceptionObject]
0x180019ecf  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@_KPEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned __int64,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned __int64,void *>>>(void)
0x180019ed4  lea     rdx, [rbp+4Fh+pExceptionObject]
0x180019ed8  mov     rcx, [rdi+40h]
0x180019edc  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x180019ee1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019ee5  mov     rdx, [rax]
0x180019ee8  mov     rcx, r14
0x180019eeb  call    ??$parse_int@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@@detail@regex@@YA_KAEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V23@_K@Z; regex::detail::parse_int<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,unsigned __int64)
0x180019ef0  test    rax, rax
0x180019ef3  jz      short loc_180019F45
0x180019ef5  lea     rdx, [rbp+4Fh+var_B8]
0x180019ef9  mov     rcx, [rdi+40h]
0x180019efd  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x180019f02  mov     r8, [rax]
0x180019f05  mov     rdx, r14
0x180019f08  mov     rcx, r15
0x180019f0b  call    ?reg_token@?$perl_syntax@G@regex@@QEAA?AW4TOKEN@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@5@@Z; regex::perl_syntax<ushort>::reg_token(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x180019f10  cmp     eax, 2
0x180019f13  jnz     short loc_180019F45
0x180019f15  mov     rcx, [rdi+18h]
0x180019f19  lea     rax, [rcx+1]
0x180019f1d  mov     [rdi+18h], rax
0x180019f21  lea     r8, [rdi+8]
0x180019f25  mov     edx, 1
0x180019f2a  call    ??$create_backref_conditional@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@YAPEAV?$match_conditional@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@U?$backref_condition@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@01@_K0AEAV?$arena_allocator@DV?$allocator@D@std@@@01@@Z; regex::detail::create_backref_conditional<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(unsigned __int64,unsigned __int64,regex::detail::arena_allocator<char,std::allocator<char>> &)
0x180019f2f  mov     [rbp+4Fh+var_C8], rax
0x180019f33  lea     rdx, [rbp+4Fh+var_C8]
0x180019f37  lea     rcx, [rbp+4Fh+var_C0]
0x180019f3b  call    ??4?$auto_ptr@V?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@QEAAAEAV01@AEAV01@@Z; std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::operator=(std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>> &)
0x180019f40  jmp     loc_180019FFB
0x180019f45  lea     rdx, [rbp+4Fh+pExceptionObject]
0x180019f49  mov     rcx, [rdi+40h]
0x180019f4d  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x180019f52  mov     rcx, [r14]
0x180019f55  mov     [rbp+4Fh+var_C8], rcx
0x180019f59  mov     r8, [rax]
0x180019f5c  lea     rdx, [rbp+4Fh+var_C8]
0x180019f60  mov     rcx, r15
0x180019f63  call    ?ext_token@?$perl_syntax@G@regex@@QEAA?AW4TOKEN@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@5@@Z; regex::perl_syntax<ushort>::ext_token(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x180019f68  sub     eax, 4Bh ; 'K'
0x180019f6b  jz      short loc_180019FAB
0x180019f6d  sub     eax, 1
0x180019f70  jz      short loc_180019FAB
0x180019f72  sub     eax, 1
0x180019f75  jz      short loc_180019FAB
0x180019f77  cmp     eax, 1
0x180019f7a  jz      short loc_180019FAB
0x180019f7c  lea     rdx, aBadExtensionSe; "bad extension sequence"
0x180019f83  lea     rcx, [rbp+4Fh+var_68]
0x180019f87  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180019f8c  nop
0x180019f8d  lea     rdx, [rbp+4Fh+var_68]
0x180019f91  lea     rcx, [rbp+4Fh+var_88]
0x180019f95  call    ??0bad_regexpr@regex@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; regex::bad_regexpr::bad_regexpr(std::string const &)
0x180019f9a  lea     rdx, _TI4?AVbad_regexpr@regex@@; pThrowInfo
0x180019fa1  lea     rcx, [rbp+4Fh+var_88]; pExceptionObject
0x180019fa5  call    _CxxThrowException_0
0x180019fab  mov     [rsp+100h+var_E0], r12
0x180019fb0  mov     r9, r15
0x180019fb3  xor     r8d, r8d
0x180019fb6  mov     rdx, r14
0x180019fb9  mov     rcx, rdi
0x180019fbc  call    ?_find_next_group@?$basic_rpattern_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$perl_syntax@G@regex@@@regex@@IEAAPEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@PEAV342@AEAV?$perl_syntax@G@2@AEAV?$vector@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@V?$allocator@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@@6@@Z; regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,regex::perl_syntax<ushort>>::_find_next_group(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,regex::perl_syntax<ushort> &,std::vector<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,std::allocator<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *>> &)
0x180019fc1  mov     [rbp+4Fh+var_C8], rax
0x180019fc5  mov     rcx, [rdi+18h]
0x180019fc9  lea     rdx, [rcx+1]
0x180019fcd  mov     [rdi+18h], rdx
0x180019fd1  lea     r8, [rdi+8]
0x180019fd5  mov     rdx, rax
0x180019fd8  call    ??$create_assertion_conditional@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@YAPEAV?$match_conditional@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@U?$assertion_condition@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@01@_KPEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@01@AEAV?$arena_allocator@DV?$allocator@D@std@@@01@@Z; regex::detail::create_assertion_conditional<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(unsigned __int64,regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,regex::detail::arena_allocator<char,std::allocator<char>> &)
0x180019fdd  mov     [rbp+4Fh+var_C8], rax
0x180019fe1  lea     rdx, [rbp+4Fh+var_C8]
0x180019fe5  lea     rcx, [rbp+4Fh+var_C0]
0x180019fe9  call    ??4?$auto_ptr@V?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@QEAAAEAV01@AEAV01@@Z; std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::operator=(std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>> &)
0x180019fee  lea     rcx, [rbp+4Fh+var_C8]
0x180019ff2  call    ??1?$auto_ptr@V?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@QEAA@XZ; std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(void)
0x180019ff7  mov     [rbp+4Fh+var_C8], r13
0x180019ffb  lea     rcx, [rbp+4Fh+var_C8]
0x180019fff  call    ??1?$auto_ptr@V?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@QEAA@XZ; std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(void)
0x18001a004  mov     r13b, 1
0x18001a007  mov     rbx, [rbp+4Fh+var_C0]
0x18001a00b  jmp     loc_18001A3F1
0x18001a010  lea     rdx, [rbp+4Fh+pExceptionObject]
0x18001a014  mov     rcx, [rdi+40h]
0x18001a018  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18001a01d  mov     r8, [rax]
0x18001a020  mov     rdx, r14
0x18001a023  mov     rcx, r15
0x18001a026  call    ?reg_token@?$perl_syntax@G@regex@@QEAA?AW4TOKEN@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@5@@Z; regex::perl_syntax<ushort>::reg_token(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x18001a02b  cmp     eax, 2
0x18001a02e  jz      loc_18001A589
0x18001a034  test    eax, eax
0x18001a036  jnz     short loc_18001A054
0x18001a038  mov     r9, [r14]
0x18001a03b  lea     rdx, [rbp+4Fh+var_90]
0x18001a03f  mov     rcx, [rdi+40h]
0x18001a043  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18001a048  cmp     [rax], r9
0x18001a04b  jz      short loc_18001A054
0x18001a04d  lea     rax, [r9+2]
0x18001a051  mov     [r14], rax
0x18001a054  lea     rdx, [rbp+4Fh+var_B8]
0x18001a058  mov     rcx, [rdi+40h]
0x18001a05c  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18001a061  mov     rcx, [r14]
0x18001a064  cmp     [rax], rcx
0x18001a067  jnz     short loc_18001A010
0x18001a069  lea     rdx, aExpectingEndOf; "Expecting end of comment"
0x18001a070  lea     rcx, [rbp+4Fh+var_68]
0x18001a074  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001a079  nop
0x18001a07a  lea     rdx, [rbp+4Fh+var_68]
0x18001a07e  lea     rcx, [rbp+4Fh+var_88]
0x18001a082  call    ??0bad_regexpr@regex@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; regex::bad_regexpr::bad_regexpr(std::string const &)
0x18001a087  lea     rdx, _TI4?AVbad_regexpr@regex@@; pThrowInfo
0x18001a08e  lea     rcx, [rbp+4Fh+var_88]; pExceptionObject
0x18001a092  call    _CxxThrowException_0
0x18001a098  lea     rsi, [rdi+68h]
0x18001a09c  mov     rax, 0AAAAAAAAAAAAAAAh
0x18001a0a6  cmp     [rsi+8], rax
0x18001a0aa  jz      loc_18001A271
0x18001a0b0  mov     rbx, [rsi]
0x18001a0b3  mov     [rbp+4Fh+pExceptionObject], rsi
0x18001a0b7  mov     [rbp+4Fh+var_A8], r13
0x18001a0bb  mov     ecx, 1
0x18001a0c0  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x18001a0c5  mov     rcx, rax
0x18001a0c8  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001a0cd  mov     rcx, [rdi+18h]
0x18001a0d1  mov     [rax+10h], rcx
0x18001a0d5  inc     qword ptr [rsi+8]
0x18001a0d9  mov     rcx, [rbx+8]
0x18001a0dd  mov     [rax], rbx
0x18001a0e0  mov     [rax+8], rcx
0x18001a0e4  mov     [rbp+4Fh+var_A8], r13
0x18001a0e8  mov     [rbx+8], rax
0x18001a0ec  mov     [rcx], rax
0x18001a0ef  lea     rcx, [rbp+4Fh+pExceptionObject]
0x18001a0f3  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@_KPEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned __int64,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned __int64,void *>>>(void)
0x18001a0f8  mov     edx, 78h ; 'x'
0x18001a0fd  lea     rcx, [rdi+8]
0x18001a101  call    ?allocate@?$arena_allocator@DV?$allocator@D@std@@@detail@regex@@QEAAPEAD_KPEBX@Z; regex::detail::arena_allocator<char,std::allocator<char>>::allocate(unsigned __int64,void const *)
0x18001a106  mov     r9, rax
0x18001a109  mov     [rbp+4Fh+pExceptionObject], rax
0x18001a10d  test    rax, rax
0x18001a110  jz      short loc_18001A18E
0x18001a112  mov     r8, [rdi+18h]
0x18001a116  lea     rcx, [r8+1]
0x18001a11a  mov     [rdi+18h], rcx
0x18001a11e  mov     [rax+8], r13
0x18001a122  lea     rax, ??_7?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@6B@; const regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::`vftable'
0x18001a129  mov     [r9], rax
0x18001a12c  mov     rcx, [rdi+8]
0x18001a130  mov     [rbp+4Fh+var_B8], rcx
0x18001a134  xor     edx, edx
0x18001a136  lea     rcx, [rbp+4Fh+var_B8]
0x18001a13a  call    ??$convert_allocator@Ucons@?$slist@PEAV?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@V?$arena_allocator@DV?$allocator@D@std@@@23@@detail@regex@@V?$arena_allocator@DV?$allocator@D@std@@@34@@detail@regex@@YAAEBV?$arena_allocator@DV?$allocator@D@std@@@01@AEBV201@ZZ; regex::detail::convert_allocator<regex::detail::slist<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,regex::detail::arena_allocator<char,std::allocator<char>>>::cons,regex::detail::arena_allocator<char,std::allocator<char>>>(regex::detail::arena_allocator<char,std::allocator<char>> const &,...)
0x18001a13f  mov     rcx, [rax]
0x18001a142  mov     [r9+10h], rcx
  ... truncated ...
```
