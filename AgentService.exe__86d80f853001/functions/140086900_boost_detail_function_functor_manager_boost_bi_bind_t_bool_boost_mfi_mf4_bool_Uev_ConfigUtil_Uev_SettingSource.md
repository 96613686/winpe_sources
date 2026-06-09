# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,boost::arg<2>,boost::arg<3>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x140086900`
- end: `0x1400869da`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEB_NAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140003e74`
- `0x140003f88`
- `0x14000adb4`
- `0x14000ba60`
- `0x140086900`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400869a5`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400869a5`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>>>::manage(
        char **a1,
        char **a2,
        int a3)
{
  char *v5; // rdi
  char *v6; // rbx
  char *v7; // rbx
  char *v8; // rax

  v5 = 0;
  switch ( a3 )
  {
    case 4:
      goto LABEL_15;
    case 0:
      v6 = *a1;
      v5 = (char *)operator new(0x30u);
      *(_QWORD *)v5 = *(_QWORD *)v6;
      *((_QWORD *)v5 + 1) = *((_QWORD *)v6 + 1);
      std::wstring::wstring((__int64)(v5 + 16), (__int64)(v6 + 16));
LABEL_9:
      *a2 = v5;
      return;
    case 1:
      *a2 = *a1;
      *a1 = 0;
      return;
    case 2:
      v7 = *a2;
      if ( *a2 )
      {
        std::wstring::_Tidy_deallocate(v7 + 16);
        operator delete(v7);
      }
      goto LABEL_9;
  }
  if ( a3 != 3 )
  {
LABEL_15:
    *a2 = (char *)&boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor';
    *((_WORD *)a2 + 4) = 0;
  }
  else
  {
    if ( (unsigned int)__std_type_info_compare(*a2 + 8, &qword_1400CC1A8) )
      v8 = 0;
    else
      v8 = *a1;
    *a2 = v8;
  }
}

```

## disassembly

```asm
0x140086900  mov     [rsp+arg_0], rbx
0x140086905  mov     [rsp+arg_8], rsi
0x14008690a  push    rdi
0x14008690b  sub     rsp, 20h
0x14008690f  mov     rsi, rdx
0x140086912  mov     rbx, rcx
0x140086915  xor     edi, edi
0x140086917  cmp     r8d, 4
0x14008691b  jz      loc_1400869BC
0x140086921  test    r8d, r8d
0x140086924  jnz     short loc_140086957
0x140086926  mov     rbx, [rcx]
0x140086929  lea     ecx, [rdi+30h]; Size
0x14008692c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140086931  mov     rdi, rax
0x140086934  mov     [rsp+28h+arg_18], rax
0x140086939  mov     rcx, [rbx]
0x14008693c  mov     [rax], rcx
0x14008693f  mov     rcx, [rbx+8]
0x140086943  mov     [rax+8], rcx
0x140086947  lea     rdx, [rbx+10h]
0x14008694b  lea     rcx, [rax+10h]
0x14008694f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140086954  nop
0x140086955  jmp     short loc_14008698C
0x140086957  cmp     r8d, 1
0x14008695b  jnz     short loc_140086968
0x14008695d  mov     rax, [rcx]
0x140086960  mov     [rdx], rax
0x140086963  mov     [rcx], rdi
0x140086966  jmp     short loc_1400869CA
0x140086968  cmp     r8d, 2
0x14008696c  jnz     short loc_140086991
0x14008696e  mov     rbx, [rdx]
0x140086971  test    rbx, rbx
0x140086974  jz      short loc_14008698C
0x140086976  lea     rcx, [rbx+10h]
0x14008697a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008697f  mov     edx, 30h ; '0'
0x140086984  mov     rcx, rbx; Block
0x140086987  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14008698c  mov     [rsi], rdi
0x14008698f  jmp     short loc_1400869CA
0x140086991  cmp     r8d, 3
0x140086995  jnz     short loc_1400869BC
0x140086997  mov     rcx, [rdx]
0x14008699a  add     rcx, 8
0x14008699e  lea     rdx, qword_1400CC1A8
0x1400869a5  call    cs:__imp___std_type_info_compare
0x1400869ab  test    eax, eax
0x1400869ad  jnz     short loc_1400869B4
0x1400869af  mov     rax, [rbx]
0x1400869b2  jmp     short loc_1400869B7
0x1400869b4  mov     rax, rdi
0x1400869b7  mov     [rsi], rax
0x1400869ba  jmp     short loc_1400869CA
0x1400869bc  lea     rax, ??_R0?AV?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEB_NAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,bool const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor'
0x1400869c3  mov     [rdx], rax
0x1400869c6  mov     [rdx+8], di
0x1400869ca  mov     rbx, [rsp+28h+arg_0]
0x1400869cf  mov     rsi, [rsp+28h+arg_8]
0x1400869d4  add     rsp, 20h
0x1400869d8  pop     rdi
0x1400869d9  retn
```
