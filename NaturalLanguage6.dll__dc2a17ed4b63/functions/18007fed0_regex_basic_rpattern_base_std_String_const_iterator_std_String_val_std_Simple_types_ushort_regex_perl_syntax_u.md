# regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,regex::perl_syntax<ushort>>::_find_next_group(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,regex::perl_syntax<ushort> &,std::vector<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,std::allocator<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *>> &)

- ea: `0x18007fed0`
- end: `0x18008070a`
- name: `?_find_next_group@?$basic_rpattern_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$perl_syntax@G@regex@@@regex@@IEAAPEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@PEAV342@AEAV?$perl_syntax@G@2@AEAV?$vector@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@V?$allocator@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@@6@@Z`
- size: `2106`
- prototype: `__int64 *__fastcall(__int64, __int64 *, __int64, int *, __int64 *)`
- caller_count: `3`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007eb2c`
- `0x18007f4e4`
- `0x18007fed0`

## callees

- `0x18003ed6c`
- `0x18003f190`
- `0x18007a110`
- `0x18007b8fc`
- `0x18007c3fc`
- `0x18007c6ec`
- `0x18007c8a4`
- `0x18007c920`
- `0x18007c990`
- `0x18007ca04`
- `0x18007ccfc`
- `0x18007d15c`
- `0x18007d8dc`
- `0x18007e6d4`
- `0x18007f4e4`
- `0x18007fed0`
- `0x180081238`
- `0x18008126c`
- `0x180081978`
- `0x18008199c`
- `0x180081d64`
- `0x180081fd0`
- `0x180085af8`
- `0x180089f90`
- `0x18009e300`
- `0x1800b0010`

## string_xrefs

- `0x180080080`: `bad extension sequence`
- `0x1800801b1`: `bad extension sequence`
- `0x1800802ad`: `Expecting end of comment`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::perl_syntax<unsigned short>>::_find_next_group(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        int *a4,
        __int64 *a5)
{
  __int64 *v8; // rbx
  __int64 v9; // r15
  _QWORD *v10; // r12
  _QWORD *v11; // rax
  __int64 v12; // r9
  int v13; // esi
  __int64 *v14; // rcx
  __int64 v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rcx
  _QWORD *v18; // rax
  int *v19; // r13
  int v20; // esi
  int v21; // esi
  int v22; // esi
  int v23; // esi
  int v24; // esi
  int v25; // esi
  int v26; // esi
  _QWORD *v27; // rax
  _QWORD *v28; // rax
  __int64 v29; // r15
  __int64 v30; // rax
  _QWORD *v31; // rbx
  __int64 *v32; // rcx
  _QWORD *v33; // rax
  int v34; // eax
  int v35; // eax
  int *next_group; // rax
  __int64 v37; // rcx
  _QWORD *v38; // rax
  int v39; // eax
  _QWORD *v40; // rax
  __int64 v41; // r9
  __int64 v42; // rax
  __int64 v43; // rbx
  __int64 v44; // rdx
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 *v51; // r15
  __int64 v52; // rdx
  __int64 i; // rcx
  _QWORD *v54; // rax
  unsigned __int64 v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rax
  unsigned __int64 v58; // r9
  __int64 v59; // rcx
  __int64 v60; // r8
  unsigned __int64 v61; // rax
  unsigned __int64 v62; // r9
  __int64 v63; // rax
  __int64 v64; // rax
  char v66; // [rsp+30h] [rbp-A1h]
  __int64 *v67; // [rsp+38h] [rbp-99h] BYREF
  __int64 v68; // [rsp+40h] [rbp-91h] BYREF
  int *v69; // [rsp+48h] [rbp-89h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+50h] [rbp-81h] BYREF
  __int64 *v71; // [rsp+68h] [rbp-69h] BYREF
  int v72; // [rsp+70h] [rbp-61h]
  __int64 v73; // [rsp+78h] [rbp-59h] BYREF
  _QWORD v74[2]; // [rsp+80h] [rbp-51h] BYREF
  _QWORD v75[4]; // [rsp+90h] [rbp-41h] BYREF
  _QWORD v76[4]; // [rsp+B0h] [rbp-21h] BYREF

  v74[1] = -2;
  v69 = a4;
  v74[0] = a1;
  v71 = a5;
  v8 = 0;
  v67 = 0;
  v9 = *a2;
  v72 = *a4;
  v10 = (_QWORD *)(a1 + 24);
  v73 = *(_QWORD *)(a1 + 24);
  v66 = 0;
  if ( *(_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &v68) == v9
    || (v11 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &v68),
        (v13 = regex::perl_syntax<unsigned short>::ext_token(v12, a2, *v11)) == 0) )
  {
    v49 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 96);
    pExceptionObject[0] = v49;
    if ( v49 )
    {
      v50 = (*v10)++;
      v49 = regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
              v49,
              v50,
              a1 + 8);
    }
    regex::detail::reset_auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(
      &v67,
      v49);
    ++*(_QWORD *)(a1 + 32);
    v19 = v69;
    goto LABEL_65;
  }
  v14 = *(__int64 **)(a1 + 64);
  if ( (unsigned __int64)v14[3] < 8 )
    v15 = *(_QWORD *)(a1 + 64);
  else
    v15 = *v14;
  if ( v15 == v9 || *(_QWORD *)std::wstring::end(v14, &v68) == *a2 )
  {
    std::string::string(v76, "ill-formed regular expression");
    regex::bad_regexpr::bad_regexpr(v75, v76);
    throw (regex::bad_regexpr *)v75;
  }
  if ( v13 == 82 )
  {
    v68 = a1 + 8;
    v16 = (_QWORD *)regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 16);
    v17 = v16;
    pExceptionObject[0] = v16;
    if ( v16 )
    {
      *v16 = &NaturalLanguage6::IKeyValuePair::`vftable';
      *v16 = &regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
      v16[1] = 0;
      *v16 = &regex::detail::match_recurse<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
    }
    else
    {
      v17 = 0;
    }
    **(_QWORD **)(a3 + 56) = v17;
    *(_QWORD *)(a3 + 56) = v17 + 1;
    *(_BYTE *)(a1 + 18) = 0;
  }
  v18 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), pExceptionObject);
  v68 = *a2;
  v19 = v69;
  if ( (unsigned int)regex::perl_syntax<unsigned short>::reg_token(v69, &v68, *v18) == 2 )
  {
    *a2 = v68;
    goto LABEL_66;
  }
  v20 = v13 - 74;
  if ( !v20 )
  {
    std::list<unsigned __int64>::push_back(a1 + 104, v10);
    v45 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 96);
    pExceptionObject[0] = v45;
    if ( v45 )
    {
      v48 = (*v10)++;
      v45 = regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
              v45,
              v48,
              a1 + 8);
    }
    goto LABEL_59;
  }
  v21 = v20 - 1;
  if ( !v21 )
  {
    v45 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 120);
    pExceptionObject[0] = v45;
    if ( v45 )
    {
      LOBYTE(v47) = 1;
      v45 = regex::detail::lookahead_assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::lookahead_assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
              v45,
              v47,
              a1 + 8);
    }
    goto LABEL_59;
  }
  v22 = v21 - 1;
  if ( !v22 )
  {
    v45 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 120);
    pExceptionObject[0] = v45;
    if ( v45 )
      v45 = regex::detail::lookahead_assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::lookahead_assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
              v45,
              0,
              a1 + 8);
    goto LABEL_59;
  }
  v23 = v22 - 1;
  if ( !v23 )
  {
    v45 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 112);
    pExceptionObject[0] = v45;
    if ( v45 )
    {
      LOBYTE(v46) = 1;
      v45 = regex::detail::lookbehind_assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::lookbehind_assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
              v45,
              v46,
              a1 + 8);
    }
    goto LABEL_59;
  }
  v24 = v23 - 1;
  if ( !v24 )
  {
    v45 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 112);
    pExceptionObject[0] = v45;
    if ( v45 )
      v45 = regex::detail::lookbehind_assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::lookbehind_assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
              v45,
              0,
              a1 + 8);
