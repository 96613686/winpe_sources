# regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,regex::perl_syntax<ushort>>::_find_next(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,regex::perl_syntax<ushort> &,std::vector<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,std::allocator<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *>> &)

- ea: `0x18007f4e4`
- end: `0x18007fec8`
- name: `?_find_next@?$basic_rpattern_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$perl_syntax@G@regex@@@regex@@IEAA_NAEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@2@AEAV?$perl_syntax@G@2@AEAV?$vector@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@V?$allocator@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@@4@@Z`
- size: `2532`
- prototype: `char __fastcall(__int64, __int64 *, __int64, int *, __int64)`
- caller_count: `1`
- callee_count: `39`
- tags: `broker_com_uri`

## callers

- `0x18007fed0`

## callees

- `0x18003ae80`
- `0x18003d2fc`
- `0x18003ed6c`
- `0x18003f190`
- `0x180064118`
- `0x180064178`
- `0x18007a054`
- `0x18007a210`
- `0x18007a2dc`
- `0x18007a398`
- `0x18007a4e0`
- `0x18007a5ac`
- `0x18007a704`
- `0x18007a7c0`
- `0x18007a8ac`
- `0x18007b3fc`
- `0x18007b8fc`
- `0x18007c398`
- `0x18007c3fc`
- `0x18007ccfc`
- `0x18007cd48`
- `0x18007d134`
- `0x18007d15c`
- `0x18007d8dc`
- `0x18007f4e4`
- `0x18007fed0`
- `0x180080710`
- `0x1800807ac`
- `0x18008083c`
- `0x1800808cc`
- `0x180080968`
- `0x1800809f8`
- `0x180080f7c`
- `0x180081238`
- `0x18008126c`
- `0x180081978`
- `0x18008199c`
- `0x180089f90`
- `0x18009e300`

## import_xrefs

- `msvcrt!towupper` at `0x18007f9d9`
- `msvcrt!towupper` at `0x18007f9d9`

## string_xrefs

- `0x18007f9eb`: `incomplete escape sequence \c`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
char __fastcall regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::perl_syntax<unsigned short>>::_find_next(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        int *a4,
        __int64 a5)
{
  __int64 v9; // r9
  int v11; // r15d
  _QWORD *v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  char v15; // r12
  __int64 v16; // rax
  int v17; // r9d
  char v18; // al
  __int64 v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  int v22; // ebx
  __int64 digit_charset; // rax
  _QWORD *v24; // rax
  unsigned __int16 *v25; // rbx
  wint_t v26; // r9
  int v27; // edx
  wint_t *v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rax
  wint_t v31; // cx
  _QWORD *v32; // rax
  unsigned __int64 v33; // rax
  wint_t v34; // r9
  __int16 v35; // r10
  __int16 v36; // r11
  __int64 v37; // rax
  unsigned __int16 *v38; // rbx
  wint_t v39; // r10
  __int16 v40; // ax
  __int16 v41; // r10
  __int16 v42; // r11
  __int64 v43; // r9
  unsigned __int16 **v44; // rax
  wint_t v45; // cx
  int v46; // r15d
  __int64 v47; // rax
  _QWORD *v48; // rax
  char v49; // cl
  wint_t *v50; // r15
  __int64 i; // rbx
  _QWORD *v52; // rax
  __int64 v53; // r9
  _QWORD *v54; // rax
  int v55; // eax
  _QWORD *v56; // rax
  _QWORD *v57; // rax
  __int64 v58; // r9
  _QWORD *v59; // rax
  _QWORD *v60; // rbx
  __int64 v61; // rdx
  _QWORD *v62; // rax
  __int64 v63; // rdx
  char v64; // [rsp+30h] [rbp-71h]
  __int64 v65; // [rsp+38h] [rbp-69h] BYREF
  __int64 v66; // [rsp+40h] [rbp-61h] BYREF
  _QWORD *next_group; // [rsp+48h] [rbp-59h] BYREF
  _QWORD *v68; // [rsp+50h] [rbp-51h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+58h] [rbp-49h] BYREF
  _QWORD v70[2]; // [rsp+70h] [rbp-31h] BYREF
  _BYTE v71[8]; // [rsp+80h] [rbp-21h] BYREF
  _QWORD v72[4]; // [rsp+88h] [rbp-19h] BYREF

  v70[1] = -2;
  v66 = a1;
  v65 = 0;
  v68 = 0;
  if ( *(_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &next_group) != *a2 )
  {
    v11 = *a4;
    v64 = v9;
    v12 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), v71);
    v13 = regex::perl_syntax<unsigned short>::reg_token(a4, a2, *v12);
    v15 = 1;
    if ( v13 <= 22 )
    {
      if ( v13 != 22 )
      {
        if ( v13 <= 6 )
        {
          if ( v13 == 6 )
          {
            v19 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 96);
            next_group = (_QWORD *)v19;
            if ( v19 )
              v19 = regex::detail::custom_charset::custom_charset(v19, a1 + 8);
            regex::detail::reset_auto_ptr<regex::detail::custom_charset,regex::detail::custom_charset>(&v68, v19);
            v20 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &v66);
            regex::detail::parse_charset<unsigned short,regex::detail::custom_charset,regex::perl_syntax<unsigned short>>(
              &v68,
              a2,
              *v20,
              a4);
            v21 = regex::detail::create_custom_charset<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                    v68,
                    *a4,
                    a1 + 8);
            regex::detail::reset_auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(
              &v65,
              v21);
            v68 = 0;
            goto LABEL_131;
          }
          if ( v13 )
          {
            if ( v13 == 1 )
            {
              next_group = (_QWORD *)regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::perl_syntax<unsigned short>>::_find_next_group(
                                       a1,
                                       (_DWORD)a2,
                                       a3,
                                       (_DWORD)a4,
                                       a5);
              std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::operator=(
                &v65,
                &next_group);
              std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(&next_group);
              v18 = 1;
              goto LABEL_132;
            }
            if ( v13 != 2 )
            {
              switch ( v13 )
              {
                case 3:
                  regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::end_alternate(a3);
                  regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::add_alternate(a3);
                  break;
                case 4:
                  v16 = regex::detail::create_bol<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                          *a4,
                          a1 + 8);
                  goto LABEL_129;
                case 5:
                  v16 = regex::detail::create_eol<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                          *a4,
                          a1 + 8);
LABEL_129:
                  v61 = v16;
LABEL_130:
                  regex::detail::reset_auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(
                    &v65,
                    v61);
                  goto LABEL_131;
              }
