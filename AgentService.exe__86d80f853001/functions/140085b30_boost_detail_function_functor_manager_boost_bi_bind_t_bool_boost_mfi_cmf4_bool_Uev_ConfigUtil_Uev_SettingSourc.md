# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,boost::arg<2>,boost::arg<3>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x140085b30`
- end: `0x140085c0a`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV45@AEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
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
- `0x140085b30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085bd5`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085bd5`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>>>::manage(
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
    *a2 = (char *)&boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor';
    *((_WORD *)a2 + 4) = 0;
  }
  else
  {
    if ( (unsigned int)__std_type_info_compare(*a2 + 8, &qword_1400CE828) )
      v8 = 0;
    else
      v8 = *a1;
    *a2 = v8;
  }
}

```

## disassembly

```asm
0x140085b30  mov     [rsp+arg_0], rbx
0x140085b35  mov     [rsp+arg_8], rsi
0x140085b3a  push    rdi
0x140085b3b  sub     rsp, 20h
0x140085b3f  mov     rsi, rdx
0x140085b42  mov     rbx, rcx
0x140085b45  xor     edi, edi
0x140085b47  cmp     r8d, 4
0x140085b4b  jz      loc_140085BEC
0x140085b51  test    r8d, r8d
0x140085b54  jnz     short loc_140085B87
0x140085b56  mov     rbx, [rcx]
0x140085b59  lea     ecx, [rdi+30h]; Size
0x140085b5c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140085b61  mov     rdi, rax
0x140085b64  mov     [rsp+28h+arg_18], rax
0x140085b69  mov     rcx, [rbx]
0x140085b6c  mov     [rax], rcx
0x140085b6f  mov     rcx, [rbx+8]
0x140085b73  mov     [rax+8], rcx
0x140085b77  lea     rdx, [rbx+10h]
0x140085b7b  lea     rcx, [rax+10h]
0x140085b7f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140085b84  nop
0x140085b85  jmp     short loc_140085BBC
0x140085b87  cmp     r8d, 1
0x140085b8b  jnz     short loc_140085B98
0x140085b8d  mov     rax, [rcx]
0x140085b90  mov     [rdx], rax
0x140085b93  mov     [rcx], rdi
0x140085b96  jmp     short loc_140085BFA
0x140085b98  cmp     r8d, 2
0x140085b9c  jnz     short loc_140085BC1
0x140085b9e  mov     rbx, [rdx]
0x140085ba1  test    rbx, rbx
0x140085ba4  jz      short loc_140085BBC
0x140085ba6  lea     rcx, [rbx+10h]
0x140085baa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140085baf  mov     edx, 30h ; '0'
0x140085bb4  mov     rcx, rbx; Block
0x140085bb7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140085bbc  mov     [rsi], rdi
0x140085bbf  jmp     short loc_140085BFA
0x140085bc1  cmp     r8d, 3
0x140085bc5  jnz     short loc_140085BEC
0x140085bc7  mov     rcx, [rdx]
0x140085bca  add     rcx, 8
0x140085bce  lea     rdx, qword_1400CE828
0x140085bd5  call    cs:__imp___std_type_info_compare
0x140085bdb  test    eax, eax
0x140085bdd  jnz     short loc_140085BE4
0x140085bdf  mov     rax, [rbx]
0x140085be2  jmp     short loc_140085BE7
0x140085be4  mov     rax, rdi
0x140085be7  mov     [rsi], rax
0x140085bea  jmp     short loc_140085BFA
0x140085bec  lea     rax, ??_R0?AV?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV45@AEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,std::wstring &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor'
0x140085bf3  mov     [rdx], rax
0x140085bf6  mov     [rdx+8], di
0x140085bfa  mov     rbx, [rsp+28h+arg_0]
0x140085bff  mov     rsi, [rsp+28h+arg_8]
0x140085c04  add     rsp, 20h
0x140085c08  pop     rdi
0x140085c09  retn
```
