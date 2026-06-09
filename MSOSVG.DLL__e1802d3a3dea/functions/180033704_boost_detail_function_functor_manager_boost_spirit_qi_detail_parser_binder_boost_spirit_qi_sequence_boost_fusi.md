# boost::detail::function::functor_manager<boost::spirit::qi::detail::parser_binder<boost::spirit::qi::sequence<boost::fusion::cons<boost::spirit::qi::no_case_literal_string<char const (&)[5],1>,boost::fusion::cons<boost::spirit::qi::reference<boost::spirit::qi::rule<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,boost::iterator_range<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>> (void),boost::spirit::unused_type,boost::spirit::unused_type,boost::spirit::unused_type> const>,boost::fusion::cons<boost::spirit::qi::literal_char<boost::spirit::char_encoding::standard,1,0>,boost::fusion::nil_>>>>,boost::mpl::bool_<0>>>::manager(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type,boost::detail::function::function_obj_tag)

- ea: `0x180033704`
- end: `0x1800337fc`
- name: `?manager@?$functor_manager@U?$parser_binder@U?$sequence@U?$cons@U?$no_case_literal_string@AEAY04$$CBD$00@qi@spirit@boost@@U?$cons@U?$reference@$$CBU?$rule@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@$$A6A?AV?$iterator_range@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@@boost@@XZUunused_type@spirit@4@U564@U564@@qi@spirit@boost@@@qi@spirit@boost@@U?$cons@U?$literal_char@Ustandard@char_encoding@spirit@boost@@$00$0A@@qi@spirit@boost@@Unil_@fusion@4@@fusion@4@@fusion@4@@fusion@boost@@@qi@spirit@boost@@U?$bool_@$0A@@mpl@4@@detail@qi@spirit@boost@@@function@detail@boost@@CAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@Ufunction_obj_tag@234@@Z`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180031a50`

## callees

- `0x180008be4`
- `0x180009474`
- `0x180033704`

## import_xrefs

- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18003372d`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18003372d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800337ab`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800337ab`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18003373b`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18003373b`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800337c7`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800337c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall boost::detail::function::functor_manager<boost::spirit::qi::detail::parser_binder<boost::spirit::qi::sequence<boost::fusion::cons<boost::spirit::qi::no_case_literal_string<char const (&)[5],1>,boost::fusion::cons<boost::spirit::qi::reference<boost::spirit::qi::rule<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,boost::iterator_range<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>> (void),boost::spirit::unused_type,boost::spirit::unused_type,boost::spirit::unused_type> const>,boost::fusion::cons<boost::spirit::qi::literal_char<boost::spirit::char_encoding::standard,1,0>,boost::fusion::nil_>>>>,boost::mpl::bool_<0>>>::manager(
        _QWORD *a1,
        __int64 a2,
        int a3)
{
  __int64 v5; // rbx
  __int64 v6; // rbp
  _QWORD *v7; // rax
  _QWORD *v8; // rsi
  Mso::Memory *v9; // rsi
  void *v10; // rdx

  v5 = 0;
  if ( a3 )
  {
    switch ( a3 )
    {
      case 1:
        *(_QWORD *)a2 = *a1;
        *a1 = 0;
        return;
      case 2:
        v9 = *(Mso::Memory **)a2;
        if ( *(_QWORD *)a2 )
        {
          std::string::~string((char *)v9 + 32);
          std::string::~string(v9);
          Mso::Memory::Free(v9, v10);
        }
        break;
      case 3:
        if ( !(unsigned int)__std_type_info_compare(*(_QWORD *)a2 + 8LL, &qword_180186D28) )
          v5 = *a1;
        break;
      default:
        *(_QWORD *)a2 = &boost::spirit::qi::detail::parser_binder<boost::spirit::qi::sequence<boost::fusion::cons<boost::spirit::qi::no_case_literal_string<char const (&)[5],1>,boost::fusion::cons<boost::spirit::qi::reference<boost::spirit::qi::rule<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,boost::iterator_range<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>> (void),boost::spirit::unused_type,boost::spirit::unused_type,boost::spirit::unused_type> const>,boost::fusion::cons<boost::spirit::qi::literal_char<boost::spirit::char_encoding::standard,1,0>,boost::fusion::nil_>>>>,boost::mpl::bool_<0>> `RTTI Type Descriptor';
        *(_WORD *)(a2 + 8) = 0;
        return;
    }
    *(_QWORD *)a2 = v5;
    return;
  }
  v6 = *a1;
  v7 = Mso::Memory::AllocateEx((Mso::Memory *)0x50, 0, 0);
  v8 = v7;
  if ( !v7 )
  {
    ThrowOOM();
    __debugbreak();
  }
  std::string::string(v7, v6);
  std::string::string(v8 + 4, v6 + 32);
  v8[8] = *(_QWORD *)(v6 + 64);
  *((_BYTE *)v8 + 72) = *(_BYTE *)(v6 + 72);
  *(_QWORD *)a2 = v8;
}