LABEL_134:
              std::auto_ptr<regex::detail::charset const>::~auto_ptr<regex::detail::charset const>(&v68);
              std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(&v65);
              return v15;
            }
            if ( !*(_QWORD *)(a3 + 32) )
            {
              std::string::string(v72, "mismatched parenthesis");
              regex::bad_regexpr::bad_regexpr(pExceptionObject, v72);
              throw (regex::bad_regexpr *)pExceptionObject;
            }
          }
          else
          {
            if ( *(_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &v66) != *a2 )
            {
              regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::perl_syntax<unsigned short>>::_find_atom(
                a1,
                a2,
                a3,
                a4);
              goto LABEL_134;
            }
            if ( *(_QWORD *)(a3 + 32) )
            {
              std::string::string(v72, "mismatched parenthesis");
              regex::bad_regexpr::bad_regexpr(pExceptionObject, v72);
              throw (regex::bad_regexpr *)pExceptionObject;
            }
          }
          v15 = 0;
          goto LABEL_134;
        }
        if ( v13 == 7 )
        {
          v66 = regex::detail::create_any<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                  *a4,
                  a1 + 8);
          std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::operator=(
            &v65,
            &v66);
          std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(&v66);
          goto LABEL_131;
        }
        if ( v13 != 8 )
        {
          switch ( v13 )
          {
            case 19:
              v22 = *a4;
              digit_charset = regex::detail::intrinsic_charsets<unsigned short>::_get_digit_charset();
              break;
            case 20:
              v22 = *a4;
              digit_charset = regex::detail::intrinsic_charsets<unsigned short>::_get_not_digit_charset();
              break;
            case 21:
              v22 = *a4;
              digit_charset = regex::detail::intrinsic_charsets<unsigned short>::_get_space_charset();
              break;
            default:
              goto LABEL_134;
          }
          goto LABEL_35;
        }
        v25 = (unsigned __int16 *)*a2;
        if ( *(unsigned __int16 **)std::wstring::end(*(_QWORD *)(a1 + 64), &v66) == v25 )
        {
          v27 = *a4;
          v28 = v25 - 1;
          *a2 = (__int64)(v25 - 1);
          v29 = a1 + 8;
          goto LABEL_40;
        }
        v31 = 9;
        if ( (unsigned __int16)(*v25 - 48) > 9u )
        {
          if ( *v25 != 101 )
          {
            if ( *v25 == 120 )
            {
              v38 = v25 + 1;
              *a2 = (__int64)v38;
              do
              {
                if ( *(unsigned __int16 **)std::wstring::end(*(_QWORD *)(a1 + 64), &v66) == v38 )
                  break;
                if ( !(unsigned __int8)regex::detail::regex_isxdigit<unsigned short>(*v38) )
                  break;
                v40 = regex::detail::regex_xdigit2int<unsigned short>(*v38);
                v39 = v40 + 16 * v41;
                v38 = (unsigned __int16 *)((char *)v38 + v43);
                *a2 = (__int64)v38;
              }
              while ( (unsigned __int16)(v42 + 1) < (unsigned __int16)v43 );
              v31 = v39;
              goto LABEL_51;
            }
            if ( *v25 == 99 )
            {
              v44 = (unsigned __int16 **)std::wstring::end(*(_QWORD *)(a1 + 64), &v66);
              *a2 = (__int64)(v25 + 1);
              if ( *v44 == v25 + 1 )
              {
                std::string::string(v72, "incomplete escape sequence \\c");
                regex::bad_regexpr::bad_regexpr(pExceptionObject, v72);
                throw (regex::bad_regexpr *)pExceptionObject;
              }
              *a2 = (__int64)(v25 + 2);
              v45 = v25[1];
              if ( (unsigned __int16)(v45 - 97) <= 0x19u )
                v45 = towupper(v45);
              v31 = v45 ^ 0x40;
              goto LABEL_51;
            }
            v46 = v11 & 0x100;
            switch ( *v25 )
            {
              case 'a':
                if ( v46 )
                {
                  *a2 = (__int64)(v25 + 1);
                  v31 = v26;
                  goto LABEL_51;
                }
                break;
              case 'f':
                if ( v46 )
                {
                  *a2 = (__int64)(v25 + 1);
                  v31 = 12;
                  goto LABEL_51;
                }
                break;
              case 'n':
                if ( v46 )
                {
                  *a2 = (__int64)(v25 + 1);
                  v31 = 10;
                  goto LABEL_51;
                }
                break;
              case 'r':
                if ( v46 )
                {
                  *a2 = (__int64)(v25 + 1);
                  v31 = 13;
                  goto LABEL_51;
                }
                break;
              default:
                if ( *v25 == 116 || (v31 = 92, *v25 == 92) )
                {
                  if ( v46 )
                  {
                    *a2 = (__int64)(v25 + 1);
                    goto LABEL_51;
                  }
                }
                break;
            }
            v47 = regex::detail::get_altern_charset<unsigned short,regex::perl_syntax<unsigned short>>(*v25, a4);
            v29 = a1 + 8;
            v27 = *a4;
            if ( v47 )
            {
              v48 = regex::detail::create_charset<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                      v47,
                      v27,
                      v29);
              regex::detail::reset_auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(
                &v65,
                v48);
              goto LABEL_41;
            }
            v28 = (wint_t *)*a2;
LABEL_40:
            v30 = regex::detail::create_char<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                    *v28,
                    v27,
                    v29);
            regex::detail::reset_auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(
              &v65,
              v30);