LABEL_59:
    regex::detail::reset_auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(
      &v67,
      v45);
LABEL_65:
    v8 = v67;
LABEL_66:
    if ( v8 )
    {
      regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::add_alternate(v8);
      v51 = v71;
      while ( regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::perl_syntax<unsigned short>>::_find_next(
                a1,
                a2,
                (__int64)v8,
                v19,
                (__int64)v51) )
        ;
      regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::end_alternate(v8);
      v52 = 0;
      for ( i = v8[3]; i; v8[3] = i )
      {
        v54 = (_QWORD *)(i + 8);
        i = *(_QWORD *)(i + 8);
        *v54 = v52;
        v52 = v8[3];
      }
      v8[3] = v52;
      regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::get_peek_chars(
        v8,
        v75,
        a1 + 8);
      if ( v66 )
      {
        v55 = 0;
        v56 = v8[3];
        if ( v56 )
        {
          do
          {
            v56 = *(_QWORD *)(v56 + 8);
            ++v55;
          }
          while ( v56 );
          if ( v55 > 2 )
          {
            std::string::string(v76, "Too many alternates in conditional subexpression");
            regex::bad_regexpr::bad_regexpr(v75, v76);
            throw (regex::bad_regexpr *)v75;
          }
        }
      }
      if ( LOBYTE(v75[0]) && !v8[4] )
      {
        v57 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 288);
        pExceptionObject[0] = v57;
        if ( v57 )
          v57 = regex::detail::boyer_moore<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::boyer_moore<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                  v57,
                  v75[1],
                  v75[2],
                  v75[3]);
        *(_QWORD *)(a1 + 120) = v57;
      }
      v58 = v8[4];
      if ( v58 != -1 )
      {
        v59 = *v51;
        v60 = v51[1];
        v61 = (v60 - *v51) >> 3;
        if ( v58 >= v61 )
        {
          v71 = 0;
          v62 = v58 + 1;
          if ( v62 >= v61 )
          {
            if ( v62 > v61 )
              std::vector<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>> *,std::allocator<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>> *>>::_Insert_n(
                v51,
                pExceptionObject,
                v60,
                v62 - v61,
                &v71);
          }
          else
          {
            v63 = v59 + 8 * v62;
            if ( v63 == v59 )
            {
              v51[1] = v59;
            }
            else if ( v63 != v60 )
            {
              v51[1] = v63;
            }
          }
        }
        *(_QWORD *)(*v51 + 8 * v8[4]) = v8;
      }
      v64 = *v8;
      pExceptionObject[0] = v73;
      pExceptionObject[1] = *v10 - v73;
      (*(void (__fastcall **)(__int64 *, _QWORD *))(v64 + 104))(v8, pExceptionObject);
      *v19 = v72;
    }
    goto LABEL_93;
  }
  v25 = v24 - 1;
  if ( !v25 )
  {
    std::list<unsigned __int64>::push_back(a1 + 104, v10);
    v42 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 120);
    v43 = v42;
    pExceptionObject[0] = v42;
    if ( v42 )
    {
      v44 = (*v10)++;
      regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
        v42,
        v44,
        a1 + 8);
      *(_QWORD *)v43 = &regex::detail::independent_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
      *(_BYTE *)(v43 + 72) = 1;
      *(_QWORD *)(v43 + 80) = 0;
      *(_QWORD *)(v43 + 88) = 0;
      *(_QWORD *)v43 = &regex::detail::independent_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
      v69 = (int *)(v43 + 96);
      *(_QWORD *)(v43 + 96) = &NaturalLanguage6::IKeyValuePair::`vftable';
      *(_QWORD *)(v43 + 96) = &regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
      *(_QWORD *)(v43 + 104) = 0;
      *(_QWORD *)(v43 + 96) = &regex::detail::indestructable_sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::detail::independent_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::end_group>::`vftable';
      *(_QWORD *)(v43 + 96) = &regex::detail::independent_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::end_group::`vftable';
      *(_QWORD *)(v43 + 112) = v43;
    }
    else
    {
      v43 = 0;
    }
    v69 = (int *)v43;
    std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::operator=(
      &v67,
      &v69);
    std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(&v69);
    goto LABEL_65;
  }
  v26 = v25 - 1;
  if ( v26 )
  {
    if ( v26 != 1 )
    {
      std::string::string(v75, "bad extension sequence");
      regex::bad_regexpr::bad_regexpr(pExceptionObject, v75);
      throw (regex::bad_regexpr *)pExceptionObject;
    }
    std::list<unsigned __int64>::push_back(a1 + 104, v10);
    v27 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), pExceptionObject);
    if ( regex::detail::parse_int<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
           a2,
           *v27,
           -1)
      && (v28 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &v69),
          (unsigned int)regex::perl_syntax<unsigned short>::reg_token(v19, a2, *v28) == 2) )
    {
      v29 = (*v10)++;
      pExceptionObject[0] = a1 + 8;
      v30 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 104);
      v31 = (_QWORD *)v30;
      v69 = (int *)v30;
      if ( v30 )
      {
        regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
          v30,
          v29,
          a1 + 8);
        *v31 = &regex::detail::match_conditional<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::detail::backref_condition<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::`vftable';
        v31[12] = 1;
      }
      else
      {
        v31 = 0;
      }
      v68 = (__int64)v31;
      std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::operator=(
        &v67,
        &v68);
      v32 = &v68;
    }
    else
    {
      v33 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), pExceptionObject);
      v68 = *a2;
      v34 = regex::perl_syntax<unsigned short>::ext_token(v19, &v68, *v33) - 75;
      if ( v34 )
      {
        v35 = v34 - 1;
        if ( v35 )
        {
          if ( (unsigned int)(v35 - 1) >= 2 )
          {
            std::string::string(v76, "bad extension sequence");
            regex::bad_regexpr::bad_regexpr(v75, v76);
            throw (regex::bad_regexpr *)v75;
          }
        }
      }
      next_group = (int *)regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::perl_syntax<unsigned short>>::_find_next_group(
                            a1,
                            (_DWORD)a2,
                            0,
                            (_DWORD)v19,
                            (__int64)v71);
      v69 = next_group;
      v37 = (*v10)++;
      v68 = (__int64)regex::detail::create_assertion_conditional<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                       v37,
                       next_group,
                       a1 + 8);
      std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::operator=(
        &v67,
        &v68);
      std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(&v68);
      v69 = 0;
      v32 = (__int64 *)&v69;
    }
    std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(v32);
    v66 = 1;
    goto LABEL_65;
  }
  while ( 1 )
  {
    v38 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), pExceptionObject);
    v39 = regex::perl_syntax<unsigned short>::reg_token(v19, a2, *v38);
    if ( v39 == 2 )
      break;
    if ( !v39 )
    {
      v40 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), v74);
      if ( *v40 != v41 )
        *a2 = v41 + 2;
    }
    if ( *(_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &v73) == *a2 )
    {
      std::string::string(v76, "Expecting end of comment");
      regex::bad_regexpr::bad_regexpr(v75, v76);
      throw (regex::bad_regexpr *)v75;
    }
  }
