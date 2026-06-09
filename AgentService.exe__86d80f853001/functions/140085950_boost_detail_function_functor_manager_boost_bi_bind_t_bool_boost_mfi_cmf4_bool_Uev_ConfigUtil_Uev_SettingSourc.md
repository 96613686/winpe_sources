# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x140085950`
- end: `0x1400859c2`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAKAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@U?$arg@$01@3@U?$arg@$02@3@U?$arg@$03@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140085950`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085986`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085986`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>>>::manage(
        unsigned __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  if ( a3 == 4 )
  {
LABEL_6:
    *(_WORD *)(a2 + 8) = 0;
    *(_QWORD *)a2 = &boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>> `RTTI Type Descriptor';
    return;
  }
  if ( a3 > 1 )
  {
    if ( a3 == 2 )
      return;
    if ( a3 == 3 )
    {
      *(_QWORD *)a2 = a1 & -(__int64)((unsigned int)__std_type_info_compare(*(_QWORD *)a2 + 8LL, &qword_1400CE698) == 0);
      return;
    }
    goto LABEL_6;
  }
  *(_OWORD *)a2 = *(_OWORD *)a1;
}

```

## disassembly

```asm
0x140085950  mov     [rsp+arg_0], rbx
0x140085955  push    rdi
0x140085956  sub     rsp, 20h
0x14008595a  mov     rbx, rdx
0x14008595d  mov     rdi, rcx
0x140085960  cmp     r8d, 4
0x140085964  jz      short loc_14008599E
0x140085966  cmp     r8d, 1
0x14008596a  jbe     short loc_1400859B0
0x14008596c  cmp     r8d, 2
0x140085970  jz      short loc_1400859B7
0x140085972  cmp     r8d, 3
0x140085976  jnz     short loc_14008599E
0x140085978  mov     rcx, [rdx]
0x14008597b  lea     rdx, qword_1400CE698
0x140085982  add     rcx, 8
0x140085986  call    cs:__imp___std_type_info_compare
0x14008598c  test    eax, eax
0x14008598e  setz    al
0x140085991  neg     al
0x140085993  sbb     rcx, rcx
0x140085996  and     rcx, rdi
0x140085999  mov     [rbx], rcx
0x14008599c  jmp     short loc_1400859B7
0x14008599e  lea     rax, ??_R0?AV?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAKAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@U?$arg@$01@3@U?$arg@$02@3@U?$arg@$03@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,ulong &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>> `RTTI Type Descriptor'
0x1400859a5  mov     word ptr [rdx+8], 0
0x1400859ab  mov     [rdx], rax
0x1400859ae  jmp     short loc_1400859B7
0x1400859b0  movups  xmm0, xmmword ptr [rcx]
0x1400859b3  movdqu  xmmword ptr [rdx], xmm0
0x1400859b7  mov     rbx, [rsp+28h+arg_0]
0x1400859bc  add     rsp, 20h
0x1400859c0  pop     rdi
0x1400859c1  retn
```
