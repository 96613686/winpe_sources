# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,unsigned __int64 &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x140085cf0`
- end: `0x140085d62`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_KAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@U?$arg@$01@3@U?$arg@$02@3@U?$arg@$03@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140085cf0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085d26`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085d26`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>>>::manage(
        unsigned __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  if ( a3 == 4 )
  {
LABEL_6:
    *(_WORD *)(a2 + 8) = 0;
    *(_QWORD *)a2 = &boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>> `RTTI Type Descriptor';
    return;
  }
  if ( a3 > 1 )
  {
    if ( a3 == 2 )
      return;
    if ( a3 == 3 )
    {
      *(_QWORD *)a2 = a1 & -(__int64)((unsigned int)__std_type_info_compare(*(_QWORD *)a2 + 8LL, &qword_1400CECC8) == 0);
      return;
    }
    goto LABEL_6;
  }
  *(_OWORD *)a2 = *(_OWORD *)a1;
}

```

## disassembly

```asm
0x140085cf0  mov     [rsp+arg_0], rbx
0x140085cf5  push    rdi
0x140085cf6  sub     rsp, 20h
0x140085cfa  mov     rbx, rdx
0x140085cfd  mov     rdi, rcx
0x140085d00  cmp     r8d, 4
0x140085d04  jz      short loc_140085D3E
0x140085d06  cmp     r8d, 1
0x140085d0a  jbe     short loc_140085D50
0x140085d0c  cmp     r8d, 2
0x140085d10  jz      short loc_140085D57
0x140085d12  cmp     r8d, 3
0x140085d16  jnz     short loc_140085D3E
0x140085d18  mov     rcx, [rdx]
0x140085d1b  lea     rdx, qword_1400CECC8
0x140085d22  add     rcx, 8
0x140085d26  call    cs:__imp___std_type_info_compare
0x140085d2c  test    eax, eax
0x140085d2e  setz    al
0x140085d31  neg     al
0x140085d33  sbb     rcx, rcx
0x140085d36  and     rcx, rdi
0x140085d39  mov     [rbx], rcx
0x140085d3c  jmp     short loc_140085D57
0x140085d3e  lea     rax, ??_R0?AV?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_KAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@U?$arg@$01@3@U?$arg@$02@3@U?$arg@$03@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,unsigned __int64 &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>> `RTTI Type Descriptor'
0x140085d45  mov     word ptr [rdx+8], 0
0x140085d4b  mov     [rdx], rax
0x140085d4e  jmp     short loc_140085D57
0x140085d50  movups  xmm0, xmmword ptr [rcx]
0x140085d53  movdqu  xmmword ptr [rdx], xmm0
0x140085d57  mov     rbx, [rsp+28h+arg_0]
0x140085d5c  add     rsp, 20h
0x140085d60  pop     rdi
0x140085d61  retn
```
