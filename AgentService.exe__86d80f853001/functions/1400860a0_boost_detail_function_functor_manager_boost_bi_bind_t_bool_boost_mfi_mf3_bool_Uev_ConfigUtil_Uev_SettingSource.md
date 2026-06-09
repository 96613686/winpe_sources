# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf3<bool,Uev::ConfigUtil,Uev::SettingSource,std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> &,long &>,boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x1400860a0`
- end: `0x140086112`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$mf3@_NVConfigUtil@Uev@@W4SettingSource@2@AEAV?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAJ@_mfi@boost@@V?$list4@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400860a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400860d6`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400860d6`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf3<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::list<std::wstring> &,long &>,boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>>>>::manage(
        unsigned __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  if ( a3 == 4 )
  {
LABEL_6:
    *(_WORD *)(a2 + 8) = 0;
    *(_QWORD *)a2 = &boost::_bi::bind_t<bool,boost::_mfi::mf3<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::list<std::wstring> &,long &>,boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor';
    return;
  }
  if ( a3 > 1 )
  {
    if ( a3 == 2 )
      return;
    if ( a3 == 3 )
    {
      *(_QWORD *)a2 = a1 & -(__int64)((unsigned int)__std_type_info_compare(*(_QWORD *)a2 + 8LL, &qword_1400CE998) == 0);
      return;
    }
    goto LABEL_6;
  }
  *(_OWORD *)a2 = *(_OWORD *)a1;
}

```

## disassembly

```asm
0x1400860a0  mov     [rsp+arg_0], rbx
0x1400860a5  push    rdi
0x1400860a6  sub     rsp, 20h
0x1400860aa  mov     rbx, rdx
0x1400860ad  mov     rdi, rcx
0x1400860b0  cmp     r8d, 4
0x1400860b4  jz      short loc_1400860EE
0x1400860b6  cmp     r8d, 1
0x1400860ba  jbe     short loc_140086100
0x1400860bc  cmp     r8d, 2
0x1400860c0  jz      short loc_140086107
0x1400860c2  cmp     r8d, 3
0x1400860c6  jnz     short loc_1400860EE
0x1400860c8  mov     rcx, [rdx]
0x1400860cb  lea     rdx, qword_1400CE998
0x1400860d2  add     rcx, 8
0x1400860d6  call    cs:__imp___std_type_info_compare
0x1400860dc  test    eax, eax
0x1400860de  setz    al
0x1400860e1  neg     al
0x1400860e3  sbb     rcx, rcx
0x1400860e6  and     rcx, rdi
0x1400860e9  mov     [rbx], rcx
0x1400860ec  jmp     short loc_140086107
0x1400860ee  lea     rax, ??_R0?AV?$bind_t@_NV?$mf3@_NVConfigUtil@Uev@@W4SettingSource@2@AEAV?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAJ@_mfi@boost@@V?$list4@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::mf3<bool,Uev::ConfigUtil,Uev::SettingSource,std::list<std::wstring> &,long &>,boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor'
0x1400860f5  mov     word ptr [rdx+8], 0
0x1400860fb  mov     [rdx], rax
0x1400860fe  jmp     short loc_140086107
0x140086100  movups  xmm0, xmmword ptr [rcx]
0x140086103  movdqu  xmmword ptr [rdx], xmm0
0x140086107  mov     rbx, [rsp+28h+arg_0]
0x14008610c  add     rsp, 20h
0x140086110  pop     rdi
0x140086111  retn
```
