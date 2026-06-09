# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x1400864e0`
- end: `0x140086552`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV45@AEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@U?$arg@$01@3@U?$arg@$02@3@U?$arg@$03@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400864e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140086516`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140086516`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>>>::manage(
        unsigned __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  if ( a3 == 4 )
  {
LABEL_6:
    *(_WORD *)(a2 + 8) = 0;
    *(_QWORD *)a2 = &boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>> `RTTI Type Descriptor';
    return;
  }
  if ( a3 > 1 )
  {
    if ( a3 == 2 )
      return;
    if ( a3 == 3 )
    {
      *(_QWORD *)a2 = a1 & -(__int64)((unsigned int)__std_type_info_compare(*(_QWORD *)a2 + 8LL, &qword_1400CC958) == 0);
      return;
    }
    goto LABEL_6;
  }
  *(_OWORD *)a2 = *(_OWORD *)a1;
}

```

## disassembly

```asm
0x1400864e0  mov     [rsp+arg_0], rbx
0x1400864e5  push    rdi
0x1400864e6  sub     rsp, 20h
0x1400864ea  mov     rbx, rdx
0x1400864ed  mov     rdi, rcx
0x1400864f0  cmp     r8d, 4
0x1400864f4  jz      short loc_14008652E
0x1400864f6  cmp     r8d, 1
0x1400864fa  jbe     short loc_140086540
0x1400864fc  cmp     r8d, 2
0x140086500  jz      short loc_140086547
0x140086502  cmp     r8d, 3
0x140086506  jnz     short loc_14008652E
0x140086508  mov     rcx, [rdx]
0x14008650b  lea     rdx, qword_1400CC958
0x140086512  add     rcx, 8
0x140086516  call    cs:__imp___std_type_info_compare
0x14008651c  test    eax, eax
0x14008651e  setz    al
0x140086521  neg     al
0x140086523  sbb     rcx, rcx
0x140086526  and     rcx, rdi
0x140086529  mov     [rbx], rcx
0x14008652c  jmp     short loc_140086547
0x14008652e  lea     rax, ??_R0?AV?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV45@AEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@U?$arg@$01@3@U?$arg@$02@3@U?$arg@$03@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,std::wstring const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>> `RTTI Type Descriptor'
0x140086535  mov     word ptr [rdx+8], 0
0x14008653b  mov     [rdx], rax
0x14008653e  jmp     short loc_140086547
0x140086540  movups  xmm0, xmmword ptr [rcx]
0x140086543  movdqu  xmmword ptr [rdx], xmm0
0x140086547  mov     rbx, [rsp+28h+arg_0]
0x14008654c  add     rsp, 20h
0x140086550  pop     rdi
0x140086551  retn
```
