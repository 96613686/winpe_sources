# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x140085e50`
- end: `0x140085ec2`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_NAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@U?$arg@$01@3@U?$arg@$02@3@U?$arg@$03@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140085e50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085e86`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085e86`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>>>::manage(
        unsigned __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  if ( a3 == 4 )
  {
LABEL_6:
    *(_WORD *)(a2 + 8) = 0;
    *(_QWORD *)a2 = &boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>> `RTTI Type Descriptor';
    return;
  }
  if ( a3 > 1 )
  {
    if ( a3 == 2 )
      return;
    if ( a3 == 3 )
    {
      *(_QWORD *)a2 = a1 & -(__int64)((unsigned int)__std_type_info_compare(*(_QWORD *)a2 + 8LL, &qword_1400CC498) == 0);
      return;
    }
    goto LABEL_6;
  }
  *(_OWORD *)a2 = *(_OWORD *)a1;
}

```

## disassembly

```asm
0x140085e50  mov     [rsp+arg_0], rbx
0x140085e55  push    rdi
0x140085e56  sub     rsp, 20h
0x140085e5a  mov     rbx, rdx
0x140085e5d  mov     rdi, rcx
0x140085e60  cmp     r8d, 4
0x140085e64  jz      short loc_140085E9E
0x140085e66  cmp     r8d, 1
0x140085e6a  jbe     short loc_140085EB0
0x140085e6c  cmp     r8d, 2
0x140085e70  jz      short loc_140085EB7
0x140085e72  cmp     r8d, 3
0x140085e76  jnz     short loc_140085E9E
0x140085e78  mov     rcx, [rdx]
0x140085e7b  lea     rdx, qword_1400CC498
0x140085e82  add     rcx, 8
0x140085e86  call    cs:__imp___std_type_info_compare
0x140085e8c  test    eax, eax
0x140085e8e  setz    al
0x140085e91  neg     al
0x140085e93  sbb     rcx, rcx
0x140085e96  and     rcx, rdi
0x140085e99  mov     [rbx], rcx
0x140085e9c  jmp     short loc_140085EB7
0x140085e9e  lea     rax, ??_R0?AV?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_NAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@U?$arg@$01@3@U?$arg@$02@3@U?$arg@$03@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,bool &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>> `RTTI Type Descriptor'
0x140085ea5  mov     word ptr [rdx+8], 0
0x140085eab  mov     [rdx], rax
0x140085eae  jmp     short loc_140085EB7
0x140085eb0  movups  xmm0, xmmword ptr [rcx]
0x140085eb3  movdqu  xmmword ptr [rdx], xmm0
0x140085eb7  mov     rbx, [rsp+28h+arg_0]
0x140085ebc  add     rsp, 20h
0x140085ec0  pop     rdi
0x140085ec1  retn
```
