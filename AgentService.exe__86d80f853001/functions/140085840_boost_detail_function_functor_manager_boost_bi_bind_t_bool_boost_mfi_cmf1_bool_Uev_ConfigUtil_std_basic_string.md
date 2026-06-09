# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf1<bool,Uev::ConfigUtil,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &>,boost::_bi::list2<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x140085840`
- end: `0x1400858b2`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$cmf1@_NVConfigUtil@Uev@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@_mfi@boost@@V?$list2@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140085840`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085876`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085876`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf1<bool,Uev::ConfigUtil,std::wstring const &>,boost::_bi::list2<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>>>>::manage(
        unsigned __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  if ( a3 == 4 )
  {
LABEL_6:
    *(_WORD *)(a2 + 8) = 0;
    *(_QWORD *)a2 = &boost::_bi::bind_t<bool,boost::_mfi::cmf1<bool,Uev::ConfigUtil,std::wstring const &>,boost::_bi::list2<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>>> `RTTI Type Descriptor';
    return;
  }
  if ( a3 > 1 )
  {
    if ( a3 == 2 )
      return;
    if ( a3 == 3 )
    {
      *(_QWORD *)a2 = a1 & -(__int64)((unsigned int)__std_type_info_compare(*(_QWORD *)a2 + 8LL, &qword_1400CEB08) == 0);
      return;
    }
    goto LABEL_6;
  }
  *(_OWORD *)a2 = *(_OWORD *)a1;
}

```

## disassembly

```asm
0x140085840  mov     [rsp+arg_0], rbx
0x140085845  push    rdi
0x140085846  sub     rsp, 20h
0x14008584a  mov     rbx, rdx
0x14008584d  mov     rdi, rcx
0x140085850  cmp     r8d, 4
0x140085854  jz      short loc_14008588E
0x140085856  cmp     r8d, 1
0x14008585a  jbe     short loc_1400858A0
0x14008585c  cmp     r8d, 2
0x140085860  jz      short loc_1400858A7
0x140085862  cmp     r8d, 3
0x140085866  jnz     short loc_14008588E
0x140085868  mov     rcx, [rdx]
0x14008586b  lea     rdx, qword_1400CEB08
0x140085872  add     rcx, 8
0x140085876  call    cs:__imp___std_type_info_compare
0x14008587c  test    eax, eax
0x14008587e  setz    al
0x140085881  neg     al
0x140085883  sbb     rcx, rcx
0x140085886  and     rcx, rdi
0x140085889  mov     [rbx], rcx
0x14008588c  jmp     short loc_1400858A7
0x14008588e  lea     rax, ??_R0?AV?$bind_t@_NV?$cmf1@_NVConfigUtil@Uev@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@_mfi@boost@@V?$list2@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::cmf1<bool,Uev::ConfigUtil,std::wstring const &>,boost::_bi::list2<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>>> `RTTI Type Descriptor'
0x140085895  mov     word ptr [rdx+8], 0
0x14008589b  mov     [rdx], rax
0x14008589e  jmp     short loc_1400858A7
0x1400858a0  movups  xmm0, xmmword ptr [rcx]
0x1400858a3  movdqu  xmmword ptr [rdx], xmm0
0x1400858a7  mov     rbx, [rsp+28h+arg_0]
0x1400858ac  add     rsp, 20h
0x1400858b0  pop     rdi
0x1400858b1  retn
```
