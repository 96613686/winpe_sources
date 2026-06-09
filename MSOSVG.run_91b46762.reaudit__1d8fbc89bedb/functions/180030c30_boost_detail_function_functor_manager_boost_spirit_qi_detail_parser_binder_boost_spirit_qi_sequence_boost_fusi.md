# boost::detail::function::functor_manager<boost::spirit::qi::detail::parser_binder<boost::spirit::qi::sequence<boost::fusion::cons<boost::spirit::qi::reference<boost::spirit::qi::rule<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,GEL::Color (void),boost::spirit::unused_type,boost::spirit::unused_type,boost::spirit::unused_type> const>,boost::fusion::cons<boost::spirit::qi::optional<boost::spirit::qi::sequence<boost::fusion::cons<boost::spirit::qi::plus<boost::spirit::qi::char_class<boost::spirit::tag::char_code<boost::spirit::tag::space,boost::spirit::char_encoding::ascii>>>,boost::fusion::cons<boost::spirit::qi::parameterized_nonterminal<boost::spirit::qi::rule<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,svgpp::tag::skip_icc_color (svgpp::factory::icc_color::stub const &),boost::spirit::locals<svgpp::factory::icc_color::stub::builder_type,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na>,boost::spirit::unused_type,boost::spirit::unused_type>,boost::fusion::vector<boost::phoenix::actor<boost::spirit::attribute<1>>>>,boost::fusion::nil_>>>>,boost::fusion::nil_>>>,boost::mpl::bool_<0>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x180030c30`
- end: `0x180030cfd`
- name: `?manage@?$functor_manager@U?$parser_binder@U?$sequence@U?$cons@U?$reference@$$CBU?$rule@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@$$A6A?AUColor@GEL@@XZUunused_type@spirit@boost@@U567@U567@@qi@spirit@boost@@@qi@spirit@boost@@U?$cons@U?$optional@U?$sequence@U?$cons@U?$plus@U?$char_class@U?$char_code@Uspace@tag@spirit@boost@@Uascii@char_encoding@34@@tag@spirit@boost@@@qi@spirit@boost@@@qi@spirit@boost@@U?$cons@U?$parameterized_nonterminal@U?$rule@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@$$A6A?AUskip_icc_color@tag@svgpp@@AEBUstub@icc_color@factory@5@@ZU?$locals@Ubuilder_type@stub@icc_color@factory@svgpp@@Una@mpl@boost@@U678@U678@U678@U678@U678@U678@U678@U678@@spirit@boost@@Uunused_type@spirit@boost@@Uunused_type@spirit@boost@@@qi@spirit@boost@@U?$vector@U?$actor@U?$attribute@$00@spirit@boost@@@phoenix@boost@@@fusion@4@@qi@spirit@boost@@Unil_@fusion@4@@fusion@4@@fusion@boost@@@qi@spirit@boost@@@qi@spirit@boost@@Unil_@fusion@4@@fusion@4@@fusion@boost@@@qi@spirit@boost@@U?$bool_@$0A@@mpl@4@@detail@qi@spirit@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180030c30`

## import_xrefs

- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180030c5e`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180030c5e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180030cb1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180030cb1`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180030c6c`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180030c6c`
- `VCRUNTIME140!__std_type_info_compare` at `0x180030ccd`
- `VCRUNTIME140!__std_type_info_compare` at `0x180030ccd`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::spirit::qi::detail::parser_binder<boost::spirit::qi::sequence<boost::fusion::cons<boost::spirit::qi::reference<boost::spirit::qi::rule<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,GEL::Color (void),boost::spirit::unused_type,boost::spirit::unused_type,boost::spirit::unused_type> const>,boost::fusion::cons<boost::spirit::qi::optional<boost::spirit::qi::sequence<boost::fusion::cons<boost::spirit::qi::plus<boost::spirit::qi::char_class<boost::spirit::tag::char_code<boost::spirit::tag::space,boost::spirit::char_encoding::ascii>>>,boost::fusion::cons<boost::spirit::qi::parameterized_nonterminal<boost::spirit::qi::rule<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,svgpp::tag::skip_icc_color (svgpp::factory::icc_color::stub const &),boost::spirit::locals<svgpp::factory::icc_color::stub::builder_type,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na>,boost::spirit::unused_type,boost::spirit::unused_type>,boost::fusion::vector<boost::phoenix::actor<boost::spirit::attribute<1>>>>,boost::fusion::nil_>>>>,boost::fusion::nil_>>>,boost::mpl::bool_<0>>>::manage(
        _QWORD *a1,
        __int64 a2,
        int a3)
{
  __int64 v3; // rbx
  __int64 v6; // rsi
  _BYTE *v7; // rax

  v3 = 0;
  if ( a3 == 4 )
    goto LABEL_15;
  if ( a3 )
  {
    switch ( a3 )
    {
      case 1:
        *(_QWORD *)a2 = *a1;
        *a1 = 0;
        return;
      case 2:
        if ( *(_QWORD *)a2 )
          Mso::Memory::Free(*(Mso::Memory **)a2, (void *)a2);
LABEL_14:
        *(_QWORD *)a2 = v3;
        return;
      case 3:
        if ( !(unsigned int)__std_type_info_compare(*(_QWORD *)a2 + 8LL, &qword_180189228) )
          v3 = *a1;
        goto LABEL_14;
    }
LABEL_15:
    *(_WORD *)(a2 + 8) = 0;
    *(_QWORD *)a2 = &boost::spirit::qi::detail::parser_binder<boost::spirit::qi::sequence<boost::fusion::cons<boost::spirit::qi::reference<boost::spirit::qi::rule<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,GEL::Color (void),boost::spirit::unused_type,boost::spirit::unused_type,boost::spirit::unused_type> const>,boost::fusion::cons<boost::spirit::qi::optional<boost::spirit::qi::sequence<boost::fusion::cons<boost::spirit::qi::plus<boost::spirit::qi::char_class<boost::spirit::tag::char_code<boost::spirit::tag::space,boost::spirit::char_encoding::ascii>>>,boost::fusion::cons<boost::spirit::qi::parameterized_nonterminal<boost::spirit::qi::rule<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,svgpp::tag::skip_icc_color (svgpp::factory::icc_color::stub const &),boost::spirit::locals<svgpp::factory::icc_color::stub::builder_type,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na>,boost::spirit::unused_type,boost::spirit::unused_type>,boost::fusion::vector<boost::phoenix::actor<boost::spirit::attribute<1>>>>,boost::fusion::nil_>>>>,boost::fusion::nil_>>>,boost::mpl::bool_<0>> `RTTI Type Descriptor';
    return;
  }
  v6 = *a1;
  v7 = Mso::Memory::AllocateEx((Mso::Memory *)0x30, 0, 0);
  if ( !v7 )
  {
    ThrowOOM();
    __debugbreak();
  }
  *(_QWORD *)v7 = *(_QWORD *)v6;
  v7[8] = *(_BYTE *)(v6 + 8);
  *((_QWORD *)v7 + 2) = *(_QWORD *)(v6 + 16);
  v7[24] = *(_BYTE *)(v6 + 24);
  *(_QWORD *)a2 = v7;
}

```

## disassembly

```asm
0x180030c30  mov     [rsp+arg_0], rbx
0x180030c35  mov     [rsp+arg_8], rsi
0x180030c3a  push    rdi
0x180030c3b  sub     rsp, 20h
0x180030c3f  xor     ebx, ebx
0x180030c41  mov     rdi, rdx
0x180030c44  mov     rsi, rcx
0x180030c47  cmp     r8d, 4
0x180030c4b  jz      loc_180030CDF
0x180030c51  test    r8d, r8d
0x180030c54  jnz     short loc_180030C92
0x180030c56  mov     rsi, [rcx]
0x180030c59  xor     edx, edx
0x180030c5b  lea     ecx, [rbx+30h]
0x180030c5e  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x180030c64  mov     rcx, rax
0x180030c67  test    rax, rax
0x180030c6a  jnz     short loc_180030C73
0x180030c6c  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x180030c72  int     3; Trap to Debugger
0x180030c73  mov     rax, [rsi]
0x180030c76  mov     [rcx], rax
0x180030c79  mov     al, [rsi+8]
0x180030c7c  mov     [rcx+8], al
0x180030c7f  mov     rax, [rsi+10h]
0x180030c83  mov     [rcx+10h], rax
0x180030c87  mov     al, [rsi+18h]
0x180030c8a  mov     [rcx+18h], al
0x180030c8d  mov     [rdi], rcx
0x180030c90  jmp     short loc_180030CED
0x180030c92  cmp     r8d, 1
0x180030c96  jnz     short loc_180030CA3
0x180030c98  mov     rax, [rcx]
0x180030c9b  mov     [rdx], rax
0x180030c9e  mov     [rcx], rbx
0x180030ca1  jmp     short loc_180030CED
0x180030ca3  cmp     r8d, 2
0x180030ca7  jnz     short loc_180030CB9
0x180030ca9  cmp     [rdx], rbx
0x180030cac  jz      short loc_180030CDA
0x180030cae  mov     rcx, [rdx]
0x180030cb1  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180030cb7  jmp     short loc_180030CDA
0x180030cb9  cmp     r8d, 3
0x180030cbd  jnz     short loc_180030CDF
0x180030cbf  mov     rcx, [rdx]
0x180030cc2  lea     rdx, qword_180189228
0x180030cc9  add     rcx, 8
0x180030ccd  call    cs:__imp___std_type_info_compare
0x180030cd3  test    eax, eax
0x180030cd5  jnz     short loc_180030CDA
0x180030cd7  mov     rbx, [rsi]
0x180030cda  mov     [rdi], rbx
0x180030cdd  jmp     short loc_180030CED
0x180030cdf  lea     rax, ??_R0?AU?$parser_binder@U?$sequence@U?$cons@U?$reference@$$CBU?$rule@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@$$A6A?AUColor@GEL@@XZUunused_type@spirit@boost@@U567@U567@@qi@spirit@boost@@@qi@spirit@boost@@U?$cons@U?$optional@U?$sequence@U?$cons@U?$plus@U?$char_class@U?$char_code@Uspace@tag@spirit@boost@@Uascii@char_encoding@34@@tag@spirit@boost@@@qi@spirit@boost@@@qi@spirit@boost@@U?$cons@U?$parameterized_nonterminal@U?$rule@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@$$A6A?AUskip_icc_color@tag@svgpp@@AEBUstub@icc_color@factory@5@@ZU?$locals@Ubuilder_type@stub@icc_color@factory@svgpp@@Una@mpl@boost@@U678@U678@U678@U678@U678@U678@U678@U678@@spirit@boost@@Uunused_type@spirit@boost@@Uunused_type@spirit@boost@@@qi@spirit@boost@@U?$vector@U?$actor@U?$attribute@$00@spirit@boost@@@phoenix@boost@@@fusion@4@@qi@spirit@boost@@Unil_@fusion@4@@fusion@4@@fusion@boost@@@qi@spirit@boost@@@qi@spirit@boost@@Unil_@fusion@4@@fusion@4@@fusion@boost@@@qi@spirit@boost@@U?$bool_@$0A@@mpl@4@@detail@qi@spirit@boost@@@8; boost::spirit::qi::detail::parser_binder<boost::spirit::qi::sequence<boost::fusion::cons<boost::spirit::qi::reference<boost::spirit::qi::rule<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,GEL::Color (void),boost::spirit::unused_type,boost::spirit::unused_type,boost::spirit::unused_type> const>,boost::fusion::cons<boost::spirit::qi::optional<boost::spirit::qi::sequence<boost::fusion::cons<boost::spirit::qi::plus<boost::spirit::qi::char_class<boost::spirit::tag::char_code<boost::spirit::tag::space,boost::spirit::char_encoding::ascii>>>,boost::fusion::cons<boost::spirit::qi::parameterized_nonterminal<boost::spirit::qi::rule<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,svgpp::tag::skip_icc_color (svgpp::factory::icc_color::stub const &),boost::spirit::locals<svgpp::factory::icc_color::stub::builder_type,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na,boost::mpl::na>,boost::spirit::unused_type,boost::spirit::unused_type>,boost::fusion::vector<boost::phoenix::actor<boost::spirit::attribute<1>>>>,boost::fusion::nil_>>>>,boost::fusion::nil_>>>,boost::mpl::bool_<0>> `RTTI Type Descriptor'
0x180030ce6  mov     [rdx+8], bx
0x180030cea  mov     [rdx], rax
0x180030ced  mov     rbx, [rsp+28h+arg_0]
0x180030cf2  mov     rsi, [rsp+28h+arg_8]
0x180030cf7  add     rsp, 20h
0x180030cfb  pop     rdi
0x180030cfc  retn
```
