# boost::detail::function::functor_manager<boost::spirit::qi::detail::parser_binder<boost::spirit::qi::action<boost::spirit::qi::char_set<boost::spirit::char_encoding::standard,0,0>,boost::phoenix::actor<boost::proto::exprns_::basic_expr<boost::phoenix::detail::tag::function_eval,boost::proto::argsns_::list2<boost::proto::exprns_::basic_expr<boost::proto::tagns_::tag::terminal,boost::proto::argsns_::term<boost::phoenix::detail::function_ptr<void,void (*)(svgpp::detail::path_events_interface<double> &)>>,0>,boost::phoenix::actor<boost::spirit::attribute<1>>>,2>>>,boost::mpl::bool_<0>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x18002fbd0`
- end: `0x18002fc97`
- name: `?manage@?$functor_manager@U?$parser_binder@U?$action@U?$char_set@Ustandard@char_encoding@spirit@boost@@$0A@$0A@@qi@spirit@boost@@U?$actor@U?$basic_expr@Ufunction_eval@tag@detail@phoenix@boost@@U?$list2@U?$basic_expr@Uterminal@tag@tagns_@proto@boost@@U?$term@U?$function_ptr@XP6AXAEAU?$path_events_interface@N@detail@svgpp@@@Z@detail@phoenix@boost@@@argsns_@45@$0A@@exprns_@proto@boost@@U?$actor@U?$attribute@$00@spirit@boost@@@phoenix@4@@argsns_@proto@5@$01@exprns_@proto@boost@@@phoenix@4@@qi@spirit@boost@@U?$bool_@$0A@@mpl@4@@detail@qi@spirit@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002fbd0`

## import_xrefs

- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18002fbfe`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18002fbfe`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18002fc4b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18002fc4b`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18002fc09`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18002fc09`
- `VCRUNTIME140!__std_type_info_compare` at `0x18002fc67`
- `VCRUNTIME140!__std_type_info_compare` at `0x18002fc67`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::spirit::qi::detail::parser_binder<boost::spirit::qi::action<boost::spirit::qi::char_set<boost::spirit::char_encoding::standard,0,0>,boost::phoenix::actor<boost::proto::exprns_::basic_expr<boost::phoenix::detail::tag::function_eval,boost::proto::argsns_::list2<boost::proto::exprns_::basic_expr<boost::proto::tagns_::tag::terminal,boost::proto::argsns_::term<boost::phoenix::detail::function_ptr<void,void (*)(svgpp::detail::path_events_interface<double> &)>>,0>,boost::phoenix::actor<boost::spirit::attribute<1>>>,2>>>,boost::mpl::bool_<0>>>::manage(
        _QWORD *a1,
        __int64 a2,
        int a3)
{
  __int64 v3; // rbx
  _OWORD *v6; // rsi
  _OWORD *v7; // rax

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
        if ( !(unsigned int)__std_type_info_compare(*(_QWORD *)a2 + 8LL, &qword_18018E828) )
          v3 = *a1;
        goto LABEL_14;
    }
LABEL_15:
    *(_WORD *)(a2 + 8) = 0;
    *(_QWORD *)a2 = &boost::spirit::qi::detail::parser_binder<boost::spirit::qi::action<boost::spirit::qi::char_set<boost::spirit::char_encoding::standard,0,0>,boost::phoenix::actor<boost::proto::exprns_::basic_expr<boost::phoenix::detail::tag::function_eval,boost::proto::argsns_::list2<boost::proto::exprns_::basic_expr<boost::proto::tagns_::tag::terminal,boost::proto::argsns_::term<boost::phoenix::detail::function_ptr<void,void (*)(svgpp::detail::path_events_interface<double> &)>>,0>,boost::phoenix::actor<boost::spirit::attribute<1>>>,2>>>,boost::mpl::bool_<0>> `RTTI Type Descriptor';
    return;
  }
  v6 = (_OWORD *)*a1;
  v7 = Mso::Memory::AllocateEx((Mso::Memory *)0x30, 0, 0);
  if ( !v7 )
  {
    ThrowOOM();
    __debugbreak();
  }
  *v7 = *v6;
  v7[1] = v6[1];
  v7[2] = v6[2];
  *(_QWORD *)a2 = v7;
}

