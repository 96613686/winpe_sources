# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,boost::arg<2>,boost::arg<3>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x1400859d0`
- end: `0x140085aaa`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAKAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
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
- `0x1400859d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085a75`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085a75`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>>>::manage(
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
    *a2 = (char *)&boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor';
    *((_WORD *)a2 + 4) = 0;
  }
  else
  {
    if ( (unsigned int)__std_type_info_compare(*a2 + 8, &qword_1400CD128) )
      v8 = 0;
    else
      v8 = *a1;
    *a2 = v8;
  }
}

```

## disassembly

```asm
0x1400859d0  mov     [rsp+arg_0], rbx
0x1400859d5  mov     [rsp+arg_8], rsi
0x1400859da  push    rdi
0x1400859db  sub     rsp, 20h
0x1400859df  mov     rsi, rdx
0x1400859e2  mov     rbx, rcx
0x1400859e5  xor     edi, edi
0x1400859e7  cmp     r8d, 4
0x1400859eb  jz      loc_140085A8C
0x1400859f1  test    r8d, r8d
0x1400859f4  jnz     short loc_140085A27
0x1400859f6  mov     rbx, [rcx]
0x1400859f9  lea     ecx, [rdi+30h]; Size
0x1400859fc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140085a01  mov     rdi, rax
0x140085a04  mov     [rsp+28h+arg_18], rax
0x140085a09  mov     rcx, [rbx]
0x140085a0c  mov     [rax], rcx
0x140085a0f  mov     rcx, [rbx+8]
0x140085a13  mov     [rax+8], rcx
0x140085a17  lea     rdx, [rbx+10h]
0x140085a1b  lea     rcx, [rax+10h]
0x140085a1f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140085a24  nop
0x140085a25  jmp     short loc_140085A5C
0x140085a27  cmp     r8d, 1
0x140085a2b  jnz     short loc_140085A38
0x140085a2d  mov     rax, [rcx]
0x140085a30  mov     [rdx], rax
0x140085a33  mov     [rcx], rdi
0x140085a36  jmp     short loc_140085A9A
0x140085a38  cmp     r8d, 2
0x140085a3c  jnz     short loc_140085A61
0x140085a3e  mov     rbx, [rdx]
0x140085a41  test    rbx, rbx
0x140085a44  jz      short loc_140085A5C
0x140085a46  lea     rcx, [rbx+10h]
0x140085a4a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140085a4f  mov     edx, 30h ; '0'
0x140085a54  mov     rcx, rbx; Block
0x140085a57  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140085a5c  mov     [rsi], rdi
0x140085a5f  jmp     short loc_140085A9A
0x140085a61  cmp     r8d, 3
0x140085a65  jnz     short loc_140085A8C
0x140085a67  mov     rcx, [rdx]
0x140085a6a  add     rcx, 8
0x140085a6e  lea     rdx, qword_1400CD128
0x140085a75  call    cs:__imp___std_type_info_compare
0x140085a7b  test    eax, eax
0x140085a7d  jnz     short loc_140085A84
0x140085a7f  mov     rax, [rbx]
0x140085a82  jmp     short loc_140085A87
0x140085a84  mov     rax, rdi
0x140085a87  mov     [rsi], rax
0x140085a8a  jmp     short loc_140085A9A
0x140085a8c  lea     rax, ??_R0?AV?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAKAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,ulong &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor'
0x140085a93  mov     [rdx], rax
0x140085a96  mov     [rdx+8], di
0x140085a9a  mov     rbx, [rsp+28h+arg_0]
0x140085a9f  mov     rsi, [rsp+28h+arg_8]
0x140085aa4  add     rsp, 20h
0x140085aa8  pop     rdi
0x140085aa9  retn
```
