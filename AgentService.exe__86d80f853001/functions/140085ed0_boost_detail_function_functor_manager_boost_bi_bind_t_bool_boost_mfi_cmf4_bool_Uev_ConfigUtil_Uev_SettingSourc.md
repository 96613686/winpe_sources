# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,boost::arg<2>,boost::arg<3>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x140085ed0`
- end: `0x140085faa`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_NAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
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
- `0x140085ed0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085f75`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085f75`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>>>::manage(
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
    *a2 = (char *)&boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor';
    *((_WORD *)a2 + 4) = 0;
  }
  else
  {
    if ( (unsigned int)__std_type_info_compare(*a2 + 8, &qword_1400CDF88) )
      v8 = 0;
    else
      v8 = *a1;
    *a2 = v8;
  }
}

```

## disassembly

```asm
0x140085ed0  mov     [rsp+arg_0], rbx
0x140085ed5  mov     [rsp+arg_8], rsi
0x140085eda  push    rdi
0x140085edb  sub     rsp, 20h
0x140085edf  mov     rsi, rdx
0x140085ee2  mov     rbx, rcx
0x140085ee5  xor     edi, edi
0x140085ee7  cmp     r8d, 4
0x140085eeb  jz      loc_140085F8C
0x140085ef1  test    r8d, r8d
0x140085ef4  jnz     short loc_140085F27
0x140085ef6  mov     rbx, [rcx]
0x140085ef9  lea     ecx, [rdi+30h]; Size
0x140085efc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140085f01  mov     rdi, rax
0x140085f04  mov     [rsp+28h+arg_18], rax
0x140085f09  mov     rcx, [rbx]
0x140085f0c  mov     [rax], rcx
0x140085f0f  mov     rcx, [rbx+8]
0x140085f13  mov     [rax+8], rcx
0x140085f17  lea     rdx, [rbx+10h]
0x140085f1b  lea     rcx, [rax+10h]
0x140085f1f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140085f24  nop
0x140085f25  jmp     short loc_140085F5C
0x140085f27  cmp     r8d, 1
0x140085f2b  jnz     short loc_140085F38
0x140085f2d  mov     rax, [rcx]
0x140085f30  mov     [rdx], rax
0x140085f33  mov     [rcx], rdi
0x140085f36  jmp     short loc_140085F9A
0x140085f38  cmp     r8d, 2
0x140085f3c  jnz     short loc_140085F61
0x140085f3e  mov     rbx, [rdx]
0x140085f41  test    rbx, rbx
0x140085f44  jz      short loc_140085F5C
0x140085f46  lea     rcx, [rbx+10h]
0x140085f4a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140085f4f  mov     edx, 30h ; '0'
0x140085f54  mov     rcx, rbx; Block
0x140085f57  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140085f5c  mov     [rsi], rdi
0x140085f5f  jmp     short loc_140085F9A
0x140085f61  cmp     r8d, 3
0x140085f65  jnz     short loc_140085F8C
0x140085f67  mov     rcx, [rdx]
0x140085f6a  add     rcx, 8
0x140085f6e  lea     rdx, qword_1400CDF88
0x140085f75  call    cs:__imp___std_type_info_compare
0x140085f7b  test    eax, eax
0x140085f7d  jnz     short loc_140085F84
0x140085f7f  mov     rax, [rbx]
0x140085f82  jmp     short loc_140085F87
0x140085f84  mov     rax, rdi
0x140085f87  mov     [rsi], rax
0x140085f8a  jmp     short loc_140085F9A
0x140085f8c  lea     rax, ??_R0?AV?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_NAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,bool &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor'
0x140085f93  mov     [rdx], rax
0x140085f96  mov     [rdx+8], di
0x140085f9a  mov     rbx, [rsp+28h+arg_0]
0x140085f9f  mov     rsi, [rsp+28h+arg_8]
0x140085fa4  add     rsp, 20h
0x140085fa8  pop     rdi
0x140085fa9  retn
```