LABEL_93:
  v67 = 0;
  std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(&v67);
  return v8;
}

```

## disassembly

```asm
0x18007fed0  push    rbp
0x18007fed2  push    rbx
0x18007fed3  push    rsi
0x18007fed4  push    rdi
0x18007fed5  push    r12
0x18007fed7  push    r13
0x18007fed9  push    r14
0x18007fedb  push    r15
0x18007fedd  lea     rbp, [rsp-17h]
0x18007fee2  sub     rsp, 0E8h
0x18007fee9  mov     [rbp+4Fh+var_98], 0FFFFFFFFFFFFFFFEh
0x18007fef1  mov     rax, cs:__security_cookie
0x18007fef8  xor     rax, rsp
0x18007fefb  mov     [rbp+4Fh+var_50], rax
0x18007feff  mov     [rsp+120h+var_D8], r9
0x18007ff04  mov     r13, r8
0x18007ff07  mov     r14, rdx
0x18007ff0a  mov     rdi, rcx
0x18007ff0d  mov     [rbp+4Fh+var_A0], rcx
0x18007ff11  mov     rax, [rbp+4Fh+arg_20]
0x18007ff15  mov     [rbp+4Fh+var_B8], rax
0x18007ff19  xor     ebx, ebx
0x18007ff1b  mov     [rsp+120h+var_E8], rbx
0x18007ff20  mov     r15, [rdx]
0x18007ff23  mov     eax, [r9]
0x18007ff26  mov     [rbp+4Fh+var_B0], eax
0x18007ff29  lea     r12, [rcx+18h]
0x18007ff2d  mov     rax, [r12]
0x18007ff31  mov     [rbp+4Fh+var_A8], rax
0x18007ff35  mov     [rsp+120h+var_F0], bl
0x18007ff39  lea     rdx, [rsp+120h+var_E0]
0x18007ff3e  mov     rcx, [rcx+40h]
0x18007ff42  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007ff47  cmp     [rax], r15
0x18007ff4a  jz      loc_1800804EE
0x18007ff50  lea     rdx, [rsp+120h+var_E0]
0x18007ff55  mov     rcx, [rdi+40h]
0x18007ff59  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007ff5e  mov     r8, [rax]
0x18007ff61  mov     rdx, r14
0x18007ff64  mov     rcx, r9
0x18007ff67  call    ?ext_token@?$perl_syntax@G@regex@@QEAA?AW4TOKEN@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@5@@Z; regex::perl_syntax<ushort>::ext_token(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x18007ff6c  mov     esi, eax
0x18007ff6e  test    eax, eax
0x18007ff70  jz      loc_1800804EE
0x18007ff76  mov     rcx, [rdi+40h]
0x18007ff7a  cmp     qword ptr [rcx+18h], 8
0x18007ff7f  jb      short loc_18007FF86
0x18007ff81  mov     rax, [rcx]
0x18007ff84  jmp     short loc_18007FF89
0x18007ff86  mov     rax, rcx
0x18007ff89  cmp     rax, r15
0x18007ff8c  jz      loc_1800804BF
0x18007ff92  lea     rdx, [rsp+120h+var_E0]
0x18007ff97  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007ff9c  mov     rcx, [r14]
0x18007ff9f  cmp     [rax], rcx
0x18007ffa2  jz      loc_1800804BF
0x18007ffa8  lea     r15, ??_7IKeyValuePair@NaturalLanguage6@@6B@; const NaturalLanguage6::IKeyValuePair::`vftable'
0x18007ffaf  cmp     esi, 52h ; 'R'
0x18007ffb2  jnz     short loc_180080008
0x18007ffb4  lea     rcx, [rdi+8]
0x18007ffb8  mov     [rsp+120h+var_E0], rcx
0x18007ffbd  lea     edx, [rsi-42h]
0x18007ffc0  call    ?allocate@?$arena_allocator@DV?$allocator@D@std@@@detail@regex@@QEAAPEAD_KPEBX@Z; regex::detail::arena_allocator<char,std::allocator<char>>::allocate(unsigned __int64,void const *)
0x18007ffc5  mov     rcx, rax
0x18007ffc8  mov     [rsp+120h+pExceptionObject], rax
0x18007ffcd  test    rax, rax
0x18007ffd0  jz      short loc_18007FFF3
0x18007ffd2  mov     [rax], r15
0x18007ffd5  lea     rax, ??_7?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@6B@; const regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::`vftable'
0x18007ffdc  mov     [rcx], rax
0x18007ffdf  mov     qword ptr [rcx+8], 0
0x18007ffe7  lea     rax, ??_7?$match_recurse@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@6B@; const regex::detail::match_recurse<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::`vftable'
0x18007ffee  mov     [rcx], rax
0x18007fff1  jmp     short loc_18007FFF5
0x18007fff3  xor     ecx, ecx
0x18007fff5  mov     rax, [r13+38h]
0x18007fff9  mov     [rax], rcx
0x18007fffc  lea     rax, [rcx+8]
0x180080000  mov     [r13+38h], rax
0x180080004  mov     byte ptr [rdi+12h], 0
0x180080008  lea     rdx, [rsp+120h+pExceptionObject]
0x18008000d  mov     rcx, [rdi+40h]
0x180080011  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x180080016  mov     rcx, [r14]
0x180080019  mov     [rsp+120h+var_E0], rcx
0x18008001e  mov     r8, [rax]
0x180080021  lea     rdx, [rsp+120h+var_E0]
0x180080026  mov     r13, [rsp+120h+var_D8]
0x18008002b  mov     rcx, r13
0x18008002e  call    ?reg_token@?$perl_syntax@G@regex@@QEAA?AW4TOKEN@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@5@@Z; regex::perl_syntax<ushort>::reg_token(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x180080033  cmp     eax, 2
0x180080036  jz      loc_1800804B5
0x18008003c  sub     esi, 4Ah ; 'J'
0x18008003f  jz      loc_180080466
0x180080045  sub     esi, 1
0x180080048  jz      loc_18008043D
0x18008004e  sub     esi, 1
0x180080051  jz      loc_180080404
0x180080057  sub     esi, 1
0x18008005a  jz      loc_1800803DB
0x180080060  sub     esi, 1
0x180080063  jz      loc_1800803A2
0x180080069  sub     esi, 1
0x18008006c  jz      loc_1800802DC
0x180080072  sub     esi, 1
0x180080075  jz      loc_180080253
0x18008007b  cmp     esi, 1
0x18008007e  jz      short loc_1800800B1
0x180080080  lea     rdx, aBadExtensionSe; "bad extension sequence"
0x180080087  lea     rcx, [rbp+4Fh+var_90]
0x18008008b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x180080090  nop
0x180080091  lea     rdx, [rbp+4Fh+var_90]
0x180080095  lea     rcx, [rsp+120h+pExceptionObject]
0x18008009a  call    ??0bad_regexpr@regex@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; regex::bad_regexpr::bad_regexpr(std::string const &)
0x18008009f  lea     rdx, _TI4?AVbad_regexpr@regex@@; pThrowInfo
0x1800800a6  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800800ab  call    _CxxThrowException_0
0x1800800b1  lea     rcx, [rdi+68h]
0x1800800b5  mov     rdx, r12
0x1800800b8  call    ?push_back@?$list@_KV?$allocator@_K@std@@@std@@QEAAXAEB_K@Z; std::list<unsigned __int64>::push_back(unsigned __int64 const &)
0x1800800bd  lea     rdx, [rsp+120h+pExceptionObject]
0x1800800c2  mov     rcx, [rdi+40h]
0x1800800c6  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1800800cb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800800cf  mov     rdx, [rax]
0x1800800d2  mov     rcx, r14
0x1800800d5  call    ??$parse_int@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@@detail@regex@@YA_KAEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V23@_K@Z; regex::detail::parse_int<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,unsigned __int64)
0x1800800da  test    rax, rax
0x1800800dd  jz      loc_180080177
0x1800800e3  lea     rdx, [rsp+120h+var_D8]
0x1800800e8  mov     rcx, [rdi+40h]
0x1800800ec  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1800800f1  mov     r8, [rax]
0x1800800f4  mov     rdx, r14
0x1800800f7  mov     rcx, r13
0x1800800fa  call    ?reg_token@?$perl_syntax@G@regex@@QEAA?AW4TOKEN@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@5@@Z; regex::perl_syntax<ushort>::reg_token(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x1800800ff  cmp     eax, 2
0x180080102  jnz     short loc_180080177
0x180080104  mov     r15, [r12]
0x180080108  lea     rax, [r15+1]
0x18008010c  mov     [r12], rax
0x180080110  lea     rsi, [rdi+8]
0x180080114  mov     [rsp+120h+pExceptionObject], rsi
0x180080119  mov     edx, 68h ; 'h'
0x18008011e  mov     rcx, rsi
0x180080121  call    ?allocate@?$arena_allocator@DV?$allocator@D@std@@@detail@regex@@QEAAPEAD_KPEBX@Z; regex::detail::arena_allocator<char,std::allocator<char>>::allocate(unsigned __int64,void const *)
0x180080126  mov     rbx, rax
0x180080129  mov     [rsp+120h+var_D8], rax
0x18008012e  test    rax, rax
0x180080131  jz      short loc_180080156
0x180080133  mov     r8, rsi
0x180080136  mov     rdx, r15
0x180080139  mov     rcx, rax
0x18008013c  call    ??0?$match_group@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@QEAA@_KAEAV?$arena_allocator@DV?$allocator@D@std@@@12@@Z; regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(unsigned __int64,regex::detail::arena_allocator<char,std::allocator<char>> &)
0x180080141  nop
0x180080142  lea     rax, ??_7?$match_conditional@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@U?$backref_condition@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@detail@regex@@6B@; const regex::detail::match_conditional<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,regex::detail::backref_condition<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::`vftable'
0x180080149  mov     [rbx], rax
0x18008014c  mov     qword ptr [rbx+60h], 1
0x180080154  jmp     short loc_180080158
0x180080156  xor     ebx, ebx
0x180080158  mov     [rsp+120h+var_E0], rbx
0x18008015d  lea     rdx, [rsp+120h+var_E0]
0x180080162  lea     rcx, [rsp+120h+var_E8]
0x180080167  call    ??4?$auto_ptr@V?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@QEAAAEAV01@AEAV01@@Z; std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::operator=(std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>> &)
0x18008016c  nop
0x18008016d  lea     rcx, [rsp+120h+var_E0]
0x180080172  jmp     loc_180080244
0x180080177  lea     rdx, [rsp+120h+pExceptionObject]
0x18008017c  mov     rcx, [rdi+40h]
0x180080180  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x180080185  mov     rcx, [r14]
0x180080188  mov     [rsp+120h+var_E0], rcx
0x18008018d  mov     r8, [rax]
0x180080190  lea     rdx, [rsp+120h+var_E0]
0x180080195  mov     rcx, r13
0x180080198  call    ?ext_token@?$perl_syntax@G@regex@@QEAA?AW4TOKEN@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@5@@Z; regex::perl_syntax<ushort>::ext_token(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x18008019d  sub     eax, 4Bh ; 'K'
0x1800801a0  jz      short loc_1800801E0
0x1800801a2  sub     eax, 1
0x1800801a5  jz      short loc_1800801E0
0x1800801a7  sub     eax, 1
0x1800801aa  jz      short loc_1800801E0
0x1800801ac  cmp     eax, 1
0x1800801af  jz      short loc_1800801E0
0x1800801b1  lea     rdx, aBadExtensionSe; "bad extension sequence"
0x1800801b8  lea     rcx, [rbp+4Fh+var_70]
0x1800801bc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x1800801c1  nop
0x1800801c2  lea     rdx, [rbp+4Fh+var_70]
0x1800801c6  lea     rcx, [rbp+4Fh+var_90]
0x1800801ca  call    ??0bad_regexpr@regex@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; regex::bad_regexpr::bad_regexpr(std::string const &)
0x1800801cf  lea     rdx, _TI4?AVbad_regexpr@regex@@; pThrowInfo
0x1800801d6  lea     rcx, [rbp+4Fh+var_90]; pExceptionObject
0x1800801da  call    _CxxThrowException_0
0x1800801e0  mov     rax, [rbp+4Fh+var_B8]
0x1800801e4  mov     [rsp+120h+var_100], rax
0x1800801e9  mov     r9, r13
0x1800801ec  xor     r8d, r8d
0x1800801ef  mov     rdx, r14
0x1800801f2  mov     rcx, rdi
0x1800801f5  call    ?_find_next_group@?$basic_rpattern_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$perl_syntax@G@regex@@@regex@@IEAAPEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@PEAV342@AEAV?$perl_syntax@G@2@AEAV?$vector@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@V?$allocator@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@@6@@Z; regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,regex::perl_syntax<ushort>>::_find_next_group(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,regex::perl_syntax<ushort> &,std::vector<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,std::allocator<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *>> &)
0x1800801fa  mov     [rsp+120h+var_D8], rax
0x1800801ff  mov     rcx, [r12]
0x180080203  lea     rdx, [rcx+1]
0x180080207  mov     [r12], rdx
0x18008020b  lea     r8, [rdi+8]
0x18008020f  mov     rdx, rax
0x180080212  call    ??$create_assertion_conditional@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@YAPEAV?$match_conditional@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@U?$assertion_condition@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@01@_KPEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@01@AEAV?$arena_allocator@DV?$allocator@D@std@@@01@@Z; regex::detail::create_assertion_conditional<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(unsigned __int64,regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,regex::detail::arena_allocator<char,std::allocator<char>> &)
0x180080217  mov     [rsp+120h+var_E0], rax
0x18008021c  lea     rdx, [rsp+120h+var_E0]
0x180080221  lea     rcx, [rsp+120h+var_E8]
0x180080226  call    ??4?$auto_ptr@V?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@QEAAAEAV01@AEAV01@@Z; std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::operator=(std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>> &)
0x18008022b  nop
0x18008022c  lea     rcx, [rsp+120h+var_E0]
0x180080231  call    ??1?$auto_ptr@V?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@QEAA@XZ; std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(void)
0x180080236  mov     [rsp+120h+var_D8], 0
0x18008023f  lea     rcx, [rsp+120h+var_D8]
0x180080244  call    ??1?$auto_ptr@V?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@QEAA@XZ; std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(void)
0x180080249  mov     [rsp+120h+var_F0], 1
0x18008024e  jmp     loc_180080535
0x180080253  lea     rdx, [rsp+120h+pExceptionObject]
0x180080258  mov     rcx, [rdi+40h]
0x18008025c  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x180080261  mov     r8, [rax]
0x180080264  mov     rdx, r14
0x180080267  mov     rcx, r13
0x18008026a  call    ?reg_token@?$perl_syntax@G@regex@@QEAA?AW4TOKEN@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@5@@Z; regex::perl_syntax<ushort>::reg_token(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x18008026f  cmp     eax, 2
0x180080272  jz      loc_1800806D4
0x180080278  test    eax, eax
0x18008027a  jnz     short loc_180080298
0x18008027c  mov     r9, [r14]
0x18008027f  lea     rdx, [rbp+4Fh+var_A0]
0x180080283  mov     rcx, [rdi+40h]
0x180080287  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18008028c  cmp     [rax], r9
0x18008028f  jz      short loc_180080298
0x180080291  lea     rax, [r9+2]
0x180080295  mov     [r14], rax
0x180080298  lea     rdx, [rbp+4Fh+var_A8]
0x18008029c  mov     rcx, [rdi+40h]
0x1800802a0  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1800802a5  mov     rcx, [r14]
0x1800802a8  cmp     [rax], rcx
0x1800802ab  jnz     short loc_180080253
0x1800802ad  lea     rdx, aExpectingEndOf; "Expecting end of comment"
0x1800802b4  lea     rcx, [rbp+4Fh+var_70]
0x1800802b8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x1800802bd  nop
0x1800802be  lea     rdx, [rbp+4Fh+var_70]
0x1800802c2  lea     rcx, [rbp+4Fh+var_90]
0x1800802c6  call    ??0bad_regexpr@regex@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; regex::bad_regexpr::bad_regexpr(std::string const &)
0x1800802cb  lea     rdx, _TI4?AVbad_regexpr@regex@@; pThrowInfo
0x1800802d2  lea     rcx, [rbp+4Fh+var_90]; pExceptionObject
0x1800802d6  call    _CxxThrowException_0
0x1800802dc  lea     rcx, [rdi+68h]
0x1800802e0  mov     rdx, r12
0x1800802e3  call    ?push_back@?$list@_KV?$allocator@_K@std@@@std@@QEAAXAEB_K@Z; std::list<unsigned __int64>::push_back(unsigned __int64 const &)
0x1800802e8  mov     edx, 78h ; 'x'
0x1800802ed  lea     rcx, [rdi+8]
0x1800802f1  call    ?allocate@?$arena_allocator@DV?$allocator@D@std@@@detail@regex@@QEAAPEAD_KPEBX@Z; regex::detail::arena_allocator<char,std::allocator<char>>::allocate(unsigned __int64,void const *)
0x1800802f6  mov     rbx, rax
0x1800802f9  mov     [rsp+120h+pExceptionObject], rax
0x1800802fe  test    rax, rax
0x180080301  jz      short loc_18008037C
0x180080303  mov     rdx, [r12]
0x180080307  lea     rcx, [rdx+1]
0x18008030b  mov     [r12], rcx
0x18008030f  lea     r8, [rdi+8]
0x180080313  mov     rcx, rax
0x180080316  call    ??0?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@QEAA@_KAEAV?$arena_allocator@DV?$allocator@D@std@@@12@@Z; regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(unsigned __int64,regex::detail::arena_allocator<char,std::allocator<char>> &)
0x18008031b  nop
0x18008031c  lea     rax, ??_7?$independent_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@6B@; const regex::detail::independent_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::`vftable'
0x180080323  mov     [rbx], rax
0x180080326  mov     byte ptr [rbx+48h], 1
0x18008032a  mov     qword ptr [rbx+50h], 0
0x180080332  mov     qword ptr [rbx+58h], 0
0x18008033a  lea     rax, ??_7?$independent_group@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@6B@; const regex::detail::independent_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::`vftable'
0x180080341  mov     [rbx], rax
0x180080344  lea     rax, [rbx+60h]
0x180080348  mov     [rsp+120h+var_D8], rax
0x18008034d  mov     [rax], r15
0x180080350  lea     rcx, ??_7?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@6B@; const regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::`vftable'
0x180080357  mov     [rax], rcx
0x18008035a  mov     qword ptr [rax+8], 0
0x180080362  lea     rcx, ??_7?$indestructable_sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@Vend_group@?$independent_group@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@detail@regex@@6B@; const regex::detail::indestructable_sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,regex::detail::independent_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::end_group>::`vftable'
0x180080369  mov     [rax], rcx
0x18008036c  lea     rcx, ??_7end_group@?$independent_group@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@6B@; const regex::detail::independent_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::end_group::`vftable'
0x180080373  mov     [rax], rcx
0x180080376  mov     [rax+10h], rbx
0x18008037a  jmp     short loc_18008037E
0x18008037c  xor     ebx, ebx
0x18008037e  mov     [rsp+120h+var_D8], rbx
0x180080383  lea     rdx, [rsp+120h+var_D8]
0x180080388  lea     rcx, [rsp+120h+var_E8]
0x18008038d  call    ??4?$auto_ptr@V?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@QEAAAEAV01@AEAV01@@Z; std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::operator=(std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>> &)
0x180080392  nop
  ... truncated ...
```