```

## disassembly

```asm
0x18002fbd0  mov     [rsp+arg_0], rbx
0x18002fbd5  mov     [rsp+arg_8], rsi
0x18002fbda  push    rdi
0x18002fbdb  sub     rsp, 20h
0x18002fbdf  xor     ebx, ebx
0x18002fbe1  mov     rdi, rdx
0x18002fbe4  mov     rsi, rcx
0x18002fbe7  cmp     r8d, 4
0x18002fbeb  jz      loc_18002FC79
0x18002fbf1  test    r8d, r8d
0x18002fbf4  jnz     short loc_18002FC2C
0x18002fbf6  mov     rsi, [rcx]
0x18002fbf9  xor     edx, edx
0x18002fbfb  lea     ecx, [rbx+30h]
0x18002fbfe  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18002fc04  test    rax, rax
0x18002fc07  jnz     short loc_18002FC10
0x18002fc09  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x18002fc0f  int     3; Trap to Debugger
0x18002fc10  movups  xmm0, xmmword ptr [rsi]
0x18002fc13  movups  xmmword ptr [rax], xmm0
0x18002fc16  movups  xmm1, xmmword ptr [rsi+10h]
0x18002fc1a  movups  xmmword ptr [rax+10h], xmm1
0x18002fc1e  movups  xmm0, xmmword ptr [rsi+20h]
0x18002fc22  movdqu  xmmword ptr [rax+20h], xmm0
0x18002fc27  mov     [rdi], rax
0x18002fc2a  jmp     short loc_18002FC87
0x18002fc2c  cmp     r8d, 1
0x18002fc30  jnz     short loc_18002FC3D
0x18002fc32  mov     rax, [rcx]
0x18002fc35  mov     [rdx], rax
0x18002fc38  mov     [rcx], rbx
0x18002fc3b  jmp     short loc_18002FC87
0x18002fc3d  cmp     r8d, 2
0x18002fc41  jnz     short loc_18002FC53
0x18002fc43  cmp     [rdx], rbx
0x18002fc46  jz      short loc_18002FC74
0x18002fc48  mov     rcx, [rdx]
0x18002fc4b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18002fc51  jmp     short loc_18002FC74
0x18002fc53  cmp     r8d, 3
0x18002fc57  jnz     short loc_18002FC79
0x18002fc59  mov     rcx, [rdx]
0x18002fc5c  lea     rdx, qword_18018E828
0x18002fc63  add     rcx, 8
0x18002fc67  call    cs:__imp___std_type_info_compare
0x18002fc6d  test    eax, eax
0x18002fc6f  jnz     short loc_18002FC74
0x18002fc71  mov     rbx, [rsi]
0x18002fc74  mov     [rdi], rbx
0x18002fc77  jmp     short loc_18002FC87
0x18002fc79  lea     rax, ??_R0?AU?$parser_binder@U?$action@U?$char_set@Ustandard@char_encoding@spirit@boost@@$0A@$0A@@qi@spirit@boost@@U?$actor@U?$basic_expr@Ufunction_eval@tag@detail@phoenix@boost@@U?$list2@U?$basic_expr@Uterminal@tag@tagns_@proto@boost@@U?$term@U?$function_ptr@XP6AXAEAU?$path_events_interface@N@detail@svgpp@@@Z@detail@phoenix@boost@@@argsns_@45@$0A@@exprns_@proto@boost@@U?$actor@U?$attribute@$00@spirit@boost@@@phoenix@4@@argsns_@proto@5@$01@exprns_@proto@boost@@@phoenix@4@@qi@spirit@boost@@U?$bool_@$0A@@mpl@4@@detail@qi@spirit@boost@@@8; boost::spirit::qi::detail::parser_binder<boost::spirit::qi::action<boost::spirit::qi::char_set<boost::spirit::char_encoding::standard,0,0>,boost::phoenix::actor<boost::proto::exprns_::basic_expr<boost::phoenix::detail::tag::function_eval,boost::proto::argsns_::list2<boost::proto::exprns_::basic_expr<boost::proto::tagns_::tag::terminal,boost::proto::argsns_::term<boost::phoenix::detail::function_ptr<void,void (*)(svgpp::detail::path_events_interface<double> &)>>,0>,boost::phoenix::actor<boost::spirit::attribute<1>>>,2>>>,boost::mpl::bool_<0>> `RTTI Type Descriptor'
0x18002fc80  mov     [rdx+8], bx
0x18002fc84  mov     [rdx], rax
0x18002fc87  mov     rbx, [rsp+28h+arg_0]
0x18002fc8c  mov     rsi, [rsp+28h+arg_8]
0x18002fc91  add     rsp, 20h
0x18002fc95  pop     rdi
0x18002fc96  retn
```