```

## disassembly

```asm
0x180033704  mov     [rsp+arg_0], rbx
0x180033709  mov     [rsp+arg_8], rbp
0x18003370e  mov     [rsp+arg_10], rsi
0x180033713  push    rdi
0x180033714  sub     rsp, 30h
0x180033718  mov     rdi, rdx
0x18003371b  mov     rsi, rcx
0x18003371e  xor     ebx, ebx
0x180033720  test    r8d, r8d
0x180033723  jnz     short loc_180033778
0x180033725  mov     rbp, [rcx]
0x180033728  xor     edx, edx
0x18003372a  lea     ecx, [rbx+50h]
0x18003372d  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x180033733  mov     rsi, rax
0x180033736  test    rax, rax
0x180033739  jnz     short loc_180033742
0x18003373b  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x180033741  int     3; Trap to Debugger
0x180033742  mov     [rsp+38h+var_18], rsi
0x180033747  mov     [rsp+38h+var_10], rsi
0x18003374c  mov     rdx, rbp
0x18003374f  mov     rcx, rsi
0x180033752  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180033757  lea     rdx, [rbp+20h]
0x18003375b  lea     rcx, [rsi+20h]
0x18003375f  nop
0x180033760  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180033765  mov     rax, [rbp+40h]
0x180033769  mov     [rsi+40h], rax
0x18003376d  mov     al, [rbp+48h]
0x180033770  mov     [rsi+48h], al
0x180033773  mov     [rdi], rsi
0x180033776  jmp     short loc_1800337E7
0x180033778  cmp     r8d, 1
0x18003377c  jnz     short loc_180033789
0x18003377e  mov     rax, [rcx]
0x180033781  mov     [rdx], rax
0x180033784  mov     [rcx], rbx
0x180033787  jmp     short loc_1800337E7
0x180033789  cmp     r8d, 2
0x18003378d  jnz     short loc_1800337B3
0x18003378f  mov     rsi, [rdx]
0x180033792  test    rsi, rsi
0x180033795  jz      short loc_1800337D4
0x180033797  lea     rcx, [rsi+20h]
0x18003379b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800337a0  mov     rcx, rsi
0x1800337a3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800337a8  mov     rcx, rsi
0x1800337ab  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800337b1  jmp     short loc_1800337D4
0x1800337b3  cmp     r8d, 3
0x1800337b7  jnz     short loc_1800337D9
0x1800337b9  mov     rcx, [rdx]
0x1800337bc  add     rcx, 8
0x1800337c0  lea     rdx, qword_180186D28
0x1800337c7  call    cs:__imp___std_type_info_compare
0x1800337cd  test    eax, eax
0x1800337cf  jnz     short loc_1800337D4
0x1800337d1  mov     rbx, [rsi]
0x1800337d4  mov     [rdi], rbx
0x1800337d7  jmp     short loc_1800337E7
0x1800337d9  lea     rax, ??_R0?AU?$parser_binder@U?$sequence@U?$cons@U?$no_case_literal_string@AEAY04$$CBD$00@qi@spirit@boost@@U?$cons@U?$reference@$$CBU?$rule@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@$$A6A?AV?$iterator_range@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@@boost@@XZUunused_type@spirit@4@U564@U564@@qi@spirit@boost@@@qi@spirit@boost@@U?$cons@U?$literal_char@Ustandard@char_encoding@spirit@boost@@$00$0A@@qi@spirit@boost@@Unil_@fusion@4@@fusion@4@@fusion@4@@fusion@boost@@@qi@spirit@boost@@U?$bool_@$0A@@mpl@4@@detail@qi@spirit@boost@@@8; boost::spirit::qi::detail::parser_binder<boost::spirit::qi::sequence<boost::fusion::cons<boost::spirit::qi::no_case_literal_string<char const (&)[5],1>,boost::fusion::cons<boost::spirit::qi::reference<boost::spirit::qi::rule<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,boost::iterator_range<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>> (void),boost::spirit::unused_type,boost::spirit::unused_type,boost::spirit::unused_type> const>,boost::fusion::cons<boost::spirit::qi::literal_char<boost::spirit::char_encoding::standard,1,0>,boost::fusion::nil_>>>>,boost::mpl::bool_<0>> `RTTI Type Descriptor'
0x1800337e0  mov     [rdx], rax
0x1800337e3  mov     [rdx+8], bx
0x1800337e7  mov     rbx, [rsp+38h+arg_0]
0x1800337ec  mov     rbp, [rsp+38h+arg_8]
0x1800337f1  mov     rsi, [rsp+38h+arg_10]
0x1800337f6  add     rsp, 30h
0x1800337fa  pop     rdi
0x1800337fb  retn
```
