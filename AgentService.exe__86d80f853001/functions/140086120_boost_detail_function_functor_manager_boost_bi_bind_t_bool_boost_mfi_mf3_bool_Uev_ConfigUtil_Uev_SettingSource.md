# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf3<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,long &>,boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x140086120`
- end: `0x140086192`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$mf3@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAJ@_mfi@boost@@V?$list4@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140086120`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140086156`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140086156`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf3<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &>,boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>>>>::manage(
        unsigned __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  if ( a3 == 4 )
  {
LABEL_6:
    *(_WORD *)(a2 + 8) = 0;
    *(_QWORD *)a2 = &boost::_bi::bind_t<bool,boost::_mfi::mf3<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &>,boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor';
    return;
  }
  if ( a3 > 1 )
  {
    if ( a3 == 2 )
      return;
    if ( a3 == 3 )
    {
      *(_QWORD *)a2 = a1 & -(__int64)((unsigned int)__std_type_info_compare(*(_QWORD *)a2 + 8LL, &qword_1400CC5B8) == 0);
      return;
    }
    goto LABEL_6;
  }
  *(_OWORD *)a2 = *(_OWORD *)a1;
}

```

## disassembly

```asm
0x140086120  mov     [rsp+arg_0], rbx
0x140086125  push    rdi
0x140086126  sub     rsp, 20h
0x14008612a  mov     rbx, rdx
0x14008612d  mov     rdi, rcx
0x140086130  cmp     r8d, 4
0x140086134  jz      short loc_14008616E
0x140086136  cmp     r8d, 1
0x14008613a  jbe     short loc_140086180
0x14008613c  cmp     r8d, 2
0x140086140  jz      short loc_140086187
0x140086142  cmp     r8d, 3
0x140086146  jnz     short loc_14008616E
0x140086148  mov     rcx, [rdx]
0x14008614b  lea     rdx, qword_1400CC5B8
0x140086152  add     rcx, 8
0x140086156  call    cs:__imp___std_type_info_compare
0x14008615c  test    eax, eax
0x14008615e  setz    al
0x140086161  neg     al
0x140086163  sbb     rcx, rcx
0x140086166  and     rcx, rdi
0x140086169  mov     [rbx], rcx
0x14008616c  jmp     short loc_140086187
0x14008616e  lea     rax, ??_R0?AV?$bind_t@_NV?$mf3@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAJ@_mfi@boost@@V?$list4@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::mf3<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,long &>,boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor'
0x140086175  mov     word ptr [rdx+8], 0
0x14008617b  mov     [rdx], rax
0x14008617e  jmp     short loc_140086187
0x140086180  movups  xmm0, xmmword ptr [rcx]
0x140086183  movdqu  xmmword ptr [rdx], xmm0
0x140086187  mov     rbx, [rsp+28h+arg_0]
0x14008618c  add     rsp, 20h
0x140086190  pop     rdi
0x140086191  retn
```