LABEL_41:
            v17 = 2;
            *a2 += 2;
            goto LABEL_131;
          }
          *a2 = (__int64)(v25 + 1);
          v31 = 27;
        }
        else
        {
          v32 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &next_group);
          v66 = (__int64)v25;
          v33 = regex::detail::parse_int<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                  &v66,
                  *v32,
                  999);
          if ( *v25 != 48 && (v33 < 0xA || v33 < *(_QWORD *)(a1 + 24)) )
          {
            next_group = regex::detail::create_backref<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                           v33,
                           *a4,
                           a1 + 8);
            std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::operator=(
              &v65,
              &next_group);
            std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(&next_group);
            *a2 = v66;
            goto LABEL_131;
          }
          do
          {
            if ( *(unsigned __int16 **)std::wstring::end(*(_QWORD *)(a1 + 64), &v66) == v25 )
              break;
            if ( (unsigned __int16)(*v25 - v36) > 7u )
              break;
            v34 = *v25++ + 8 * v34 - v36;
            *a2 = (__int64)v25;
          }
          while ( (unsigned __int16)(v35 + 1) < 3u );
          v31 = v34;
        }
LABEL_51:
        v37 = regex::detail::create_char<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                v31,
                *a4,
                a1 + 8);
        regex::detail::reset_auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(
          &v65,
          v37);
        goto LABEL_131;
      }
      v22 = *a4;
      digit_charset = regex::detail::intrinsic_charsets<unsigned short>::_get_not_space_charset(22);
LABEL_35:
      v24 = regex::detail::create_charset<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
              digit_charset,
              v22,
              a1 + 8);
      regex::detail::reset_auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(
        &v65,
        v24);
LABEL_131:
      v18 = v64;
