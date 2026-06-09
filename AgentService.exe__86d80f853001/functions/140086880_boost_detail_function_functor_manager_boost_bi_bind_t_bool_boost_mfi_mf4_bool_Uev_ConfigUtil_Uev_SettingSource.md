# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x140086880`
- end: `0x1400868f2`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEB_NAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@U?$arg@$01@3@U?$arg@$02@3@U?$arg@$03@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140086880`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400868b6`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400868b6`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>>>::manage(
        unsigned __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  if ( a3 == 4 )
  {
LABEL_6:
    *(_WORD *)(a2 + 8) = 0;
    *(_QWORD *)a2 = &boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>> `RTTI Type Descriptor';
    return;
  }
  if ( a3 > 1 )
  {
    if ( a3 == 2 )
      return;
    if ( a3 == 3 )
    {
      *(_QWORD *)a2 = a1 & -(__int64)((unsigned int)__std_type_info_compare(*(_QWORD *)a2 + 8LL, &qword_1400CCF08) == 0);
      return;
    }
    goto LABEL_6;
  }
  *(_OWORD *)a2 = *(_OWORD *)a1;
}

```

## disassembly

```asm
0x140086880  mov     [rsp+arg_0], rbx
0x140086885  push    rdi
0x140086886  sub     rsp, 20h
0x14008688a  mov     rbx, rdx
0x14008688d  mov     rdi, rcx
0x140086890  cmp     r8d, 4
0x140086894  jz      short loc_1400868CE
0x140086896  cmp     r8d, 1
0x14008689a  jbe     short loc_1400868E0
0x14008689c  cmp     r8d, 2
0x1400868a0  jz      short loc_1400868E7
0x1400868a2  cmp     r8d, 3
0x1400868a6  jnz     short loc_1400868CE
0x1400868a8  mov     rcx, [rdx]
0x1400868ab  lea     rdx, qword_1400CCF08
0x1400868b2  add     rcx, 8
0x1400868b6  call    cs:__imp___std_type_info_compare
0x1400868bc  test    eax, eax
0x1400868be  setz    al
0x1400868c1  neg     al
0x1400868c3  sbb     rcx, rcx
0x1400868c6  and     rcx, rdi
0x1400868c9  mov     [rbx], rcx
0x1400868cc  jmp     short loc_1400868E7
0x1400868ce  lea     rax, ??_R0?AV?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEB_NAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@U?$arg@$01@3@U?$arg@$02@3@U?$arg@$03@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,bool const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>> `RTTI Type Descriptor'
0x1400868d5  mov     word ptr [rdx+8], 0
0x1400868db  mov     [rdx], rax
0x1400868de  jmp     short loc_1400868E7
0x1400868e0  movups  xmm0, xmmword ptr [rcx]
0x1400868e3  movdqu  xmmword ptr [rdx], xmm0
0x1400868e7  mov     rbx, [rsp+28h+arg_0]
0x1400868ec  add     rsp, 20h
0x1400868f0  pop     rdi
0x1400868f1  retn
```
