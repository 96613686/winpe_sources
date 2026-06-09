# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,unsigned __int64 &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,boost::arg<2>,boost::arg<3>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x140085d70`
- end: `0x140085e4a`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_KAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
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
- `0x140085d70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085e15`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140085e15`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>>>::manage(
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
    *a2 = (char *)&boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor';
    *((_WORD *)a2 + 4) = 0;
  }
  else
  {
    if ( (unsigned int)__std_type_info_compare(*a2 + 8, &qword_1400CE4B8) )
      v8 = 0;
    else
      v8 = *a1;
    *a2 = v8;
  }
}

```

## disassembly

```asm
0x140085d70  mov     [rsp+arg_0], rbx
0x140085d75  mov     [rsp+arg_8], rsi
0x140085d7a  push    rdi
0x140085d7b  sub     rsp, 20h
0x140085d7f  mov     rsi, rdx
0x140085d82  mov     rbx, rcx
0x140085d85  xor     edi, edi
0x140085d87  cmp     r8d, 4
0x140085d8b  jz      loc_140085E2C
0x140085d91  test    r8d, r8d
0x140085d94  jnz     short loc_140085DC7
0x140085d96  mov     rbx, [rcx]
0x140085d99  lea     ecx, [rdi+30h]; Size
0x140085d9c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140085da1  mov     rdi, rax
0x140085da4  mov     [rsp+28h+arg_18], rax
0x140085da9  mov     rcx, [rbx]
0x140085dac  mov     [rax], rcx
0x140085daf  mov     rcx, [rbx+8]
0x140085db3  mov     [rax+8], rcx
0x140085db7  lea     rdx, [rbx+10h]
0x140085dbb  lea     rcx, [rax+10h]
0x140085dbf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140085dc4  nop
0x140085dc5  jmp     short loc_140085DFC
0x140085dc7  cmp     r8d, 1
0x140085dcb  jnz     short loc_140085DD8
0x140085dcd  mov     rax, [rcx]
0x140085dd0  mov     [rdx], rax
0x140085dd3  mov     [rcx], rdi
0x140085dd6  jmp     short loc_140085E3A
0x140085dd8  cmp     r8d, 2
0x140085ddc  jnz     short loc_140085E01
0x140085dde  mov     rbx, [rdx]
0x140085de1  test    rbx, rbx
0x140085de4  jz      short loc_140085DFC
0x140085de6  lea     rcx, [rbx+10h]
0x140085dea  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140085def  mov     edx, 30h ; '0'
0x140085df4  mov     rcx, rbx; Block
0x140085df7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140085dfc  mov     [rsi], rdi
0x140085dff  jmp     short loc_140085E3A
0x140085e01  cmp     r8d, 3
0x140085e05  jnz     short loc_140085E2C
0x140085e07  mov     rcx, [rdx]
0x140085e0a  add     rcx, 8
0x140085e0e  lea     rdx, qword_1400CE4B8
0x140085e15  call    cs:__imp___std_type_info_compare
0x140085e1b  test    eax, eax
0x140085e1d  jnz     short loc_140085E24
0x140085e1f  mov     rax, [rbx]
0x140085e22  jmp     short loc_140085E27
0x140085e24  mov     rax, rdi
0x140085e27  mov     [rsi], rax
0x140085e2a  jmp     short loc_140085E3A
0x140085e2c  lea     rax, ??_R0?AV?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_KAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,unsigned __int64 &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor'
0x140085e33  mov     [rdx], rax
0x140085e36  mov     [rdx+8], di
0x140085e3a  mov     rbx, [rsp+28h+arg_0]
0x140085e3f  mov     rsi, [rsp+28h+arg_8]
0x140085e44  add     rsp, 20h
0x140085e48  pop     rdi
0x140085e49  retn
```