LABEL_132:
      if ( v65 )
      {
        LOBYTE(v17) = v18;
        regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::perl_syntax<unsigned short>>::_quantify(
          a1,
          (unsigned int)&v65,
          (_DWORD)a2,
          v17,
          (__int64)a4);
        v63 = v65;
        v65 = 0;
        **(_QWORD **)(a3 + 56) = v63;
        *(_QWORD *)(a3 + 56) = v63 + 8;
      }
      goto LABEL_134;
    }
    if ( v13 > 28 )
    {
      if ( v13 != 29 )
      {
        switch ( v13 )
        {
          case 30:
            v70[0] = a1 + 8;
            v62 = (_QWORD *)regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 24);
            v60 = v62;
            v66 = (__int64)v62;
            if ( v62 )
            {
              *v62 = &NaturalLanguage6::IKeyValuePair::`vftable';
              *v62 = &regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
              v62[1] = 0;
              *v62 = &regex::detail::assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
              *v62 = &regex::detail::word_assertion_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::detail::word_start>::`vftable';
              v62[2] = regex::detail::intrinsic_charsets<unsigned short>::_get_word_charset(&regex::detail::assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable');
            }
            else
            {
              v60 = 0;
            }
            break;
          case 31:
            v70[0] = a1 + 8;
            v59 = (_QWORD *)regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 24);
            v60 = v59;
            v66 = (__int64)v59;
            if ( v59 )
            {
              *v59 = &NaturalLanguage6::IKeyValuePair::`vftable';
              *v59 = &regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
              v59[1] = 0;
              *v59 = &regex::detail::assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
              *v59 = &regex::detail::word_assertion_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::detail::word_stop>::`vftable';
              v59[2] = regex::detail::intrinsic_charsets<unsigned short>::_get_word_charset(&regex::detail::assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable');
            }
            else
            {
              v60 = 0;
            }
            break;
          case 32:
            v50 = (wint_t *)*a2;
            for ( i = *a2; ; i = *a2 )
            {
              v52 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &v66);
              if ( *v52 == v53 )
                break;
              v54 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), &next_group);
              v55 = regex::perl_syntax<unsigned short>::reg_token(a4, a2, *v54);
              if ( v55 )
              {
                if ( v55 == 33 )
                  break;
              }
              else
              {
                v57 = (_QWORD *)std::wstring::end(*(_QWORD *)(a1 + 64), v70);
                if ( *v57 != v58 )
                  *a2 = v58 + 2;
              }
            }
            if ( (wint_t *)i != v50 )
            {
              v56 = regex::detail::create_literal<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                      v50,
                      i,
                      *a4,
                      a1 + 8);
              **(_QWORD **)(a3 + 56) = v56;
              *(_QWORD *)(a3 + 56) = v56 + 1;
            }
            break;
          case 33:
            std::string::string(v72, "quotemeta turned off, but was never turned on");
            regex::bad_regexpr::bad_regexpr(pExceptionObject, v72);
            throw (regex::bad_regexpr *)pExceptionObject;
          default:
            goto LABEL_134;
        }
        v61 = (__int64)v60;
        goto LABEL_130;
      }
      v49 = 0;
    }
    else
    {
      if ( v13 != 28 )
      {
        if ( v13 == 23 )
        {
          v22 = *a4;
          digit_charset = regex::detail::intrinsic_charsets<unsigned short>::_get_word_charset((unsigned int)(v13 - 23));
        }
        else
        {
          if ( v13 != 24 )
          {
            if ( v13 == 25 )
            {
              v66 = a1 + 8;
              v16 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 16);
              next_group = (_QWORD *)v16;
              if ( v16 )
              {
                *(_OWORD *)v16 = 0;
                *(_QWORD *)v16 = &NaturalLanguage6::IKeyValuePair::`vftable';
                *(_QWORD *)v16 = &regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
                *(_QWORD *)(v16 + 8) = 0;
                *(_QWORD *)v16 = &regex::detail::assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
                *(_QWORD *)v16 = &regex::detail::assert_op<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::detail::opwrap<regex::detail::bos_t<regex::detail::bool2type<0>>,regex::detail::bos_t<regex::detail::bool2type<1>>>>::`vftable';
              }
            }
            else if ( v13 == 26 )
            {
              v66 = a1 + 8;
              v16 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 16);
              next_group = (_QWORD *)v16;
              if ( v16 )
              {
                *(_OWORD *)v16 = 0;
                *(_QWORD *)v16 = &NaturalLanguage6::IKeyValuePair::`vftable';
                *(_QWORD *)v16 = &regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
                *(_QWORD *)(v16 + 8) = 0;
                *(_QWORD *)v16 = &regex::detail::assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
                *(_QWORD *)v16 = &regex::detail::assert_op<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::detail::opwrap<regex::detail::peos_t<regex::detail::bool2type<0>>,regex::detail::peos_t<regex::detail::bool2type<1>>>>::`vftable';
              }
            }
            else
            {
              v66 = a1 + 8;
              v16 = regex::detail::arena_allocator<char,std::allocator<char>>::allocate(a1 + 8, 16);
              next_group = (_QWORD *)v16;
              if ( v16 )
              {
                *(_OWORD *)v16 = 0;
                *(_QWORD *)v16 = &NaturalLanguage6::IKeyValuePair::`vftable';
                *(_QWORD *)v16 = &regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
                *(_QWORD *)(v16 + 8) = 0;
                *(_QWORD *)v16 = &regex::detail::assertion<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::`vftable';
                *(_QWORD *)v16 = &regex::detail::assert_op<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,regex::detail::opwrap<regex::detail::eos_t<regex::detail::bool2type<0>>,regex::detail::eos_t<regex::detail::bool2type<1>>>>::`vftable';
              }
            }
            goto LABEL_129;
          }
          v22 = *a4;
          digit_charset = regex::detail::intrinsic_charsets<unsigned short>::_get_not_word_charset();
        }
        goto LABEL_35;
      }
      v49 = 1;
    }
    v16 = (__int64)regex::detail::create_word_boundary<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                     v49,
                     v14,
                     a1 + 8);
    goto LABEL_129;
  }
  if ( *(_QWORD *)(a3 + 32) != v9 )
  {
    std::string::string(v72, "mismatched parenthesis");
    regex::bad_regexpr::bad_regexpr(pExceptionObject, v72);
    throw (regex::bad_regexpr *)pExceptionObject;
  }
  std::auto_ptr<regex::detail::charset const>::~auto_ptr<regex::detail::charset const>(&v68);
  std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(&v65);
  return 0;
}

```

## disassembly

```asm
0x18007f4e4  push    rbp
0x18007f4e6  push    rbx
0x18007f4e7  push    rsi
0x18007f4e8  push    rdi
0x18007f4e9  push    r12
0x18007f4eb  push    r13
0x18007f4ed  push    r14
0x18007f4ef  push    r15
0x18007f4f1  lea     rbp, [rsp-17h]
0x18007f4f6  sub     rsp, 0B8h
0x18007f4fd  mov     [rbp+4Fh+var_78], 0FFFFFFFFFFFFFFFEh
0x18007f505  mov     rax, cs:__security_cookie
0x18007f50c  xor     rax, rsp
0x18007f50f  mov     [rbp+4Fh+var_48], rax
0x18007f513  mov     r14, r9
0x18007f516  mov     r13, r8
0x18007f519  mov     rsi, rdx
0x18007f51c  mov     rdi, rcx
0x18007f51f  mov     [rbp+4Fh+var_B0], rcx
0x18007f523  mov     rbx, [rbp+4Fh+arg_20]
0x18007f527  xor     r9d, r9d
0x18007f52a  mov     [rbp+4Fh+var_B8], r9
0x18007f52e  mov     [rbp+4Fh+var_A0], r9
0x18007f532  lea     rdx, [rbp+4Fh+var_A8]
0x18007f536  mov     rcx, [rcx+40h]
0x18007f53a  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007f53f  mov     rcx, [rsi]
0x18007f542  cmp     [rax], rcx
0x18007f545  jnz     short loc_18007F596
0x18007f547  cmp     [r13+20h], r9
0x18007f54b  jz      short loc_18007F57C
0x18007f54d  lea     rdx, aMismatchedPare; "mismatched parenthesis"
0x18007f554  lea     rcx, [rbp+4Fh+var_68]
0x18007f558  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18007f55d  nop
0x18007f55e  lea     rdx, [rbp+4Fh+var_68]
0x18007f562  lea     rcx, [rbp+4Fh+pExceptionObject]
0x18007f566  call    ??0bad_regexpr@regex@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; regex::bad_regexpr::bad_regexpr(std::string const &)
0x18007f56b  lea     rdx, _TI4?AVbad_regexpr@regex@@; pThrowInfo
0x18007f572  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18007f576  call    _CxxThrowException_0
0x18007f57c  lea     rcx, [rbp+4Fh+var_A0]
0x18007f580  call    ??1?$auto_ptr@$$CBUcharset@detail@regex@@@std@@QEAA@XZ; std::auto_ptr<regex::detail::charset const>::~auto_ptr<regex::detail::charset const>(void)
0x18007f585  nop
0x18007f586  lea     rcx, [rbp+4Fh+var_B8]
0x18007f58a  call    ??1?$auto_ptr@V?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@QEAA@XZ; std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(void)
0x18007f58f  xor     al, al
0x18007f591  jmp     loc_18007FEA8
0x18007f596  mov     r15d, [r14]
0x18007f599  mov     [rbp+4Fh+var_C0], r9b
0x18007f59d  lea     rdx, [rbp+4Fh+var_70]
0x18007f5a1  mov     rcx, [rdi+40h]
0x18007f5a5  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007f5aa  mov     r8, [rax]
0x18007f5ad  mov     rdx, rsi
0x18007f5b0  mov     rcx, r14
0x18007f5b3  call    ?reg_token@?$perl_syntax@G@regex@@QEAA?AW4TOKEN@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@5@@Z; regex::perl_syntax<ushort>::reg_token(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x18007f5b8  mov     ecx, eax
0x18007f5ba  mov     r12w, 1
0x18007f5bf  cmp     eax, 16h
0x18007f5c2  jg      loc_18007FB39
0x18007f5c8  jz      loc_18007FB2C
0x18007f5ce  cmp     eax, 6
0x18007f5d1  jg      loc_18007F792
0x18007f5d7  jz      loc_18007F719
0x18007f5dd  test    eax, eax
0x18007f5df  jz      loc_18007F6B0
0x18007f5e5  sub     ecx, 1
0x18007f5e8  jz      loc_18007F677
0x18007f5ee  sub     ecx, 1
0x18007f5f1  jz      short loc_18007F63D
0x18007f5f3  sub     ecx, 1
0x18007f5f6  jz      short loc_18007F628
0x18007f5f8  sub     ecx, 1
0x18007f5fb  jz      short loc_18007F617
0x18007f5fd  cmp     ecx, 1
0x18007f600  jnz     loc_18007FE92
0x18007f606  lea     rdx, [rdi+8]
0x18007f60a  mov     ecx, [r14]
0x18007f60d  call    ??$create_eol@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@YAPEAV?$assertion@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@01@W4REGEX_FLAGS@1@AEAV?$arena_allocator@DV?$allocator@D@std@@@01@@Z; regex::detail::create_eol<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(regex::REGEX_FLAGS,regex::detail::arena_allocator<char,std::allocator<char>> &)
0x18007f612  jmp     loc_18007FE4A
0x18007f617  lea     rdx, [rdi+8]
0x18007f61b  mov     ecx, [r14]
0x18007f61e  call    ??$create_bol@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@YAPEAV?$assertion@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@01@W4REGEX_FLAGS@1@AEAV?$arena_allocator@DV?$allocator@D@std@@@01@@Z; regex::detail::create_bol<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(regex::REGEX_FLAGS,regex::detail::arena_allocator<char,std::allocator<char>> &)
0x18007f623  jmp     loc_18007FE4A
0x18007f628  mov     rcx, r13
0x18007f62b  call    ?end_alternate@?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@QEAAXXZ; regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::end_alternate(void)
0x18007f630  mov     rcx, r13
0x18007f633  call    ?add_alternate@?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@QEAAXXZ; regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::add_alternate(void)
0x18007f638  jmp     loc_18007FE92
0x18007f63d  cmp     qword ptr [r13+20h], 0
0x18007f642  jnz     loc_18007F6FB
0x18007f648  lea     rdx, aMismatchedPare; "mismatched parenthesis"
0x18007f64f  lea     rcx, [rbp+4Fh+var_68]
0x18007f653  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18007f658  nop
0x18007f659  lea     rdx, [rbp+4Fh+var_68]
0x18007f65d  lea     rcx, [rbp+4Fh+pExceptionObject]
0x18007f661  call    ??0bad_regexpr@regex@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; regex::bad_regexpr::bad_regexpr(std::string const &)
0x18007f666  lea     rdx, _TI4?AVbad_regexpr@regex@@; pThrowInfo
0x18007f66d  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18007f671  call    _CxxThrowException_0
0x18007f677  mov     [rsp+0F0h+var_D0], rbx
0x18007f67c  mov     r9, r14
0x18007f67f  mov     r8, r13
0x18007f682  mov     rdx, rsi
0x18007f685  mov     rcx, rdi
0x18007f688  call    ?_find_next_group@?$basic_rpattern_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$perl_syntax@G@regex@@@regex@@IEAAPEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@2@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@PEAV342@AEAV?$perl_syntax@G@2@AEAV?$vector@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@V?$allocator@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@@6@@Z; regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,regex::perl_syntax<ushort>>::_find_next_group(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,regex::perl_syntax<ushort> &,std::vector<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,std::allocator<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *>> &)
0x18007f68d  mov     [rbp+4Fh+var_A8], rax
0x18007f691  lea     rdx, [rbp+4Fh+var_A8]
0x18007f695  lea     rcx, [rbp+4Fh+var_B8]
0x18007f699  call    ??4?$auto_ptr@V?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@QEAAAEAV01@AEAV01@@Z; std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::operator=(std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>> &)
0x18007f69e  nop
0x18007f69f  lea     rcx, [rbp+4Fh+var_A8]
0x18007f6a3  call    ??1?$auto_ptr@V?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@QEAA@XZ; std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(void)
0x18007f6a8  mov     al, r12b
0x18007f6ab  jmp     loc_18007FE59
0x18007f6b0  lea     rdx, [rbp+4Fh+var_B0]
0x18007f6b4  mov     rcx, [rdi+40h]
0x18007f6b8  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007f6bd  mov     rcx, [rsi]
0x18007f6c0  cmp     [rax], rcx
0x18007f6c3  jnz     short loc_18007F703
0x18007f6c5  cmp     qword ptr [r13+20h], 0
0x18007f6ca  jz      short loc_18007F6FB
0x18007f6cc  lea     rdx, aMismatchedPare; "mismatched parenthesis"
0x18007f6d3  lea     rcx, [rbp+4Fh+var_68]
0x18007f6d7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18007f6dc  nop
0x18007f6dd  lea     rdx, [rbp+4Fh+var_68]
0x18007f6e1  lea     rcx, [rbp+4Fh+pExceptionObject]
0x18007f6e5  call    ??0bad_regexpr@regex@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; regex::bad_regexpr::bad_regexpr(std::string const &)
0x18007f6ea  lea     rdx, _TI4?AVbad_regexpr@regex@@; pThrowInfo
0x18007f6f1  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18007f6f5  call    _CxxThrowException_0
0x18007f6fb  xor     r12b, r12b
0x18007f6fe  jmp     loc_18007FE92
0x18007f703  mov     r9, r14
0x18007f706  mov     r8, r13
0x18007f709  mov     rdx, rsi
0x18007f70c  mov     rcx, rdi
0x18007f70f  call    ?_find_atom@?$basic_rpattern_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$perl_syntax@G@regex@@@regex@@IEAAXAEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@PEAV?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@2@AEAV?$perl_syntax@G@2@@Z; regex::basic_rpattern_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,regex::perl_syntax<ushort>>::_find_atom(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,regex::perl_syntax<ushort> &)
0x18007f714  jmp     loc_18007FE92
0x18007f719  lea     rbx, [rdi+8]
0x18007f71d  mov     edx, 60h ; '`'
0x18007f722  mov     rcx, rbx
0x18007f725  call    ?allocate@?$arena_allocator@DV?$allocator@D@std@@@detail@regex@@QEAAPEAD_KPEBX@Z; regex::detail::arena_allocator<char,std::allocator<char>>::allocate(unsigned __int64,void const *)
0x18007f72a  mov     [rbp+4Fh+var_A8], rax
0x18007f72e  test    rax, rax
0x18007f731  jz      short loc_18007F73F
0x18007f733  mov     rdx, rbx
0x18007f736  mov     rcx, rax
0x18007f739  call    ??0custom_charset@detail@regex@@QEAA@AEAV?$arena_allocator@DV?$allocator@D@std@@@12@@Z; regex::detail::custom_charset::custom_charset(regex::detail::arena_allocator<char,std::allocator<char>> &)
0x18007f73e  nop
0x18007f73f  mov     rdx, rax
0x18007f742  lea     rcx, [rbp+4Fh+var_A0]
0x18007f746  call    ??$reset_auto_ptr@Ucustom_charset@detail@regex@@U123@@detail@regex@@YAXAEAV?$auto_ptr@Ucustom_charset@detail@regex@@@std@@PEAUcustom_charset@01@@Z; regex::detail::reset_auto_ptr<regex::detail::custom_charset,regex::detail::custom_charset>(std::auto_ptr<regex::detail::custom_charset> &,regex::detail::custom_charset *)
0x18007f74b  lea     rdx, [rbp+4Fh+var_B0]
0x18007f74f  mov     rcx, [rdi+40h]
0x18007f753  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007f758  mov     r9, r14
0x18007f75b  mov     r8, [rax]
0x18007f75e  mov     rdx, rsi
0x18007f761  lea     rcx, [rbp+4Fh+var_A0]
0x18007f765  call    ??$parse_charset@GUcustom_charset@detail@regex@@V?$perl_syntax@G@3@@detail@regex@@YAXAEAV?$auto_ptr@Ucustom_charset@detail@regex@@@std@@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@3@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@3@AEAV?$perl_syntax@G@1@@Z; regex::detail::parse_charset<ushort,regex::detail::custom_charset,regex::perl_syntax<ushort>>(std::auto_ptr<regex::detail::custom_charset> &,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,regex::perl_syntax<ushort> &)
0x18007f76a  mov     r8, rbx
0x18007f76d  mov     edx, [r14]
0x18007f770  mov     rcx, [rbp+4Fh+var_A0]
0x18007f774  call    ??$create_custom_charset@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@YAPEAV?$match_charset@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@01@PEBUcustom_charset@01@W4REGEX_FLAGS@1@AEAV?$arena_allocator@DV?$allocator@D@std@@@01@@Z; regex::detail::create_custom_charset<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(regex::detail::custom_charset const *,regex::REGEX_FLAGS,regex::detail::arena_allocator<char,std::allocator<char>> &)
0x18007f779  mov     rdx, rax
0x18007f77c  lea     rcx, [rbp+4Fh+var_B8]
0x18007f780  call    ??$reset_auto_ptr@V?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@V?$match_group@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@23@@detail@regex@@YAXAEAV?$auto_ptr@V?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@PEAV?$match_group@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@01@@Z; regex::detail::reset_auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(std::auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>> &,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *)
0x18007f785  mov     [rbp+4Fh+var_A0], 0
0x18007f78d  jmp     loc_18007FE56
0x18007f792  mov     r9d, 7
0x18007f798  sub     ecx, r9d
0x18007f79b  jz      loc_18007FB00
0x18007f7a1  sub     ecx, 1
0x18007f7a4  jz      short loc_18007F7F4
0x18007f7a6  sub     ecx, 0Bh
0x18007f7a9  jz      short loc_18007F7EA
0x18007f7ab  sub     ecx, 1
0x18007f7ae  jz      short loc_18007F7E0
0x18007f7b0  cmp     ecx, 1
0x18007f7b3  jnz     loc_18007FE92
0x18007f7b9  mov     ebx, [r14]
0x18007f7bc  call    ?_get_space_charset@?$intrinsic_charsets@G@detail@regex@@CAAEAUintrinsic_charset@123@XZ; regex::detail::intrinsic_charsets<ushort>::_get_space_charset(void)
0x18007f7c1  lea     r8, [rdi+8]
0x18007f7c5  mov     edx, ebx
0x18007f7c7  mov     rcx, rax
0x18007f7ca  call    ??$create_charset@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@YAPEAV?$match_charset@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@01@AEBUcharset@01@W4REGEX_FLAGS@1@AEAV?$arena_allocator@DV?$allocator@D@std@@@01@@Z; regex::detail::create_charset<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(regex::detail::charset const &,regex::REGEX_FLAGS,regex::detail::arena_allocator<char,std::allocator<char>> &)
0x18007f7cf  mov     rdx, rax
0x18007f7d2  lea     rcx, [rbp+4Fh+var_B8]
0x18007f7d6  call    ??$reset_auto_ptr@V?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@V?$match_group@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@23@@detail@regex@@YAXAEAV?$auto_ptr@V?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@PEAV?$match_group@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@01@@Z; regex::detail::reset_auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(std::auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>> &,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *)
0x18007f7db  jmp     loc_18007FE56
0x18007f7e0  mov     ebx, [r14]
0x18007f7e3  call    ?_get_not_digit_charset@?$intrinsic_charsets@G@detail@regex@@CAAEAUintrinsic_charset@123@XZ; regex::detail::intrinsic_charsets<ushort>::_get_not_digit_charset(void)
0x18007f7e8  jmp     short loc_18007F7C1
0x18007f7ea  mov     ebx, [r14]
0x18007f7ed  call    ?_get_digit_charset@?$intrinsic_charsets@G@detail@regex@@CAAEAUintrinsic_charset@123@XZ; regex::detail::intrinsic_charsets<ushort>::_get_digit_charset(void)
0x18007f7f2  jmp     short loc_18007F7C1
0x18007f7f4  mov     rbx, [rsi]
0x18007f7f7  lea     rdx, [rbp+4Fh+var_B0]
0x18007f7fb  mov     rcx, [rdi+40h]
0x18007f7ff  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007f804  cmp     [rax], rbx
0x18007f807  jnz     short loc_18007F839
0x18007f809  mov     edx, [r14]
0x18007f80c  lea     rcx, [rbx-2]
0x18007f810  mov     [rsi], rcx
0x18007f813  lea     r8, [rdi+8]
0x18007f817  movzx   ecx, word ptr [rcx]
0x18007f81a  call    ??$create_char@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@YAPEAV?$match_char@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@01@GW4REGEX_FLAGS@1@AEAV?$arena_allocator@DV?$allocator@D@std@@@01@@Z; regex::detail::create_char<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(ushort,regex::REGEX_FLAGS,regex::detail::arena_allocator<char,std::allocator<char>> &)
0x18007f81f  mov     rdx, rax
0x18007f822  lea     rcx, [rbp+4Fh+var_B8]
0x18007f826  call    ??$reset_auto_ptr@V?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@V?$match_group@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@23@@detail@regex@@YAXAEAV?$auto_ptr@V?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@PEAV?$match_group@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@01@@Z; regex::detail::reset_auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(std::auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>> &,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *)
0x18007f82b  mov     r9d, 2
0x18007f831  add     [rsi], r9
0x18007f834  jmp     loc_18007FE56
0x18007f839  movzx   eax, word ptr [rbx]
0x18007f83c  sub     ax, 30h ; '0'
0x18007f840  mov     ecx, 9
0x18007f845  cmp     ax, cx
0x18007f848  ja      loc_18007F928
0x18007f84e  lea     rdx, [rbp+4Fh+var_A8]
0x18007f852  mov     rcx, [rdi+40h]
0x18007f856  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007f85b  mov     [rbp+4Fh+var_B0], rbx
0x18007f85f  mov     r8d, 3E7h
0x18007f865  mov     rdx, [rax]
0x18007f868  lea     rcx, [rbp+4Fh+var_B0]
0x18007f86c  call    ??$parse_int@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@@detail@regex@@YA_KAEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V23@_K@Z; regex::detail::parse_int<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,unsigned __int64)
0x18007f871  mov     r11d, 30h ; '0'
0x18007f877  cmp     r11w, [rbx]
0x18007f87b  jz      short loc_18007F8BF
0x18007f87d  cmp     rax, 0Ah
0x18007f881  jb      short loc_18007F889
0x18007f883  cmp     rax, [rdi+18h]
0x18007f887  jnb     short loc_18007F8BF
0x18007f889  lea     r8, [rdi+8]
0x18007f88d  mov     edx, [r14]
0x18007f890  mov     rcx, rax
0x18007f893  call    ??$create_backref@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@YAPEAV?$match_backref@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@01@_KW4REGEX_FLAGS@1@AEAV?$arena_allocator@DV?$allocator@D@std@@@01@@Z; regex::detail::create_backref<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(unsigned __int64,regex::REGEX_FLAGS,regex::detail::arena_allocator<char,std::allocator<char>> &)
0x18007f898  mov     [rbp+4Fh+var_A8], rax
0x18007f89c  lea     rdx, [rbp+4Fh+var_A8]
0x18007f8a0  lea     rcx, [rbp+4Fh+var_B8]
0x18007f8a4  call    ??4?$auto_ptr@V?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@QEAAAEAV01@AEAV01@@Z; std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::operator=(std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>> &)
0x18007f8a9  nop
0x18007f8aa  lea     rcx, [rbp+4Fh+var_A8]
0x18007f8ae  call    ??1?$auto_ptr@V?$sub_expr@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@QEAA@XZ; std::auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::~auto_ptr<regex::detail::sub_expr<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(void)
0x18007f8b3  mov     rax, [rbp+4Fh+var_B0]
0x18007f8b7  mov     [rsi], rax
0x18007f8ba  jmp     loc_18007FE56
0x18007f8bf  xor     r9d, r9d
0x18007f8c2  xor     r10d, r10d
0x18007f8c5  lea     r15d, [r9+7]
0x18007f8c9  lea     rdx, [rbp+4Fh+var_B0]
0x18007f8cd  mov     rcx, [rdi+40h]
0x18007f8d1  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007f8d6  cmp     [rax], rbx
0x18007f8d9  jz      short loc_18007F907
0x18007f8db  movzx   eax, word ptr [rbx]
0x18007f8de  sub     ax, r11w
0x18007f8e2  cmp     ax, r15w
0x18007f8e6  ja      short loc_18007F907
0x18007f8e8  shl     r9w, 3
0x18007f8ed  add     r9w, [rbx]
0x18007f8f1  sub     r9w, r11w
0x18007f8f5  add     r10w, r12w
0x18007f8f9  add     rbx, 2
0x18007f8fd  mov     [rsi], rbx
0x18007f900  cmp     r10w, 3
0x18007f905  jb      short loc_18007F8C9
0x18007f907  movzx   ecx, r9w
0x18007f90b  lea     r8, [rdi+8]
0x18007f90f  mov     edx, [r14]
0x18007f912  call    ??$create_char@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@YAPEAV?$match_char@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@01@GW4REGEX_FLAGS@1@AEAV?$arena_allocator@DV?$allocator@D@std@@@01@@Z; regex::detail::create_char<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(ushort,regex::REGEX_FLAGS,regex::detail::arena_allocator<char,std::allocator<char>> &)
0x18007f917  mov     rdx, rax
0x18007f91a  lea     rcx, [rbp+4Fh+var_B8]
0x18007f91e  call    ??$reset_auto_ptr@V?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@V?$match_group@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@23@@detail@regex@@YAXAEAV?$auto_ptr@V?$match_group_base@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@@std@@PEAV?$match_group@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@01@@Z; regex::detail::reset_auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(std::auto_ptr<regex::detail::match_group_base<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>> &,regex::detail::match_group<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *)
0x18007f923  jmp     loc_18007FE56
0x18007f928  mov     eax, 65h ; 'e'
0x18007f92d  cmp     ax, [rbx]
0x18007f930  jnz     short loc_18007F940
0x18007f932  lea     rax, [rbx+2]
0x18007f936  mov     [rsi], rax
0x18007f939  mov     ecx, 1Bh
0x18007f93e  jmp     short loc_18007F90B
0x18007f940  mov     eax, 78h ; 'x'
0x18007f945  cmp     ax, [rbx]
0x18007f948  jnz     short loc_18007F9A3
0x18007f94a  xor     r10d, r10d
0x18007f94d  xor     r11d, r11d
0x18007f950  add     rbx, 2
0x18007f954  mov     [rsi], rbx
0x18007f957  lea     r9d, [rax-76h]
0x18007f95b  lea     rdx, [rbp+4Fh+var_B0]
0x18007f95f  mov     rcx, [rdi+40h]
0x18007f963  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18007f968  cmp     [rax], rbx
  ... truncated ...
```
